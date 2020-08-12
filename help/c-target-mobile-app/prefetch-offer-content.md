---
keywords: offer;prefetch;iOS;android;sdk;mobile;mobile sdk
description: Adobe Target 预取功能使用 iOS 和 Android Mobile SDK 获取选件内容，并通过缓存服务器响应来尽量减少获取次数。
title: 预取选件内容
feature: null
topic: Advanced,Standard,Classic
uuid: 715e0e77-bfd9-437b-b42c-899d66f2890c
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 62%

---


# 预取选件内容{#prefetch-offer-content}

[!DNL Target] 预取功能使用 iOS 和 Android Mobile SDK 获取选件内容，并通过缓存服务器响应来尽量减少获取次数。

此过程可缩短加载时间，阻止多个网络调用，并允许 [!DNL Target] 接收有关移动设备应用程序用户访问了哪个 mbox 的通知。在预取调用期间将检索和缓存所有内容，对于以后所有包含指定 mbox 名称的缓存内容的调用，都将从缓存中检索该内容。

在iOS和Android Mobile SDK中使用预取方法时，请考虑以下限制：

* 在启动时，预取内容不会持久保留。只要应用程序处于活动状态，或者在调用 `clearPrefetchCache()` 方法之前，都会一直缓存预取内容。
* 自动分配和自动 [!UICONTROL 目标流量分配方] 法、 [!UICONTROL Automated Personalization] 或Recommendations [!UICONTROL 活动类][](/help/c-recommendations/recommendations-as-an-offer.md)型或A/B或XT活动优惠中不支持预取功能。

有关更多信息（包括预取方法、公共类和代码示例），请参阅：

* **iOS:** [预取iOS中的优惠](https://docs.adobe.com/content/help/en/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) 内 *容，请参阅Mobile Services iOS SDK*。
* **Android:** [Mobile Services Android SDK帮助中](https://docs.adobe.com/content/help/en/mobile-services/android/target-android/c-mob-target-prefetch-android.html) ，预 *取Android中的优惠内容*。
