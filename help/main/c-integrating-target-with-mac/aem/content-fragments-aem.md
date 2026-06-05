---
keywords: 体验;json;AEM;Adobe Experience Manager;导出到 Adobe Target;内容片段;片段;CF;cf;headless;个性化;试验
description: 了解如何在 [!DNL Adobe Target] 活动中使用 [!DNL Adobe Experience Manager] [!UICONTROL 内容片段]。
title: 如何使用 [!DNL Adobe Experience Manager] (AEM) [!UICONTROL 内容片段]？
feature: Integrations
exl-id: 2057d9fe-c0f9-41d5-82e1-529db9ef7ca5
TQID: https://experienceleague.adobe.com/tb500kFSZoR3czs10Gs3EIOWEX2ybnd7tSWwDmWSMWQ
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: f7c7de77-382f-4f48-8b36-61a170f06d3d
topic_v2: id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8cid: bcc5edb5-84c3-4940-9f84-ed88b6c16274id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: e0eb8757-182f-49f3-94a4-1587d16f5094id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 775
ht-degree: 20%

---

# AEM [!UICONTROL 内容片段]

在[!DNL Target]活动中使用在[!DNL Adobe Experience Manager] (AEM)中创建的[!UICONTROL 内容片段] (CF)来辅助Headless个性化和实验。

## 注意事项

在[!DNL Target]中使用AEM [!UICONTROL 内容片段]时，请考虑以下事项：

* 此功能要求您是 [!DNL Adobe Experience Manager as a Cloud Service] 客户。 有关更多信息，请见以下[要求](#section_AE6F0971E1574B3AA324003599B96E5A)。
* [!UICONTROL 体验片段]和[!UICONTROL 内容片段]可用于以下活动类型：

   * [[!UICONTROL A/B 测试]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL 自动分配]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Auto-Target（自动定位）]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL 体验定位] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL 体验片段]和[!UICONTROL 内容片段]不适用于以下活动类型：

   * [[!UICONTROL 多变量测试] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL 推荐]](/help/main/c-recommendations/recommendations.md)

* 您只能使用基于[表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)在[!DNL Target]活动中使用[!UICONTROL 内容片段]。 您&#x200B;*不能*&#x200B;在使用[!UICONTROL 可视化体验编辑器] (VEC)的[!DNL Target]活动中使用[!UICONTROL 内容片段]。

要了解有关AEM [!UICONTROL 内容片段]和[!UICONTROL 体验片段]的更多信息，请参阅[AEM [!UICONTROL 体验片段]和[!UICONTROL 内容片段]概述](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md)。

## 要求 {#requirements}

您必须使用[[!DNL AEM] as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html){target=_blank}。 您的客户代表可帮助确保您满足使用此功能的要求：

请联系 [Adobe Target 客户关怀](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)以启用集成并为您提供身份验证详细信息。

## 在[!DNL AEM]中配置和使用[!UICONTROL 内容片段] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

要导出[!UICONTROL 内容片段]以在[!DNL Target]活动中使用，您必须在AEM中执行一些初步步骤。 有关详细信息，请参阅&#x200B;*Adobe Target as a Cloud Service文档*&#x200B;中的[将内容片段导出到Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/content-fragments-target.html){target=_blank}。

有关设计、创建、管理和发布[!UICONTROL 内容片段]的信息，请参阅[Experience Manager as a Cloud Service文档](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html){target=_blank}中的[[!UICONTROL 内容片段]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/content-fragments.html?lang=zh-Hans){target=_blank}和[使用内容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments.html){target=_blank}。

## 在[!DNL Target]活动中使用[!UICONTROL 内容片段] {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

执行上述任务后，[!UICONTROL 内容片段]显示在[!DNL Target]的[!UICONTROL 选件]页面中。

[!DNL Target]当前查找[!UICONTROL 内容片段]以每10分钟导入一次。 导入的[!UICONTROL 内容片段]应在10分钟内[!DNL Target]内可用，但以后，此时间应会缩短。

