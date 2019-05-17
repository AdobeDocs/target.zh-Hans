---
description: Adobe Target Mobile Visual Experience Composer(CMS)使开发人员能在其iOS移动应用程序上一次性设置，并使营销人员能够使用移动App CMS的功能。
keywords: 移动App CMS；移动可视体验书写器；移动体验书写器选项；设置；iOS；Apple
seo-description: Adobe Target Mobile Visual Experience Composer(CMS)使开发人员能在其iOS移动应用程序上一次性设置，并使营销人员能够使用移动App CMS的功能。
seo-title: iOS - 设置移动设备应用程序
solution: Target
title: iOS - 设置移动设备应用程序
topic: Standard
uuid: 6db4f06a-d8f4-4192-af6f-917594e721e6
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# iOS - 设置移动设备应用程序{#ios-set-up-the-mobile-app}

Adobe Target Mobile App Visual Experience Composer(CMS)使开发人员能在其iOS移动应用程序上一次性设置，并使营销人员能够使用移动App CMS的功能。

有关启用Adobe Target CMS扩展的更多信息，请参阅 [Adobe Experience Platform Mobile SDK](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-target-vec) 中的Adobe *Target- Visual Experience Composer*。

## 包括Mobile SDK和Target库 {#sdk-library}

1. 通过添加窗格将库添加到您的项目 [!DNL Podfile] 中`ACPTargetVEC`。
1. 在 XCode 中打开您的 Objective-C 应用程序项目。
1. 如果尚未设置，请转到项目构建设置并将“始终嵌入快速标准库”设置为“是”。
1. 在项目构建设置中找到“其他链接器标记”，添加 `$(inherited)`（如果尚未添加）。
1. 对于仅限 Objective-C 项目 - 创建一个 swift 文件以创建桥接标头。此操作将为 Swift 设置您的应用程序环境。
1. 添加深层链接处理程序：

   1. 在您的应用程序项目设置中，单击**[!UICONTROL 信息]**。
   1. 在 **[!UICONTROL URL类型]**下，单击三角形以将其打开，然后单击加号以添加新字段。
   1. 添加以下信息：

      * 标识符: `com.adobe.sdktest`
      * URL方案： `vectester`
      * 角色：编辑者
   1. 单击以离开您的应用程序项目设置 &gt; **[!UICONTROL 常规]**。
   1. 单击以返回您的应用程序项目设置 &gt; **[!UICONTROL 信息]，以确保您的设置已保存。**

      对于示例 URL 类型，适用于您的应用程序的 URL 方案将是：

      ```
      vectester://com.adobe.sdktest
      ```


1. 在 XCode 中，打开您的 [!DNL AppDelegate] 文件。
1. 在该文件的顶部，在导入内容的末尾添加以下行：

   `#import "ACPTargetVEC.h"`

   如果您使用的是 Swift，请添加以下行：

   `import ACPTargetVEC`

1. 在您的 [!DNL AppDelegate] 文件中，将以下行添加到 `AppDelegate::application:didFinishLaunchingWithOptions:`。如果未定义委托函数，请创建此函数，并分别为 Objective-C 或 Swift 应用程序添加以下行：

   ```
   // CONFIGURATION LINE FOR OBJECTIVE C ONLY (Skip any framework which is not applicable for you): 
   [ACPCore configureWithAppId:@"YOUR_ADOBE_LAUNCH_APP_ID"]; 
   [ACPCore setLogLevel:ACPMobileLogLevelDebug]; 
   [ACPLifecycle registerExtension]; 
   [ACPIdentity registerExtension]; 
   [ACPUserProfile registerExtension]; 
   [ACPTarget registerExtension];
   
   [ACPTargetVEC registerExtension];
   [ACPCore start:^{
        [ACPCore lifecycleStart:nil];
   }];
   
   // CONFIGURATION LINE FOR SWIFT ONLY: 
   ACPCore.configure(withAppId: "YOUR_ADOBE_LAUNCH_APP_ID") 
   ACPCore.setLogLevel(ACPMobileLogLevel.debug) 
   ACPLifecycle.registerExtension() 
   ACPIdentity.registerExtension() 
   ACPUserProfile.registerExtension() 
   ACPTarget.registerExtension() 
   
   ACPTargetVEC.registerExtension() 
   
   ACPCore.start {
     ACPCore.lifecycleStart(nil)
   }
   ```

   例如，该方法应类似于以下示例：

   ```
   // EXAMPLE OVERRIDE METHOD FOR OBJECTIVE C ONLY: 
   - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions { 
        // Override point for customization after application launch. 
       [ACPCore configureWithAppId:@"YOUR_ADOBE_LAUNCH_APP_ID"]; 
       [ACPCore setLogLevel:ACPMobileLogLevelDebug]; 
       [ACPLifecycle registerExtension]; 
       [ACPIdentity registerExtension]; 
       [ACPUserProfile registerExtension]; 
       [ACPTarget registerExtension]; 
   
       [ACPTargetVEC registerExtension]; 
   
       [ACPCore start:nil]; 
       [ACPCore lifecycleStart:nil]; 
   
      return YES; 
   } 
   
   // EXAMPLE OVERRIDE METHOD FOR SWIFT ONLY: 
   func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey : Any]? = nil) 
   { 
       ACPCore.configure(withAppId: "YOUR_ADOBE_LAUNCH_APP_ID") 
       ACPCore.setLogLevel(ACPMobileLogLevel.debug) 
       ACPLifecycle.registerExtension() 
       ACPIdentity.registerExtension() 
       ACPUserProfile.registerExtension() 
       ACPTarget.registerExtension() 
   
       ACPTargetVEC.registerExtension() 
   
       ACPCore.start(nil) 
       ACPCore.lifecycleStart(nil)
   
       return true 
   
   }
   ```

