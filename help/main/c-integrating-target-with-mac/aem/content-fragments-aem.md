---
keywords: 体验;json;AEM;Adobe Experience Manager;导出到 Adobe Target;内容片段;片段;CF;cf;headless;个性化;试验
description: 了解如何在 [!DNL Adobe Experience Manager] [!UICONTROL Content Fragments]活动中使用 [!DNL Adobe Target] 。
title: 如何使用 [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Content Fragments]？
feature: Integrations
exl-id: 2057d9fe-c0f9-41d5-82e1-529db9ef7ca5
source-git-commit: b29614680b27c9c33f11eed85d8ab4feebc28b0d
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 15%

---

# AEM [!UICONTROL Content Fragments]

在[!UICONTROL Content Fragments]活动中使用在[!DNL Adobe Experience Manager] (AEM)中创建的[!DNL Target] (CF)来辅助Headless个性化和实验。

## 注意事项

在[!UICONTROL Content Fragments]中使用AEM [!DNL Target]时，请考虑以下事项：

* 此功能要求您是 [!DNL Adobe Experience Manager as a Cloud Service] 客户。有关更多信息，请见以下[要求](#section_AE6F0971E1574B3AA324003599B96E5A)。
* [!UICONTROL Experience Fragments]和[!UICONTROL Content Fragments]可用于以下活动类型：

   * [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Experience Targeting] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL Experience Fragments]和[!UICONTROL Content Fragments]不适用于以下活动类型：

   * [[!UICONTROL Multivariate Test] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* 您只能使用基于[!UICONTROL Content Fragments]表单的体验编辑器[!DNL Target]，在[活动中使用](/help/main/c-experiences/form-experience-composer.md)。 您&#x200B;*不能*&#x200B;在使用[!UICONTROL Content Fragments] (VEC)的[!DNL Target]活动中使用[!UICONTROL Visual Experience Composer]。

要了解有关AEM [!UICONTROL Content Fragments]和[!UICONTROL Experience Fragments]的更多信息，请参阅[AEM [!UICONTROL Experience Fragments]和[!UICONTROL Content Fragments]概述](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md)。

## 要求 {#requirements}

您必须使用[[!DNL AEM] as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html){target=_blank}。 您的客户代表可帮助确保您满足使用此功能的要求：

请联系 [Adobe Target 客户关怀](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)以启用集成并为您提供身份验证详细信息。

## 在[!UICONTROL Content Fragments]中配置和使用[!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

要导出[!UICONTROL Content Fragments]以在[!DNL Target]活动中使用，您必须在AEM中执行一些初步步骤。 有关详细信息，请参阅[Adobe Target as a Cloud Service文档](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/content-fragments-target.html){target=_blank}中的&#x200B;*将内容片段导出到Experience Manager*。

有关设计、创建、策划和发布[!UICONTROL Content Fragments]的信息，请参阅[[!UICONTROL Content Fragments]Experience Manager as a Cloud Service文档](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/content-fragments.html?lang=zh-Hans){target=_blank}中的[](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments.html){target=_blank}和[使用内容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html){target=_blank}。

## 在[!UICONTROL Content Fragments]活动中使用[!DNL Target] {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

执行上述任务后，[!UICONTROL Content Fragment]将显示在[!UICONTROL Offers]的[!DNL Target]页面上。

[!DNL Target]当前查找[!UICONTROL Content Fragments]以每十分钟导入一次。 导入的[!UICONTROL Content Fragment]应在10分钟内在[!DNL Target]内可用，但以后，此时间应会缩短。

[!UICONTROL Content Fragment]作为JSON选件导入到[!DNL Target]中。 [!UICONTROL Content Fragment]“主要”版本保留在[!DNL AEM]中。 您无法在[!UICONTROL Content Fragment]中编辑[!DNL Target]。

您可以按[!UICONTROL HTML XFs]、[!UICONTROL JSON XFs]和[!UICONTROL Content Fragments]筛选和搜索，以帮助您区分导出到[!DNL Target]的不同优惠类型。

![按内容片段类型筛选：Target UI 中的 HTML 或 JSON](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

您可以将鼠标悬停在列表中的[!UICONTROL Experience Fragment]上，然后单击[!UICONTROL View]图标![信息图标](/help/main/assets/icons/InfoOutline.svg)以查看有关[!UICONTROL Content Fragment]的其他信息，包括其[!UICONTROL Name]、[!UICONTROL Type]、[!UICONTROL Offer ID]、[!UICONTROL Offer path]以及上次修改信息。 单击[!UICONTROL [!UICONTROL View Full Details]]可查看引用此选件的活动。

您只能使用基于[!UICONTROL Content Fragments]表单的体验编辑器[!DNL Target]，在[活动中使用](/help/main/c-experiences/form-experience-composer.md)。 您&#x200B;*不能*&#x200B;在使用[!UICONTROL Content Fragments]可视化体验编辑器[!DNL Target] (VEC)的[活动中使用](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md)。 [!UICONTROL Content Fragments]在[!DNL Target]中导出为JSON，无法在使用VEC创建的活动中使用。

>[!TIP]
>
>将人工智能、机器学习和推荐与[!UICONTROL Content Fragments]结合使用：
>
>* 要充分利用[!DNL Target] AI和ML功能，您可以在创建[活动时选择](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)自动分配[或](/help/main/c-activities/auto-target/auto-target-to-optimize.md)自动定位[!UICONTROL A/B Test]。
>
>* [!UICONTROL Content Fragments]活动中不支持[!DNL Recommendations]。 但是，要将[!UICONTROL Content Fragments]用于推荐，您可以创建[!UICONTROL A/B Test]活动（包括[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]）或[!UICONTROL Experience Targeting] (XT)活动以及[将推荐作为选件](/help/main/c-recommendations/recommendations-as-an-offer.md)。

**使用[!UICONTROL Content Fragments]使用[!UICONTROL Form-based Experience Composer]：**

1. 在[!DNL Target]中，在[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)中创建或编辑体验时，在页面上选择要插入[!DNL AEM]内容的位置，然后选择&#x200B;**[!UICONTROL Change Content Fragment]**&#x200B;以显示[!UICONTROL Choose a Content Fragment]列表。

   ![内容片段列表图像](/help/main/c-integrating-target-with-mac/aem/assets/choose-content-fragment.png)

   [!UICONTROL Content Fragment]列表显示在[!DNL AEM]中创建的内容，该内容现在可从[!DNL Target]中以本地方式使用。

1. 选择所需的[!UICONTROL Content Fragment]，然后单击&#x200B;**[!UICONTROL Save]**。
1. 配置完活动。

## 其他信息

* [!DNL Target]当前查找[!UICONTROL Content Fragments]以每十分钟导入一次。 导入的[!UICONTROL Content Fragment]应在10分钟内在[!DNL Target]内可用，但以后，此时间应会缩短。
* [!UICONTROL Content Fragment]作为JSON选件导入到[!DNL Target]中。 [!UICONTROL Content Fragment]“主要”版本保留在[!DNL AEM]中。 您无法在[!UICONTROL Content Fragment]中编辑[!DNL Target]。
* 无法使用[!UICONTROL Content Fragments]创建[!DNL Adobe I/O]。 使用AEM创建[!UICONTROL Content Fragments]，如上所述。
* 如果您在AEM中更新[!UICONTROL Content Fragment]，则必须再次发布[!UICONTROL Content Fragment]并将其导出到[!DNL Target]，以便[!DNL Target]可以使用最新更改。
