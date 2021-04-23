---
keywords: 优惠；预取；iOS;android;sdk;mobile;mobile sdk
description: 使用iOS和Android Mobile SDK中的Adobe [!DNL Target] 预取功能，通过缓存服务器响应来尽可能少地获取优惠内容。
title: 能否预取移动应用程序的优惠内容？
feature: 实施移动
role: Developer
exl-id: 83a96a41-cf27-4ed8-8169-277f3ef3f249
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 47%

---

# 预取选件内容

[!DNL Target] 预取功能使用 iOS 和 Android Mobile SDK 获取选件内容，并通过缓存服务器响应来尽量减少获取次数。

此过程可缩短加载时间，阻止多个网络调用，并允许 [!DNL Target] 接收有关移动设备应用程序用户访问了哪个 mbox 的通知。在预取调用期间将检索和缓存所有内容，对于以后所有包含指定 mbox 名称的缓存内容的调用，都将从缓存中检索该内容。

在iOS和Android Mobile SDK中使用预取方法时，请考虑以下限制：

* 在启动时，预取内容不会持久保留。只要应用程序处于活动状态，或者在调用 `clearPrefetchCache()` 方法之前，都会一直缓存预取内容。
* [!UICONTROL 自动分配]和[!UICONTROL 自动目标]流量分配方法、[!UICONTROL Automated Personalization]或[!UICONTROL Recommendations]活动类型或A/B或XT活动](/help/c-recommendations/recommendations-as-an-offer.md)中的[推荐优惠不支持预取功能。

有关更多信息（包括预取方法、公共类和代码示例），请参阅：

* **iOS：在**  [Mobile Services iOS SDK帮](https://experienceleague.adobe.com/docs/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) 助中预 *取iOS中的优惠内容*。
* **Android：在**  [Mobile Services Android SDK帮](https://experienceleague.adobe.com/docs/mobile-services/android/target-android/c-mob-target-prefetch-android.html) 助中预 *取Android中的优惠内容*。
