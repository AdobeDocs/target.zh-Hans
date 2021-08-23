---
keywords: 移动设备应用程序；常见问题解答；FAQ；定位移动设备应用程序
description: 查看有关Adobe [!DNL Target] 的移动设备应用程序的常见问题解答。
title: 有关 [!DNL Target] 移动设备应用程序的常见问题解答有哪些？
feature: 实施移动设备
role: Developer
exl-id: 1ddd8345-e753-4608-9293-939e092cb16d
source-git-commit: fd7d3900f9e5d1a6c3d13fd2452de8528f8fd248
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 1%

---

# Target 移动应用程序版常见问题解答

有关移动设备应用程序[!DNL Target]的常见问题解答列表。

## 我应该使用[!DNL Adobe Experience Platform Launch]来部署SDK，还是我是否可以在不使用[!DNL Launch]的情况下部署SDK?

该SDK位于[Adobe Marketing Cloud git](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)上。 如果不在Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html)中使用[标记，则必须管理自己的设置文件，并在应用程序中对其进行管理。

## 当前提供哪些SDK?

Adobe Experience Platform Mobile SDK当前支持iOS、Android和React。 有关更多信息，请参阅[Adobe Experience Cloud Platform Mobile SDK指南](https://aep-sdks.gitbook.io/docs/)。

## 根据经纬度的验证，基于位置的功能的频率是多少？

有关更多信息，请参阅[Adobe位置文档](https://placesdocs.com/places-services-by-adobe-documentation/)。

## 我是否需要at.js才能使用Adobe Experience Platform Mobile SDK?

不需要，您无需at.js即可使用Mobile SDK。 at.js是适用于网站的[!DNL Target] JavaScript库。 Adobe Experience Platform Mobile SDK适用于移动设备应用程序。

## [!DNL Target] Mobile是否仅是Adobe[!DNL Target] Premium产品SKU的功能？

否. 对于[!DNL Adobe Target Standard]客户，您只能将我们的Mobile SDK用于A/B测试和体验定位(XT)活动，并且该活动与[!DNL Target Standard]移动设备应用程序加载项一起使用。 如果要在移动设备应用程序中使用Recommendations或AI支持的功能，您需要[Adobe Target Premium](/help/c-intro/intro.md#premium)许可证。

## Adobe Experience Manager(AEM)与[!DNL Target]移动设备活动之间是否存在移动设备应用程序集成？

它在我们的路线图上，但还没有时间表。 目前，您可以将JSON [体验片段](/help/c-experiences/c-manage-content/aem-experience-fragments.md)从AEM共享到Target，然后可能会在移动设备应用程序活动中使用它们。
