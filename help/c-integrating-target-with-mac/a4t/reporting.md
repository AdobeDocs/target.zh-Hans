---
keywords: analytics for target;a4t;analytics as the reporting source
description: 使用 Analytics 作为 Target 报表源 (A4T)，您可以访问 Target 活动的 Analytics 报表。
title: A4T 报表
feature: null
subtopic: Multivariate Test
topic: Standard
uuid: bd3a7fa4-ba45-4ea3-81b6-fc2584831ce4
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 35%

---


# A4T 报表{#a-t-reporting}

Using [!DNL Analytics] as your reporting source for [!DNL Target] (A4T) gives you access to [!DNL Analytics] reports for your [!DNL Target] activities.

You can view reports for your activities in both [!DNL Analytics] and [!DNL Target].

For reporting best practices using [!DNL Analytics] for [!DNL Target], [visit this Adobe Spark page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## 概述 {#section_035A62D65608423285D8A5A54731E2C5}

Both [!DNL Analytics] and [!DNL Target] reports measure entrants (the people who enter the tests), rather than visitors to the site.

Every time a visitor sees activity content on the page, [!DNL Target] makes a direct server-to-server call to [!DNL Analytics], including which activity and experience the visitor saw. [!DNL Target] 进行转 [!DNL Analytics] 换时也会进行调用。 [!DNL Analytics] 将转换添加为名为“事件转 [!DNL Analytics] 换”的特定新活动，该与由收集的其他数据一起跟踪 [!DNL Analytics]。

When the [!UICONTROL Select] operation is used and you sort on *Entrants*, then only experiences that received entrants during the selected time period are displayed in the reports.

>[!NOTE]
>
>Reports powered by [!DNL Target] have a latency of four minutes. For activities powered by A4T, in both the [!DNL Target] and [!DNL Analytics] reports, it can take up to 24 hours after the activity is initially saved before the report data can be broken down by experiences. 在划分数据之前的这 24 小时内收集到的数据仍然准确，并且会被分配给正确的体验。

## Analytics 中的报表 {#analytics}

在中 [!DNL Analytics]，启用A4T集成后，有几个维度和指标可用。

### 维度

* [!UICONTROL 目标分析] -通过集成传入的父ID。 此维的格式为 `Activity ID:Experience ID:3rd ID`。 以下维是此维的分类。
* [!UICONTROL Target 活动]
* [!UICONTROL Target 体验]
* [!UICONTROL 目标活动] >体 [!UICONTROL 验]
* [!UICONTROL 第3个ID] —— 可忽略

### 量度

* [!UICONTROL 活动印象] -匹配报 [!UICONTROL 表中的] “新进者 [!DNL Target] ”编号。
* [!UICONTROL 活动转换] -匹配报 [!UICONTROL 表中的] “自定义转 [!DNL Target] 换”。

在中 [!DNL Analysis Workspace]，使用“ [!UICONTROL 目标分析”面板] ，以提升并自信 [!DNL Target] 地分析活动和体验。 有关详细信息，请 [参阅《Analytics工具指南》中的“目标分析(A4T](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/a4t-panel.html) ) *面板”*。

>[!IMPORTANT]
>
>If your [!UICONTROL Target Activities] report in [!DNL Analytics] lists &quot;unspecified&quot; instead of listing your activities, an update is required to your provisioned account. 请联系客户关怀团队以解决此问题。

For detailed information and examples, open the [Analytics &amp; Target: Best Practices for Analysis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) tutorial, provided by Adobe Experience League.

## Target 中的报表 {#section_C0D1F17F88374B6690BF904D7B83B42E}

When [!DNL Analytics] is used as the reporting source, reports in [!DNL Target] show the data gathered from [!DNL Analytics]. The report differs somewhat from other [!DNL Target] reports:

* The [!UICONTROL Audiences] list shows the audiences available to your [!DNL Analytics] report suite.
* The [!UICONTROL Metric] list shows every metric available through [!DNL Analytics].

   Every metric is available, including any custom or calculated metrics that are built-in in [!DNL Analytics].

   请注意，在报表中，任何增大的数字都显示为正值，即使增大的数字实际上并不是所需的结果也是如此。例如，虽然您希望降低跳出率，但是较高的跳出率会显示为具有最高提升度的入选者。根据报表做出决策时，请留心这些量度及类似量度，并确定您是希望降低还是提高这些量度的数值。

You can apply the metric or audience to the report in [!DNL Target] after the activity has started, or even after the test has completed. 您无需事先知晓要衡量的确切内容。

Click to view the full [!DNL Analytics] report directly from the activity report page.

## 活动创建 {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

在活动创建期间，您必须在“[!UICONTROL 设置]”页面中指定活动的目标。此目标将作为报表的默认量度并且在量度选择器中始终列为第一个选项。您将无法像设置常规 Target 活动的报表那样选择报表的区段。A test with [!DNL Analytics] uses [!DNL Adobe Analytics] segments rather than [!DNL Target] audiences.

## Performing offline calculations for Analytics for Target (A4T) {#section_33A97A691F3A45D497DAF57A844388F0}

您可以为 A4T 执行离线计算，但需要在 [!DNL Analytics] 中完成数据导出步骤。

有关更多信息，请参阅[为 Analytics for Target (A4T) 执行离线计算](../../c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B)。
