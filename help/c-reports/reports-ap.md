---
keywords: Targeting;AP reports;automated personalization reports;activity level report;offer level report;offer detail report
description: 向Automated Personalization活动的Adobe Target用户提供专门报告。
title: 自动个性化摘要报表
feature: reports
uuid: 959b6814-9686-4741-8a79-5957e64f6209
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 68%

---


# ![PREMIUM](/help/assets/premium.png) 自动个性化摘要报表{#automated-personalization-summary-reports}

Specialized reports are available to users of [!UICONTROL Automated Personalization] activities in [!DNL Adobe Target].

>[!NOTE]
>
>[!UICONTROL 自动个性化]作为 [!DNL Target Premium] 解决方案的一部分提供。It is not included with [!DNL Target Standard] without a [Target Premium license](/help/c-intro/intro.md#premium).

1. 单击&#x200B;**[!UICONTROL 活动]**，从列表中单击所需的[!UICONTROL 自动个性化]活动，然后单击&#x200B;**[!UICONTROL 报表]**&#x200B;选项卡。

   如果您有多种活动，则可以对活动列表进行筛选，方法是从“[!UICONTROL 类型]”下拉列表中选择“[!UICONTROL 自动个性化]”。

1. （可选）单击“[!UICONTROL 下载]”图标，以下载按所有可用成功量度划分的摘要视图（例如，比较控制流量和目标流量）。

[!UICONTROL 自动个性化]提供了以下报表：

## Activity Level report {#section_6F72FC5C790B4492B3DCECBFFA971337}

[!UICONTROL 活动级别]的报表可将使用[!UICONTROL 自动个性化]算法的整体性能与使用随机提供内容（控制）的整体性能进行比较。

![活动级别的报表](/help/c-reports/assets/box_plot_ap.png)

用于解释 A/B 测试结果的标准规则仍然适用，包括提升度、置信度、趋势、持续时间等。有关结果解释的更多信息，请参阅[关于转化率](/help/c-reports/conversion-rate.md#concept_2D9FEDE8F94A485DAC86D611BFBDC844)。

## Offer Level report {#section_CAA6409879E349C6906E2BE8156D87A1}

随机林体验的[!UICONTROL 选件级别]的报表可将每个应用了算法的选件与随机提供内容的同一选件（控制）进行比较。由此可见，此视图不会对选件进行相互比较。

Click the experience algorithm (Random Forest or control) to view the [!UICONTROL Offer Level] report.

![](assets/ap_OfferLevelRpt.png)

选件可以在报表组中显示，而这些报表组可以折叠或展开。在下拉列表中选择“[!UICONTROL 报表组]”，可查看按报表组（而不是选件）汇总的信息。

>[!NOTE]
>
>时钟图标指示仍在构建算法模型。复选标记图标指示已建立基础算法。

## 自动化区段

单击“自 [!UICONTROL 动化区段] ”图标。 此报告显示不同访客对AP/AT活动中的优惠/体验的响应方式。 此报表可显示 Target 的个性化模型定义的不同自动化区段如何响应活动中的选件/体验。

![自动细分图标](/help/c-reports/assets/icon-automated-sements-ap.png)

有关详细信息，请参阅 [自动化细分报告](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md)。

## 重要属性

单击“重 [!UICONTROL 要属性] ”图标。 此报告显示不同活动中不同属性对模型决定如何个性化的重要性如何。 此报表可显示影响模型的排名靠前的属性及其相对重要性。

![重要属性图标](/help/c-reports/assets/icon-important-attributes-ap.png)

有关详细信息，请参阅 [重要属性报告](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md)。