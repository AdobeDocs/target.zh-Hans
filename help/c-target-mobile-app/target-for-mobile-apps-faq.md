---
keywords: 移动应用程序；常见问题解答；目标移动应用程序
description: 视图关于移动应用程序的Adobe [!DNL Target] 的常见问题解答。
title: 关于 [!DNL Target] 移动应用程序的常见问题有哪些？
feature: 实施移动
role: Developer
exl-id: 1ddd8345-e753-4608-9293-939e092cb16d
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 0%

---

# 目标移动应用程序常见问题解答

列表有关移动应用程序[!DNL Target]的常见问题。

## 我应使用[!DNL Adobe Experience Platform Launch]部署SDK，还是可以在不使用[!DNL Launch]的情况下部署SDK?

SDK位于[Adobe Marketing Cloud git](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)中。 如果您不使用[Launch](https://experienceleague.adobe.com/docs/launch/using/overview.html)，则必须管理您自己的设置文件并在应用程序中管理它。

## 目前提供哪些SDK?

Adobe Experience Platform Mobile SDK目前支持iOS、Android和React。 有关详细信息，请参阅[Adobe Experience Cloud Platform Mobile SDK指南](https://aep-sdks.gitbook.io/docs/)。

## 从经纬度的验证来看，基于位置的功能的频率是多少？

有关详细信息，请参阅[Adobe位置文档](https://placesdocs.com/places-services-by-adobe-documentation/)。

## 我是否需要at.js才能使Adobe Experience Platform Mobile SDK正常工作？

不，您无需at.js即可使用移动SDK。 at.js是用于网站的[!DNL Target] JavaScript库。 Adobe Experience Platform Mobile SDK适用于移动应用程序。

## [!DNL Target]移动是否仅是Adobe [!DNL Target]高级产品SKU的功能？

否. 对于[!DNL Adobe Target Standard]客户，您只能将我们的Mobile SDK用于A/B测试和体验定位(XT)活动，与[!DNL Target Standard]移动应用程序加载项一起使用。 如果要在移动应用程序中使用Recommendations或人工智能支持的功能，您需要[Adobe Target Premium](/help/c-intro/intro.md#premium)许可证。

## Adobe Experience Manager(AEM)和[!DNL Target]移动活动之间是否存在移动应用程序集成？

它在我们的路线图上，但还没有时间表。 目前，您可以将JSON [体验片段](/help/c-experiences/c-manage-content/aem-experience-fragments.md)从AEM共享到目标，然后可能会在移动应用程序活动中使用它们。
