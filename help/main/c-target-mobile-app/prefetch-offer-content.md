---
keywords: 选件；预取；iOS;Android;SDK；移动设备；移动SDK
description: 使用Adobe [!DNL Target] iOS和Android Mobile SDK中的预取功能，通过缓存服务器响应来尽量减少获取选件内容的次数。
title: 我能否预取移动设备应用程序的选件内容？
feature: Implement Mobile
role: Developer
exl-id: 83a96a41-cf27-4ed8-8169-277f3ef3f249
source-git-commit: e152d3d68eede9c7606e546e30bd3e65bb8bcb9a
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 54%

---

# 预取选件内容

[!DNL Target] 预取功能使用 iOS 和 Android Mobile SDK 获取选件内容，并通过缓存服务器响应来尽量减少获取次数。

此过程可缩短加载时间，阻止多个网络调用，并允许 [!DNL Target] 接收有关移动设备应用程序用户访问了哪个 mbox 的通知。在预取调用期间将检索和缓存所有内容，对于以后所有包含指定 mbox 名称的缓存内容的调用，都将从缓存中检索该内容。

在iOS和Android Mobile SDK中使用预取方法时，请考虑以下限制：

* 在启动时，预取内容不会持久保留。只要应用程序处于活动状态，或者在调用 `clearPrefetchCache()` 方法之前，都会一直缓存预取内容。

有关更多信息（包括预取方法、公共类和代码示例），请参阅：

* **iOS:**  [在iOS中预取选件内容](https://experienceleague.adobe.com/docs/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) 在 *Mobile Services iOS SDK帮助*.
* **Android:**  [在Android中预取选件内容](https://experienceleague.adobe.com/docs/mobile-services/android/target-android/c-mob-target-prefetch-android.html) 在 *Mobile Services Android SDK帮助*.
