---
description: Target 的新 SDK 库允许开发人员在其 Android 移动设备应用程序上进行一次性设置，并使营销人员能够使用移动设备可视化体验编辑器 (VEC) 的功能。
keywords: 移动设备 VEC;移动设备可视化体验编辑器;移动设备体验编辑器选项;设置;Android
seo-description: Target 的新 SDK 库允许开发人员在其 Android 移动设备应用程序上进行一次性设置，并使营销人员能够使用移动设备可视化体验编辑器 (VEC) 的功能。
seo-title: Android - 设置移动设备应用程序
solution: Target
title: Android - 设置移动设备应用程序
topic: Standard
uuid: 39938ec2-b12e-44cf-9218-69195fba0ff7
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Android - 设置移动设备应用程序{#android-set-up-the-mobile-app}

Adobe Target Mobile App Visual Experience Composer(CMS)使开发人员能在他们的Android移动应用程序上一次性设置，并使营销人员能够使用移动App CMS的功能。

有关启用Adobe Target CMS扩展的更多信息，请参阅 [Adobe Experience Platform Mobile SDK](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-target-vec) 中的Adobe *Target- Visual Experience Composer*。

## 包括Mobile SDK和Target库 {#sdk-library}

1. 有关 SDK V5 初始化的信息，请参阅[初始化 SDK 和设置跟踪](https://aep-sdks.gitbook.io/docs/getting-started/initialize-the-sdk)。
1. 在依赖关系部分添加以下行：

   ```
   implementation 'com.adobe.marketing.mobile:target-vec:1.+'
   ```

1. 移动App CMS需要将以下人工包含作为依赖项 `build.gradle`。

   ```
    implementation 'com.google.code.gson:gson:2.8.2'
    implementation 'android.arch.lifecycle:extensions:1.1.1'
    implementation('io.github.sac:SocketclusterClientJava:1.7.5')
    implementation 'com.android.support:support-annotations:28.0.0'
    implementation 'com.android.support:support-compat:28.0.0'
    implementation 'com.android.support:design:28.0.0'
   ```

1. 在 `AndroidManifest.XML` 文件中添加意图过滤器，为Mobile App CMS创作选择唯一的深层链接方案(例如， `[sdkbetabus://com.adobe.sdkbetabus](sdkbetabus://com.adobe.sdkbetabus)`)：

   ```
   <activity 
       android:name=".listing.MoviesListingActivity" 
       android:launchMode="singleTask"> 
       <intent-filter> 
           <action android:name="android.intent.action.VIEW" /> 
   
           <category android:name="android.intent.category.DEFAULT" /> 
           <category android:name="android.intent.category.BROWSABLE" /> 
   
           <data 
               android:host="com.adobe.sdkbetabus" 
               android:scheme="sdkbetabus" /> 
       </intent-filter> 
   </activity>
   ```

1. 转到您的移动设备项目，并在 `Application::onCreate override` 的末尾插入以下行：

   ```
   public class SDKTest extends MultiDexApplication { 
   
       @Override 
       public void onCreate() { 
           /* Put Your App's implementation */ 
           MobileCore.setApplication(this); 
           MobileCore.setLogLevel(LoggingMode.DEBUG); 
           MobileCore.configureWithAppID("YOUR_ADOBE_LAUNCH_APP_ID"); 
   
           ... 
           try { 
               TargetVEC.registerExtension(); //Single line code to initialize TargetVEC
               Target.registerExtension();
               Identity.registerExtension();
               Lifecycle.registerExtension();
               Signal.registerExtension();
               MobileCore.start(new AdobeCallback () {
                  @Override
                  public void call(Object o) {
                     MobileCore.configureWithAppID("launch-EN4e833d644d1949e39e985ddad4f52bd4-development");
                  }
               });
           } catch (InvalidInitException e) { 
             .. 
           }
       }
   
   /* Rest of Application test goes here ... */
   ```

1. 如果您构建的项目不能正常运行，请查看下面提供的示例项目，这些项目应当直接构建，可在以下位置查看所做的更改：

   1. `Application::OnCreate override`
   1. `AndroidManifest.XML`
   1. `build.gradle` Android应用程序的应用程序

## 在移动应用程序上设置目标视图 {#views}

Adobe Mobile SDK 公开了一种新方法，供开发人员在渲染新视图时触发。作为开发人员，您必须确保视图的名称是唯一的，并且 `targetView` 调用位于 UI 主线程上。在本部分中，我们将首先演示如何使用两个不同的演示应用程序插入这些调用，并讨论如何正确插入针对任何Android应用程序的Target视图API调用的一般指导方针。

>[!NOTE]
>
>如果未 `targetView function` 触发该功能，则CMS扩展会尝试从Android活动中识别查看。对于没有动态视图的应用程序，这可以是可选步骤。

可以通过函数调用触发目标视图。可以在视图中选择提供任何定位参数。

```
public class TargetVEC { 
   
   /** 
    * Marks a view hierarchy for editing in Mobile App VEC.  Call must insert when the view hierarchy 
    * is memory and committed to being shown, but not yet shown on the screen. 
    * 
    * @param viewName the unique Target View Name 
    */ 
   public static void targetView(String viewName); 
  
  /** 
   * Trigger Target view 
   * Triggering a Target view may cause Target offers to be applied on the current container component. 
   * Note that Target offers are applied from local Target cache, so flicker should be negligible. 
   * 
   * @param viewName Mandatory Target View name, which must be unique at app level 
   * @param parameters Parameters to be included in the next Target call 
   */ 
  
    public static void targetView(String viewName, TargetParameters parameters); 
}
```

我们的第一个示例项目是一个简单的总线调度应用程序模型。要设置此应用程序以在移动应用程序CMS中使用，请执行以下操作：

1. 在 Android Studio 中，使用包子目录 `build.gradle` 中的 `BusBooking` 文件打开项目。
1. 在 `DemoApplication::OnCreate` 方法中，添加 `TargetVEC.registerExtension()` 以注册 Target VEC 扩展以及其他扩展。
1. 构建并运行应用程序。
1. 要进入Mobile App CMS创作模式，请使用作为 [!DNL sdkbetabus://com.adobe.sdkbetabus] 其URL方案，然后在设备上打开生成的深层链接(请参阅下面的说明)。

通过此简单的总线预订应用程序，我们可以使用与活动生命周期关联的所有自动生成的 Target 视图。此外，我们还通过在单击隐藏的按钮（屏幕上的选件图像）后，调用动态添加的自定义视图元素上的 Target 视图 API，来演示 API 的灵活性。此新 Target 视图通过在 `OfferDetailsActivity.java:40` 的代码中插入 API 调用来实施。单击隐藏的按钮后，会触发名为“SURPRISE_VIEW”的新 Target 视图事件，从而允许营销人员更准确地定位对应用程序体验所做的更改。

目标动态视图插入：

```
package com.adobe.target.examples.bus; 
   
import android.app.DialogFragment; 
import android.os.Bundle; 
import android.os.Handler; 
import android.support.v7.app.AppCompatActivity; 
import android.support.v7.widget.Toolbar; 
import android.view.View; 
import android.view.ViewGroup; 
import android.widget.LinearLayout; 
import android.widget.Toast; 
   
import com.adobe.target.mobile.TargetVEC; 
   
/** 
 * This activity class is responsible to show offer details 
 */ 
public class OfferDetailsActivity extends AppCompatActivity { 
    @Override 
    protected void onCreate(Bundle savedInstanceState) { 
        super.onCreate(savedInstanceState); 
        setContentView(R.layout.activity_offer_details); 
        setUpToolBar(); 
        final Handler mainHandler = new Handler(getApplicationContext().getMainLooper()); 
   
        final View surpriseView = getLayoutInflater().inflate(R.layout.suprise_layout, 
                (ViewGroup) findViewById(android.R.id.content), false); 
   
        final View imagePresentView = this.findViewById(R.id.image_present); 
        final LinearLayout currentLayout = this.findViewById(R.id.offer_layout); 
   
        imagePresentView.setOnClickListener(new View.OnClickListener() { 
            @Override 
            public void onClick(View v) { 
                Toast.makeText(getApplicationContext(),"Surprise!", Toast.LENGTH_SHORT).show(); 
                mainHandler.post(new Runnable() { 
                    @Override 
                    public void run() { 
                        currentLayout.addView(surpriseView); 
                        TargetVEC.targetView("SURPRISE_VIEW"); 
                        currentLayout.invalidate(); 
                    } 
                }); 
                // One-shot.  Remove clicker afterwards. 
                imagePresentView.setOnClickListener(null); 
            } 
        }); 
    } 
   
    private void setUpToolBar() { 
        Toolbar toolbar = findViewById(R.id.toolbar); 
        toolbar.setNavigationIcon(R.drawable.abc_ic_ab_back_material); 
        toolbar.setTitle("Buy 1 Get 1"); 
        toolbar.setNavigationOnClickListener(new View.OnClickListener() { 
            @Override 
            public void onClick(View v) { 
                onBackPressed(); 
            } 
        }); 
    } 
   
    @Override 
    protected void onPause() { 
        super.onPause();
        MobileCore.lifecyclePause();
    } 
   
    @Override 
    protected void onResume() { 
        super.onResume();
        MobileCore.lifecycleStart(null);
    } 
}
```

## 设置配置文件参数和其他全局参数 {#parameters}

我们现在支持设置将在每个API调用中传递的全局参数，以及将mbox/View参数传递给相应视图。

这些参数包括：

* mbox/视图参数
* 配置文件参数
* 产品参数
* 订单参数

**全局参数支持：**

```
Map<String, String> mboxParams = new HashMap<>();  //Mbox or view params 
mboxParams.put("mboxparam1", "mboxvalue1"); 
Map<String, String> profileParams = new HashMap<>();  //Profile params 
profileParams.put("profilekey1", "profilevalue1"); 
  
TargetVEC.setGlobalRequestParameters(new TargetParameters.Builder() 
        .parameters(mboxParams) 
        .profileParameters(profileParams) 
        .product(new TargetProduct("1234", "furniture")) 
        .order(new TargetOrder("12343", 123.45, Arrays.asList("100", "200"))) 
        .build());
```

**传递用于触发下一个视图的参数：**

We have provided some automatic views that are created by default, such as &quot;`AUTO_<activity|fragment name>`&quot; for each activity and fragment present in your app. 如果要传递这些参数，可以调用以下 API：

```
Map<String, String> mboxParams = new HashMap<>();  //Mbox or view params 
mboxParams.put("viewKey1", "viewparam1"); 
Map<String, String> profileParams = new HashMap<>();  //Profile params 
profileParams.put("profilekeyforview1", "profilevalueforview1"); 
  
TargetVEC.setRequestParameters(new TargetParameters.Builder() 
        .parameters(mboxParams) 
        .profileParameters(profileParams) 
        .product(new TargetProduct("1234", "furniture")) 
        .order(new TargetOrder("12343", 123.45, Arrays.asList("100", "200"))) 
        .build());
```

**将参数传递到特定视图：**

我们已看到API触发Views通过 `TargetVEC.targetView("view_name")`。此外，您还可以传递特定于特定视图的参数，如下所示：

```
Map<String, String> profileParams = new HashMap<>(); 
profileParams.put("surprisekey1", "surprisevalue1");  //ProfileParams 
TargetVEC.targetView("SURPRISE_VIEW", 
        new TargetParameters.Builder() 
                .profileParameters(profileParams) 
                .product(new TargetProduct("3354", "kitchen")) 
                .build());
```

## 显式调用预吸引API {#section_2D02B74558474D3BA9F25E4D25E7C7E3}

在某些情况下，您可能想通过再次调用预取 API 来刷新存储在缓存中的选件。以下 API 已经公开，其描述如下：

* **prefetchOffers**

   ```
   /** 
    * Prefetch Target offers. 
    * Note that calling this will pre-hide the current layout, until Target offers are prefetched 
    * and applied to currently visible Target views, possibly causing flicker, thus it's recommended 
    * to call this method inside the containing component's onCreate() lifecycle method 
    */ 
   public static void prefetchOffers();
   ```

* **prefetchOffersBackground**

   ```
   /** 
    * Prefetch Target offers in the background. 
    * Note, that in contrast to prefetchOffers(), calling this method will NOT pre-hide 
    * the current layout, instead prefetched Target offers will be only be cached and will subsequently 
    * be applied as Target Views are being triggered. 
    */ 
   public static void prefetchOffersBackground();
   ```