1. 将以下行添加到 `AppDelegate:application:openURL` 的开头。如果未定义委托函数，请创建此函数并添加以下行。

   ```
   // URL HANDLER LINE FOR OBJECTIVE C ONLY: 
   [ACPTargetVEC handleDeepLink:url];
   
   // URL HANDLER LINE FOR SWIFT ONLY: 
   ACPTargetVEC.handleDeepLink(url)
   ```

   例如，该方法应类似于以下示例：

   ```
   // EXAMPLE OVERRIDE METHOD FOR OBJECTIVE C ONLY:
   -  (BOOL)application:(UIApplication *)application openURL:(NSURL *)url options:(NSDictionary<NSString *, id> *)options {
    [ACPTargetVEC handleDeepLink:url];
    return YES;
   }
   
   // EXAMPLE OVERRIDE METHOD FOR SWIFT ONLY:
   func application(_ app: UIApplication, open url: URL, options: [UIApplication.OpenURLOptionsKey : Any] = [:]) -> Bool {
      ACPTargetVEC.handleDeepLink(url)
      return true;
   }
   ```

1. 构建和运行应用程序，并使用它测试Mobile App CMS功能。

## 在移动应用程序上设置目标视图 {#views}

Adobe Mobile SDK 公开了一种新方法，供开发人员在渲染新视图时触发。请阅读有关如何正确插入针对iOS应用程序的Target View API调用的一般指导方针。在 iOS 中，所有 Target 视图都是相对于显示它们的 `UIViewController` 定义的。因此，与 Android 不同，`TargetViews` 的插入仅限于以下调用。

Adobe Mobile App CMS扩展根据子类的类名自动生成您 `UIViewControllers` 在移动App CMS框架内交互的名称 `UIViewController`。如果要覆盖这些名称，则可以在其中调用以下 `viewWillAppear` 方法 `ViewController`。

```
// TARGET VIEW LINE FOR OBJECTIVE C ONLY 
[ACPTargetVEC setTargetView:@"exampleViewController"]; 
   
// TARGET VIEW LINE FOR SWIFT ONLY 
ACPTargetVEC.setTargetView("exampleViewController")
```

Adobe Mobile SDK 还公开了一种替代方法，供开发人员在运行时定位自定义视图。作为开发人员，您必须确保该视图的名称是唯一的。在添加视图之前，请先调用以下方法 `superview`：

```
// EXAMPLE TARGET VIEW FOR A CUSTOM VIEW IN OBJECTIVE C 
CustomPopupView *popupView = [[CustomPopupView alloc] initWithFrame:CGRectMake(0, 0, 300, 200)]; 
[ACPTargetVEC setTargetView:@"myCustomPopupView" forView:popupView];

// EXAMPLE TARGET VIEW FOR A CUSTOM VIEW IN SWIFT 
let popupView = CustomPopupView.init(frame: CGRect(x: 0, y: 0, width: 300, height: 200)) 
ACPTargetVEC.setTargetView("myCustomPopupView", for: popupView)
```

## 设置配置文件参数和其他全局参数 {#parameters}

我们现在支持设置每个API调用中传递的全局参数，以及将mbox/View参数传递给相应视图。

