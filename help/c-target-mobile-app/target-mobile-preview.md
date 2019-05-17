---
description: 使用移动预览链接可对移动设备应用程序活动轻松执行端到端 QA，并且无需任何特殊的测试设备即可在您的设备上感受到不同的体验。
keywords: QA;预览;预览链接;移动设备;移动设备预览
seo-description: 使用移动预览链接可对移动设备应用程序活动轻松执行端到端 QA，并且无需任何特殊的测试设备即可在您的设备上感受到不同的体验。
seo-title: Target 移动设备预览
solution: Target
title: Target 移动设备预览
topic: Advanced,Standard,Classic
uuid: 313150fa-a7ec-46fe-9166-742a5c246a72
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Target 移动设备预览{#target-mobile-preview}

使用移动预览链接可对移动设备应用程序活动轻松执行端到端 QA，并且无需任何特殊的测试设备即可在您的设备上感受到不同的体验。

>[!NOTE]
>
>此功能将于 2017 年 10 月 12 日后在 UI 中启用，以供所有客户使用。移动设备预览功能要求您下载并安装相应的 Adobe Mobile SDK 4.14（或更高）版本。

## 概述 {#section_981D6FA4AEE64098809EA606E89E4A5E}

通过移动设备预览功能，您可以在启动移动设备应用程序活动之前，对其进行全面测试。

## 先决条件 {#section_A763C564C9E84B0EB448237B5B1E4068}

1. **使用受支持的 SDK 版本：**移动设备预览功能要求您在相应的应用程序中下载并安装适当的 Adobe Mobile SDK 4.14（或更高）版本。

   有关下载适当 SDK 的说明，请参阅：

   * **iOS：**《适用于 Experience Cloud 解决方案的 iOS SDK 4.x》[](https://marketing.adobe.com/resources/help/en_US/mobile/ios/requirements.html)指南中的*开始之前*部分。
   * **Android：**《适用于 Experience Cloud 解决方案的 Android SDK 4.x》指南中的[开始之前](https://marketing.adobe.com/resources/help/en_US/mobile/android/requirements.html)*部分。*

1. **设置 URL 方案：**预览链接需使用 URL 方案来打开应用程序。您必须为预览指定一个唯一的 URL 方案。

   下图显示了 iOS 上的一个示例：

   ![](assets/mobile-preview-url-scheme-ios.png)

   下图显示了 Android 上的一个示例：

   ![](assets/Android_Deeplink.png)

1. **跟踪 Adobe 深层链接**

   **iOS：**在应用程序代理中，如果要求代理使用上一步中指定的 URL 方案打开资源，请调用 `[ADBMobile trackAdobeDeepLink:url`。

   下面是一个代码片段示例：

   ```
   - (BOOL) application:(UIApplication *)app openURL:(NSURL *)url 
                options:(NSDictionary<NSString *,id> *)options { 
   
       if ([[url scheme] isEqualToString:@"com.adobe.targetmobile"]) { 
           [ADBMobile trackAdobeDeepLink:url]; 
           return YES; 
       } 
       return NO; 
   } 
   ```

   **Android：**在应用程序中，如果要求调用方使用上一步中指定的 URL 方案打开资源，请调用 `Config.trackAdobeDeepLink(URL);`。

   ```
    private Boolean shouldOpenDeeplinkUrl() { 
        Intent appLinkIntent = getIntent(); 
        String appLinkAction = appLinkIntent.getAction(); 
        Uri appLinkData = appLinkIntent.getData; 
        if (appLinkData.toString().startsWith("com.adobe.targetmobile")) { 
            Config.trackAdobeDeepLink(appLinkData); 
            return true; 
        } 
        return false; 
     }
   ```

   为使移动设备预览功能在 Android 中正常工作，您还必须在 [!DNL AndroidManifest.xml] 中添加以下代码片段：

   ```
   <activity android:name="com.adobe.mobile.MessageFullScreenActivity" />
   ```

## 生成预览链接 {#section_D9D58173FFF34E9BB75EBF357273F128}

1. 在 Target UI 中，单击**[!UICONTROL 更多选项]**图标（三个垂直省略号），然后选择**[!UICONTROL 创建移动设备预览]**。

   ![](assets/mobile-preview-create.png)

1. 选择要预览的活动，然后单击**[!UICONTROL 生成移动设备预览链接]**。

   >[!NOTE]
   >
   >只能选择基于表单的 AB 活动和 XT 活动。

   ![](assets/mobile-preview-select-activities.png)

1. 指定应用程序的 URL 方案。

   这需要与您的 iOS 或 Android 应用程序中存在的方案相同。如有需要，请分别对 iOS 和 Android 重复此过程。

   ![](assets/mobile-preview-enter-url-scheme.png)

1. 单击**[!UICONTROL 生成移动设备预览链接]**，然后复制该链接。

   ![](assets/mobile-preview-generate-and-copy.png)

## 在设备上预览 {#section_521F0D46F3DE4A2A98283A1B73FF69F6}

在安装了您的应用程序的设备上，使用移动设备浏览器打开链接。此应用程序可以是您从 Apple App Store 或 Google Play 商店下载的生产应用程序。此应用程序不必是某个特殊版本。如果您有一个有效的预览链接，您便能够在设备上查看体验。

1. 在移动设备浏览器中打开链接。

   可通过一种简便的方式（例如使用文本、电子邮件或 Slack），将您在上一步中从 Target UI 复制的链接共享到移动设备。

   |![预览深层链接 1](/help/c-target-mobile-app/assets/mobile-preview-open-deeplink.png)|![预览深层链接 2](/help/c-target-mobile-app/assets/mobile-preview-open-app.png)|

   您的应用程序随即会打开，并启动 Target 移动设备预览模式。

1. 选择要查看的体验组合，然后单击**[!UICONTROL 启动体验]**。

   |![移动设备预览 1](/help/c-target-mobile-app/assets/mobile-preview-experience-selection-1.png)|![移动设备预览 2](/help/c-target-mobile-app/assets/mobile-preview-experience-result-1-france.png)|![移动设备预览 3](/help/c-target-mobile-app/assets/mobile-preview-experience-result-1-shipfree.png)|
|![移动设备预览 4](/help/c-target-mobile-app/assets/mobile-preview-experience-selection-2.png)|![移动设备预览 5](/help/c-target-mobile-app/assets/mobile-preview-experience-result-2-aus.png)|![移动设备预览 6](/help/c-target-mobile-app/assets/mobile-preview-experience-result-2-10off.png)|

## 限制 {#section_4E9BDED0F718485292527EFB508305BD}

* 单击“[!UICONTROL 启动体验]”按钮后，必须重新加载视图，才能显示新内容。最简单的方式是先切换到另一个屏幕，然后再返回到您期待发生更改的屏幕。
* 低于 API-19 (KitKat) 的 Android 版本不支持移动设备预览功能。