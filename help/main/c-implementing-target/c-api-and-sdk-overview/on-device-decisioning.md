---
keywords: 服务器端；SDK;SDK；设备上；决策；设备上；设备上；零延迟；延迟；接近零；node.js
description: 了解如何使用设备决策来缓存 [!DNL Target] A/B和MVT活动，以便在接近零的延迟下执行内存决策。
title: 什么是设备上决策？
feature: Implement Server-side
role: Developer
exl-id: ae782511-6f32-4123-be76-838584e05b39
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 10%

---

# 设备上决策

设备内决策提供了缓存 [!DNL Adobe Target] [!UICONTROL A/B测试] 和 [!UICONTROL 体验定位] (XT)活动，并在接近零的延迟下执行内存中决策，而不会阻止向 [!DNL Adobe Target] 边缘网络。

有关更多信息，请参阅 [设备上决策简介](https://adobetarget-sdks.gitbook.io/docs/on-device-decisioning/introduction-to-on-device-decisioning) 在 *[Adobe Target SDK文档](https://adobetarget-sdks.gitbook.io/docs/)*.

## 网络研讨会：通过 [!DNL Adobe Target] 的设备上决策进行无延迟的个性化和测试

相比以往，营销人员、产品所有者和开发人员需要更多地在网站上、应用程序中以及他们与客户联系的其他各个环节优化整体客户体验。多种工具（具有数据孤岛和复杂的实施）并不充分。

在这次录制的网络研讨会中， [!DNL Adobe Target] 产品专家讨论了如何在设备上将关键体验优化决策移动到本地执行，并且延迟接近零，从而为激动人心的新用例打开了大门，同时为您的客户改善了站点性能。

>[!VIDEO](https://video.tv.adobe.com/v/328148)

## 最佳实践

Adobe建议在使用设备上决策时遵循以下最佳实践：

### 决策方法为“设备上”时的最佳实践 {#best-practices-on-device}

当使用“设备内”作为决策方法时，将在访客首次加载网页时下载项目。 只有在完全下载对象后，才会进行首次页面加载（无缓存）时需要进行的任何活动鉴别。 您可以遵循某些最佳实践，以确保新匿名访客能够快速获得活动资格。

* 停用不会出现在对象中、支持“设备上”的活动。
* 如果 [!DNL Target Premium]，您可以使用 [属性/工作区](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) 为不同的工作区创建不同的工件文件。
* 如果您的项目文件由于合法原因变得非常大，则可以使用“混合”决策方法。 此方法允许您并行下载项目以及所有 [!DNL Target] API调用会一直通过电话线直到下载对象为止。 阅读最佳内容 [&quot;混合&quot;决策模式实践部分](#best-practices-hybrid) 下方将详细了解此方法。
* 如果您有单页应用程序(SPA), [!DNL Adobe] 建议您在首次页面加载期间先加载并初始化at.js，然后再加载应用程序的主JavaScript文件。 此方法会更早地启动项目下载，从而提供更快的渲染体验。

### 决策方法为“混合”时的最佳实践 {#best-practices-hybrid}

使用“混合”作为决策方法时，将并行下载伪像。 在下载藏物之前， [!DNL Target] 即使“位置”在设备上可用，API调用仍会通过电汇。 此行为是所有 `getOffers()` 在大多数情况下，会调用并提供最佳性能。 如果更改 `getOffers()` 设置 `decisioningMethod` to `on-device`，请按照这些最佳实践来避免错误并确保最佳性能。

* 如果你决定打电话 `getOffers()` with `decisioningMethod` as `on-device` 当页面首次加载时，必须在at.js事件处理程序中“ARTIFACT_DOWNLOAD_SUCCEEDED”执行该操作，以避免出现错误。 如果您的项目很大，则使用此方法的任何“位置”仅在项目完全下载后才会渲染，这可能会延迟体验渲染。 [!DNL Adobe] 建议您很少使用此方法。 按照最佳实践，在 [“在设备上”最佳实践部分](#best-practices-on-device) 上，使用此方法时。

## 教程：设备内决策

[!DNL Adobe Target] 设备内决策支持近乎零的延迟内容交付。

此7分钟视频：

* 介绍设备上决策，包括与其他方法相比较的情况 [!DNL Target] 实施
* 演示如何在 [!DNL Target]
* 检查已配置JSON内容的基于表单的编辑器活动示例
* 显示示例Node.JS SDK代码，其中包含设备决策所需的密钥配置
* 在浏览器中演示结果

>[!VIDEO](https://video.tv.adobe.com/v/329032)

有关更多视频和教程，请参阅 [Adobe TargetTutorials](https://experienceleague.adobe.com/docs/target-learn/tutorials/overview.html?lang=zh-Hans) 的双曲余切值。

## Adobe技术博客 — 第1部分：运行 [!DNL Adobe Target] 用于在边缘平台上进行实验和进行个性化的NodeJS SDK（Akamai边缘工作程序）

[单击此处访问博客帖子](https://medium.com/adobetech/part-1-run-adobe-target-nodejs-sdk-for-experimentation-and-personalization-on-edge-platforms-4d8660964ed9).

## Adobe Tech Blog - 第 2 部分：在 Edge 平台上运行 [!DNL Adobe Target] NodeJS SDK 以提供试验性和个性化 (AWS Lambda@Edge)

[单击此处访问博客帖子](https://medium.com/adobetech/part-2-run-adobe-target-nodejs-sdk-for-experimentation-and-personalization-on-edge-platforms-aws-4d6bdac24563).