这些参数包括：

* mbox/视图参数
* 配置文件参数
* 产品参数
* 订单参数

**全局参数支持：**

```
//For Objective-c 
NSDictionary *mboxParams = @{@"mboxparam1":@"mboxvalue1"}; //mbox or view params 
NSDictionary *profileParams = @{@"profilekey1":@"profilevalue1"}; //profile params 
  
ACPTargetProduct *product = [ACPTargetProduct targetProductWithId:@"1234" categoryId:@"furniture"]; 
ACPTargetOrder *order = [ACPTargetOrder targetOrderWithId:@"12343" total:@(123.45) purchasedProductIds:@[@"100",@"200"]]; 
ACPTargetParameters *targetParams = [ACPTargetParameters targetParametersWithParameters:mboxParams 
                                                                      profileParameters:profileParams 
                                                                                product:product 
                                                                                  order:order]; 
[ACPTargetVEC setGlobalRequestParameters:targetParams];

//For Swift 
var mboxParams = ["mboxparam1":"mboxvalue1"] 
var profileParams = ["profilekey1":"profilevalue1"] 
var product : ACPTargetProduct = ACPTargetProduct.init(id: "1234", categoryId: "furniture") 
var order : ACPTargetOrder = ACPTargetOrder.init(id: "12345", total: 123.45, purchasedProductIds: ["100", "200"]) 
var targetParams : ACPTargetParameters = ACPTargetParameters.init(parameters: mboxParams, profileParameters: profileParams, product: product, order: order) 
ACPTargetVEC.setGlobalRequest(targetParams)
```

**传递用于触发下一个视图的参数：**

We have provided some automatic views that are created by default, such as &quot;`AUTO_<viewControllerName>`&quot; for each view controller present in your app. 如果要传递这些参数，可以调用以下 API：

```
//For Objective-c 
NSDictionary *mboxParams = @{@"viewparam1":@"viewvalue1"}; //mbox or view params 
NSDictionary *profileParams = @{@"profilekeyforview1":@"profilevalueforview1"}; //profile params 
  
ACPTargetProduct *product = [ACPTargetProduct targetProductWithId:@"1234" categoryId:@"furniture"]; 
ACPTargetOrder *order = [ACPTargetOrder targetOrderWithId:@"12343" total:@(123.45) purchasedProductIds:@[@"100",@"200"]]; 
ACPTargetParameters *targetParams = [ACPTargetParameters targetParametersWithParameters:mboxParams 
                                                                      profileParameters:profileParams 
                                                                                product:product 
                                                                                  order:order]; 
[ACPTargetVEC setGlobalRequestParameters:targetParams];

//For Swift 
var mboxParams = ["mboxparam1":"mboxvalue1"] 
var profileParams = ["profilekey1":"profilevalue1"] 
var product : ACPTargetProduct = ACPTargetProduct.init(id: "1234", categoryId: "furniture") 
var order : ACPTargetOrder = ACPTargetOrder.init(id: "12345", total: 123.45, purchasedProductIds: ["100", "200"]) 
var targetParams : ACPTargetParameters = ACPTargetParameters.init(parameters: mboxParams, profileParameters: profileParams, product: product, order: order) 
ACPTargetVEC.setRequest(targetParams)
```

**将这些参数传递给特定视图：**

我们已看到API触发Views通过 `TargetVEC.targetView("view_name")`。此外，您还可以传递特定于特定视图的参数，如下所示：

```
//For Objective-c 
[ACPTargetVEC setTargetView:@"VIEW_NAME" withParameters:TARGET_PARAMS];

//FOR SWIFT 
ACPTargetVEC.setTargetView("VIEW_NAME", with: TARGET_PARAMS)
```

## 显式调用预吸引API {#section_373DB4527FC649C58FBA3DF0C18C9836}

在某些情况下，您可能想通过再次调用预取 API 来刷新存储在缓存中的选件。以下 API 已经公开，其描述如下：

**预取选件：**

```
/** 
 * Prefetch all offers for all views in the cache. It will remove existing offers and changes for the current view will be 
 refreshed only when the view is triggered. This call happens on the main thread blocking the UI. 
 */ 
+ (void) prefetchOffers;
```

**在后台预取选件：**

```
/** 
 * Prefetch all offers for all views in the cache. It will remove existing offers and changes for the current view will be 
 refreshed only when the view is triggered. This call happens on the background thread so doesn't block UI. 
 */ 
+ (void) prefetchOffersBackground;
```

