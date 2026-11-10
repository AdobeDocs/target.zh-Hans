---
title: Android集成指南的Flags扩展
description: 了解如何将Flags扩展与Android上的Adobe Experience Platform Mobile SDK集成。
badge: label="Beta" type="Informative"
hide: true
exl-id: 683ef4d4-e637-4b7b-b694-689c7e65a99e
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
source-git-commit: c1fafcfcd7d5d22781abdd10e6eb3c2b84136c2d
workflow-type: tm+mt
source-wordcount: '1379'
ht-degree: 4%
---
# 标记Android的扩展 {#android-extension-integration-guide}

本指南介绍如何将Flags扩展与Android上的Adobe Experience Platform Mobile SDK集成。

## 先决条件 {#prerequisites}

在实施Flags扩展之前，请确保您已：

* 在[Adobe Experience Platform数据收集](https://experience.adobe.com/#/data-collection)中配置的移动属性
* 在您的移动资产中安装和配置Adobe Flags扩展
* Adobe Experience Cloud组织ID
* 在移动资产中配置的Edge Network数据流，用于接收曝光度分析
* Android API 21 (Android 5.0 Lollipop)或更高版本
* Mobile Core 3.6.0或更高版本（包含在`sdk-bom` 3.17.0及更高版本中）

## 扩展依赖关系 {#extension-dependencies}

Flags扩展需要以下Adobe Experience Platform扩展：

| 扩展 | 描述 | 必需 |
|---|---|---|
| [移动核心](https://developer.adobe.com/client-sdks/home/base/mobile-core/) | 提供配置、事件处理和SDK初始化 | 是 |
| [生命周期](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/) | 应用程序移至前台或后台时报告 | 是 |
| [Edge Network](https://developer.adobe.com/client-sdks/edge/edge-network/) | 将曝光分析发送到Adobe Experience Platform | 是 |
| Edge Network的[标识](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/) | 提供用于将用户分配给变体的身份 | 是 |

确保这些扩展已安装在数据收集移动资产中并包含在应用程序依赖项中。

## 在数据收集中配置标志扩展 {#configure}

### 安装扩展 {#install-extension}

1. 登录到[Adobe Experience Platform数据收集](https://experience.adobe.com/#/data-collection)。

1. 选择&#x200B;**[!UICONTROL 标记]**&#x200B;菜单并选择您的移动属性。

1. 导航到&#x200B;**[!UICONTROL 扩展]** > **[!UICONTROL 目录]**。

1. 搜索&#x200B;**[!DNL Adobe Flags]**&#x200B;并选择&#x200B;**[!UICONTROL 安装]**。

   ![](../assets/extension-install.png)

1. 配置扩展设置：

   * **[!UICONTROL 沙盒]**：包含您的Flags配置的Adobe Experience Platform沙盒。
   * **[!UICONTROL 应用程序ID]**： Flags中应用程序的标识符。

1. 选择&#x200B;**[!UICONTROL 保存]**。

1. 按照[发布流程](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)更新您的配置。

### 获取环境文件ID {#environment-file-id}

1. 在移动资产中，导航到&#x200B;**[!UICONTROL 环境]**。

1. 选择所选环境的&#x200B;**[!UICONTROL Install]**&#x200B;列中的框图标。

   ![](../assets/extension-install-2.png)

1. 在&#x200B;**[!UICONTROL 移动设备安装说明]**&#x200B;对话框中，复制&#x200B;**[!UICONTROL 环境文件ID]**。

   ![](../assets/extension-install-3.png)

## 向应用程序添加Flags扩展 {#add-to-app}

### 添加依赖项 {#add-dependencies}

>[!IMPORTANT]
>
>Flags扩展不是Mobile SDK BOM的一部分。 将`<latest-version>`替换为Maven Central中的最新版本。 如果没有版本，Gradle将无法解析依赖关系。
>
></br>
&gt;对于生产应用程序，Adobe建议使用明确的版本号，而不是使用动态版本，例如“3.+”。 有关更多信息，请参阅[管理Gradle依赖项](https://docs.gradle.org/current/userguide/dependency_management.html)。

将以下依赖项添加到应用程序的`build.gradle.kts` (Kotlin)或`build.gradle` (Groovy)文件：

>[!BEGINTABS]

>[!TAB Kotlin]

```kotlin
dependencies {
    // Adobe Experience Platform Mobile SDK BOM (3.17.0 or later)
    implementation(platform("com.adobe.marketing.mobile:sdk-bom:3.+"))

    // Required extensions (versions managed by the BOM)
    implementation("com.adobe.marketing.mobile:core")
    implementation("com.adobe.marketing.mobile:lifecycle")
    implementation("com.adobe.marketing.mobile:edge")
    implementation("com.adobe.marketing.mobile:edgeidentity")

    // Flags extension (not managed by the BOM; specify the version)
    implementation("com.adobe.marketing.mobile:flags:<latest-version>")
}
```

>[!TAB Groovy]

```groovy
dependencies {
    // Adobe Experience Platform Mobile SDK BOM (3.17.0 or later)
    implementation platform('com.adobe.marketing.mobile:sdk-bom:3.+')

    // Required extensions (versions managed by the BOM)
    implementation 'com.adobe.marketing.mobile:core'
    implementation 'com.adobe.marketing.mobile:lifecycle'
    implementation 'com.adobe.marketing.mobile:edge'
    implementation 'com.adobe.marketing.mobile:edgeidentity'

    // Flags extension (not managed by the BOM; specify the version)
    implementation 'com.adobe.marketing.mobile:flags:<latest-version>'
}
```

>[!ENDTABS]

### 初始化SDK {#initialize-sdk}

>[!IMPORTANT]
>
>对于生产应用，仅使用`LoggingMode.ERROR`。 请勿在版本内部版本中使用`DEBUG`或`VERBOSE`。

在调用任何Flags扩展API之前，初始化`Application`类中的Mobile SDK。 使用您的移动资产中的环境文件ID，以便应用程序会选取您在数据收集中发布的标志设置。

`MobileCore.initialize`注册您的Gradle依赖项中包含的每个Adobe扩展，包括Flags扩展。

请注意，当您使用`MobileCore.initialize`时，请不要同时调用`MobileCore.registerExtensions`、`MobileCore.lifecycleStart`或`MobileCore.lifecyclePause`。 这些是给你处理的。

>[!BEGINTABS]

>[!TAB Kotlin]

```kotlin
import android.app.Application
import com.adobe.marketing.mobile.LoggingMode
import com.adobe.marketing.mobile.MobileCore

class MainApplication : Application() {

    override fun onCreate() {
        super.onCreate()

        MobileCore.setLogLevel(LoggingMode.ERROR)

        // Initialize with your Environment File ID from Data Collection
        MobileCore.initialize(this, "YOUR_ENVIRONMENT_FILE_ID")
    }
}
```

>[!TAB Java]

```java
import android.app.Application;
import com.adobe.marketing.mobile.LoggingMode;
import com.adobe.marketing.mobile.MobileCore;

public class MainApplication extends Application {

    @Override
    public void onCreate() {
        super.onCreate();

        MobileCore.setLogLevel(LoggingMode.ERROR);

        // Initialize with your Environment File ID from Data Collection
        MobileCore.initialize(this, "YOUR_ENVIRONMENT_FILE_ID");
    }
}
```

>[!ENDTABS]

### 注册Application类 {#register-application}

在`AndroidManifest.xml`中注册您的`Application`类：

```xml
<application
    android:name=".MainApplication"
    ... >
</application>
```

### 如果手动注册扩展 {#register-manually}

如果您的应用无法使用`MobileCore.initialize`并使用`MobileCore.registerExtensions`注册扩展，请将`Flag.EXTENSION`添加到列表中。 使用Edge Network类`com.adobe.marketing.mobile.edge.identity.Identity`的标识，而不是旧版`com.adobe.marketing.mobile.Identity`。

```kotlin
import com.adobe.marketing.mobile.Edge
import com.adobe.marketing.mobile.Lifecycle
import com.adobe.marketing.mobile.MobileCore
import com.adobe.marketing.mobile.edge.identity.Identity
import com.adobe.marketing.mobile.flags.Flag

MobileCore.setApplication(this)
MobileCore.configureWithAppID("YOUR_ENVIRONMENT_FILE_ID")
MobileCore.registerExtensions(
    listOf(Lifecycle.EXTENSION, Identity.EXTENSION, Edge.EXTENSION, Flag.EXTENSION)
) { }
```

在此设置中，不会自动跟踪生命周期。 在每个活动的`onResume`中调用`MobileCore.lifecycleStart(null)`，并在其`onPause`中调用`MobileCore.lifecyclePause()`。 如果没有这些调用，扩展会在应用程序处于后台时继续刷新标记，并且稍后会发送曝光度分析。

## 评估上下文 {#evaluation-context}

`FeatureEvaluationContext`包含标记规则使用的定位属性。 您未传递身份：每次评估时，扩展都会从Edge Network的身份中读取身份。 请参阅[自定义标识](#custom-identity)。

| 方法 | 必需 | 描述 |
|---|---|---|
| `withAttributes(map)` | 否 | `Map<String, List<String>>`. 每个键都是标记规则使用的属性名称（例如，`locale`或`appVersion`）。 每个值都是当前用户的值列表（例如，`["en_US"]`）。 |

* 每次评估都需要上下文。 如果您没有属性，请传递`FeatureEvaluationContext.builder().build()`。
* 每个生成器最多调用`withAttributes`一次。
* 无法更改构建上下文，因此您可以在评估中重复使用它。

### 使用情况 {#evaluation-context-usage}

>[!BEGINTABS]

>[!TAB Kotlin]

```kotlin
import com.adobe.marketing.mobile.flags.FeatureEvaluationContext

val ctx = FeatureEvaluationContext.builder()
    .withAttributes(
        mapOf(
            "locale" to listOf("en_US"),
            "platform" to listOf("ANDROID")
        )
    )
    .build()
```

>[!TAB Java]

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

>[!ENDTABS]

### 定位属性示例 {#sample-attributes}

| 属性 | 描述 | 示例值 |
|---|---|---|
| `locale` | 用户的区域设置 | `["en_US"]`, `["fr_FR"]` |
| `platform` | 平台 | `["ANDROID"]` |
| `appVersion` | 应用程序版本 | `["3.0.0"]` |
| `deviceType` | 设备类型 | `["phone"]`, `["tablet"]` |

属性名称和值必须匹配标记规则中使用的名称和值。

## 自定义身份 {#custom-identity}

Flags扩展使用[Edge Network扩展](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/)的标识进行身份解析。 功能标志可以根据自定义身份（例如CRM ID或忠诚度ID）进行同类群组，这样变体拆分和分析就会绑定到对应用程序至关重要的身份。

在创作功能标记时，必须在标记UI中选择自定义身份命名空间。 要根据该标识评估标记，设备上的Edge标识`identityMap`中必须存在相同的标识，并使用匹配的命名空间。 在运行时为其提供Edge Network `updateIdentities` API的标识。

### 将自定义身份添加到身份映射 {#add-identity}

在评估该标记之前，在功能标记上配置的相同命名空间下添加身份。

添加身份时，请注意以下事项：

* 命名空间必须完全匹配，包括大小写。
* 如果命名空间有多个标识，则使用标记为主的标识。 否则，使用第一个。
* 如果评估标记时缺少身份，则会通过临时ID为用户分配，临时ID会在每次应用程序启动时更改。 之后，用户的变体可以在应用程序启动之间更改。 在评估使用标识的标记之前，请始终设置标识。

>[!BEGINTABS]

>[!TAB Kotlin]

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

>[!TAB Java]

```java
import com.adobe.marketing.mobile.edge.identity.AuthenticatedState;
import com.adobe.marketing.mobile.edge.identity.Identity;
import com.adobe.marketing.mobile.edge.identity.IdentityItem;
import com.adobe.marketing.mobile.edge.identity.IdentityMap;

IdentityMap identityMap = new IdentityMap();
identityMap.addItem(
        new IdentityItem("1111", AuthenticatedState.AUTHENTICATED, true),
        "userCRMId"); // must match the namespace configured on the feature flag
Identity.updateIdentities(identityMap);
```

>[!ENDTABS]

## API 引用 {#api-reference}

### 回调和错误处理 {#callbacks-errors}

这些规则适用于`isFeatureEnabled`和`getFeature`：

* 始终提供默认体验。 传递`AdobeCallbackWithError`并在`fail`中显示您的默认体验。 使用纯`AdobeCallback`，在发生错误时不会调用任何内容。

* 应用程序启动时，扩展会预加载标志定义。 之后，将在设备上评估标记。

* 其他错误： `fail`与`AdobeError.UNEXPECTED_ERROR`一起调用，当时：

  * 功能键为空，
  * 发布的配置中缺少标志设置或Experience Cloud组织ID，或者
  * 应用程序启动时（例如，设备处于脱机状态），无法下载标志定义。 扩展会在下次配置更新时重试，通常是在下次应用程序启动时重试。

### isFeatureEnable {#is-feature-enabled}

返回是否为当前用户启用了某个功能。

**签名**

>[!BEGINTABS]

>[!TAB Kotlin]

```kotlin
Flag.isFeatureEnabled(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    callback: AdobeCallback<Boolean>
)
```

>[!TAB Java]

```java
Flag.isFeatureEnabled(
    String featureKey,
    FeatureEvaluationContext evaluationContext,
    AdobeCallback<Boolean> callback);
```

>[!ENDTABS]

**参数**

| 参数 | 类型 | 描述 |
|---|---|---|
| `featureKey` | 字符串 | 要评估的功能的键 |
| `evaluationContext` | FeatureEvaluationContext | 定位属性。 如果您没有，请使用`FeatureEvaluationContext.builder().build()`。 查看[评估上下文](#evaluation-context)。 |
| `callback` | AdobeCallback&lt;布尔值> | 如果用户启用了此功能，则通过`true`调用。 如果找不到该功能、定位规则不匹配或用户位于控制组中，则通过`false`调用。 传递`AdobeCallbackWithError<Boolean>`以也接收错误。 |

**示例**

>[!BEGINTABS]

>[!TAB Kotlin]

```kotlin
import com.adobe.marketing.mobile.AdobeCallbackWithError
import com.adobe.marketing.mobile.AdobeError
import com.adobe.marketing.mobile.flags.Flag

Flag.isFeatureEnabled(
    "new-checkout",
    ctx,
    object : AdobeCallbackWithError<Boolean> {
        override fun call(isEnabled: Boolean?) {
            runOnUiThread {
                if (isEnabled == true) showNewCheckout() else showDefaultCheckout()
            }
        }

        override fun fail(error: AdobeError?) {
            runOnUiThread { showDefaultCheckout() }
        }
    }
)
```

>[!TAB Java]

```java
import com.adobe.marketing.mobile.AdobeCallbackWithError;
import com.adobe.marketing.mobile.AdobeError;
import com.adobe.marketing.mobile.flags.Flag;

Flag.isFeatureEnabled(
    "new-checkout",
    ctx,
    new AdobeCallbackWithError<Boolean>() {
        @Override
        public void call(Boolean isEnabled) {
            runOnUiThread(() -> {
                if (Boolean.TRUE.equals(isEnabled)) {
                    showNewCheckout();
                } else {
                    showDefaultCheckout();
                }
            });
        }

        @Override
        public void fail(AdobeError error) {
            runOnUiThread(() -> showDefaultCheckout());
        }
    }
);
```

>[!ENDTABS]

### getFeature {#get-feature}

返回当前用户的计算功能，包括其元数据。 当您需要启用或禁用的内容以外的内容时，请使用此API。

**签名**

>[!BEGINTABS]

>[!TAB Kotlin]

```kotlin
Flag.getFeature(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    callback: AdobeCallback<FeatureEvaluationResult>
)
```

>[!TAB Java]

```java
Flag.getFeature(
    String featureKey,
    FeatureEvaluationContext evaluationContext,
    AdobeCallback<FeatureEvaluationResult> callback);
```

>[!ENDTABS]

**参数**

| 参数 | 类型 | 描述 |
|---|---|---|
| `featureKey` | 字符串 | 要评估的功能的键 |
| `evaluationContext` | FeatureEvaluationContext | 定位属性。 如果您没有，请使用`FeatureEvaluationContext.builder().build()`。 查看[评估上下文](#evaluation-context)。 |
| `callback` | AdobeCallback&lt;功能评估结果> | 使用已评估的功能调用，或者当此功能未提供给用户时通过`null`调用：键未知、不满足定位条件或用户位于控制同类群组中。 `null`是正常结果，不是错误。 控制同类群组接触仍会报告给Analytics。 传递`AdobeCallbackWithError<FeatureEvaluationResult>`以接收真正失败的`fail(...)`，例如超时。 |

将`null`结果视为“功能关闭”，并显示您的默认体验。 在调用`fail`时也显示默认体验，这仅在真正失败（如超时）时发生。

**响应**

*FeatureEvaluationResult*

| 字段 | 类型 | 描述 |
|---|---|---|
| `id` | 整数 | 功能Id |
| `key` | 字符串 | 功能键 |
| `featureGroupKey` | 字符串？ | 功能组键（如果功能属于某个组） |
| `meta` | 字符串？ | 为该功能配置的元数据，为纯文本，如果未设置任何元数据，则为`null`。 如果存储JSON，请在应用程序中解析该字符串。 |
| `analyticsParam` | AnalyticsParam？ | 用于评估的Analytics详细信息 |

*AnalyticsParam*

| 字段 | 类型 | 描述 |
|---|---|---|
| `featureGroupId` | 整数 | 功能组标识 |
| `featureId` | 整数 | 功能Id |
| `variantId` | 字符串？ | 用户被分配到的变体的ID |

**示例**

>[!BEGINTABS]

>[!TAB Kotlin]

```kotlin
import com.adobe.marketing.mobile.AdobeCallbackWithError
import com.adobe.marketing.mobile.AdobeError
import com.adobe.marketing.mobile.flags.FeatureEvaluationResult
import com.adobe.marketing.mobile.flags.Flag

Flag.getFeature(
    "new-checkout",
    ctx,
    object : AdobeCallbackWithError<FeatureEvaluationResult> {
        override fun call(feature: FeatureEvaluationResult?) {
            val meta = feature?.meta
            runOnUiThread {
                if (!meta.isNullOrEmpty()) applyExperience(meta) else showDefaultExperience()
            }
        }

        override fun fail(error: AdobeError?) {
            runOnUiThread { showDefaultExperience() }
        }
    }
)
```

>[!TAB Java]

```java
import com.adobe.marketing.mobile.AdobeCallbackWithError;
import com.adobe.marketing.mobile.AdobeError;
import com.adobe.marketing.mobile.flags.FeatureEvaluationResult;
import com.adobe.marketing.mobile.flags.Flag;

Flag.getFeature(
    "new-checkout",
    ctx,
    new AdobeCallbackWithError<FeatureEvaluationResult>() {
        @Override
        public void call(FeatureEvaluationResult feature) {
            final String meta = feature != null ? feature.getMeta() : null;
            runOnUiThread(() -> {
                if (meta != null && !meta.isEmpty()) {
                    applyExperience(meta);
                } else {
                    showDefaultExperience();
                }
            });
        }

        @Override
        public void fail(AdobeError error) {
            runOnUiThread(() -> showDefaultExperience());
        }
    }
);
```

>[!ENDTABS]

### extensionVersion {#extension-version}

返回Flags扩展的版本。

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
| `isFeatureEnabled(featureKey, evaluationContext, callback)`. 请参阅[isFeatureEnabled](#is-feature-enabled)。 | 通过回调的布尔值 |
| `getFeature(featureKey, evaluationContext, callback)`. 请参阅[getFeature](#get-feature)。 | 通过回调的FeatureEvaluationResult |
| `extensionVersion()` | 字符串 |

## 调试 {#debugging}

要调试，请在调试内部版本中设置`MobileCore.setLogLevel(LoggingMode.DEBUG)`并按`Flags`筛选Logcat。 您应该会看到MobileCore中有关`com.adobe.marketing.mobile.flags.FlagExtension`的`Discovered extension`消息。


