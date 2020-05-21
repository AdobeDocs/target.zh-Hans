---
keywords: analytics for target;a4t;analytics as the reporting source
description: 使用 Analytics 作为 Target 报表源 (A4T)，您可以访问 Target 活动的 Analytics 报表。
title: A4T 报表
subtopic: Multivariate Test
topic: Standard
uuid: bd3a7fa4-ba45-4ea3-81b6-fc2584831ce4
translation-type: tm+mt
source-git-commit: 68f356b0711abf9acf7ef631edf3656bd3dd49e3
workflow-type: tm+mt
source-wordcount: '733'
ht-degree: 44%

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

## Analytics 中的报表 {#section_F6884872DC864AE7913587FAED4CD11C}

In [!DNL Analytics], click **[!UICONTROL Target]** > **[!UICONTROL Target Activities]** in the left menu. In [!DNL Target], the activity&#39;s reports automatically show [!DNL Analytics] data, metrics, and segments. 从网站收集数据大约一小时后，数据便会显示在这些报表中。报表中的所有量度、受众和值都来自您在设置活动时选择的报表包。

In [!DNL Analytics], use the [!UICONTROL Target Activities] report to view the results of your [!DNL Target] activity. Test&amp;Target (Legacy) Reports provides information about your old Test&amp;Target plug-in style page integrations and does not include [!DNL Analytics] for [!DNL Target] data. In the [!UICONTROL Activities] report, view information about your [!DNL Target] experiences. 单击&#x200B;**[!UICONTROL 量度]**，然后选择&#x200B;**[!UICONTROL 目标]**&#x200B;量度类型。您的报表有两个可用的量度：

* **活动参加：**[!DNL Target]匹配 报表中的参加者数量。
* **活动转化：**[!DNL Target]匹配 报表中的自定义转化数量。

>[!NOTE]
>
>[!DNL Target] 此外，还提供提升和置信度详细信 [!DNL Analytics]息。 有关详细信息，请参 [阅《Analytics Components Guide》(分析组件指南](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/report-target-lift-confidence.html) )中的 *目标提升和信心*。

>[!IMPORTANT]
>
>If your [!UICONTROL Target Activities] report in [!DNL Analytics] lists &quot;unspecified&quot; instead of listing your activities, an update is required to your provisioned account. 请联系客户关怀团队以解决此问题。

## Target 中的报表 {#section_C0D1F17F88374B6690BF904D7B83B42E}

When [!DNL Analytics] is used as the reporting source, reports in [!DNL Target] show the data gathered from [!DNL Analytics]. The report differs somewhat from other [!DNL Target] reports:

* The [!UICONTROL Audiences] list shows the audiences available to your [!DNL Analytics] report suite.
* The [!UICONTROL Metric] list shows every metric available through [!DNL Analytics].

   Every metric is available, including any custom or calculated metrics that are built-in in [!DNL Analytics].

   请注意，在报表中，任何增大的数字都显示为正值，即使增大的数字实际上并不是所需的结果也是如此。例如，虽然您希望降低跳出率，但是较高的跳出率会显示为具有最高提升度的入选者。根据报表做出决策时，请留心这些量度及类似量度，并确定您是希望降低还是提高这些量度的数值。

You can apply the metric or audience to the report in [!DNL Target] after the activity has started, or even after the test has completed. 您无需事先知晓要衡量的确切内容。

Click to view the full [!DNL Analytics] report directly from the activity report page.

## Analysis Workspace 中的报表 {#reports-in-analysis-workspace}

您可以使用 [!DNL Adobe Analysis Workspace] 来深入挖掘和可视化数据，或揭示隐藏在表面下的洞察。

For detailed information and examples, open the [Analytics &amp; Target: Best Practices for Analysis tutorial](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), provided by [!DNL Adobe Experience League].

## 活动创建 {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

在活动创建期间，您必须在“[!UICONTROL 设置]”页面中指定活动的目标。此目标将作为报表的默认量度并且在量度选择器中始终列为第一个选项。您将无法像设置常规 Target 活动的报表那样选择报表的区段。A test with [!DNL Analytics] uses [!DNL Adobe Analytics] segments rather than [!DNL Target] audiences.

## Performing offline calculations for Analytics for Target (A4T) {#section_33A97A691F3A45D497DAF57A844388F0}

您可以为 A4T 执行离线计算，但需要在 [!DNL Analytics] 中完成数据导出步骤。

有关更多信息，请参阅[为 Analytics for Target (A4T) 执行离线计算](../../c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B)。
