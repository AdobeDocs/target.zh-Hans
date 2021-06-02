---
keywords: a4t;analytics;analytics for target;analytics报表源；adobe analytics作为target的报表源；atjs;at.js;adobe experience platform web sdk;platform web sdk;platform sdk
description: 使用 [!DNL Analytics] for [!DNL Target] (A4T) to create activities based on [!DNL Analytics] conversion metrics and audience segments and use [!DNL Analytics] 报告来检查结果。
title: 什么是 [!DNL Analytics] for [!DNL Target] (A4T)?
feature: Analytics for Target (A4T)
exl-id: 5bb80b03-8209-4932-a838-0e11c5865133
source-git-commit: 14dfc3e19333848e50324a61539ddf693e17d3ce
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 31%

---

# [!DNL Adobe Analytics] 作为(A4T) [!DNL Adobe Target] 的报表源

[!DNL Adobe Analytics for Target] (A4T)是一种跨解决方案的集成，允许您根据转化量度和 [!DNL Analytics] 受众区段创建活动。A4T集成允许您使用[!DNL Analytics]报表来检查结果。 如果使用[!DNL Analytics]作为活动的报表源，则该活动的所有报表和分段都将基于[!DNL Analytics]数据收集。

## 概述 {#section_92B66069210C40DBA937790E8CC596CF}

[!DNL Analytics]和[!DNL Target]之间的[!DNL Analytics for Target]集成为优化程序提供了强大的分析和省时工具。

在[!DNL Target]中使用[!DNL Analytics]数据的三大好处是：

* 营销人员可以随时将[!DNL Analytics]成功量度或报表区段动态应用到[!DNL Target]活动报表。 在运行活动之前不需要指定各项内容。
* 单一数据源可消除在两个不同的系统中收集数据时出现的差异。
* 您现有的[!DNL Analytics]实施会收集所有必需的数据。 不需要专门为了收集报表数据而在页面上实施相关 mbox。

如果使用[!DNL Analytics]作为活动的报表源，则该活动的所有报表和分段都将基于[!DNL Analytics]。

所有[!DNL Analytics]量度（包括计算量度）均在[!DNL Target]和[!DNL Analytics]中的[!UICONTROL 目标活动]报表中可用，但有一个例外。 不支持[!UICONTROL 提升度和置信度]的计算量度。 同样，[!DNL Analytics]中可用的任何区段都可应用于两个解决方案。 在[!DNL Target]中，您可以在活动开始后，甚至在活动结束后，将量度或受众应用于报表。

包含每个量度，包括[!DNL Analytics]中内置的任何自定义或计算量度。

分类期过后，数据会在从网站收集大约一小时后显示在这些报表中。报表中的所有量度、区段和值都来自您在设置活动时选择的报表包。

在考虑使用 A4T 时，请牢记以下几点：

* 要使用[!DNL Analytics]作为[!DNL Target]的报表源，您和您的公司都必须有权访问[!DNL Analytics]和[!DNL Target]。 [请联系您的帐户代表](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB)，以便使用这些解决方案。
* 为每个活动设置报表源。[!DNL Target] 会继续收集要在报表中使用的数据， [!DNL Target] 如果您希望将活动基于由收集的数据，则仍可以使用数 [!DNL Target]据。
* 使用一个报表源或另一个报表源。 您无法从两个报表源为单个活动收集数据。
* 使用A4T时，您活动可用的所有成功量度都是[!DNL Analytics]量度。 但是，如果使用at.js，则您的目标量度可以基于mbox调用。 例如，您可以将Target的现成点击跟踪功能与A4T结合使用，而不必实施[!DNL Analytics]点击跟踪代码。
* 在[!DNL Target] UI中查看A4T活动的报表时，您会查看[!DNL Analytics]数据。 例如，如果您在[!DNL Target]中使用[!UICONTROL 访客]量度，则使用的是[!DNL Analytics] [!UICONTROL 访客]量度，而不是[!DNL Target] [!UICONTROL 访客]量度，该量度现在称为[!UICONTROL 参加者]。 此差异对于基本流量量度（[!UICONTROL 访客]、[!UICONTROL 访问次数]、[!UICONTROL 页面查看次数]）和转化量度尤为重要。
* 任何现有的[!DNL Target]活动都会继续使用[!DNL Target]数据收集，并且不会受启用A4T的影响。
* 使用A4T时，只允许使用一个基于mbox的量度。
* 从[!DNL Target]到[!DNL Analytics]的服务器到服务器调用会将活动和体验信息发送到[!DNL Analytics]。 此集成不会导致对[!DNL Target]或[!DNL Analytics]进行额外的服务器调用。

   在某些情况下，从[!DNL Target]到[!DNL Analytics]的分类会失败，并且活动不显示[!DNL Analytics]中的数据。 请参阅[Analytics与Target集成(A4T)](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md)故障诊断。 您还可以[联系客户关怀团队](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB)以获取进一步帮助。

## 实施A4T

