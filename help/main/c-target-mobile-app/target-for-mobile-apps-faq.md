---
keywords: 移动设备应用程序；常见问题解答；FAQ；定位移动设备应用程序
description: 查看有关Adobe的常见问题及其解答 [!DNL Target] （适用于移动设备应用程序）。
title: 有关 [!DNL Target] 移动设备应用程序？
feature: Implement Mobile
role: Developer
exl-id: 1ddd8345-e753-4608-9293-939e092cb16d
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 3%

---

# Target 移动应用程序版常见问题解答

有关 [!DNL Target] （适用于移动设备应用程序）。

## 我是否应在 [!DNL Adobe Experience Platform] 来部署SDK，或者我是否可以在不使用 [!DNL Launch]?

该SDK位于 [Adobe Marketing Cloud git](https://github.com/Adobe-Marketing-Cloud/acp-sdks/). 如果您不使用 [Adobe Experience Platform中的标记](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html)，则必须在应用程序中管理自己的设置文件并对其进行管理。

## 当前提供哪些SDK?

Adobe Experience Platform Mobile SDK当前支持iOS、Android和React。 有关更多信息，请参阅 [Adobe Experience Cloud Platform Mobile SDK指南](https://aep-sdks.gitbook.io/docs/).

## 根据经纬度的验证，基于位置的功能的频率是多少？

请参阅 [Adobe位置文档](https://placesdocs.com/places-services-by-adobe-documentation/) 以了解更多信息。

## 我是否需要at.js才能使用Adobe Experience Platform Mobile SDK?

不需要，您无需at.js即可使用Mobile SDK。 at.js是 [!DNL Target] 适用于网站的JavaScript库。 Adobe Experience Platform Mobile SDK适用于移动设备应用程序。

## 是 [!DNL Target] 移动Adobe功能 [!DNL Target] 仅限高级产品SKU?

否. 对于 [!DNL Adobe Target Standard] 客户，则您只能将我们的Mobile SDK用于A/B测试和体验定位(XT)活动，该活动 [!DNL Target Standard] 移动设备应用程序加载项。 如果要在移动设备应用程序中使用Recommendations或AI支持的功能，您需要 [Adobe Target Premium](/help/main/c-intro/intro.md#premium) 许可证。

## Adobe Experience Manager(AEM)与 [!DNL Target] 移动设备活动？

它在我们的路线图上，但还没有时间表。 当前，您可以共享JSON [体验片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) 从AEM到Target，然后可能会在移动设备应用程序活动中使用它们。
