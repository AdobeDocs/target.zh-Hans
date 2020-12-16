---
keywords: offer;prefetch;iOS;android;sdk;mobile;mobile sdk
description: Adobe Target 预取功能使用 iOS 和 Android Mobile SDK 获取选件内容，并通过缓存服务器响应来尽量减少获取次数。
title: 预取选件内容
feature: mobile implementation
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 63%

---


# 预取选件内容{#prefetch-offer-content}

[!DNL Target] 预取功能使用 iOS 和 Android Mobile SDK 获取选件内容，并通过缓存服务器响应来尽量减少获取次数。

此过程可缩短加载时间，阻止多个网络调用，并允许 [!DNL Target] 接收有关移动设备应用程序用户访问了哪个 mbox 的通知。在预取调用期间将检索和缓存所有内容，对于以后所有包含指定 mbox 名称的缓存内容的调用，都将从缓存中检索该内容。

在iOS和Android Mobile SDK中使用预取方法时，请考虑以下限制：

* 在启动时，预取内容不会持久保留。只要应用程序处于活动状态，或者在调用 `clearPrefetchCache()` 方法之前，都会一直缓存预取内容。
* [!UICONTROL 自动分配]和[!UICONTROL 自动目标]流量分配方法、[!UICONTROL Automated Personalization]或[!UICONTROL Recommendations]活动类型或A/B或XT活动](/help/c-recommendations/recommendations-as-an-offer.md)中的[推荐优惠不支持预取功能。

有关更多信息（包括预取方法、公共类和代码示例），请参阅：

* **iOS：在**  [“Mobile Services iOS ](https://experienceleague.adobe.com/docs/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) SDK帮助” *中预取iOS中的优惠内容*。
* **Android：在**  [Mobile Services Android SDK帮](https://experienceleague.adobe.com/docs/mobile-services/android/target-android/c-mob-target-prefetch-android.html) 助中预 *取Android中的优惠内容*。
