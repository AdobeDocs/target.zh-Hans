---
description: Adobe Target 预取功能使用 iOS 和 Android Mobile SDK 获取选件内容，并通过缓存服务器响应来尽量减少获取次数。
keywords: 选件;预取;iOS;Android;sdk;mobile;mobile sdk
seo-description: Adobe Target 预取功能使用 iOS 和 Android Mobile SDK 获取选件内容，并通过缓存服务器响应来尽量减少获取次数。
seo-title: 预取选件内容
solution: Target
title: 预取选件内容
topic: Advanced,Standard,Classic
uuid: 715e0e77-bfd9-437b-b42c-899d66f2890c
translation-type: tm+mt
source-git-commit: ce8a890d0d662c0eec4d7fe254da371694811822

---


# 预取选件内容{#prefetch-offer-content}

[!DNL Target] 预取功能使用 iOS 和 Android Mobile SDK 获取选件内容，并通过缓存服务器响应来尽量减少获取次数。

此过程可缩短加载时间，阻止多个网络调用，并允许 [!DNL Target] 接收有关移动设备应用程序用户访问了哪个 mbox 的通知。All content is retrieved and cached during the prefetch call, and this content is retrieved from the cache for all future calls that contain cached content for the specified mbox name.

Consider the following when uses in prefetch method with the iOS and Android Mobile SDKs:

* 在启动时，预取内容不会持久保留。只要应用程序处于活动状态，或者在调用 `clearPrefetchCache()` 方法之前，都会一直缓存预取内容。
* “自动定位”、“自动分配”和“自动个性化”活动类型不支持iOs和Android Mobile SDK中的预取功能。

有关更多信息（包括预取方法、公共类和代码示例），请参阅：

* **** iOS:  Prefetch offer content in iOS in the Mobile Services iOS SDK Help.[](https://docs.adobe.com/content/help/en/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html)**
* **** Android:  Prefetch offer content in Android in the Mobile Services Android SDK Help.[](https://docs.adobe.com/content/help/en/mobile-services/android/target-android/c-mob-target-prefetch-android.html)**