[!UICONTROL 内容片段]作为JSON选件导入到[!DNL Target]中。 [!UICONTROL 内容片段]“主要”版本保留在[!DNL AEM]中。 您无法在[!DNL Target]中编辑[!UICONTROL 内容片段]。

您可以按[!UICONTROL HTML XF]、[!UICONTROL JSON XF]和[!UICONTROL 内容片段]进行筛选和搜索，以帮助您区分导出到[!DNL Target]的各种选件类型。

![按内容片段类型筛选：Target UI 中的 HTML 或 JSON](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

您可以将鼠标悬停在列表中的[!UICONTROL 体验片段]上，然后单击[!UICONTROL 查看]图标![信息图标](/help/main/assets/icons/InfoOutline.svg)以查看有关[!UICONTROL 内容片段]的其他信息，包括其[!UICONTROL 名称]、[!UICONTROL 类型]、[!UICONTROL 选件ID]、[!UICONTROL 选件路径]和上次修改信息。 单击[!UICONTROL [!UICONTROL 查看完整详细信息]]可查看引用此选件的活动。

您只能使用基于[表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)在[!DNL Target]活动中使用[!UICONTROL 内容片段]。 您&#x200B;*不能*&#x200B;在使用[可视化体验编辑器](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC)的[!DNL Target]活动中使用[!UICONTROL 内容片段]。 [!UICONTROL 内容片段]在[!DNL Target]中导出为JSON，无法在使用VEC创建的活动中使用。

>[!TIP]
>
>对[!UICONTROL 内容片段]使用人工智能、机器学习和推荐：
>
>* 要充分利用[!DNL Target]人工智能和ML功能，您可以在创建[!UICONTROL A/B测试]活动时选择[自动分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)或[自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md)。
>
>* [!UICONTROL 内容片段]在[!DNL Recommendations]活动中不受支持。 但是，要将[!UICONTROL 内容片段]用于推荐，您可以创建[!UICONTROL A/B测试]活动（包括[!UICONTROL 自动分配]和[!UICONTROL 自动定位]）或[!UICONTROL 体验定位] (XT)活动，以及[将推荐作为选件](/help/main/c-recommendations/recommendations-as-an-offer.md)。

**要使用基于[!UICONTROL 表单的体验编辑器]的[!UICONTROL 内容片段]：**

1. 在[!DNL Target]中，在[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)中创建或编辑体验时，在页面上选择要插入[!DNL AEM]内容的位置，然后选择&#x200B;**[!UICONTROL 更改内容片段]**&#x200B;以显示[!UICONTROL 选择内容片段]列表。

   ![内容片段列表图像](/help/main/c-integrating-target-with-mac/aem/assets/choose-content-fragment.png)

   [!UICONTROL 内容片段]列表显示在[!DNL AEM]中创建的内容，该内容现在可从[!DNL Target]中以本地方式使用。

1. 选择所需的[!UICONTROL 内容片段]，然后单击&#x200B;**[!UICONTROL 保存]**。
1. 配置完活动。

## 其他信息

* [!DNL Target]当前查找[!UICONTROL 内容片段]以每10分钟导入一次。 导入的[!UICONTROL 内容片段]应在10分钟内[!DNL Target]内可用，但以后，此时间应会缩短。
* [!UICONTROL 内容片段]作为JSON选件导入到[!DNL Target]中。 [!UICONTROL 内容片段]“主要”版本保留在[!DNL AEM]中。 您无法在[!DNL Target]中编辑[!UICONTROL 内容片段]。
* 无法使用[!DNL Adobe I/O]创建[!UICONTROL 内容片段]。 使用AEM创建[!UICONTROL 内容片段]，如上所述。
* 如果您在AEM中更新[!UICONTROL 内容片段]，则必须发布[!UICONTROL 内容片段]并再次将其导出到[!DNL Target]，以便[!DNL Target]可以使用最新更改。
