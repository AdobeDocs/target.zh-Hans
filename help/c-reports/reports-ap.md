---
keywords: Targeting;AP reports;automated personalization reports;activity level report;offer level report;offer detail report
description: 如何使用“Automated Personalization摘要”报告？
title: 自动个性化摘要报表
feature: Reports
translation-type: tm+mt
source-git-commit: eb51e8951643fcf64d7a9464d57f809636c9c931
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 41%

---


# ![PREMIUM](/help/assets/premium.png) 自动个性化摘要报表

[!DNL Adobe Target]中的[!UICONTROL Automated Personalization]活动的用户可使用专门的报告。

>[!NOTE]
>
>[!UICONTROL 自动个性化]作为 [!DNL Target Premium] 解决方案的一部分提供。没有[目标高级许可证](/help/c-intro/intro.md#premium)，它不包含在[!DNL Target Standard]中。

1. 单击&#x200B;**[!UICONTROL 活动]**，从列表中单击所需的[!UICONTROL 自动个性化]活动，然后单击&#x200B;**[!UICONTROL 报表]**&#x200B;选项卡。

   如果您有多种活动，则可以对活动列表进行筛选，方法是从“[!UICONTROL 类型]”下拉列表中选择“[!UICONTROL 自动个性化]”。

1. （可选）单击“**[!UICONTROL 下载]**”图标，以下载按所有可用成功量度划分的摘要视图（例如，比较控制流量和目标流量）。

[!UICONTROL 自动个性化]提供了以下报表：

* 活动级别
* 优惠级别
* 自动化区段
* 重要属性

## 活动级别报告{#section_6F72FC5C790B4492B3DCECBFFA971337}

[!UICONTROL 活动级别]的报表可将使用[!UICONTROL 自动个性化]算法的整体性能与使用随机提供内容（控制）的整体性能进行比较。

![活动级别的报表](/help/c-reports/assets/box_plot_ap.png)

用于解释 A/B 测试结果的标准规则仍然适用，包括提升度、置信度、趋势、持续时间等。有关结果解释的更多信息，请参阅[关于转化率](/help/c-reports/conversion-rate.md#concept_2D9FEDE8F94A485DAC86D611BFBDC844)。

## 优惠级别报告{#section_CAA6409879E349C6906E2BE8156D87A1}

随机林体验的[!UICONTROL 选件级别]的报表可将每个应用了算法的选件与随机提供内容的同一选件（控制）进行比较。由此可见，此视图不会对选件进行相互比较。

单击体验算法（随机林或控制）以视图[!UICONTROL 优惠级别]报告。

![](assets/ap_OfferLevelRpt.png)

选件可以在报表组中显示，而这些报表组可以折叠或展开。在下拉列表中选择“[!UICONTROL 报表组]”，可查看按报表组（而不是选件）汇总的信息。

>[!NOTE]
>
>时钟图标指示仍在构建算法模型。复选标记图标表示已建立基本算法。

## 活动级别和优惠级别报表之间的数据差异

**[!UICONTROL 活动] 级别报告**:活动级别 [!UICONTROL 报] 告中记录的访问记录了控制体验与“目标”流量。目标流量包括探索流量和个性化流量的混合。

**优惠级别报告**:优惠级别报 [!UICONTROL 表] 上记录的展示次数捕获每个优惠的展示次数。因此，在具有多个位置的活动中，在所有报告组中记录在[!UICONTROL 优惠级别]报告中的访问总数等于在[!UICONTROL 活动级别]报告中为控制或目标流量记录的访问次数乘以活动中的位置总数。 默认内容在默认内容为可用选项的位置出现的印象记录在“默认内容”优惠组中。 未分配给优惠组的报告印象将记录在“未分组”优惠组中。

>[!NOTE]

在[!UICONTROL 优惠级别]报告中记录的展示次数可能不是在[!UICONTROL 活动级别]报告中记录的访问次数的整数倍。 这是由于在通过Internet捕获报告数据流量时出现细微差异（通常差异率低于5%）所致。 因此，当活动中的可用位置数在活动激活后发生更改时，印象数不会是精确倍数。

## 自动化区段

单击[!UICONTROL 自动化区段]图标。 此报告显示不同访客对AP/AT活动中的优惠/体验的响应方式。 此报表可显示 Target 的个性化模型定义的不同自动化区段如何响应活动中的选件/体验。

![自动细分图标](/help/c-reports/assets/icon-automated-sements-ap.png)

有关详细信息，请参阅[自动细分报告](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md)。

## 重要属性

单击[!UICONTROL 重要属性]图标。 此报告显示不同活动中不同属性对模型决定如何个性化的重要性如何。 此报表可显示影响模型的排名靠前的属性及其相对重要性。

![重要属性图标](/help/c-reports/assets/icon-important-attributes-ap.png)

有关详细信息，请参阅[重要属性报告](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md)。
