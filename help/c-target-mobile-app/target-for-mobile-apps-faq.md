---
description: 有关Adobe Target移动应用程序的常见问题解答。
keywords: 移动应用程序；常见问题解答；常见问题解答；目标移动应用程序
seo-description: 有关Adobe Target移动应用程序的常见问题解答。
seo-title: 有关Adobe Target移动应用程序的常见问题解答
title: Adobe Target移动应用程序常见问题解答
topic: Target
uuid: 3d6422ac-7cff-4e0d-9cea-64a64cd1a098
translation-type: tm+mt
source-git-commit: 43a00c7ade1f2e10a023ffdcb2e75cf2483e6907

---


# 针对移动应用程序的Target常见问题解答

移动应用程序的常见问题 [!DNL Target] 的列表。

## 我是否应使用 [!DNL Adobe Experience Platform Launch] SDK部署SDK，或者我是否可以部署SDK [!DNL Launch]？

SDK可用于 [Adobe Marketing Cloud Git](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)。如果您不使用 [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html)，则必须管理自己的设置文件并在应用程序中管理它。

## 移动应用程序的Visual Experience Composer(CMS)是否可以与Adobe Experience Platform SDK v的反应本机支持一起使用？

本机Mobile应用程序 [的CMS](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md) 当前不支持反应本机应用程序。您必须使用 [基于表单的Experience Composer](/help/c-experiences/form-experience-composer.md)。

## Mobile SDK集成是否允许推出新的移动功能？如果没有新的代码部署，能否打开和关闭功能标志？

是的，您可以使用我们的移动SDK逐步推出功能。

## 对于更复杂的逻辑，我应该直接在应用程序中开发，而不是使用Mobile CMS？如果是，应该使用哪种开发语言？

目前，CMS支持常用用例，如更改图像、文本、颜色等。对于更高级的用例(如个性化应用程序布局)，您必须在代码中插入 [!DNL Target] 请求/位置(mbox)，并使用 [基于表单的Experience Composer](/help/c-experiences/form-experience-composer.md) 设计体验和分配流量。我们的移动SDK支持Java、Objective C和Swift。这取决于您的团队首选项和资源来选择语言。

## 现在提供哪些SDK？

Adobe Experience Platform Mobile SDK目前支持iOS、Android和响应。有关更多信息，请参阅 [Adobe Experience Cloud Platform Mobile SDK指南](https://aep-sdks.gitbook.io/docs/)。

## 在关于纬度和经度的验证方面，基于位置的功能的频率是多少？

有关更多信息，请参阅 [Adobe Place文档](https://placesdocs.com/places-services-by-adobe-documentation/) 。

## 哪些本机类支持移动“视图”支持？它们支持任何NSobject派生类(或任何Android对象)或仅限NSViewController和活动？

有关详细信息，请访问Android文档 [以手动声明视图](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md#views)。

## 我是否需要在. js上使用Adobe Experience Platform Mobile SDK才能工作？

不需要，您无需在. js使用移动SDK。at. js是网站 [!DNL Target] 的JavaScript库。Adobe Experience Platform Mobile SDK适用于移动应用程序。

## Target Mobile是否仅提供Adobe Target Premium产品SKU的功能？

对于Adobe Target Standard客户，您只能将我们的Mobile SDK用于A/B测试和体验定位(XT)活动。如果要在移动应用程序中使用Recommendations或AI支持的功能，您需要一个 [Adobe Target Premium](/help/c-intro/intro.md#premium) 许可证。

## 我是否可以在用于移动应用程序的CMS中利用Adobe Audience Manager(AAM)的受众？

是的，Adobe Experience Platform Mobile SDK专为 [Audience Manager](https://docs.adobe.com/content/help/en/audience-manager/user-guide/aam-home.html)、 [Analytics](https://docs.adobe.com/content/help/en/analytics/landing/home.html)、 [Campaign](https://docs.adobe.com/content/help/en/campaign-standard/using/campaign-standard-home.html)和Target构建。Audience Manager中的受众 [!DNL Target]将与您分享。

## Adobe Experience Manager(AEM)与Target移动活动之间是否存在移动应用程序集成？

它在我们的路线图上，但还没有时间线。目前，您可以将JSON [体验片段](/help/c-experiences/c-manage-content/aem-experience-fragments.md) 从AEM共享到Target，可能有可能在移动应用程序活动中使用这些片段。

## 我是否可以使用CMS添加更多图像，或只更改现有图像？

您当前只能更改现有图像。
