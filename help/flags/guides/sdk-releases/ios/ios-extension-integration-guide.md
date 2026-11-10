---
title: iOS集成指南的Flags扩展
description: 了解如何将Flags扩展与iOS上的Adobe Experience Platform Mobile SDK集成。
badge: label="Beta" type="Informative"
hide: true
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
source-git-commit: c1fafcfcd7d5d22781abdd10e6eb3c2b84136c2d
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 3%
---
# 标记iOS的扩展 {#ios-extension-integration-guide}

本指南介绍如何将Flags扩展与iOS上的Adobe Experience Platform Mobile SDK集成。 源代码在[aepsdk-flags-ios](https://github.com/adobe/aepsdk-flags-ios)存储库中可用。

## 先决条件 {#prerequisites}

在开始之前，请确保您拥有：

* iOS 12.0或更高版本，以及Swift 5.7或更高版本
* [Adobe Experience Platform数据收集](https://experience.adobe.com/#/data-collection)中的移动属性
* 在移动资产中安装和配置的扩展包括：

  | 扩展 | 描述 | 最低SDK版本 |
  |---|---|---|
  | [移动核心](https://developer.adobe.com/client-sdks/home/base/mobile-core/) | 配置和事件处理 | AEPCore 5.8.0 |
  | [生命周期](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/) | 应用程序生命周期数据 | 与AEPCore相同 |
  | [Edge Network](https://developer.adobe.com/client-sdks/edge/edge-network/) | 与Adobe Experience Platform Edge Network的通信。 需要数据流。 | AEPEdge 5.0.2 |
  | Edge Network的[标识](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/) | Edge Network的身份管理 | AEPEdgeIdentity 5.0.0 |
  | [标志](https://experienceleague.adobe.com/zh-hans/docs/target/flags/home) | 功能标志评估 | 查看[安装](#installation) |

## 在数据收集中配置标志 {#configure}

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

1. 按照[发布流程](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/publish/overview)更新您的配置。

### 获取环境文件ID {#environment-file-id}

1. 在移动资产中，导航到&#x200B;**[!UICONTROL 环境]**。

1. 选择所选环境的&#x200B;**[!UICONTROL Install]**&#x200B;列中的框图标。

   ![](../assets/extension-install-2.png)

1. 在&#x200B;**[!UICONTROL 移动设备安装说明]**&#x200B;对话框中，复制&#x200B;**[!UICONTROL 环境文件ID]**。

   ![](../assets/extension-install-3.png)

## 安装 {#installation}

使用Swift包管理器或XCFramework添加该扩展。 为每个应用程序目标使用一个方法。

### Swift包管理器 {#swift-package-manager}

在Xcode中：

1. 选择&#x200B;**文件** > **添加包依赖项**。

1. 输入包URL： `https://github.com/adobe/aepsdk-flags-ios.git`

1. 对于版本规则，请选择&#x200B;**确切版本**&#x200B;并从[版本页面](https://github.com/adobe/aepsdk-flags-ios/releases)输入最新版本。

1. 将`AEPFlags`库添加到应用程序目标。

1. 添加扩展所依赖的Adobe包，并将其库添加到您的应用程序目标：

   * `https://github.com/adobe/aepsdk-core-ios.git`： `AEPCore`、`AEPLifecycle`和`AEPServices`
   * `https://github.com/adobe/aepsdk-edge-ios.git`: `AEPEdge`
   * `https://github.com/adobe/aepsdk-edgeidentity-ios.git`: `AEPEdgeIdentity`

如果您的项目使用`Package.swift`文件，请在该处添加依赖项。 将`<latest-version>`替换为发行版页面中的最新版本。

```swift
dependencies: [
    .package(url: "https://github.com/adobe/aepsdk-flags-ios.git", exact: "<latest-version>"),
    .package(url: "https://github.com/adobe/aepsdk-core-ios.git", .upToNextMajor(from: "5.8.0")),
    .package(url: "https://github.com/adobe/aepsdk-edge-ios.git", .upToNextMajor(from: "5.0.2")),
    .package(url: "https://github.com/adobe/aepsdk-edgeidentity-ios.git", .upToNextMajor(from: "5.0.0"))
],
targets: [
    .target(
        name: "YourTarget",
        dependencies: [
            .product(name: "AEPFlags", package: "aepsdk-flags-ios"),
            .product(name: "AEPCore", package: "aepsdk-core-ios"),
            .product(name: "AEPLifecycle", package: "aepsdk-core-ios"),
            .product(name: "AEPServices", package: "aepsdk-core-ios"),
            .product(name: "AEPEdge", package: "aepsdk-edge-ios"),
            .product(name: "AEPEdgeIdentity", package: "aepsdk-edgeidentity-ios")
        ]
    )
]
```

### XCFramework {#xcframework}

1. 从[发行版页面](https://github.com/adobe/aepsdk-flags-ios/releases)下载`AEPFlags-<version>.xcframework.zip`并将其解压缩。

1. 从每个存储库的发行版页面下载扩展所依赖的XCFramework：

   * [aepsdk-core-ios版本](https://github.com/adobe/aepsdk-core-ios/releases)： `AEPCore`、`AEPServices`、`AEPLifecycle`和`AEPRulesEngine`
   * [aepsdk-edge-ios发行版](https://github.com/adobe/aepsdk-edge-ios/releases)： `AEPEdge`
   * [aepsdk-edgeidentity-ios发行版](https://github.com/adobe/aepsdk-edgeidentity-ios/releases)： `AEPEdgeIdentity`

1. 在Xcode中，选择您的应用程序目标，然后打开&#x200B;**常规** > **框架、库和嵌入的内容**。

1. 添加`AEPFlags.xcframework`和所有依赖的XCFramework。

1. 将每个框架设置为&#x200B;**嵌入和签名**。

## 初始化SDK {#initialize-sdk}

注册Flags扩展，然后使用移动资产中的环境文件ID初始化SDK。 `MobileCore.initialize`不为您注册Flags扩展，因此请先注册它。

>[!BEGINTABS]

>[!TAB Swift]

```swift
import AEPCore
import AEPFlags
import UIKit

class AppDelegate: UIResponder, UIApplicationDelegate {
    func application(
        _ application: UIApplication,
        didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?
    ) -> Bool {
        MobileCore.registerExtensions([Flag.self])
        MobileCore.initialize(appId: "<your-environment-file-id>")
        return true
    }
}
```

>[!TAB Objective-C]

```objc
@import AEPCore;
@import AEPFlags;

- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    [AEPMobileCore registerExtensions:@[AEPMobileFlag.class] completion:nil];
    [AEPMobileCore initializeWithAppId:@"<your-environment-file-id>" completion:nil];
    return YES;
}
```

>[!ENDTABS]

### 手动注册扩展 {#register-manually}

如果您自己注册扩展，请注册所有扩展。 应用程序进入前台时调用`MobileCore.lifecycleStart`，进入后台时调用`MobileCore.lifecyclePause`。

如果您的应用程序使用场景，请改为在`sceneWillEnterForeground(_:)`和`sceneDidEnterBackground(_:)`中进行这些调用。

>[!BEGINTABS]

>[!TAB Swift]

```swift
import AEPCore
import AEPEdge
import AEPEdgeIdentity
import AEPFlags
import AEPLifecycle
import UIKit

class AppDelegate: UIResponder, UIApplicationDelegate {
    func application(
        _ application: UIApplication,
        didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?
    ) -> Bool {
        MobileCore.registerExtensions([
            Lifecycle.self,
            Edge.self,
            AEPEdgeIdentity.Identity.self,
            Flag.self
        ]) {
            MobileCore.configureWith(appId: "<your-environment-file-id>")
            DispatchQueue.main.async {
                if application.applicationState != .background {
                    MobileCore.lifecycleStart(additionalContextData: nil)
                }
            }
        }
        return true
    }

    func applicationWillEnterForeground(_ application: UIApplication) {
        MobileCore.lifecycleStart(additionalContextData: nil)
    }

    func applicationDidEnterBackground(_ application: UIApplication) {
        MobileCore.lifecyclePause()
    }
}
```

>[!TAB Objective-C]

```objc
@import AEPCore;
@import AEPEdge;
@import AEPEdgeIdentity;
@import AEPFlags;
@import AEPLifecycle;

- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    [AEPMobileCore registerExtensions:@[
        AEPMobileLifecycle.class,
        AEPMobileEdge.class,
        AEPMobileEdgeIdentity.class,
        AEPMobileFlag.class
    ] completion:^{
        [AEPMobileCore configureWithAppId:@"<your-environment-file-id>"];
        dispatch_async(dispatch_get_main_queue(), ^{
            if (application.applicationState != UIApplicationStateBackground) {
                [AEPMobileCore lifecycleStart:nil];
            }
        });
    }];
    return YES;
}

- (void)applicationWillEnterForeground:(UIApplication *)application {
    [AEPMobileCore lifecycleStart:nil];
}

- (void)applicationDidEnterBackground:(UIApplication *)application {
    [AEPMobileCore lifecyclePause];
}
```

>[!ENDTABS]

## 评估上下文 {#evaluation-context}

每个评估调用都需要`FeatureEvaluationContext`。 它包含标记定位规则使用的属性。

| 参数 | 必需 | 描述 |
|---|---|---|
| `attributes` | 否 | `[String: [String]]`. 每个键值都是标记定位规则使用的属性名称。 每个值都是当前用户的值列表。 |

* 使用与您在Flags中定义的定位规则匹配的属性名称和值。
* 每个生成器最多调用`withAttributes`一次。 第二次调用会终止应用程序。
* 要计算不含属性的值，请调用`build()`而不调用`withAttributes`。

>[!BEGINTABS]

>[!TAB Swift]

```swift
import AEPFlags

let context = FeatureEvaluationContext.builder()
    .withAttributes([
        "locale": ["en_US"],
        "appVersion": ["3.0.0"]
    ])
    .build()
```

>[!TAB Objective-C]

```objc
@import AEPFlags;

AEPFeatureEvaluationContext *context = [[[AEPFeatureEvaluationContext builder]
    withAttributes:@{
        @"locale": @[@"en_US"],
        @"appVersion": @[@"3.0.0"]
    }]
    build];
```

>[!ENDTABS]

## 自定义身份 {#custom-identity}

Flags扩展使用Identity for Edge Network扩展进行身份解析。 功能标记可以按自定义身份（例如CRM ID或忠诚度ID）进行同类群组，以便变体拆分和分析捆绑到对您的应用程序重要的身份。

在创作功能标记时，必须在标记UI中选择自定义身份命名空间。 要根据该标识评估标记，设备上的Edge标识`identityMap`中必须存在相同的标识，并使用匹配的命名空间。 在运行时为其提供Edge Network `updateIdentities` API的标识。

### 将自定义身份添加到身份映射 {#add-identity}

在功能标记上配置的相同命名空间下添加身份。

请注意以下行为：

* 命名空间必须与在标记上配置的命名空间完全匹配，包括大写和小写字母。
* 如果命名空间中有多个标识，则使用标记为主的标识。 如果没有一个标记为主，则使用第一个标记。
* 如果缺少身份，调用不会失败。 用户仅会被随机分配到当前应用程序会话的变体，并可在应用程序重新启动后分配到其他变体。 在评估使用标识的标记之前设置标识。

>[!BEGINTABS]

>[!TAB Swift]

```swift
import AEPEdgeIdentity

let identityMap = IdentityMap()
identityMap.add(
    item: IdentityItem(id: "1111", authenticatedState: .authenticated, primary: true),
    withNamespace: "userCRMId" // must match the namespace configured on the feature flag
)
Identity.updateIdentities(with: identityMap)
```

>[!TAB Objective-C]

```objc
@import AEPEdgeIdentity;

AEPIdentityItem *item = [[AEPIdentityItem alloc] initWithId:@"1111"
                                         authenticatedState:AEPAuthenticatedStateAuthenticated
                                                    primary:YES];
AEPIdentityMap *identityMap = [[AEPIdentityMap alloc] init];
[identityMap addItem:item withNamespace:@"userCRMId"]; // must match the namespace configured on the feature flag
[AEPMobileEdgeIdentity updateIdentities:identityMap];
```

>[!ENDTABS]


## API 引用 {#api-reference}

### isFeatureEnable {#is-feature-enabled}

检查是否为当前用户启用了某个功能。 当该功能存在，用户与其定位规则匹配，并且用户不在控制组中时，结果为`true`。 否则，结果为`false`。

>[!BEGINTABS]

>[!TAB Swift]

```swift
static func isFeatureEnabled(
    _ featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    completion: @escaping (Bool) -> Void,
    errorCallback: ((AEPError) -> Void)?
)
```

>[!TAB Objective-C]

```objc
+ (void)isFeatureEnabled:(NSString *)featureKey
       evaluationContext:(AEPFeatureEvaluationContext *)evaluationContext
              completion:(void (^)(BOOL))completion
           errorCallback:(void (^ _Nullable)(enum AEPError))errorCallback;
```

>[!ENDTABS]

**参数**

| 参数 | 类型 | 描述 |
|---|---|---|
| `featureKey` | 字符串 | 在Flags中评估的功能键 |
| `evaluationContext` | FeatureEvaluationContext | 根据需要包括定位属性；将`FeatureEvaluationContext.builder().build()`用于空上下文。 查看[评估上下文](#evaluation-context)。 |
| `completion` | `(Bool) -> Void` | 如果功能已启用，则通过`true`调用，否则通过`false`调用。 |
| `errorCallback` | `((AEPError) -> Void)?` | 可选。 仅针对真正的故障（如空密钥、缺少配置、评估失败或超时）调用。 |

**示例**

>[!BEGINTABS]

>[!TAB Swift]

```swift
Flag.isFeatureEnabled("new-flag", evaluationContext: context) { isEnabled in
    DispatchQueue.main.async {
        if isEnabled {
            // Run the feature-specific behavior
        } else {
            // Run the default behavior
        }
    }
} errorCallback: { _ in
    DispatchQueue.main.async {
        // Run the default behavior
    }
}
```

>[!TAB Objective-C]

```objc
[AEPMobileFlag isFeatureEnabled:@"new-flag"
              evaluationContext:context
                     completion:^(BOOL isEnabled) {
    dispatch_async(dispatch_get_main_queue(), ^{
        if (isEnabled) {
            // Run the feature-specific behavior
        } else {
            // Run the default behavior
        }
    });
} errorCallback:^(enum AEPError error) {
    dispatch_async(dispatch_get_main_queue(), ^{
        // Run the default behavior
    });
}];
```

>[!ENDTABS]

### getFeature {#get-feature}

>[!IMPORTANT]
>
>在没有提供某项功能时，早期版本通过`AEPError.unexpected`调用了错误回调。 如果您的应用程序将该错误视为“功能缺失”，请改为在完成中处理`nil`。

返回当前用户的某个功能的详细信息，包括其元数据和用户所分配的变体。 当您需要的不只是启用或禁用此功能时，请使用该功能。

仅当向用户提供了该功能时，才调用完成并返回结果。 如果未提供该功能，则使用`nil`调用完成。 这是正常结果，而不是错误，并且不会调用错误回调。 在以下情况下，使用`nil`调用完成：

* 没有任何功能具有此密钥。
* 用户不符合定位规则。
* 用户位于控制组中。

仅当出现以下问题时才通过`AEPError.unexpected`（或其他`AEPError`）调用错误回调：功能键为空、缺少所需的配置值、评估失败、无法读取响应或请求超时。

>[!BEGINTABS]

>[!TAB Swift]

```swift
static func getFeature(
    _ featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    completion: @escaping (FeatureEvaluationResult?) -> Void,
    errorCallback: ((AEPError) -> Void)?
)
```

>[!TAB Objective-C]

```objc
+ (void)getFeature:(NSString *)featureKey
 evaluationContext:(AEPFeatureEvaluationContext *)evaluationContext
        completion:(void (^)(AEPFeatureEvaluationResult * _Nullable))completion
     errorCallback:(void (^ _Nullable)(enum AEPError))errorCallback;
```

>[!ENDTABS]

**参数**

| 参数 | 类型 | 描述 |
|---|---|---|
| `featureKey` | 字符串 | 在Flags中评估的功能键 |
| `evaluationContext` | FeatureEvaluationContext | 根据需要包括定位属性；将`FeatureEvaluationContext.builder().build()`用于空上下文。 查看[评估上下文](#evaluation-context)。 |
| `completion` | `(FeatureEvaluationResult?) -> Void` | 使用评估后的功能有效负载调用。 当此功能未提供给用户（未知键、目标不匹配或控制组）时，通过`nil`调用。 `nil`不是错误。 |
| `errorCallback` | `((AEPError) -> Void)?` | 可选。 仅针对真正的故障（如空密钥、缺少配置、评估失败或超时）调用。 未提供该功能时不会调用。 |

**响应**

*FeatureEvaluationResult*

| 字段 | 类型 | 描述 |
|---|---|---|
| `id` | 整数 | 功能ID |
| `key` | 字符串 | 功能键 |
| `featureGroupKey` | 字符串？ | 包含该功能的功能组的键 |
| `meta` | 字符串？ | 为该功能配置的元数据，作为文本。 如果您的元数据是JSON，请在应用程序中对其进行解码。 |
| `analyticsParam` | AnalyticsParam？ | 功能和用户变体的标识符 |

**示例**

>[!BEGINTABS]

>[!TAB Swift]

```swift
Flag.getFeature("new-flag", evaluationContext: context) { feature in
    DispatchQueue.main.async {
        guard let meta = feature?.meta, !meta.isEmpty else {
            // The feature is not served to this user (feature is nil), or it has no metadata.
            // Run the default behavior
            return
        }
        // Use the metadata to drive the feature behavior
    }
} errorCallback: { _ in
    DispatchQueue.main.async {
        // A genuine failure occurred. Run the default behavior
    }
}
```

>[!TAB Objective-C]

```objc
[AEPMobileFlag getFeature:@"new-flag"
        evaluationContext:context
               completion:^(AEPFeatureEvaluationResult * _Nullable feature) {
    dispatch_async(dispatch_get_main_queue(), ^{
        if (feature.meta.length > 0) {
            // Use the metadata to drive the feature behavior
        } else {
            // Run the default behavior
        }
    });
} errorCallback:^(enum AEPError error) {
    dispatch_async(dispatch_get_main_queue(), ^{
        // Run the default behavior
    });
}];
```

>[!ENDTABS]

### extensionVersion {#extension-version}

返回Flags扩展的版本。

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
| `isFeatureEnabled(_:evaluationContext:completion:errorCallback:)` | 完成整个步骤 |
| `getFeature(_:evaluationContext:completion:errorCallback:)` | 功能评估结果？ 直至完成 |
| `extensionVersion` | 字符串 |
