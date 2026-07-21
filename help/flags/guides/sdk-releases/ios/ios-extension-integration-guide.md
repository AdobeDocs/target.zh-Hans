---
title: iOS集成指南的Flags扩展
description: 了解如何将Flags扩展与iOS上的Adobe Experience Platform Mobile SDK集成。
hide: true
source-git-commit: eeba7af62ab101e687852ce993a001832ce4a83b
workflow-type: tm+mt
source-wordcount: '1035'
ht-degree: 5%

---

# 标记iOS的扩展 {#ios-extension-integration-guide}

本指南介绍如何将Flags扩展与iOS上的Adobe Experience Platform Mobile SDK集成。

## 先决条件 {#prerequisites}

在实施Flags扩展之前，请确保您已：

* 在[Adobe Experience Platform数据收集](https://experience.adobe.com/#/data-collection)中配置的移动属性
* 在您的移动资产中安装和配置的Flags扩展
* Adobe Experience Cloud组织ID
* 最低部署目标： iOS 12.0

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
1. 按照[发布流程](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)更新您的配置。

### 获取环境文件ID {#environment-file-id}

1. 在移动资产中，导航到&#x200B;**环境**。
1. 为您的环境选择&#x200B;**Install**&#x200B;列下的框图标。
1. 在&#x200B;**移动设备安装说明**&#x200B;对话框中，复制&#x200B;**环境文件ID**。

## 向应用程序添加Flags扩展 {#add-to-app}

### 添加依赖项 {#add-dependencies}

将Mobile SDK依赖项添加到您的项目中。 Flags扩展需要具备Mobile Core以及下面列出的与Edge相关的扩展。

#### 使用Swift Package Manager {#swift-package-manager}

在Xcode中，选择&#x200B;**文件** > **添加包**&#x200B;并添加以下Adobe Experience Platform Mobile SDK包URL：

| 包 | URL |
|---|---|
| AEPCore | `https://github.com/adobe/aepsdk-core-ios.git` |
| AEPEdge | `https://github.com/adobe/aepsdk-edge-ios.git` |
| AEPEdgeIdentity | `https://github.com/adobe/aepsdk-edgeidentity-ios.git` |

出现提示时，选择以下库以添加到您的目标：

* `AEPCore`，`AEPLifecycle` （来自`aepsdk-core-ios`）
* `AEPEdge` （来自`aepsdk-edge-ios`）
* `AEPEdgeIdentity` （来自`aepsdk-edgeidentity-ios`）

使用AEPCore 5.8.0或更高版本。

>[!NOTE]
>
>在Xcode中添加包时，请为每个包选择依赖项规则（例如&#x200B;**到下一个主要版本**），这样可以在排除下一个主要版本时自动选取新的次要版本和修补程序版本。 有关最新发布的版本，请查看GitHub上每个扩展的发布页面。

### 添加标记包 {#add-flags-package}

请将Swift程序包或XCFramework集成方法用于应用程序目标，而不是同时使用两者。

#### 对于没有Package.swift文件的Xcode项目 {#xcode-project}

1. 在Xcode中，选择&#x200B;**文件** > **添加包**。
1. 选择&#x200B;**添加本地**。
1. 选择提供的`Packages/AEPFlags`目录，其中包含`Package.swift`。
1. 将`AEPFlags`库添加到应用程序目标。

Xcode将本地包引用存储在项目中，因此您的应用程序不需要自己的`Package.swift`文件。

#### 对于包含Package.swift文件的项目 {#package-swift-project}

在现有清单中，将`AEPFlags`添加到应用程序目标依赖项，并使用提供的URL和清单中的校验和添加二进制目标：

```swift
targets: [
    .target(
        name: "YourApp",
        dependencies: [
            "AEPFlags"
        ]
    ),
    .binaryTarget(
        name: "AEPFlags",
        url: "<AEPFlags binary URL>",
        checksum: "<AEPFlags binary checksum>"
    )
]
```

Swift包管理器解析本地Xcode、CI和存档内部版本的二进制目标。

#### 直接添加XCFramework {#xcframework}

或者，将提供的`AEPFlags.xcframework`拖动到Xcode项目导航器中，并将其添加到您的应用程序目标。 在&#x200B;**常规** > **框架、库和嵌入的内容**&#x200B;下，将框架设置为&#x200B;**嵌入和签名**。

### 初始化SDK {#initialize-sdk}

在调用任何Flags API之前，请在`AppDelegate`中注册Mobile SDK扩展。 在身份、Edge和生命周期后注册`Flag`，然后使用移动资产中的环境文件ID配置SDK。

#### 注册和配置扩展 {#register-configure}

>[!IMPORTANT]
>
>对于生产应用，仅使用`.error`日志级别；请勿在发行版内部版本中使用`.debug`或`.trace`。

**Swift**

```swift
// AppDelegate.swift
import AEPCore
import AEPLifecycle
import AEPEdge
import AEPEdgeIdentity
import AEPFlags
import UIKit

final class AppDelegate: NSObject, UIApplicationDelegate {

    func application(_: UIApplication,
                      didFinishLaunchingWithOptions _: [UIApplication.LaunchOptionsKey: Any]? = nil) -> Bool {
        // Production: use .error only. Do not use .debug or .trace in release builds.
        MobileCore.setLogLevel(.error)

        MobileCore.registerExtensions([
            Identity.self,
            Edge.self,
            Lifecycle.self,
            Flag.self
        ]) {
            MobileCore.configureWith(appId: "YOUR_ENVIRONMENT_FILE_ID")
            MobileCore.lifecycleStart(additionalContextData: nil)
        }

        return true
    }
}
```

**Objective-C**

```objc
// AppDelegate.m
#import "AppDelegate.h"
@import AEPCore;
@import AEPLifecycle;
@import AEPEdge;
@import AEPEdgeIdentity;
@import AEPFlags;

@implementation AppDelegate

- (BOOL)application:(UIApplication *)application
    didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {

    // Production: use AEPLogLevelError only. Do not use Debug or Trace in release builds.
    [AEPMobileCore setLogLevel:AEPLogLevelError];

    [AEPMobileCore registerExtensions:@[
        AEPMobileEdgeIdentity.class,
        AEPMobileEdge.class,
        AEPMobileLifecycle.class,
        AEPMobileFlag.class
    ] completion:^{
        [AEPMobileCore configureWithAppId:@"YOUR_ENVIRONMENT_FILE_ID"];
        [AEPMobileCore lifecycleStart:nil];
    }];

    return YES;
}

@end
```

## 评估上下文 {#evaluation-context}

`FeatureEvaluationContext`包含定位属性（用于标记规则匹配）。

| 参数 | 必需 | 描述 |
|---|---|---|
| `attributes` | 否 | `[String: [String]]`. 键是标记规则使用的上下文属性名称（例如`locale`、`platform`、`appVersion`、`deviceType`）。 值是当前用户/会话的该键的候选属性值列表（例如`["en_US"]`或`["phone"]`）。 |

**Swift**

```swift
import AEPFlags

let attrs: [String: [String]] = [
    "locale": ["en_US"],
    "platform": ["IOS"],
    "appVersion": ["3.0.0"]
]

let ctx = FeatureEvaluationContext.builder()
    .withAttributes(attrs)
    .build()
```

**Objective-C**

```objc
@import AEPFlags;

NSDictionary<NSString *, NSArray<NSString *> *> *attrs = @{
    @"locale": @[@"en_US"],
    @"platform": @[@"IOS"],
    @"appVersion": @[@"3.0.0"]
};

AEPFeatureEvaluationContextBuilder *builder = [AEPFeatureEvaluationContext builder];
AEPFeatureEvaluationContext *ctx = [[builder withAttributes:attrs] build];
```

### 定位属性示例 {#sample-attributes}

| 属性 | 描述 | 示例值 |
|---|---|---|
| `locale` | 用户的区域设置/语言 | `["en_US"]`, `["fr_FR"]` |
| `platform` | 平台标识符 | `["IOS"]` |
| `appVersion` | 应用程序版本 | `["3.0.0"]` |
| `deviceType` | 设备类型 | `["phone"]`, `["tablet"]` |

### 自定义身份 {#custom-identity}

Flags扩展使用Identity for Edge Network扩展进行身份解析。 功能标记可以按自定义身份（例如CRM ID或忠诚度ID）进行同类群组，以便变体拆分和分析捆绑到对您的应用程序重要的身份。

在创作功能标记时，必须在标记UI中选择自定义身份命名空间。 要根据该标识评估标记，设备上的Edge标识`identityMap`中必须存在相同的标识，并使用匹配的命名空间。 在运行时为其提供Edge Network `updateIdentities` API的标识。

#### 将自定义身份添加到身份映射 {#add-identity}

在功能标记上配置的相同命名空间下添加身份。

**Swift**

```swift
import AEPEdgeIdentity

let identityMap = IdentityMap()
identityMap.add(item: IdentityItem(id: "1111", authenticatedState: .authenticated, primary: true),
                 withNamespace: "userCRMId") // must match the namespace configured on the feature flag
Identity.updateIdentities(with: identityMap)
```

**Objective-C**

```objc
@import AEPEdgeIdentity;

AEPIdentityItem *item = [[AEPIdentityItem alloc]
    initWithId:@"1111"
    authenticatedState:AEPAuthenticatedStateAuthenticated
    primary:YES];
AEPIdentityMap *identityMap = [[AEPIdentityMap alloc] init];
[identityMap addItem:item withNamespace:@"userCRMId"]; // must match the namespace configured on the feature flag
[AEPMobileEdgeIdentity updateIdentities:identityMap];
```

## API 引用 {#api-reference}

### isFeatureEnable {#is-feature-enabled}

`isFeatureEnabled`返回给定上下文的标志功能是打开还是关闭。 传递`featureKey`、`FeatureEvaluationContext`（可选定位属性）和完成结束。 查看[评估上下文](#evaluation-context)。

**签名**

*Swift*

```swift
static func isFeatureEnabled(
    _ featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    completion: @escaping (Bool) -> Void
)
```

*Objective-C*

```objc
+ (void)isFeatureEnabled:(NSString *)featureKey
       evaluationContext:(AEPFeatureEvaluationContext *)evaluationContext
               completion:(void (^)(BOOL))completion;
```

**参数**

| 参数 | 类型 | 描述 |
|---|---|---|
| `featureKey` | 字符串 | 在Flags中评估的功能键 |
| `evaluationContext` | FeatureEvaluationContext | 根据需要包括定位属性；将`FeatureEvaluationContext.builder().build()`用于空上下文。 查看[评估上下文](#evaluation-context)。 |
| `completion` | `(Bool) -> Void` | 如果功能已启用，则通过`true`调用，否则通过`false`调用。 |

**示例**

*Swift*

```swift
import AEPFlags

Flag.isFeatureEnabled(
    "new-flag",
    evaluationContext: ctx
) { isEnabled in
    if isEnabled {
        // Feature is enabled: run the feature-specific behavior
    } else {
        // Feature is disabled: fall back to the default behavior
    }
}
```

*Objective-C*

```objc
@import AEPFlags;

[AEPMobileFlag isFeatureEnabled:@"new-flag"
              evaluationContext:ctx
                      completion:^(BOOL isEnabled) {
    if (isEnabled) {
        // Feature is enabled: run the feature-specific behavior
    } else {
        // Feature is disabled: fall back to the default behavior
    }
}];
```

### getFeature {#get-feature}

`getFeature`针对提供的上下文返回已评估的功能有效负载。 当您需要启用/禁用以外的功能，并且需要功能元数据或值时，请使用此API。

**签名**

*Swift*

```swift
static func getFeature(
    _ featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    completion: @escaping (FeatureEvaluationResult?) -> Void
)
```

*Objective-C*

```objc
+ (void)getFeature:(NSString *)featureKey
 evaluationContext:(AEPFeatureEvaluationContext *)evaluationContext
        completion:(void (^)(AEPFeatureEvaluationResult * _Nullable))completion;
```

**参数**

| 参数 | 类型 | 描述 |
|---|---|---|
| `featureKey` | 字符串 | 在Flags中评估的功能键 |
| `evaluationContext` | FeatureEvaluationContext | 根据需要包括定位属性；将`FeatureEvaluationContext.builder().build()`用于空上下文。 查看[评估上下文](#evaluation-context)。 |
| `completion` | `(FeatureEvaluationResult?) -> Void` | 使用评估的功能有效负载调用；未找到该功能时`nil`。 |

**响应**

*FeatureEvaluationResult*

| 字段 | 类型 | 描述 |
|---|---|---|
| `id` | 整数 | 数字功能标识符 |
| `key` | 字符串 | 功能键 |
| `featureGroupKey` | 字符串？ | 功能组密钥（可用时） |
| `meta` | 字符串？ | 不透明功能元数据（可用时） |
| `analyticsParam` | AnalyticsParam？ | 已评估功能的Analytics详细信息 |

*AnalyticsParam*

| 字段 | 类型 | 描述 |
|---|---|---|
| `featureGroupId` | 整数 | 数字功能组标识符 |
| `featureId` | 整数 | 数字功能标识符 |
| `variantId` | 字符串？ | 变量标识符 |

**示例**

*Swift*

```swift
import AEPFlags

Flag.getFeature(
    "new-flag",
    evaluationContext: ctx
) { feature in
    guard let meta = feature?.meta, !meta.isEmpty else {
        // No metadata available: fall back to the default behavior
        return
    }
    // Feature metadata is available: use it to drive the feature behavior
}
```

*Objective-C*

```objc
@import AEPFlags;

[AEPMobileFlag getFeature:@"new-flag"
        evaluationContext:ctx
                completion:^(AEPFeatureEvaluationResult * _Nullable feature) {
    NSString *meta = feature.meta;
    if (meta.length > 0) {
        // Feature metadata is available: use it to drive the feature behavior
    } else {
        // No metadata available: fall back to the default behavior
    }
}];
```

### extensionVersion {#extension-version}

返回Flags扩展的版本字符串。

**语法**

*Swift*

```swift
static var extensionVersion: String
```

*Objective-C*

```objc
+ (nonnull NSString *)flagExtensionVersion;
```

**示例**

*Swift*

```swift
let version = Flag.extensionVersion
```

*Objective-C*

```objc
NSString *version = [AEPMobileFlag flagExtensionVersion];
```

## API摘要 {#api-summary}

| API | 返回值 |
|---|---|
| `isFeatureEnabled(_:evaluationContext:completion:)`. `FeatureEvaluationContext`携带规则的定位属性。 请参阅[isFeatureEnabled](#is-feature-enabled)。 | 通过完成关闭的布尔值 |
| `getFeature(_:evaluationContext:completion:)`. 返回给定上下文的已评估功能有效负载。 请参阅[getFeature](#get-feature)。 | 功能评估结果？ 通过关闭 |
| `extensionVersion` | 字符串 |

## 另请参阅 {#see-also}

* [移动设备应用程序](../../integrate/mobile-applications.md)
* [SDK](../../integrate/sdks.md)
* [Android扩展集成指南](../android/android-extension-integration-guide.md)

<!-- -->
