---
keywords: mobile app;frequently asked questions;faq;target mobile app
description: 关于Adobe Target移动应用程序的常见问题解答。
title: 关于Adobe Target移动应用程序的常见问题解答
topic: Target
uuid: 3d6422ac-7cff-4e0d-9cea-64a64cd1a098
translation-type: tm+mt
source-git-commit: 4ce4cf754ec64ec54c72bcb0557f042a92f5a8e3

---


# 针对移动应用程序的Target常见问题解答

有关移动应用程序的常见 [!DNL Target] 问题列表。

## 我应该使 [!DNL Adobe Experience Platform Launch] 用来部署SDK，还是可以在不使用的情况下部署SDK [!DNL Launch]?

SDK可在 [Adobe Marketing Cloud Git上找到](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)。 如果您不使用 [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html)，则必须管理您自己的设置文件并在应用程序中管理它。

## 目前提供哪些SDK?

Adobe Experience Platform Mobile SDK目前支持iOS、Android和React。 有关详细信息，请参 [阅Adobe Experience Cloud Platform Mobile SDK指南](https://aep-sdks.gitbook.io/docs/)。

## 从纬度和经度的验证角度看，基于位置的功能的频率是多少？

有关详细 [信息，请参阅Adobe Places文档](https://placesdocs.com/places-services-by-adobe-documentation/) 。

## 我是否需要at.js才能使Adobe Experience Platform Mobile SDK正常工作？

不，您无需at.js即可使用移动SDK。 at.js是网站的 [!DNL Target] JavaScript库。 Adobe Experience Platform Mobile SDK适用于移动应用程序。

## Target Mobile是否仅是Adobe Target Premium产品SKU的功能？

对于Adobe Target Standard客户，您只能将我们的Mobile SDK用于A/B测试和体验定位(XT)活动。 如果要在移动应用程序中使用Recommendations或AI支持的功能，则需要 [Adobe Target Premium](/help/c-intro/intro.md#premium) 许可证。

## 我是否可以在VEC for Mobile Apps中利用Adobe Audience Manager(AAM)的受众？

是的，Adobe Experience Platform Mobile SDK是为 [Audience Manager](https://docs.adobe.com/content/help/en/audience-manager/user-guide/aam-home.html)、 [Analytics](https://docs.adobe.com/content/help/en/analytics/landing/home.html)、 [Campaign](https://docs.adobe.com/content/help/en/campaign-standard/using/campaign-standard-home.html)和Target构建的。 Audience manager中的受众将与共享 [!DNL Target]。

## Adobe Experience Manager(AEM)与Target移动活动之间是否存在移动应用程序集成？

这是在我们的路线图上，但还没有时间表。 目前，您可以将JSON [体验片段从AEM共享到Target](/help/c-experiences/c-manage-content/aem-experience-fragments.md) ，然后可能会在移动应用程序活动中使用这些片段。

## 我是否可以使用VEC添加更多图像，或仅更改现有图像？

当前只能更改现有图像。
