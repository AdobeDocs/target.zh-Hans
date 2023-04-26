---
keywords: 体验;json;AEM;Adobe Experience Manager;导出到 Adobe Target;内容片段;片段;CF;cf;Headless;个性化;试验
description: 了解如何在 [!DNL Adobe Target] 活动中使用 [!DNL Adobe Experience Manager] [!UICONTROL 内容片段]。
title: 如何使用 [!DNL Adobe Experience Manager] (AEM) [!UICONTROL 内容片段]？
feature: Integrations
exl-id: 2057d9fe-c0f9-41d5-82e1-529db9ef7ca5
source-git-commit: fe9811185328754ef983bdd5db3a4cd7fad772f6
workflow-type: ht
source-wordcount: '748'
ht-degree: 100%

---

# AEM [!UICONTROL 内容片段]

在 [!DNL Target] 活动中使用在 [!DNL Adobe Experience Manager] (AEM) 中创建的[!UICONTROL 内容片段] (CF) 帮助进行 Headless 个性化或试验。

## 注意事项

在 [!DNL Target] 中使用 AEM [!UICONTROL 内容片段]时，请考虑以下内容：

* 此功能要求您是 [!DNL Adobe Experience Manager as a Cloud Service] 客户。有关更多信息，请见以下[要求](#section_AE6F0971E1574B3AA324003599B96E5A)。
* [!UICONTROL 体验片段]和[!UICONTROL 内容片段]可用于以下活动类型：

   * [[!UICONTROL A/B 测试]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL 自动分配]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL 自动定位]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL 体验定位] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL 体验片段]和[!UICONTROL 内容片段]不可用于以下活动类型：

   * [[!UICONTROL 多变量测试] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* 您只能通过[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)在 [!DNL Target] 活动中使用[!UICONTROL 内容片段]。 您&#x200B;*无法*&#x200B;通过[!UICONTROL 视觉体验编辑器] (VEC) 在 [!DNL Target] 活动中使用[!UICONTROL 内容片段]。

要详细了解 AEM [!UICONTROL 内容片段]和[!UICONTROL 体验片段]，请参阅 [AEM [!UICONTROL 体验片段]和[!UICONTROL 内容片段]概述](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md)。

## 要求 {#requirements}

必须在 [!DNL Target] 中为您配置[!UICONTROL 内容片段]功能。此外，还必须使用 [[!DNL AEM] as a Cloud Service](https://experienceleague.corp.adobe.com/docs/experience-manager-cloud-service.html){target=_blank}。您的客户代表可帮助确保您满足使用此功能的要求：

请联系 [Adobe Target 客户关怀](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)以启用集成并为您提供身份验证详细信息。

## 在 [!DNL AEM] 中配置和使用[!UICONTROL 内容片段] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

要导出[!UICONTROL 内容片段]以在 [!DNL Target] 活动中使用，您必须在 AEM 中执行一些预备步骤。有关更多信息，请参阅 *Experience Manager as a Cloud Service 文档*&#x200B;中的[将内容片段导出到 Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/content-fragments-target.html){target=_blank} 部分。

有关设计、创建、策划和发布[!UICONTROL 内容片段]的信息，请参阅[[!UICONTROL 内容片段]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/content-fragments.html?lang=zh-Hans){target=_blank} and [Working with Content Fragments](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments.html){target=_blank} in the [Experience Manager as a Cloud Service documentation](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html){target=_blank}。

## 在 [!DNL Target] 活动中使用 [!UICONTROL 内容片段] {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

执行上述任务后，将在 [!DNL Target] 中的[!UICONTROL 选件]页面上显示[!UICONTROL 内容片段]。

[!DNL Target] 当前每 10 分钟查找一次要导入的[!UICONTROL 内容片段]。应在十分钟内可在 [!DNL Target] 中找到导入的[!UICONTROL 内容片段]，但此时间范围以后应可缩短。

[!UICONTROL 内容片段]作为 JSON 选件导入到 [!DNL Target] 中。该[!UICONTROL 内容片段]的“主要”版本保留在 [!DNL AEM] 中。您无法在 [!DNL Target] 中编辑[!UICONTROL 内容片段]。

您可以按 [!UICONTROL HTML XF]、[!UICONTROL JSON XF] 和[!UICONTROL 内容片段]进行筛选和搜索，以帮助您区分导出到 [!DNL Target] 的不同选件类型。

![按内容片段类型筛选：Target UI 中的 HTML 或 JSON](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

可将光标悬停在列表中的某个[!UICONTROL 内容片段]上，然后单击[!UICONTROL 查看]图标 ![信息图标](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png) 以查看关于该[!UICONTROL 内容片段]的其他信息，包括其 [!UICONTROL AEM 路径]和 [!UICONTROL AEM 深度链接]。单击[!UICONTROL 选件使用情况]选项卡以查看引用此选件的活动。

![内容片段信息弹出窗口](/help/main/c-integrating-target-with-mac/aem/assets/cf-info-popup.png)

您只能通过[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)在 [!DNL Target] 活动中使用[!UICONTROL 内容片段]。您&#x200B;*无法*&#x200B;通过[视觉体验编辑器](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) 在 [!DNL Target] 活动中使用[!UICONTROL 内容片段]。[!UICONTROL 内容片段]在 [!DNL Target] 中导出为 JSON，无法在使用 VEC 创建的活动中使用它们。

>[!TIP]
>
>使用人工智能、机器学习和推荐配合[!UICONTROL 内容片段]：
>
>* 要充分利用 [!DNL Target] AI 和 ML 功能，您可以在创建[!UICONTROL  A/B 测试]时选择[自动分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)或[自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md)。
>
>* [!DNL Recommendations] 活动中不支持[!UICONTROL 内容片段]。但是，要使用[!UICONTROL 内容片段]进行推荐，您可以创建[!UICONTROL  A/B 测试]活动（包括[!UICONTROL 自动分配]和[!UICONTROL 自动定位]）或[!UICONTROL 体验定位] (XT) 活动，并[包括推荐作为选件](/help/main/c-recommendations/recommendations-as-an-offer.md)。


**通过[!UICONTROL 基于表单的体验编辑器]使用[!UICONTROL 内容片段]：**

1. 在 [!DNL Target] 的[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)中创建或编辑体验时，选择要在页面上插入 [!DNL AEM] 内容的位置，然后选择&#x200B;**[!UICONTROL 更改内容片段]**&#x200B;以显示[!UICONTROL 选择内容片段]列表。

   ![内容片段列表图像](/help/main/c-integrating-target-with-mac/aem/assets/choose-content-fragment.png)

   [!UICONTROL 内容片段]列表显示在现在从 [!DNL AEM] 中原生提供的 [!DNL Target] 中创建的内容。

1. 选择所需的[!UICONTROL 内容片段]，然后单击&#x200B;**[!UICONTROL 保存]**。
1. 配置完活动。

## 其他信息

* [!DNL Target] 当前每 10 分钟查找一次要导入的[!UICONTROL 内容片段]。应在十分钟内可在 [!DNL Target] 中找到导入的[!UICONTROL 内容片段]，但此时间范围以后应可缩短。
* [!UICONTROL 内容片段]作为 JSON 选件导入到 [!DNL Target] 中。该[!UICONTROL 内容片段]的“主要”版本保留在 [!DNL AEM] 中。您无法在 [!DNL Target] 中编辑[!UICONTROL 内容片段]。
* 您无法使用 [!DNL Adobe I/O] 创建[!UICONTROL 内容片段]。请使用 AEM 创建[!UICONTROL 内容片段]，如上所述。
* 如果在 AEM 中更新[!UICONTROL 内容片段]，则必须再次发布该[!UICONTROL 内容片段]并将其导出到 [!DNL Target]，以使 [!DNL Target] 可使用最新更改。