有关使用at.js和[!DNL Adobe Experience Platform Web SDK]实施A4T的信息，请参阅[用于 [!DNL Target] 实施](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)的Analytics。

## 支持的活动类型 {#section_F487896214BF4803AF78C552EF1669AA}

以下部分包含有关使用[!DNL Adobe Experience Platform Web SDK]或at.js时支持的活动类型的信息：

| 活动类型 | 是否兼容 A4T？ | 注释（如果适用） |
|--- |--- |--- |
| [使用手动流量拆分的 A/B 活动](/help/c-activities/t-test-ab/test-ab.md) | 是 |  |
| [使用自动分配的 A/B 活动](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | 是 | 请参阅[A4T对自动分配和自动定位活动的支持](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md) |
| [使用自动定位的 A/B 活动](/help/c-activities/auto-target/auto-target-to-optimize.md) | 是 | 请参阅[A4T对自动分配和自动定位活动的支持](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md)。 |
| [Experience Targeting (XT)](/help/c-activities/t-experience-target/experience-target.md) | 是 |  |
| [多变量测试 (MVT)](/help/c-activities/c-multivariate-testing/multivariate-testing.md) | 是 | 需要基于mbox的目标量度目标来获取[!UICONTROL 元素贡献]报表。 [!UICONTROL 元素贡献]报表当前不支持[!DNL Analytics]量度。 |
| [自动个性化 (AP) 活动](/help/c-activities/t-automated-personalization/automated-personalization.md) | 否 |  |
| [“推荐”活动](/help/c-recommendations/recommendations.md) | 是 |  |
| [使用重定向选件的任何活动](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) | 是 |

由于所有活动类型尚不支持A4T，因此建议您保留或实施重要的转化mbox，如`orderConfirmPage` mbox。

## A4T报表示例 {#section_F0A43A1CB2F04E8282B909E4D7034361}

要在[!DNL Target]中查看A4T报表，请单击&#x200B;**[!UICONTROL 活动]**，在列表中单击使用[!DNL Analytics]作为报表源的所需活动，然后单击&#x200B;**[!UICONTROL 报表]**&#x200B;选项卡。

>[!NOTE]
>
>您可以使用[!UICONTROL 活动]页面顶部的[!UICONTROL 报表源]下拉列表来仅显示使用A4T的活动。

您可以单击报表右上方的相应图标，在报表的[!UICONTROL 表格视图]和[!UICONTROL 图形视图]之间进行切换。

下图显示了 A4T 报表的“[!UICONTROL 图形视图]”，其中的“[!UICONTROL 报表量度]”下拉列表显示了可用的 [!DNL Analytics] 目标量度：

![](assets/a4t_report_graph1.png)

下图显示了 A4T 报表的“[!UICONTROL 图形视图]”，其中的“[!UICONTROL 受众”下拉列表显示了可用的 ][!DNL Analytics] 受众：

![](assets/a4t_report_graph2.png)

下图显示了 A4T 报表的“[!UICONTROL 表格视图]”：

![](assets/a4t_report_table.png)

要在 [!DNL Analytics] 而不是 [!DNL Target] 中查看报表，请单击报表顶部的&#x200B;****&#x200B;在 Analytics 中查看。

## Analytics 与 Target：分析最佳实践教程 {#section_3438E6E77A464424B717A4FD333B84B2}

打开[Analytics和Target:Analysis最佳实践](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)教程，由[!DNL Adobe Experience League]提供。

## 培训视频：

以下视频包含有关本主题中所讨论概念的更多信息。

### Analytics for Adobe Target(A4T)(4:32) ![概述徽章](/help/assets/overview.png)

此视频介绍如何在[!DNL Target]中使用[!DNL Analytics]作为报表源来驱动优化程序的分析。

* 介绍什么是 A4T 以及为何要使用它
* 介绍 A4T 的工作原理
* 了解使用 A4T 之前需要满足的先决条件

>[!VIDEO](https://video.tv.adobe.com/v/17384)

### Analytics/Adobe Target集成(A4T)(40:33) ![教程徽章](/help/assets/tutorial.png)

此视频是“[办公时间](/help/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)”的录像，“办公时间”是 Adobe 客户关怀团队发起的一项计划。

* 如何设置集成并验证集成可正常工作
* 集成的工作原理
* 了解要在 Analytics 中使用的理想报表
* 关于 A4T 的常见问题解答

[Analytics/Target集成(A4T)办公时间](https://helpx.adobe.com/cn/customer-care-office-hours/target/analytics-target-A4T-integration.html)

>[!MORELIKETHIS]
>
>* [实施 [!DNL Target] 的Analytics](/help/c-integrating-target-with-mac/a4t/a4timplementation.md):包含at.js和平台Web SDK的实施信息。
>* [重定向选件 - A4T 常见问题解答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md)
* [什么是Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html):包含有关Platform Web SDK的概述信息。
* [Target概述](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html):包含特定于和 [!DNL Target] 的信 [!DNL Platform Web SDK]息。

