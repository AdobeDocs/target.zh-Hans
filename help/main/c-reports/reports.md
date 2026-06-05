---
keywords: 报表；阻止ip地址；阻止来自ip地址的访客；下载报表；csv；报表
description: 通过掌握 [!DNL Adobe Target]的报告功能优化您的活动，以增强决策能力并提高ROI。
title: 如何查看报表？
feature: Reports
exl-id: c5710eb3-0c72-47f8-870d-df50453ecf08
TQID: https://experienceleague.adobe.com/aRp-t-Z-Hfu5O01RqfxnKyHHL2suM2ahkteDQJShGQI
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 947
ht-degree: 24%

---

# 报表

报表提供有关[!DNL Adobe Target]活动进度和结果的信息，帮助您根据数据做出决策。 报表数据可以帮助您确定何时结束活动，向您显示哪个体验或选件已入选，并提供确定后续操作所需的分析或学习数据。

## 显示报表 {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. 单击“**[!UICONTROL 活动]**”，然后在列表中单击所需的活动。

   如果您拥有多个活动，可以通过从[!UICONTROL 类型]、[!UICONTROL 状态]、[!UICONTROL 报告Source]、[!UICONTROL 体验编辑器]、[!UICONTROL 量度类型]、[!UICONTROL 决策方法]和[!UICONTROL 活动Source]列表中选择选项来单击“筛选器”图标（![筛选器图标](/help/main/assets/icons/Filter.svg)）以筛选列表。

   例如，您可以从[!UICONTROL 类型]下拉列表中选择[!UICONTROL A/B测试]和[!UICONTROL 体验定位]，从[!UICONTROL 状态]下拉列表中选择[!UICONTROL 实时]，以仅显示处于活动状态的[!UICONTROL A/B测试]和[!UICONTROL 体验定位]活动。

   下图显示了选定了两种类型的[!UICONTROL 类型]下拉列表：[!UICONTROL A/B测试]和[!UICONTROL 体验定位]。 请注意，默认情况下会选择三种类型的 A/B 测试（手动、[自动分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)和[自动锁定](/help/main/c-activities/auto-target/auto-target-to-optimize.md)）。 您可以根据需要取消选择一种或多种类型。

   ![按类型筛选报表](/help/main/c-reports/assets/report-filters-refresh.png)

1. 单击列表中的所需活动以显示其[!UICONTROL 概述]页面。

1. 单击左边栏中的&#x200B;**[!UICONTROL 报表]**&#x200B;选项卡。

   ![A/B报告](/help/main/c-reports/assets/reports-refresh.png)

   每个报表都包含一个图例，以帮助您了解报表。

   图例显示了以下信息：

   * 活动状态，包括活动运行的日期范围。
   * [预计的入选体验](/help/main/c-activities/automated-traffic-allocation/determine-winner.md)（如果可用）。

   >[!NOTE]
   >
   >至少有一个参加者查看了体验后，才会显示体验结果。

1. （可选） [通过单击“报表设置”图标（![报表设置图标](/help/main/assets/icons/Setting.svg)）配置报表](/help/main/c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA)。
1. （可选）单击“下载报表”图标（![下载报表图标](/help/main/assets/icons/Download.svg)）可[以CSV格式下载报表](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md)，以便在Excel和其他工具中进行分析。

   以下选项可供选择：

   * [!UICONTROL 将报表导出到 CSV]
   * [!UICONTROL 将订单详细信息导出到 CSV]

