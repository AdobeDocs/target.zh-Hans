---
title: Android集成指南的Flags扩展
description: 了解如何将Flags扩展与Android上的Adobe Experience Platform Mobile SDK集成。
badge: label="Beta" type="Informative"
hide: true
exl-id: 683ef4d4-e637-4b7b-b694-689c7e65a99e
source-git-commit: 8fffd619232b2cae2f5dd0aa1e0a55183c4be698
workflow-type: tm+mt
source-wordcount: '984'
ht-degree: 5%

---

# 标记Android的扩展 {#android-extension-integration-guide}

本指南介绍如何将Flags扩展与Android上的Adobe Experience Platform Mobile SDK集成。

## 先决条件 {#prerequisites}

在实施Flags扩展之前，请确保您已：

* 在[Adobe Experience Platform数据收集](https://experience.adobe.com/#/data-collection)中配置的移动属性
* 在您的移动资产中安装和配置的Flags扩展
* Adobe Experience Cloud组织ID
* 最小SDK：API 21 (Android 5.0 Lollipop)

## 扩展依赖关系 {#extension-dependencies}

Flags扩展需要以下Adobe Experience Platform扩展：

| 扩展 | 描述 | 必需 |
|---|---|---|
| 移动核心 | 提供核心功能，包括配置和事件处理 | 是 |
| 生命周期 | 为Mobile SDK收集应用程序生命周期和会话数据 | 是 |
| Edge Network | 启用与Adobe Experience Platform Edge Network的通信 | 是 |
| Edge标识 | 在使用Edge Network扩展时，通过移动设备应用程序启用身份管理 | 是 |

确保这些扩展已安装在数据收集移动资产中并包含在应用程序依赖项中。

## 在数据收集中配置标志扩展 {#configure}

### 安装扩展 {#install-extension}

1. 登录到[Adobe Experience Platform数据收集](https://experience.adobe.com/#/data-collection)。
1. 选择&#x200B;**标记**&#x200B;选项卡并选择您的移动属性。
1. 导航到&#x200B;**扩展** > **目录**。
1. 搜索&#x200B;**标记扩展**&#x200B;并选择&#x200B;**安装**。
1. 配置扩展设置：

   | 设置 | 描述 |
   |---|---|
   | 应用程序 ID | 标记中应用程序的唯一标识符 |

1. 选择&#x200B;**保存**。
1. 按照[发布流程](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/publish/overview)更新您的配置。

### 获取环境文件ID {#environment-file-id}

1. 在移动资产中，导航到&#x200B;**环境**。
1. 为您的环境选择&#x200B;**Install**&#x200B;列下的框图标。
1. 在&#x200B;**移动设备安装说明**&#x200B;对话框中，复制&#x200B;**环境文件ID**。

## 向应用程序添加Flags扩展 {#add-to-app}

### 添加依赖项 {#add-dependencies}

将Mobile SDK依赖项添加到您的项目中。 Flags扩展需要具备Mobile Core以及下面列出的与Edge相关的扩展。

#### 将Gradle与BOM结合使用（推荐） {#gradle-bom}

将以下依赖项添加到应用程序的`build.gradle.kts`文件中：

```kotlin
dependencies {
    // Adobe Experience Platform Mobile SDK BOM
    implementation(platform("com.adobe.marketing.mobile:sdkbom:3.+"))

    // Required extensions
    implementation("com.adobe.marketing.mobile:core")
    implementation("com.adobe.marketing.mobile:lifecycle")
    implementation("com.adobe.marketing.mobile:edge")
    implementation("com.adobe.marketing.mobile:edgeidentity")
}
```

#### 使用Gradle (Groovy) {#gradle-groovy}

```groovy
dependencies {
    // Adobe Experience Platform Mobile SDK BOM
    implementation platform('com.adobe.marketing.mobile:sdkbom:3.+')

    // Required extensions
    implementation 'com.adobe.marketing.mobile:core'
    implementation 'com.adobe.marketing.mobile:lifecycle'
    implementation 'com.adobe.marketing.mobile:edge'
    implementation 'com.adobe.marketing.mobile:edgeidentity'
}
```

>[!IMPORTANT]
>
>对于生产应用程序，Adobe建议使用显式版本号而不是动态版本。 有关详细信息，请参阅[管理Gradle依赖项](https://docs.gradle.org/current/userguide/dependency_management.html)。

### 添加标记依赖项 {#add-flags-dependency}

#### 使用托管的Maven存储库（推荐） {#hosted-maven}

将标志Maven存储库添加到`settings.gradle.kts`中的`repositories`块：

```kotlin
maven {
    url = uri("<HTTPS Flags Maven repository URL>")
}
```

对于Groovy `settings.gradle`文件：

```groovy
maven {
    url = uri('<HTTPS Flags Maven repository URL>')
}
```

将`<HTTPS Flags Maven repository URL>`替换为为Flags扩展提供的安全存储库URL。

然后，将版本化的标记依赖项添加到应用程序的`build.gradle.kts`：

```kotlin
implementation("com.adobe.marketing.mobile:flags:<version>")
```

对于Groovy `build.gradle`文件：

```groovy
implementation 'com.adobe.marketing.mobile:flags:<version>'
```

将`<version>`替换为为您的版本提供的准确的Flags扩展版本。

#### 使用标志分发包 {#distribution-package}

Flags扩展分发包包括：

* `flags-3.x.aar`
* `flags-3.x.module`
* `flags-3.x.pom`

使用以下方法之一使该扩展对Android项目可用：

* 将分发包中的所有文件发布到本地或专用Maven存储库，并将您的项目配置为使用该存储库。
* 将`flags-3.x.aar`直接添加到您的项目，并声明在`flags-3.x.pom`中指定的可传递依赖项。

### 添加权限 {#add-permissions}

向您的`AndroidManifest.xml`文件添加以下权限：

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

### 初始化SDK {#initialize-sdk}

在调用任何Flags扩展API之前，初始化`Application`类中的Mobile SDK。 将移动属性中的环境文件ID与`MobileCore.initialize`一起使用，以便应用程序选取您在数据收集中发布的标志设置。

#### 使用MobileCore.initialize {#mobile-core-initialize}

从Android BOM版本3.8.0开始，此API使用您的数据收集环境文件初始化SDK。

>[!IMPORTANT]
>
>对于生产应用，仅使用`LoggingMode.ERROR`；请勿在版本内部版本中使用`DEBUG`或`VERBOSE`。

**Kotlin**

```kotlin
import android.app.Application
import com.adobe.marketing.mobile.LoggingMode
import com.adobe.marketing.mobile.MobileCore

class MainApplication : Application() {

    override fun onCreate() {
        super.onCreate()

        // Production: use LoggingMode.ERROR only. Do not use DEBUG or VERBOSE in release builds.
        MobileCore.setLogLevel(LoggingMode.ERROR)

        // Initialize with your Environment File ID from Data Collection
        MobileCore.initialize(this, "YOUR_ENVIRONMENT_FILE_ID")
    }
}
```

**Java**

```java
import android.app.Application;
import com.adobe.marketing.mobile.LoggingMode;
import com.adobe.marketing.mobile.MobileCore;

public class MainApplication extends Application {

    @Override
    public void onCreate() {
        super.onCreate();

        // Production: use LoggingMode.ERROR only. Do not use DEBUG or VERBOSE in release builds.
        MobileCore.setLogLevel(LoggingMode.ERROR);

        // Initialize with your Environment File ID from Data Collection
        MobileCore.initialize(this, "YOUR_ENVIRONMENT_FILE_ID", null);
    }
}
```

### 注册Application类 {#register-application}

在`AndroidManifest.xml`中注册您的`Application`类：

```xml
<application
    android:name=".MainApplication"
    ... >
</application>
```

## 评估上下文 {#evaluation-context}

`FeatureEvaluationContext`类包含定位属性（用于标志规则匹配）。

| 方法 | 必需 | 描述 |
|---|---|---|
| `withAttributes(map)` | 否 | `Map<String, List<String>>`. 键是标记规则使用的上下文属性名称（例如`locale`、`platform`、`appVersion`、`deviceType`）。 值是当前用户/会话的该键的候选属性值列表（例如`["en_US"]`或`["phone"]`）。 |

**Kotlin**

```kotlin
import com.adobe.marketing.mobile.flags.FeatureEvaluationContext

val attrs = mapOf(
    "locale" to listOf("en_US"),
    "platform" to listOf("ANDROID")
)

val ctx = FeatureEvaluationContext.builder()
    .withAttributes(attrs)
    .build()
```

**Java**

```java
import com.adobe.marketing.mobile.flags.FeatureEvaluationContext;
import java.util.Arrays;
import java.util.HashMap;
import java.util.List;
import java.util.Map;

Map<String, List<String>> attrs = new HashMap<>();
attrs.put("locale", Arrays.asList("en_US"));
attrs.put("platform", Arrays.asList("ANDROID"));

FeatureEvaluationContext ctx = FeatureEvaluationContext.builder()
        .withAttributes(attrs)
        .build();
```

### 自定义身份 {#custom-identity}

Flags扩展使用Identity for Edge Network扩展进行身份解析。 功能标记可以按自定义身份（例如CRM ID或忠诚度ID）进行同类群组，以便变体拆分和分析捆绑到对您的应用程序重要的身份。

在创作功能标记时，必须在标记UI中选择自定义身份命名空间。 要根据该标识评估标记，设备上的Edge标识`identityMap`中必须存在相同的标识，并使用匹配的命名空间。 在运行时为其提供Edge Network `updateIdentities` API的标识。

#### 将自定义身份添加到身份映射 {#add-identity}

在功能标记上配置的相同命名空间下添加身份。

**Kotlin**

```kotlin
import com.adobe.marketing.mobile.edge.identity.AuthenticatedState
import com.adobe.marketing.mobile.edge.identity.Identity
import com.adobe.marketing.mobile.edge.identity.IdentityItem
import com.adobe.marketing.mobile.edge.identity.IdentityMap

val identityMap = IdentityMap()
identityMap.addItem(
    IdentityItem("1111", AuthenticatedState.AUTHENTICATED, true),
    "userCRMId" // must match the namespace configured on the feature flag
)
Identity.updateIdentities(identityMap)
```

**Java**

```java
import com.adobe.marketing.mobile.edge.identity.AuthenticatedState;
import com.adobe.marketing.mobile.edge.identity.Identity;
import com.adobe.marketing.mobile.edge.identity.IdentityItem;
import com.adobe.marketing.mobile.edge.identity.IdentityMap;

final IdentityItem item = new IdentityItem("1111", AuthenticatedState.AUTHENTICATED, true);
final IdentityMap identityMap = new IdentityMap();
identityMap.addItem(item, "userCRMId"); // must match the namespace configured on the feature flag
Identity.updateIdentities(identityMap);
```

## API 引用 {#api-reference}

### isFeatureEnable {#is-feature-enabled}

`isFeatureEnabled`返回给定上下文的标志功能是打开还是关闭。 传递`featureKey`、`FeatureEvaluationContext`（可选定位属性）和回调。 查看[评估上下文](#evaluation-context)。

**签名**

*Kotlin*

```kotlin
Flag.isFeatureEnabled(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    callback: AdobeCallback<Boolean>
)
```

*Java*

```java
Flag.isFeatureEnabled(
    String featureKey,
    FeatureEvaluationContext evaluationContext,
    AdobeCallback<Boolean> callback);
```

**参数**

| 参数 | 类型 | 描述 |
|---|---|---|
| `featureKey` | 字符串 | 在Flags中评估的功能键 |
| `evaluationContext` | FeatureEvaluationContext | 根据需要包括定位属性；将`FeatureEvaluationContext.builder().build()`用于空上下文。 查看[评估上下文](#evaluation-context)。 |
| `callback` | AdobeCallback&lt;布尔值> | 如果功能已启用，则通过`true`调用，否则通过`false`调用。 您还可以传递`AdobeCallbackWithError<Boolean>`以处理`fail(...)`。 |

**示例**

*Kotlin*

```kotlin
import com.adobe.marketing.mobile.AdobeCallback
import com.adobe.marketing.mobile.flags.Flag

Flag.isFeatureEnabled(
    "new-flag",
    ctx,
    object : AdobeCallback<Boolean> {
        override fun call(isEnabled: Boolean?) {
            if (isEnabled == true) {
                // run the feature-specific behavior
            } else {
                // fall back to the default behavior
            }
        }
    }
)
```

*Java*

```java
import com.adobe.marketing.mobile.AdobeCallback;
import com.adobe.marketing.mobile.flags.Flag;

Flag.isFeatureEnabled(
    "new-flag",
    ctx,
    new AdobeCallback<Boolean>() {
        @Override
        public void call(Boolean isEnabled) {
            if (Boolean.TRUE.equals(isEnabled)) {
                // run the feature-specific behavior
            } else {
                // fall back to the default behavior
            }
        }
    }
);
```

### getFeature {#get-feature}

`getFeature`针对提供的上下文返回已评估的功能有效负载。 当您需要启用/禁用以外的功能，并且需要功能元数据或值时，请使用此API。

**签名**

*Kotlin*

```kotlin
Flag.getFeature(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    callback: AdobeCallback<FeatureEvaluationResult>
)
```

*Java*

```java
Flag.getFeature(
    String featureKey,
    FeatureEvaluationContext evaluationContext,
    AdobeCallback<FeatureEvaluationResult> callback);
```

**参数**

| 参数 | 类型 | 描述 |
|---|---|---|
| `featureKey` | 字符串 | 在Flags中评估的功能键 |
| `evaluationContext` | FeatureEvaluationContext | 根据需要包括定位属性；将`FeatureEvaluationContext.builder().build()`用于空上下文。 查看[评估上下文](#evaluation-context)。 |
| `callback` | AdobeCallback&lt;功能评估结果> | 使用评估的功能有效负载调用；当未找到该功能时，可能为`null`。 您还可以传递`AdobeCallbackWithError<FeatureEvaluationResult>`以处理`fail(...)`。 |

**响应**

*FeatureEvaluationResult*

| 字段 | 类型 | 描述 |
|---|---|---|
| `id` | 整数 | 数字功能标识符 |
| `key` | 字符串 | 功能键 |
| `featureGroupKey` | 字符串？ | 功能组密钥（可用时） |
| `meta` | 字符串？ | 在可用时以JSON字符串形式提供功能元数据 |
| `analyticsParam` | AnalyticsParam？ | 已评估功能的Analytics详细信息 |

*AnalyticsParam*

| 字段 | 类型 | 描述 |
|---|---|---|
| `featureGroupId` | 整数 | 数字功能组标识符 |
| `featureId` | 整数 | 数字功能标识符 |
| `variantId` | 字符串？ | 变量标识符 |

**示例**

*Kotlin*

```kotlin
import com.adobe.marketing.mobile.AdobeCallback
import com.adobe.marketing.mobile.flags.FeatureEvaluationResult
import com.adobe.marketing.mobile.flags.Flag

Flag.getFeature(
    "new-flag",
    ctx,
    object : AdobeCallback<FeatureEvaluationResult> {
        override fun call(feature: FeatureEvaluationResult?) {
            val meta = feature?.meta
            if (!meta.isNullOrEmpty()) {
                // Feature metadata is available: use it to drive the feature behavior
            } else {
                // No metadata available: fall back to the default behavior
            }
        }
    }
)
```

*Java*

```java
import com.adobe.marketing.mobile.AdobeCallback;
import com.adobe.marketing.mobile.flags.FeatureEvaluationResult;
import com.adobe.marketing.mobile.flags.Flag;

Flag.getFeature(
    "new-flag",
    ctx,
    new AdobeCallback<FeatureEvaluationResult>() {
        @Override
        public void call(FeatureEvaluationResult feature) {
            String meta = feature != null ? feature.getMeta() : null;
            if (meta != null && !meta.isEmpty()) {
                // Feature metadata is available: use it to drive the feature behavior
            } else {
                // No metadata available: fall back to the default behavior
            }
        }
    }
);
```

### extensionVersion {#extension-version}

返回Flags扩展的版本字符串。

**语法**

```kotlin
Flag.extensionVersion(): String
```

**示例**

*Kotlin*

```kotlin
val version = Flag.extensionVersion()
```

*Java*

```java
String version = Flag.extensionVersion();
```

## API摘要 {#api-summary}

| API | 返回值 |
|---|---|
| `isFeatureEnabled(featureKey, evaluationContext, callback)`. `FeatureEvaluationContext`携带规则的定位属性。 请参阅[功能评估](#is-feature-enabled)。 | 通过回调的布尔值 |
| `getFeature(featureKey, evaluationContext, callback)`. 返回给定上下文的已评估功能有效负载。 请参阅[getFeature](#get-feature)。 | 通过回调的FeatureEvaluationResult |
| `extensionVersion()` | 字符串 |

## 另请参阅 {#see-also}

* [移动设备应用程序](../../integrate/mobile-applications.md)
* [SDK](../../integrate/sdks.md)

<!-- -->
