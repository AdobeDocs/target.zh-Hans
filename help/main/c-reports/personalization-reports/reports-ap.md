---
keywords: 定位；AP报表；自动个性化报表；活动级别报表；选件级别报表；选件详细信息报表；常见问题解答
description: 了解如何在Adobe Target中解释Automated Personalization摘要报表。 您可以从此报表切换到自动化区段和重要属性报表。
title: 如何使用Automated Personalization摘要报表？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Reports
exl-id: 2708eba4-72d5-4e6b-b01b-d27de03463b2
TQID: https://experienceleague.adobe.com/Gj9Jo0NHnSxGE4BpvFbd0SudYjbkP4yrV3GFHWHNPjw
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 702
ht-degree: 20%

---

# Automated Personalization 摘要报表

[!DNL Adobe Target]中[!UICONTROL Automated Personalization]活动的用户可以使用专门的摘要报告。

>[!NOTE]
>
>[!UICONTROL Automated Personalization]作为[!DNL Target Premium]解决方案的一部分提供。 在没有[Target Premium许可证](/help/main/c-intro/intro.md#premium)的[!DNL Target Standard]中不包括它。

1. 单击&#x200B;**[!UICONTROL 活动]**，从列表中单击所需的[!UICONTROL 自动个性化]活动，然后单击&#x200B;**[!UICONTROL 报表]**&#x200B;选项卡。

   如果您有许多活动，请单击“筛选器”（![筛选器图标](/help/main/assets/icons/Filter.svg)）图标以筛选列表，方法是从[!UICONTROL 类型]、[!UICONTROL 状态]、[!UICONTROL 报告Source]、[!UICONTROL 体验编辑器]、[!UICONTROL 量度类型]和[!UICONTROL 活动Source]下拉列表中选择相应的选项。

1. （可选）单击&#x200B;**[!UICONTROL 下载]** （![下载图标](/help/main/assets/icons/Download.svg) ）图标可下载按所有可用成功量度划分的摘要视图（例如，比较控制和目标流量）。

[!UICONTROL 自动个性化]提供了以下报表：

* 活动级别
* 选件级别
* 自动化区段
* 重要属性

## 活动级别报表 {#section_6F72FC5C790B4492B3DCECBFFA971337}

[!UICONTROL 活动级别]的报表可将使用[!UICONTROL 自动个性化]算法的整体性能与使用随机提供内容（控制）的整体性能进行比较。

用于解释 A/B 测试结果的标准规则仍然适用，包括提升度、置信度、趋势、持续时间等。 有关解释结果的更多信息，请参阅[A/Bn测试中的统计计算](/help/main/c-reports/statistical-methodology/statistical-calculations.md)。

## 选件级别报表 {#section_CAA6409879E349C6906E2BE8156D87A1}

随机林体验的[!UICONTROL 选件级别]的报表可将每个应用了算法的选件与随机提供内容的同一选件（控制）进行比较。 由此可见，此视图不会对选件进行相互比较。

单击体验算法（随机林或控制）以查看[!UICONTROL 选件级别]报表。

>[!NOTE]
>
>时钟图标表示仍在构建算法模型。 复选标记图标表示已建立基本算法。

选件可以显示在[报表组](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md)中，并且这些报表组可以折叠和展开。 单击表中的&#x200B;**[!UICONTROL 控件]**&#x200B;或&#x200B;**[!UICONTROL 目标]**&#x200B;以查看按报表组而不是按选件汇总的信息。

## 自动化区段

单击[!UICONTROL 自动化区段]图标。 此报表可显示不同访客对您的AP/AT活动中的选件/体验做出的不同响应。 此报表可显示 Target 的个性化模型定义的不同自动化区段如何响应活动中的产品建议/体验。

有关详细信息，请参阅[自动化区段报表](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md)。

## 重要属性

单击[!UICONTROL 重要属性]图标。 此报表显示了在不同活动中，不同属性对模型如何决定进行个性化的重要性如何。 此报表可显示影响模型的排名靠前的属性及其相对重要性。

有关详细信息，请参阅[重要属性报表](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md)。

## 常见问题解答

### 为什么活动级别报表和选件级别报表中的数据存在差异？

**[!UICONTROL 活动级别]报告**：在[!UICONTROL 活动级别]报告上记录的访问捕获了对控制体验的访问次数与“目标”流量。 目标流量包括探索流量和个性化流量的组合。

**选件级别报表**： [!UICONTROL 选件级别]报表中记录的展示次数捕获了每个选件的展示次数。 因此，在具有多个位置的活动中，所有报表组在[!UICONTROL 选件级别]报表中记录的访问总数等于[!UICONTROL 活动级别]报表中为控制流量或目标流量记录的访问次数与活动中位置总数的倍数。 在默认内容为可用选项的位置发生的默认内容展示记录在“默认内容”选件组中。 未分配给报表组的选件展示次数记录在“未分组”选件组中。

>[!NOTE]
>
>在[!UICONTROL 选件级别]报表中记录的展示次数可能不是[!UICONTROL 活动级别]报表中记录的访问次数的精确整数倍。 这是由于通过Internet捕获报表数据流量时发生的细微差异（典型差异率低于5%）。 因此，当活动中的可用位置数量在激活活动后发生更改时，展示次数不会是准确的倍数。