1. （可选）单击&#x200B;**[!UICONTROL 表格视图]** （![表格视图图标](/help/main/assets/icons/Table.svg) ）和&#x200B;**[!UICONTROL 图形视图]** （![图形视图图标](/help/main/assets/icons/GraphTrend.svg) ）图标以在报表格式之间切换。

   根据您选择的报告类型，可能会提供其他视图和报告：

   | 报表类型 | 查看 |
   | --- | --- |
   | [[!UICONTROL Auto-Target（自动定位）]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | 单击&#x200B;**[!UICONTROL 自动化区段]** （![自动化区段报表](/help/main/assets/icons/AutomatedSegment.svg) ）或&#x200B;**[!UICONTROL 重要属性]** （![重要属性图标](/help/main/assets/icons/ViewList.svg) ）图标。<ul><li>[[!UICONTROL 自动化区段]报表](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md)显示了不同访客对您的[!UICONTROL Automated Personalization]或[!UICONTROL 自动定位]活动中的选件和体验做出的不同响应。 此报表显示[!DNL Target]个性化模型定义的不同自动化区段如何响应活动中的选件和体验。</li><li>[[!UICONTROL 重要属性]报告](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md)显示了在不同的活动中，不同属性对于模型如何决定进行个性化的重要性如何。 此报表可显示影响模型的排名靠前的属性及其相对重要性。</li></ul> |
   | [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | 除了[[!UICONTROL Automated Personalization摘要]报告](/help/main/c-reports/personalization-reports/reports-ap.md)之外，您还可以单击&#x200B;**[!UICONTROL 自动化区段]** （![自动化区段报告](/help/main/assets/icons/AutomatedSegment.svg)）或&#x200B;**[!UICONTROL 重要属性]** （![重要属性图标](/help/main/assets/icons/ViewList.svg) ）图标。<ul><li>[[!UICONTROL 自动化区段]报表](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md)显示了不同访客对您的[!UICONTROL Automated Personalization]或[!UICONTROL 自动定位]活动中的选件和体验做出的不同响应。 此报表显示[!DNL Target]个性化模型定义的不同自动化区段如何响应活动中的选件和体验。</li><li>[[!UICONTROL 重要属性]报告](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md)显示了在不同的活动中，不同属性对于模型如何决定进行个性化的重要性如何。 此报表可显示影响模型的排名靠前的属性及其相对重要性。</li></ul> |
   | [[!UICONTROL 多变量测试]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | 除了[[!UICONTROL 体验性能]报表](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md)之外，您还可以单击[[!UICONTROL 位置贡献]](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) （![位置贡献图标](/help/main/assets/icons/LocationContribution.svg) ）图标以将报表切换为按位置显示贡献。 |

## 特定活动类型的其他报表信息 {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

除了本主题及其子主题中的一般报表信息之外，本指南的其他部分还提供了特定于各个活动类型的其他信息：

| 活动类型 | 详细信息 |
|--- |--- |
| [[!UICONTROL A/B 测试]](/help/main/c-activities/t-test-ab/test-ab.md) | 要了解 [!DNL Target] 中使用的提升度和置信度以及统计方法，请参阅[计划 A/B 测试](/help/main/c-activities/t-test-ab/sample-size-determination.md)。 |
| [解释[!UICONTROL 自动分配]报告](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) | 通过检查[!DNL Target] UI中的重要指标（包括提升度和置信度），解释[!UICONTROL 自动分配] A/B活动的结果。 |
| [[!UICONTROL 自动定位]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT) | 有关AT活动[!UICONTROL 摘要]报告的信息。 有关详细信息，请参阅[[!UICONTROL 自动定位摘要]报告](/help/main/c-reports/personalization-reports/auto-target-summary-report.md)。<br>有关AT和AP活动的两个[!UICONTROL Personalization分析]报告的信息： [!UICONTROL 自动化区段]报告和[!UICONTROL 重要属性]报告。 有关更多信息，请参阅[个性化洞察报告](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)。 |
| [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | 有关AP活动的两个[!UICONTROL Automated Personalization摘要]报表的信息： [!UICONTROL 活动级别]报表和[!UICONTROL 选件级别]报表。 有关详细信息，请参阅[Automated Personalization摘要报表](/help/main/c-reports/personalization-reports/reports-ap.md)。<br>有关AT和AP活动的两个[!UICONTROL Personalization Insights]报表的信息： [!UICONTROL 自动化区段]报表和[!UICONTROL 重要属性]报表。 有关更多信息，请参阅[个性化洞察报告](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)。 |
| [[!UICONTROL 多变量测试]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | 有关MVT活动的以下两个报表的信息：[!UICONTROL 体验性能]报表和[!UICONTROL 位置贡献]报表。 有关详细信息，请参阅[体验性能报表](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md) (MVT)和[位置贡献报表](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) (MVT)。 |
| [[!DNL Adobe Analytics] 作为Adobe Target的报表Source](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | 有关使用[!DNL Adobe Analytics]作为[!DNL Target] (A4T)的报表源的信息。 通过 A4T，您可以访问 [!DNL Target] 活动的 [!DNL Analytics] 报表。 有关更多信息，请参阅 [Analytics for Target (A4T) 报表](/help/main/c-reports/analytics-for-target-a4t-reporting.md)。 |
| [[!DNL Target] 在 [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)中报告 | 有关[Adobe Customer Journey Analytics](https://experienceleague.adobe.com/zh-hans/docs/customer-journey-analytics){target=_blank}与[!DNL Target]之间集成的信息，该集成为您的优化程序提供了强大的分析和省时的工具。 |

## 阻止来自指定IP地址的报表数据

您可以阻止将来自指定 IP 地址的访客计入报表。 例如，此选项有助于阻止来自内部访客的报表数据。

[联系客户关怀团队](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)以设置IP过滤器。 使用[Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) (A4T)作为报表源时，此筛选不适用。
