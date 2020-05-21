---
keywords: a4t;analytics;analytics for target;analytics reporting source;adobe analytics as the reporting source for target
description: Adobe“Analytics for Target”(A4T) 是一种跨解决方案的集成，通过该集成，您可以基于 Analytics 转化量度和受众区段来创建活动。该集成使您能够使用 Analytics 报表来检查结果。如果您使用 Analytics 作为活动的报表源，则该活动的所有报表和分段都将基于 Analytics 数据收集。
title: 将 Adobe Analytics 作为 Adobe Target 报表源 (A4T)
subtopic: Integrating
topic: Standard
uuid: 616798a6-1587-410f-9ac6-473beb39e3fc
translation-type: tm+mt
source-git-commit: 68f356b0711abf9acf7ef631edf3656bd3dd49e3
workflow-type: tm+mt
source-wordcount: '1247'
ht-degree: 47%

---


# 将 Adobe Analytics 作为 Adobe Target 报表源 (A4T){#adobe-analytics-as-the-reporting-source-for-adobe-target-a-t}

[!DNL Adobe Analytics for Target] (A4T)是一种跨解决方案集成，允许您根据转化指标和活动细 [!DNL Analytics] 分创建受众。 The A4T integration lets you use [!DNL Analytics] reports to examine your results. If you use [!DNL Analytics] as the reporting source for an activity, all reporting and segmentation for that activity is based on [!DNL Analytics] data collection.

## A4T 概述 {#section_92B66069210C40DBA937790E8CC596CF}

The [!DNL Analytics for Target] integration between [!DNL Analytics] and [!DNL Target] provides powerful analysis and timesaving tools for your optimization program.

The three primary benefits of using [!DNL Analytics] data in [!DNL Target] are:

* Marketers can dynamically apply [!DNL Analytics] success metrics or reporting segments to [!DNL Target] activity reports at any time. 在运行活动之前不需要指定各项内容。
* 单一数据源可消除在两个不同的系统中收集数据时出现的差异。
* Your existing [!DNL Analytics] implementation collects all required data. 不需要专门为了收集报表数据而在页面上实施相关 mbox。Although, it is still recommended that you implement an order confirmation mbox for [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) activities.

