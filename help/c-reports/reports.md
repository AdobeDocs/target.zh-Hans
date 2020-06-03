---
keywords: reports;block ip address;block visitor from ip address;download reports;csv;reporting
description: 报表提供了有关活动性能的信息
title: 报表
subtopic: Multivariate Test
topic: Standard
uuid: 8d20f4e7-72fd-4872-a21f-54ce16a2d2ab
translation-type: tm+mt
source-git-commit: 316c1157a4dff346f16862cfd7a04994c6a1bc7d
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 77%

---


# 报表{#reports}

报表提供了有关活动进度和结果的信息，可帮助您根据数据做出决策。报表数据可以帮助您确定何时结束测试，向您显示哪个体验或选件已入选，并提供确定后续操作所需的分析或学习数据。

>[!NOTE]
>
>您可以阻止将来自指定 IP 地址的访客计入报表。请联系客户关怀团队以设置 IP 筛选器。此筛选器不适用于将 [Analytics for Target](../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) (A4T) 用作报表源的情况。

## 特定活动类型的报表信息 {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

除了本主题及其子主题中的一般报表信息之外，本指南的其他部分还提供了特定于各个活动类型的其他信息：

| 活动类型 | 详细信息 |
|--- |--- |
| [A/B 测试](/help/c-activities/t-test-ab/test-ab.md) | 要了解 [!DNL Target] 中使用的提升度和置信度以及统计方法，请参阅[计划 A/B 测试](/help/c-activities/t-test-ab/sample-size-determination.md)。 |
| [解释自动分配报告](/help/c-activities/automated-traffic-allocation/determine-winner.md) | 通过检查活动UI中的重要指标（包括提升和置信度）来解释自动分配A/B目标的结果。 |
| [自动定位](/help/c-activities/auto-target-to-optimize.md) (AT) | 有关 AT 活动的[!UICONTROL 摘要]报表的信息。有关更多信息，请参阅[自动定位摘要报告](/help/c-reports/auto-target-summary-report.md)。<br>有关 AT 和 AP 活动的以下两个[!UICONTROL 个性化分析]报表的信息：[!UICONTROL 自动化区段]报表和[!UICONTROL 重要属性]报表。有关更多信息，请参阅[个性化分析报表](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)。 |
| [自动个性化](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) | 有关 AP 活动的以下两个[!UICONTROL 自动个性化摘要]报表的信息：[!UICONTROL 活动级别]报表和[!UICONTROL 选件级别]报表。有关更多信息，请参阅[自动个性化摘要报表](/help/c-reports/reports-ap.md)。<br>有关 AT 和 AP 活动的以下两个[!UICONTROL 个性化分析]报表的信息：[!UICONTROL 自动化区段]报表和[!UICONTROL 重要属性]报表。有关更多信息，请参阅[个性化分析报表](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)。 |
| [多变量测试](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | 有关 MVT 活动的以下两个报表的信息：[!UICONTROL 体验性能]报表和[!UICONTROL 位置贡献]报表。有关更多信息，请参阅[体验性能报表](/help/c-reports/experience-performance-report.md) (MVT) 和[位置贡献报表](/help/c-reports/location-contribution-report.md) (MVT)。 |
| [将 Adobe Analytics 作为 Adobe Target 报表源](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | 有关使用 [!DNL Adobe Analytics] 作为 [!DNL Target] 报表源的信息。通过 A4T，您可以访问 [!DNL Target] 活动的 [!DNL Analytics] 报表。有关更多信息，请参阅 [Analytics for Target (A4T) 报表](/help/c-reports/analytics-for-target-a4t-reporting.md)。 |

## 显示报表 {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. 单击&#x200B;**[!UICONTROL 活动]**，然后在列表中单击所需的活动。

   如果您拥有多个活动，可以通过从[!UICONTROL 类型]、[!UICONTROL 状态]、[!UICONTROL 报表源]、[!UICONTROL 体验编辑器]、[!UICONTROL 量度类型]和[!UICONTROL 活动来源]下拉列表中选择相应选项来筛选列表。

   例如，您可以从“[!UICONTROL 类型]”下拉列表中选择“[!UICONTROL A/B 测试]”和“[!UICONTROL 体验定位]”，并从“[!UICONTROL 状态]”下拉列表中选择“[!UICONTROL 实时]”，以仅显示处于活跃状态的 A/B 测试活动和体验定位活动。

   下图显示了“[!UICONTROL 类型]”下拉列表，其中选定了两个类型：A/B 测试和体验定位。请注意，默认情况下会选择三种类型的 A/B 测试（手动、[自动分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)和[自动定位](/help/c-activities/auto-target-to-optimize.md)）。您可以根据需要取消选择一种或多种类型。

   ![按类型筛选报表](/help/c-reports/assets/report_filters-new.png)

1. 单击&#x200B;**[!UICONTROL 报表]**&#x200B;选项卡。

   每个报表都包含一个图例，以帮助您了解报表。

   ![报表图例](/help/c-reports/assets/report_menu_bar-new.png)

   图例显示了以下信息：

   * 活动状态，包括活动运行的日期范围。
   * The [projected winning experience](/help/c-activities/automated-traffic-allocation/determine-winner.md) (if available).
   >[!NOTE]
   >
   >至少有一个参加者查看了体验后，才会显示体验结果。

1. （可选）[配置报表](../c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA)（如有需要）。
1. （可选）[以 CSV 格式下载报表](../c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75)，以便在 Excel 和其他工具中进行分析。

   以下选项可供选择：

   * [!UICONTROL 将报表导出到 CSV]
   * [!UICONTROL 将订单详细信息导出到 CSV]

1. （可选）单击&#x200B;**[!UICONTROL 表格视图]**&#x200B;图标和&#x200B;**[!UICONTROL 图形视图]**&#x200B;图标，以在这两种报表格式之间进行切换。

   根据您选择的报告类型，可能会提供其他视图和报告：

   | 报表类型 | 查看 |
   | --- | --- |
   | 自动定位 | 单击“自 **[!UICONTROL 动化区段]** ”或 **[!UICONTROL “重要属性]** ”图标。<ul><li>The [Automated Segments report](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md) shows how different visitors respond differently to the offers/experiences in your AP/AT activity. 此报表可显示 Target 的个性化模型定义的不同自动化区段如何响应活动中的选件/体验。</li><li>The [Important Attributes report](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md) hows how, in different activities, different attributes are more (or less) important to how the model decides to personalize. 此报表可显示影响模型的排名靠前的属性及其相对重要性。</li></ul> |
   | 自动个性化 (AP) | 除了“自动个性化 [摘要”报表](/help/c-reports/reports-ap.md)，您还可以单击“自动 **[!UICONTROL 细分”或“重]** 要属性”图标 **** 。<ul><li>The [Automated Segments report](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md) shows how different visitors respond differently to the offers/experiences in your AP/AT activity. 此报表可显示 Target 的个性化模型定义的不同自动化区段如何响应活动中的选件/体验。</li><li>The [Important Attributes report](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md) hows how, in different activities, different attributes are more (or less) important to how the model decides to personalize. 此报表可显示影响模型的排名靠前的属性及其相对重要性。</li></ul> |
   | 多变量测试 (MVT) | 除了“体验 [效果”报告](/help/c-reports/experience-performance-report.md)，您还可以单击“ [位置贡献](/help/c-reports/location-contribution-report.md) ”图标，以切换报告以按位置显示贡献。 |
