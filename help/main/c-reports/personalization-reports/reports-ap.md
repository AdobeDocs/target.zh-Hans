---
keywords: 定位；AP报表；自动个性化报表；活动级别报表；选件级别报表；选件详细信息报表；常见问题解答
description: 了解如何在Adobe Target中解释Automated Personalization摘要报表。 您可以从此报表切换到自动化区段和重要属性报表。
title: 如何使用Automated Personalization摘要报表？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Reports
exl-id: 2708eba4-72d5-4e6b-b01b-d27de03463b2
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 31%

---

# Automated Personalization 摘要报表

专门化的摘要报告可供用户使用 [!UICONTROL Automated Personalization] 中的活动 [!DNL Adobe Target].

>[!NOTE]
>
>[!UICONTROL 自动个性化]作为 [!DNL Target Premium] 解决方案的一部分提供。它不包含在中 [!DNL Target Standard] 没有 [Target Premium许可证](/help/main/c-intro/intro.md#premium).

1. 单击&#x200B;**[!UICONTROL 活动]**，从列表中单击所需的[!UICONTROL 自动个性化]活动，然后单击&#x200B;**[!UICONTROL 报表]**&#x200B;选项卡。

   如果您有多种活动，则可以对活动列表进行筛选，方法是从“[!UICONTROL 类型]”下拉列表中选择“[!UICONTROL 自动个性化]”。

1. （可选）单击“**[!UICONTROL 下载]**”图标，以下载按所有可用成功量度划分的摘要视图（例如，比较控制流量和目标流量）。

[!UICONTROL 自动个性化]提供了以下报表：

* 活动级别
* 选件级别
* 自动化区段
* 重要属性

## 活动级别报表 {#section_6F72FC5C790B4492B3DCECBFFA971337}

[!UICONTROL 活动级别]的报表可将使用[!UICONTROL 自动个性化]算法的整体性能与使用随机提供内容（控制）的整体性能进行比较。

![活动级别的报表](/help/main/c-reports/assets/box_plot_ap.png)

用于解释 A/B 测试结果的标准规则仍然适用，包括提升度、置信度、趋势、持续时间等。有关结果解释的更多信息，请参阅 [A/Bn 测试中的统计计算](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## 选件级别报表 {#section_CAA6409879E349C6906E2BE8156D87A1}

随机林体验的[!UICONTROL 选件级别]的报表可将每个应用了算法的选件与随机提供内容的同一选件（控制）进行比较。由此可见，此视图不会对选件进行相互比较。

单击体验算法（随机林或控制）以查看 [!UICONTROL 选件级别] 报告。

![Adobe Target中的选件级别报表](/help/main/c-reports/assets/ap_OfferLevelRpt.png)

>[!NOTE]
>
>时钟图标表示仍在构建算法模型。 复选标记图标表示已建立基本算法。

选件可以显示在 [报表组](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md)，并且可以折叠和展开这些报表组。 单击 **[!UICONTROL 控制]** 或 **[!UICONTROL 已定位]** 表中查看按报表组而不是选件列出的汇总信息。

## 自动化区段

单击 [!UICONTROL 自动化区段] 图标。 此报表可显示不同访客对您的AP/AT活动中的选件/体验做出的不同响应。 此报表可显示 Target 的个性化模型定义的不同自动化区段如何响应活动中的选件/体验。

![“自动化区段”图标](/help/main/c-reports/assets/icon-automated-sements-ap.png)

有关更多信息，请参阅 [“自动化区段”报表](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## 重要属性

单击 [!UICONTROL 重要属性] 图标。 此报表显示在不同的活动中，不同属性对模型如何决定进行个性化的重要性如何。 此报表可显示影响模型的排名靠前的属性及其相对重要性。

![“重要属性”图标](/help/main/c-reports/assets/icon-important-attributes-ap.png)

有关更多信息，请参阅 [重要属性报表](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).

## 常见问题解答

### 为什么活动级别报表和选件级别报表中的数据存在差异？

**[!UICONTROL 活动级别] 报告**：访客记录于 [!UICONTROL 活动级别] 报表会捕获对控制体验与“目标”流量的访问次数。 目标流量包括探索流量和个性化流量的组合。

**选件级别报表**：在上记录的展示次数 [!UICONTROL 选件级别] 报表捕获每个选件的展示次数。 因此，在一个具有多个位置的活动中，在中记录的访问总数 [!UICONTROL 选件级别] 所有报表组的报表均等于中针对控制流量或目标流量记录的访问次数的倍数。 [!UICONTROL 活动级别] 报告乘以活动中的位置总数。 在默认内容为可用选项的位置发生的默认内容展示记录在“默认内容”选件组中。 未分配给报表组的选件展示次数记录在“未分组”选件组中。

>[!NOTE]
>
>上记录的展示次数 [!UICONTROL 选件级别] 报表可能不是中记录的访问次数的精确整数倍。 [!UICONTROL 活动级别] 报告。 这是由于通过Internet捕获报表数据流量时出现的小幅度差异（典型差异率低于5%）。 因此，当活动激活后活动中可用的位置数量发生更改时，展示次数不会是准确的倍数。
