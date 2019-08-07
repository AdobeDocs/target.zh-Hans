---
description: Adobe Target 预取功能使用 iOS 和 Android Mobile SDK 获取选件内容，并通过缓存服务器响应来尽量减少获取次数。
keywords: 选件;预取;iOS;Android；sdk；移动；mobile sdk
seo-description: Adobe Target 预取功能使用 iOS 和 Android Mobile SDK 获取选件内容，并通过缓存服务器响应来尽量减少获取次数。
seo-title: 预取选件内容
solution: Target
title: 预取选件内容
topic: Advanced,Standard,Classic
uuid: 715e0e77-bfd9-437b-b42c-899d66f2890c
translation-type: tm+mt
source-git-commit: 95bf4b2070cc2de235ac09ac164f0f9ec48dd6cd

---


# 预取选件内容{#prefetch-offer-content}

[!DNL Target] 预取功能使用 iOS 和 Android Mobile SDK 获取选件内容，并通过缓存服务器响应来尽量减少获取次数。

此过程可缩短加载时间，阻止多个网络调用，并允许 [!DNL Target] 接收有关移动设备应用程序用户访问了哪个 mbox 的通知。在预检调用期间检索和缓存所有内容，并从缓存检索此内容，所有调用的未来调用包含指定mbox名称的缓存内容。

在使用iOS和Android Mobile SDK预览方法时，请考虑以下几点：

* 在启动时，预取内容不会持久保留。只要应用程序处于活动状态，或者在调用 `clearPrefetchCache()` 方法之前，都会一直缓存预取内容。
* 自动Target、自动分配和自动个性化活动类型不支持iOS和Android Mobile SDK中的抢占功能。

有关更多信息（包括预取方法、公共类和代码示例），请参阅：

* **iOS：**《适用于 Experience Cloud 解决方案的 iOS SDK 4.x》[](https://marketing.adobe.com/resources/help/en_US/mobile/ios/c_mob_target-prefetch_ios.html)指南中的&#x200B;*在 iOS 中预取选件内容*。
* **Android：**《适用于 Experience Cloud 解决方案的 Android SDK 4.x》[](https://marketing.adobe.com/resources/help/en_US/mobile/android/c_mob_target-prefetch_android.html)指南中的&#x200B;*在 Android 中预取选件内容*。
