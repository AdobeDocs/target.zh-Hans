---
keywords: 移动应用程序；常见问题解答；常见问题；目标移动应用程序
description: 关于Adobe Target移动应用程序的常见问题。
title: 关于移动应用程序目标的常见问题
feature: Implement Mobile
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 0%

---


# 目标移动应用程序常见问题解答

列表有关移动应用程序[!DNL Target]的常见问题。

## 我应使用[!DNL Adobe Experience Platform Launch]部署SDK，还是可以在不使用[!DNL Launch]的情况下部署SDK?

SDK可在[Adobe Marketing Cloudgit](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)上找到。 如果不使用[Launch](https://experienceleague.adobe.com/docs/launch/using/overview.html)，则必须管理您自己的设置文件并在应用程序中管理它。

## 目前提供哪些SDK?

Adobe Experience Platform移动SDK目前支持iOS、Android和React。 有关详细信息，请参阅[Adobe Experience Cloud平台移动SDK指南](https://aep-sdks.gitbook.io/docs/)。

## 根据经纬度的验证，基于位置的功能的频率是多少？

有关详细信息，请参阅[Adobe位置文档](https://placesdocs.com/places-services-by-adobe-documentation/)。

## 我是否需要at.js才能使Adobe Experience Platform移动SDK正常工作？

不，您无需at.js即可使用移动SDK。 at.js是网站的[!DNL Target] JavaScript库。 Adobe Experience Platform移动SDK适用于移动应用程序。

## 目标移动是否只是Adobe Target高级产品SKU的功能？

否. 对于[!DNL Adobe Target Standard]客户，您只能将我们的Mobile SDK用于A/B测试和体验定位(XT)活动，与[!DNL Target Standard]移动应用程序加载项一起使用。 如果要在移动应用程序中使用Recommendations或人工智能支持的功能，您需要[Adobe Target高级版](/help/c-intro/intro.md#premium)许可证。

## Adobe Experience Manager(AEM)和目标移动活动之间是否有移动App集成？

它在我们的路线图上，但还没有时间表。 目前，您可以将JSON [体验片段](/help/c-experiences/c-manage-content/aem-experience-fragments.md)从AEM共享到目标，然后可能会在移动应用程序活动中使用它们。
