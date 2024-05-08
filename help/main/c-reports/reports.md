---
keywords: 报表；阻止ip地址；阻止来自ip地址的访客；下载报表；csv；报表
description: 了解如何在Adobe中使用报表功能 [!DNL Target] 检查活动的性能。 根据您的数据做出更好的决策以提高ROI。
title: 如何查看报表？
feature: Reports
exl-id: c5710eb3-0c72-47f8-870d-df50453ecf08
source-git-commit: a7a03cba466fbe7abfc8eb1f80292e1a2de7fe2d
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 41%

---

# 报表

报表提供有关您的项目的进度和结果的信息 [!DNL Adobe Target] 帮助您根据数据做出决策的活动。 报表数据可以帮助您确定何时结束活动，向您显示哪个体验或选件已入选，并提供确定后续操作所需的分析或学习数据。

## 显示报表 {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. 单击 **[!UICONTROL Activities]**，然后在列表中单击所需的活动。

   如果您有多种活动，则可以通过从以下列表中选择选项来筛选列表： [!UICONTROL Type]， [!UICONTROL Status]， [!UICONTROL Reporting Source]， [!UICONTROL Experience Composer]， [!UICONTROL Metrics Type]、和 [!UICONTROL Activity Source] 下拉列表。

   例如，您可以选择 [!UICONTROL A/B Test] 和 [!UICONTROL Experience Targeting] 从 [!UICONTROL Type] 下拉列表和 [!UICONTROL Live] 从 [!UICONTROL Status] 下拉列表，仅显示处于活动状态的A/B测试和体验定位活动。

   下图显示了 [!UICONTROL Type] 下拉列表中已选择两种类型： [!UICONTROL A/B Test] 和 [!UICONTROL Experience Targeting]. 请注意，默认情况下会选择三种类型的 A/B 测试（手动、[自动分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)和[自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md)）。您可以根据需要取消选择一种或多种类型。

   ![按类型筛选报表](/help/main/c-reports/assets/report_filters-new.png)

1. 单击 **[!UICONTROL Reports]** 选项卡。

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

   * [!UICONTROL Export Report to CSV]
   * [!UICONTROL Export Order Details to CSV]

1. （可选）单击 **[!UICONTROL Table View]** 和 **[!UICONTROL Graph View]** 用于切换报表格式的图标。

   ![表格视图和图形视图图标](/help/main/c-reports/assets/table-and-graph-icons.png)

   根据您选择的报告类型，可能会提供其他视图和报告：

   | 报表类型 | 查看 |
   | --- | --- |
   | [自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | 单击 **[!UICONTROL Automated Segments]** 或 **[!UICONTROL Important Attributes]** 图标。<ul><li>此 [自动化区段报表](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) 显示不同访客对您的AP/AT活动中的选件/体验做出的不同响应。 此报表可显示 Target 的个性化模型定义的不同自动化区段如何响应活动中的选件/体验。</li><li>此 [重要属性报表](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) 显示了在不同活动中，不同属性对模型如何决定进行个性化的重要性如何。 此报表可显示影响模型的排名靠前的属性及其相对重要性。</li></ul> |
   | [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | 除了 [Automated Personalization摘要报表](/help/main/c-reports/personalization-reports/reports-ap.md)，您可以单击 **[!UICONTROL Automated Segments]** 或 **[!UICONTROL Important Attributes]** 图标。<ul><li>此 [自动化区段报表](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) 显示不同访客对您的AP/AT活动中的选件/体验做出的不同响应。 此报表可显示 Target 的个性化模型定义的不同自动化区段如何响应活动中的选件/体验。</li><li>此 [重要属性报表](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) 说明在不同的活动中，不同的属性如何对模型决定个性化的方式更加（或更少）重要。 此报表可显示影响模型的排名靠前的属性及其相对重要性。</li></ul> |
   | [多变量测试](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | 除了 [体验性能报表](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md)，您可以单击 [位置贡献](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) 图标可将报表切换为按位置显示贡献。 |

## 特定活动类型的其他报表信息 {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

除了本主题及其子主题中的一般报表信息之外，本指南的其他部分还提供了特定于各个活动类型的其他信息：

| 活动类型 | 详细信息 |
|--- |--- |
| [A/B 测试](/help/main/c-activities/t-test-ab/test-ab.md) | 要了解 [!DNL Target] 中使用的提升度和置信度以及统计方法，请参阅[计划 A/B 测试](/help/main/c-activities/t-test-ab/sample-size-determination.md)。 |
| [解释自动分配报表](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) | 解释的结果 [!UICONTROL Auto-Allocate] A/B活动，检查以下各项的重要指标，包括提升度和信心： [!DNL Target] UI。 |
| [自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT) | 关于 [!UICONTROL Summary] AT活动的报表。 有关更多信息，请参阅[自动定位摘要报告](/help/main/c-reports/personalization-reports/auto-target-summary-report.md)。<br>关于两者的信息 [!UICONTROL Personalization Insights] AT和AP活动的报表： [!UICONTROL Automated Segments] 报告和 [!UICONTROL Important Attributes] 报告。 有关更多信息，请参阅[个性化分析报表](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)。 |
| [自动个性化](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | 关于两者的信息 [!UICONTROL Automated Personalization Summary] AP活动报表： [!UICONTROL Activity Level] 报告和 [!UICONTROL Offer Level] 报告。 有关更多信息，请参阅[自动个性化摘要报表](/help/main/c-reports/personalization-reports/reports-ap.md)。<br>关于两者的信息 [!UICONTROL Personalization Insights] AT和AP活动的报表： [!UICONTROL Automated Segments] 报告和 [!UICONTROL Important Attributes] 报告。 有关更多信息，请参阅[个性化分析报表](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)。 |
| [多变量测试](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | 有关MVT活动的以下两个报表的信息： [!UICONTROL Experience Performance] 报告和 [!UICONTROL Location Contribution] 报告。 有关更多信息，请参阅[体验性能报表](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md) (MVT) 和[位置贡献报表](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) (MVT)。 |
| [将 Adobe Analytics 作为 Adobe Target 报表源](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | 有关使用 [!DNL Adobe Analytics] 作为 [!DNL Target] 报表源的信息。通过 A4T，您可以访问 [!DNL Target] 活动的 [!DNL Analytics] 报表。有关更多信息，请参阅 [Analytics for Target (A4T) 报表](/help/main/c-reports/analytics-for-target-a4t-reporting.md)。 |
| [[!DNL Target] 报告 [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) | 有关以下对象之间的集成的信息： [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/customer-journey-analytics){target=_blank} 和 [!DNL Target] 为您的优化项目提供强大的分析和省时的工具。 |

## 阻止来自指定IP地址的报表数据

您可以阻止将来自指定 IP 地址的访客计入报表。例如，这有助于阻止来自内部访客的报表数据。

[联系客户关怀团队](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) 设置IP过滤器。 使用时，此筛选不适用 [目标分析](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) (A4T)作为报表源。
