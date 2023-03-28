---
keywords: AEM;Experience Manager;Adobe Experience Manager；集成；体验片段；内容片段
description: 了解如何使用 [!DNL Adobe Experience Manager] 中的体验和内容片段 [!DNL Adobe Target] 活动。
title: 如何使用 [!DNL Adobe Experience Manager] (AEM) [!UICONTROL 体验片段] 和 [!UICONTROL 内容片段]?
feature: Integrations
source-git-commit: 0135831b56c48b0adca49e843c5ddd6574358aa4
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 14%

---

# AEM [!UICONTROL 体验片段] 和 [!UICONTROL 内容片段] 概述

使用 [!UICONTROL 体验片段] (XF)和 [!UICONTROL 内容片段] (CF)在中创建 [!DNL Adobe Experience Manager] (AEM)in [!DNL Target] 活动来帮助优化或个性化。

>[!NOTE]
>
>使用AEM时，请考虑以下事项 [!UICONTROL 体验片段] 和 [!UICONTROL 内容片段] in [!DNL Target]:
> 
>* 这些功能要求您是 [!DNL Adobe Experience Manager] (AEM)客户。 确保满足每个片段类型的要求： [体验片段](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md#requirements) 或 [内容片段](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md#requirements).
>
>* 以下功能适用于以下活动类型： [!UICONTROL A/B测试], [!UICONTROL 自动分配], [!UICONTROL 自动定位], [!UICONTROL Automated Personalization] （美联社）和 [!UICONTROL 体验定位] (XT)。 此功能在 [!UICONTROL 多变量测试] (MVT)和 [!UICONTROL Recommendations] 活动。
>* 您可以使用 [!UICONTROL 体验片段] in [!DNL Target] 活动 [可视化体验编辑器](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC)或 [基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md).
>
>* 您可以使用 [!UICONTROL 内容片段] 在 [基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md) 仅。


使用 [!UICONTROL 体验片段] 和 [!UICONTROL 内容片段] 创建于 [!DNL AEM] in [!DNL Target] 通过活动，您可以将 [!DNL AEM] 在 [!DNL Target] 以大规模测试和个性化体验。

[!DNL AEM] 可将您的所有内容和资产汇集到一个中心位置，以帮助实施您的个性化策略。[!DNL AEM]通过 ，您能够在一个位置轻松创建适用于桌面、平板电脑和移动设备的内容，而无需编写代码。无需为每个设备创建页面。 [!DNL AEM] 可使用您的内容自动调整每个设备的每个体验。

[!DNL Target] 允许您根据一组基于规则且由 AI 驱动的机器学习方法（这些方法包含行为、上下文和离线变量），交付大量的个性化体验。使用 [!DNL Target]，则可以轻松设置和运行 [A/B测试](/help/main/c-activities/t-test-ab/test-ab.md) 和 [多变量](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT)活动来确定最佳选件、内容和体验。

[!UICONTROL 体验片段] 和 [!UICONTROL 内容片段] 这是向将内容/体验创建者和经理与优化和个性化专业人员(这些专业人员正在使用 [!DNL Target].

## 两者之间的区别 [!UICONTROL 体验片段] 和 [!UICONTROL 内容片段]?

[!DNL Adobe Experience Manager] [!UICONTROL 体验片段] 和 [!UICONTROL 内容片段] 表面上可能看起来相似，但每个片段类型在不同用例中都起着关键作用。

有关如何 [!UICONTROL 内容片段] 和 [!UICONTROL 体验片段] 是相似的、不同的，以及何时以及如何使用每个视图 [了解 [!UICONTROL 内容片段] 和 [!UICONTROL 体验片段]](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/content-fragments/understand-content-fragments-and-experience-fragments.html){target=_blank} in the [AEM Sites videos and tutorials guide](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/overview.html){target=_blank}.