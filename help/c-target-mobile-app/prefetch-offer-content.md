---
description: Adobe Target 预取功能使用 iOS 和 Android Mobile SDK 获取选件内容，并通过缓存服务器响应来尽量减少获取次数。
keywords: 选件;预取;iOS;Android
seo-description: Adobe Target 预取功能使用 iOS 和 Android Mobile SDK 获取选件内容，并通过缓存服务器响应来尽量减少获取次数。
seo-title: 预取选件内容
solution: Target
title: 预取选件内容
topic: Advanced,Standard,Classic
uuid: 715e0e77-bfd9-437b-b42c-899d66f2890c
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 预取选件内容{#prefetch-offer-content}

[!DNL Adobe Target] 预取功能使用 iOS 和 Android Mobile SDK 获取选件内容，并通过缓存服务器响应来尽量减少获取次数。

此过程可缩短加载时间，阻止多个网络调用，并允许 [!DNL Target] 接收有关移动设备应用程序用户访问了哪个 mbox 的通知。在预取调用期间将检索和缓存所有内容，对于以后所有包含指定 mbox 名称的缓存内容的调用，都将从缓存中检索该内容。

在启动时，预取内容不会持久保留。只要应用程序处于活动状态，或者在调用 `clearPrefetchCache()` 方法之前，都会一直缓存预取内容。

有关更多信息（包括预取方法、公共类和代码示例），请参阅：

* **iOS：**[在iOS](https://marketing.adobe.com/resources/help/en_US/mobile/ios/c_mob_target-prefetch_ios.html) SDK4.x for Experience Cloud解决方案*指南中预购iOS中的选件内容。
* **Android：**《适用于 Experience Cloud 解决方案的 Android SDK 4.x》[](https://marketing.adobe.com/resources/help/en_US/mobile/android/c_mob_target-prefetch_android.html)指南中的&#x200B;*在 Android 中预取选件内容*。