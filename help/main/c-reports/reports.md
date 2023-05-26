---
keywords: 报表；阻止ip地址；阻止来自ip地址的访客；下载报表；csv；报表
description: 了解如何在Adobe中使用报表功能 [!DNL Target] 检查活动的性能。 根据您的数据做出更好的决策以提高ROI。
title: 如何查看报表？
feature: Reports
exl-id: c5710eb3-0c72-47f8-870d-df50453ecf08
source-git-commit: d90e541588f51e16dd9b11ead1ece77e9ca1408b
workflow-type: tm+mt
source-wordcount: '859'
ht-degree: 62%

---

# 报表

报表提供有关您的项目的进度和结果的信息， [!DNL Adobe Target] 帮助您根据数据做出决策的活动。 报表数据可以帮助您确定何时结束活动，向您显示哪个体验的选件已入选，并提供确定后续操作所需的分析或学习数据。

## 显示报告 {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. 单击&#x200B;**[!UICONTROL 活动]**，然后在列表中单击所需的活动。

   如果您拥有多个活动，可以通过从[!UICONTROL 类型]、[!UICONTROL 状态]、[!UICONTROL 报表源]、[!UICONTROL 体验编辑器]、[!UICONTROL 量度类型]和[!UICONTROL 活动来源]下拉列表中选择相应选项来筛选列表。

   例如，您可以从“[!UICONTROL 类型]”下拉列表中选择“[!UICONTROL A/B 测试]”和“[!UICONTROL 体验定位]”，并从“[!UICONTROL 状态]”下拉列表中选择“[!UICONTROL 实时]”，以仅显示处于活跃状态的 A/B 测试活动和体验定位活动。

   下图显示了“[!UICONTROL 类型]”下拉列表，其中选定了两个类型： [!UICONTROL A/B测试] 和 [!UICONTROL 体验定位]. 请注意，默认情况下会选择三种类型的 A/B 测试（手动、[自动分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)和[自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md)）。您可以根据需要取消选择一种或多种类型。

   ![按类型筛选报表](/help/main/c-reports/assets/report_filters-new.png)

1. 单击&#x200B;**[!UICONTROL 报表]**&#x200B;选项卡。

   每个报表都包含一个图例，以帮助您了解报表。

   ![报表图例](/help/main/c-reports/assets/report_menu_bar-new.png)

   图例显示了以下信息：

   * 活动状态，包括活动运行的日期范围。
   * 此 [预计的获胜体验](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) （如果可用）。

   >[!NOTE]
   >
   >至少有一个参加者查看了体验后，才会显示体验结果。

1. （可选）[配置报表](/help/main/c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA)（如有需要）。
1. （可选）[以 CSV 格式下载报表](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md)，以便在 Excel 和其他工具中进行分析。

   以下选项可供选择：

   * [!UICONTROL 将报表导出到 CSV]
   * [!UICONTROL 将订单详细信息导出到 CSV]

1. （可选）单击&#x200B;**[!UICONTROL 表格视图]**&#x200B;图标和&#x200B;**[!UICONTROL 图形视图]**&#x200B;图标，以在这两种报表格式之间进行切换。

   ![表格视图和图形视图图标](/help/main/c-reports/assets/table-and-graph-icons.png)

   根据您选择的报告类型，可能有其他视图和报告可用：

   | 报表类型 | 查看 |
   | --- | --- |
   | [自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | 单击 **[!UICONTROL 自动化区段]** 或 **[!UICONTROL 重要属性]** 图标。<ul><li>此 [“自动化区段”报表](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) 显示不同访客对AP/AT活动中的选件/体验做出的响应方式。 此报表可显示 Target 的个性化模型定义的不同自动化区段如何响应活动中的选件/体验。</li><li>此 [重要属性报表](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) 显示了在不同活动中，不同属性对模型如何决定进行个性化的重要性如何。 此报表可显示影响模型的排名靠前的属性及其相对重要性。</li></ul> |
   | [自当个性化](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | 除了 [Automated Personalization摘要报表](/help/main/c-reports/personalization-reports/reports-ap.md)，您可以单击 **[!UICONTROL 自动化区段]** 或 **[!UICONTROL 重要属性]** 图标。<ul><li>此 [“自动化区段”报表](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) 显示不同访客对AP/AT活动中的选件/体验做出的响应方式。 此报表可显示 Target 的个性化模型定义的不同自动化区段如何响应活动中的选件/体验。</li><li>此 [重要属性报表](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) 说明在不同的活动中，不同属性如何对模型如何决定进行个性化更重要（或更重要）。 此报表可显示影响模型的排名靠前的属性及其相对重要性。</li></ul> |
   | [多变量测试](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | 除了 [体验性能报表](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md)，您可以单击 [位置贡献](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) 图标，以将报表切换为按位置显示贡献。 |

## 特定活动类型的其他报表信息 {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

除了本主题及其子主题中的一般报表信息之外，本指南的其他部分还提供了特定于各个活动类型的其他信息：

| 活动类型 | 详细信息 |
|--- |--- |
| [A/B 测试](/help/main/c-activities/t-test-ab/test-ab.md) | 要了解 [!DNL Target] 中使用的提升度和置信度以及统计方法，请参阅[计划 A/B 测试](/help/main/c-activities/t-test-ab/sample-size-determination.md)。 |
| [解释自动分配报表](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) | 解释的结果 [!UICONTROL 自动分配] A/B活动，检查重要指标，包括提升度和信心 [!DNL Target] UI。 |
| [自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT) | 有关 AT 活动的[!UICONTROL 摘要]报表的信息。有关更多信息，请参阅[自动定位摘要报告](/help/main/c-reports/personalization-reports/auto-target-summary-report.md)。<br>有关 AT 和 AP 活动的以下两个[!UICONTROL 个性化分析]报表的信息：[!UICONTROL 自动化区段]报表和[!UICONTROL 重要属性]报表。有关更多信息，请参阅[个性化分析报表](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)。 |
| [自动个性化](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | 有关 AP 活动的以下两个[!UICONTROL 自动个性化摘要]报表的信息：[!UICONTROL 活动级别]报表和[!UICONTROL 选件级别]报表。有关更多信息，请参阅[自动个性化摘要报表](/help/main/c-reports/personalization-reports/reports-ap.md)。<br>有关 AT 和 AP 活动的以下两个[!UICONTROL 个性化分析]报表的信息：[!UICONTROL 自动化区段]报表和[!UICONTROL 重要属性]报表。有关更多信息，请参阅[个性化分析报表](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)。 |
| [多变量测试](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | 有关 MVT 活动的以下两个报表的信息：[!UICONTROL 体验性能]报表和[!UICONTROL 位置贡献]报表。有关更多信息，请参阅[体验性能报表](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md) (MVT) 和[位置贡献报表](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) (MVT)。 |
| [将 Adobe Analytics 作为 Adobe Target 报表源](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | 有关使用 [!DNL Adobe Analytics] 作为 [!DNL Target] 报表源的信息。通过 A4T，您可以访问 [!DNL Target] 活动的 [!DNL Analytics] 报表。有关更多信息，请参阅 [Analytics for Target (A4T) 报表](/help/main/c-reports/analytics-for-target-a4t-reporting.md)。 |

## 阻止来自指定IP地址的报表数据

您可以阻止将来自指定 IP 地址的访客计入报表。例如，这有助于阻止来自内部访客的报告数据。

[请联系客户关怀团队以设置 IP 筛选器。](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)使用时，此筛选不适用 [目标分析](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) (A4T)作为报表源。
