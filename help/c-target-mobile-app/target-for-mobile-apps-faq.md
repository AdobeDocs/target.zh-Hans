---
description: 关于Adobe Target移动应用程序的常见问题解答。
keywords: 移动应用；常见问题解答；常见问题解答；目标移动应用
seo-description: 关于Adobe Target移动应用程序的常见问题解答。
seo-title: 关于Adobe Target移动应用程序的常见问题解答
title: Adobe Target移动应用程序常见问题解答
topic: Target
uuid: 3d6422ac-7cff-4e0d-9cea-64a64cd1a098
translation-type: tm+mt
source-git-commit: 43a00c7ade1f2e10a023ffdcb2e75cf2483e6907

---


# Target for mobile apps FAQ

有关移动应用程序的常见 [!DNL Target] 问题列表。

## 我应该使 [!DNL Adobe Experience Platform Launch] 用来部署SDK，还是可以在不使用的情况下部署SDK [!DNL Launch]?

SDK可在 [Adobe Marketing Cloud Git上找到](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)。 如果您不使用 [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html)，则必须管理您自己的设置文件并在应用程序中管理它。

## 是否可以将适用于移动应用程序的可视体验书写器(VEC)与Adobe Experience Platform SDK v5的React-Native支持一起使用？

用 [于本机移动应用程序的VEC](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md) 当前不支持React本机应用程序。 必须使用基 [于表单的体验书写器](/help/c-experiences/form-experience-composer.md)。

## Mobile SDK集成是否允许推出新的移动功能？ 如果没有新的代码部署，能否打开和关闭功能标记？

Yes, you can use our mobile SDK to roll out features gradually.

## 对于更复杂的逻辑，我应该直接在应用程序中开发而不是使用Mobile VEC吗？ 如果是，我应使用哪种开发语言？

目前，VEC支持更改图像、文本、颜色等常见用例。 对于更高级的用例（如个性化应用程序布局），您必须在代码中插入请求／位置(mbox)，然后使用基于 [!DNL Target][](/help/c-experiences/form-experience-composer.md) Form的体验书写器来设计体验和分配流量。 我们的移动SDK支持Java、Objective c和Swift。 选择语言取决于团队的偏好和资源。

## 目前提供哪些SDK?

Adobe Experience Platform Mobile SDK目前支持iOS、Android和React。 有关详细信息，请参 [阅Adobe Experience Cloud Platform Mobile SDK指南](https://aep-sdks.gitbook.io/docs/)。

## 从纬度和经度的验证角度看，基于位置的功能的频率是多少？

有关详细 [信息，请参阅Adobe Places文档](https://placesdocs.com/places-services-by-adobe-documentation/) 。

## 移动“视图”支持哪些本机类？ Do they support any NSObject derived class (or any Android Object) or just NSViewController and Activities?

For more information, visit the Android documentation for the manual way of declaring views.[](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md#views)

## Do I need at.js for the Adobe Experience Platform Mobile SDKs to work?

不，您无需at.js即可使用移动SDK。 at.js是网站的 [!DNL Target] JavaScript库。 The Adobe Experience Platform Mobile SDKs are for mobile apps.

## Is Target Mobile a functionality of Adobe Target Premium Product SKU only?

For Adobe Target Standard customers, you can use our Mobile SDKs for A/B Test and Experience Targeting (XT) activities only. If you want to use Recommendations or AI-powered features in the mobile app, you need an Adobe Target Premium license.[](/help/c-intro/intro.md#premium)

## Can I leverage audiences from Adobe Audience Manager (AAM) in the VEC for Mobile Apps?

Yes, Adobe Experience Platform Mobile SDKs are built for Audience Manager, Analytics, Campaign, and Target. [](https://docs.adobe.com/content/help/en/audience-manager/user-guide/aam-home.html)[](https://docs.adobe.com/content/help/en/analytics/landing/home.html)[](https://docs.adobe.com/content/help/en/campaign-standard/using/campaign-standard-home.html)Your audiences in Audience Manager are shared with .[!DNL Target]

## Is there a mobile app integration between Adobe Experience Manager (AEM) and Target mobile activities?

It is on our roadmap but there is no timeline yet. Currently, you can share JSON Experience Fragments from AEM to Target and there might be potential to then use them in a mobile app activity.[](/help/c-experiences/c-manage-content/aem-experience-fragments.md)

## Can I add more images using the VEC or only change existing images?

当前只能更改现有图像。