>[!IMPORTANT]
>
>在开始使用 A4T 之前，您需要请求对您的帐户进行配置，以便使用该集成。可使用[此表单](https://www.adobe.com/go/audiences_cn)提交配置请求。
>
>The integration that enables [!DNL Analytics] as the data source for [!DNL Target] (A4T) represents the next generation of the Test&amp;Target to SiteCatalyst plug-in. 虽然此插件已被弃用，但已使用它的客户仍可获得支持。

If you use [!DNL Analytics] as the reporting source for an activity, all reporting and segmentation for that activity is based on [!DNL Analytics].

All [!DNL Analytics] metrics, including calculated metrics, are available in [!DNL Target] and the [!UICONTROL Target Activities] report in [!DNL Analytics]. Likewise, any segment available in [!DNL Analytics] can be applied to both solutions. You can apply the metric or audience to the report in [!DNL Target] after the activity has started, or even after the activity has completed.

Every metric is included, including any customer or calculated metrics that are built-in in [!DNL Analytics].

分类期过后，数据会在从网站收集大约一小时后显示在这些报表中。报表中的所有量度、区段和值都来自您在设置活动时选择的报表包。

在考虑使用 A4T 时，请牢记以下几点：

* To use [!DNL Analytics] as the reporting source for [!DNL Target], both you and your company must have access to [!DNL Analytics] and to [!DNL Target]. [请联系您的帐户代表](../../cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB)，以便使用这些解决方案。
* 为每个活动设置报表源。[!DNL Target] 继续收集要在报告中使用的 [!DNL Target] ，如果您希望根据收集的活动来收集数据，数据仍可 [!DNL Target]用。
* 您只能使用一个报表源。您无法从两个报表源为单个活动收集数据。
* When using A4T, all success metrics available to your activities are [!DNL Analytics] metrics. 但是，您的目标量度可以基于 mbox 调用。For example, you can use Target&#39;s out-of-the-box click-tracking capabilities with A4T instead of having to implement [!DNL Analytics] click-tracking code.
* When viewing reporting of an A4T activity in the [!DNL Target] UI, you are viewing [!DNL Analytics] data. For example, if you use the [!UICONTROL Visitor] metric in [!DNL Target], you are using the [!DNL Analytics] [!UICONTROL Visitor] metric, not the [!DNL Target] [!UICONTROL Visitors] metric, which is now called [!UICONTROL Entrants]. This difference is especially important for basic traffic metrics ([!UICONTROL Visitors], [!UICONTROL Visits], [!UICONTROL Page Views]) and conversion metrics.
* Any existing [!DNL Target] activities continue to use [!DNL Target] data collection and are not affected by enabling A4T.
* Only one mbox-based metric is allowed when using [!DNL Analytics] as the reporting source.
* A server-to-server call from [!DNL Target] to [!DNL Analytics] sends activity and experience information to [!DNL Analytics]. This integration does not result in additional server calls for either [!DNL Target] or [!DNL Analytics].

   在某些情况下，从到的分类调 [!DNL Target] 用可 [!DNL Analytics] 能会失败，活动不在中显示数据 [!DNL Analytics]。 如果发生这种情况，请 [参阅Analytics和目标集成疑难解答(A4T)](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md)。 您还可以联 [系客户关怀](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) ，获取进一步帮助。

## Supported activity types {#section_F487896214BF4803AF78C552EF1669AA}

The following table shows you which activity types support [!DNL Analytics] as the reporting source in [!DNL Target] (A4T):

| 活动类型 | 是否兼容 A4T？ | 注释（如果适用） |
|--- |--- |--- |
| 使用手动流量拆分的 A/B 活动 | 是 |  |
| 使用自动分配的 A/B 活动 | 否 |  |
| 使用自动定位的 A/B 活动 | 否 |  |
| 体验定位 (XT) | 是 |  |
| 多变量测试 (MVT) | 是 | Requires mbox-based goal metric goal to get the [!UICONTROL Element Contribution] report.  The [!UICONTROL Element Contribution] report does not currently support [!DNL Analytics] metrics. |
| 自动个性化 (AP) 活动 | 否 |  |
| “推荐”活动 | 是 |  |
| 移动设备应用程序 | 是 | 在 Mobile Services SDK 版本 4.13.1 或更高版本中受支持。有关更多信息，请参阅 [Mobile Services 文档](https://docs.adobe.com/content/help/en/mobile-services/using/home.html)。 |
| 电子邮件 | 否 |  |
| 服务器端交付 API | 是 | 有关更多信息，请参阅[服务器端：实施 Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md)。 |
| NodeJS SDK | 是 | 有关更多信息，请参阅[服务器端：实施 Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md)。 |
| AEM 6.1（或更低版本）云服务集成 | 否 |  |
| AEM 6.2（或更高版本）云服务集成 | 是 | For more information, see [Integrating with Adobe Target](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html) in the [!DNL Adobe Experience Manager] 6.2 documentation. |
| 使用重定向活动的任何优惠 | 是 | 要将重定向选件与 A4T 配合使用，需满足一些较为严格的最低要求。有关更多信息，请参阅[重定向选件 - A4T 常见问题解答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md)。 |
| Node.JS | 是 |  |

Because all activity types do not yet support A4T, it is recommended that you keep or implement important conversion mboxes, such as the `orderConfirmPage` mbox.

## Examples of A4T reports {#section_F0A43A1CB2F04E8282B909E4D7034361}

To view A4T reports in [!DNL Target], click **[!UICONTROL Activities]**, click the desired activity from the list that uses [!DNL Analytics] as its reporting source, then click the **[!UICONTROL Reports]** tab.

>[!NOTE]
>
>您可以使用[!UICONTROL 活动]页面顶部的[!UICONTROL 报表源]下拉列表来仅显示使用 [!DNL Analytics] 作为报表源的活动。

You can toggle between the [!UICONTROL Table View] and [!UICONTROL Graph View] of the report by clicking the appropriate icon at the top right side of the report.

下图显示了 A4T 报表的“[!UICONTROL 图形视图]”，其中的“[!UICONTROL 报表量度]”下拉列表显示了可用的 [!DNL Analytics] 目标量度：

![](assets/a4t_report_graph1.png)

下图显示了 A4T 报表的“[!UICONTROL 图形视图]”，其中的“[!UICONTROL 受众”下拉列表显示了可用的 ][!DNL Analytics] 受众：

![](assets/a4t_report_graph2.png)

下图显示了 A4T 报表的“[!UICONTROL 表格视图]”：

![](assets/a4t_report_table.png)

要在 [!DNL Analytics] 而不是 [!DNL Target] 中查看报表，请单击报表顶部的&#x200B;****&#x200B;在 Analytics 中查看。

## Analytics 与 Target：分析最佳实践教程 {#section_3438E6E77A464424B717A4FD333B84B2}

Open the [Analytics &amp; Target: Best Practices for Analysis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) tutorial, provided by [!DNL Adobe Experience League].

## 培训视频：

以下视频包含有关本主题中讨论的概念的更多信息。

### 目标分析(A4T)(4:32)概 ![述徽章](/help/assets/overview.png)

This video explains how to use [!DNL Analytics] as a reporting source in [!DNL Target] to drive the analysis of your optimization program.

* 介绍什么是 A4T 以及为何要使用它
* 介绍 A4T 的工作原理
* 了解使用 A4T 之前需要满足的先决条件

>[!VIDEO](https://video.tv.adobe.com/v/17384)

### 分析/目标集成(A4T)(40:33)教 ![程徽章](/help/assets/tutorial.png)

此视频是“[办公时间](../../cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)”的录像，“办公时间”是 Adobe 客户关怀团队发起的一项计划。

* 如何设置集成并验证集成可正常工作
* 集成的工作原理
* 了解要在 Analytics 中使用的理想报表
* 关于 A4T 的常见问题解答

[分析/目标集成(A4T)办公时间](https://helpx.adobe.com/customer-care-office-hours/target/analytics-target-A4T-integration.html)