---
keywords: a4t;analytics;analytics for target;analytics reporting source;adobe analytics as the reporting source for target
description: Adobe“Analytics for Target”(A4T) 是一种跨解决方案的集成，通过该集成，您可以基于 Analytics 转化量度和受众区段来创建活动。该集成使您能够使用 Analytics 报表来检查结果。如果您使用 Analytics 作为活动的报表源，则该活动的所有报表和分段都将基于 Analytics 数据收集。
title: 将 Adobe Analytics 作为 Adobe Target 报表源 (A4T)
feature: a4t general
translation-type: tm+mt
source-git-commit: fe6826e25b2d7c66ab245492f610585d0f5b3d69
workflow-type: tm+mt
source-wordcount: '1306'
ht-degree: 45%

---


# 将 Adobe Analytics 作为 Adobe Target 报表源 (A4T)

[!DNL Adobe Analytics for Target] (A4T)是一种跨解决方案集成，允许您根据转化指标和活动 [!DNL Analytics] 细分创建受众。A4T集成允许您使用[!DNL Analytics]报告来检查结果。 如果使用[!DNL Analytics]作为报告的活动源，则该活动的所有报告和分段均基于[!DNL Analytics]数据收集。

## A4T 概述 {#section_92B66069210C40DBA937790E8CC596CF}

[!DNL Analytics]和[!DNL Target]之间的[!DNL Analytics for Target]集成为优化项目提供了强大的分析和省时工具。

在[!DNL Target]中使用[!DNL Analytics]数据的三个主要好处是：

* 营销人员可以随时将[!DNL Analytics]成功指标或报告细分动态应用于[!DNL Target]活动报告。 在运行活动之前不需要指定各项内容。
* 单一数据源可消除在两个不同的系统中收集数据时出现的差异。
* 您现有的[!DNL Analytics]实现会收集所有必需的数据。 不需要专门为了收集报表数据而在页面上实施相关 mbox。但是，仍建议您为[Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md)(AP)活动实施订单确认mbox。

>[!IMPORTANT]
>
>在开始使用 A4T 之前，您需要请求对您的帐户进行配置，以便使用该集成。可使用[此表单](https://www.adobe.com/go/audiences_cn)提交配置请求。
>
>使[!DNL Analytics]成为[!DNL Target](A4T)数据源的集成表示下一代Test&amp;目标到SiteCatalyst插件。 虽然此插件已被弃用，但已使用它的客户仍可获得支持。

如果使用[!DNL Analytics]作为报告的活动源，则该活动的所有报告和分段均基于[!DNL Analytics]。

所有[!DNL Analytics]度量（包括计算度量）均在[!DNL Target]和[!DNL Analytics]的[!UICONTROL 目标活动]报告中可用。 同样，[!DNL Analytics]中可用的任何段都可以应用于这两种解决方案。 在活动开始后，甚至在活动完成后，您都可以将度量或受众应用到[!DNL Target]中的报表。

包括每个指标，包括[!DNL Analytics]中内置的任何客户或计算指标。

分类期过后，数据会在从网站收集大约一小时后显示在这些报表中。报表中的所有量度、区段和值都来自您在设置活动时选择的报表包。

在考虑使用 A4T 时，请牢记以下几点：

* 要使用[!DNL Analytics]作为[!DNL Target]的报告源，您和您的公司都必须有权访问[!DNL Analytics]和[!DNL Target]。 [请联系您的帐户代表](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB)，以便使用这些解决方案。
* 为每个活动设置报表源。[!DNL Target] 继续收集要在报告中使用的数 [!DNL Target] 据，如果您希望根据所收集的数据来进行活动，则仍可使用 [!DNL Target]数据。
* 您只能使用一个报表源。您无法从两个报表源为单个活动收集数据。
* 使用A4T时，活动可用的所有成功指标均为[!DNL Analytics]指标。 但是，您的目标量度可以基于 mbox 调用。例如，您可以将目标的现成单击跟踪功能与A4T结合使用，而不必实现[!DNL Analytics]单击跟踪代码。
* 在[!DNL Target] UI中查看A4T报告活动时，您正在查看[!DNL Analytics]数据。 例如，如果您在[!DNL Target]中使用[!UICONTROL 访客]指标，则使用[!DNL Analytics] [!UICONTROL 访客]指标，而不是[!DNL Target] [!UICONTROL 访客]指标，现在称为[!UICONTROL 新进者]。 这一差异对于基本流量度量([!UICONTROL 访客]、[!UICONTROL 访问]、[!UICONTROL 页面视图])和转化度量尤为重要。
* 任何现有的[!DNL Target]活动都继续使用[!DNL Target]数据收集，并且不会因启用A4T而受到影响。
* 当使用[!DNL Analytics]作为报告源时，仅允许一个基于mbox的度量。
* 从[!DNL Target]到[!DNL Analytics]的服务器到服务器调用会向[!DNL Analytics]发送活动和体验信息。 此集成不会导致对[!DNL Target]或[!DNL Analytics]进行额外的服务器调用。

   在某些情况下，从[!DNL Target]到[!DNL Analytics]的分类调用可能会失败，活动不显示[!DNL Analytics]中的数据。 如果发生这种情况，请参阅[分析和目标集成疑难解答(A4T)](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md)。 您还可以[联系客户关怀部门](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB)以获得进一步帮助。

## 支持的活动类型{#section_F487896214BF4803AF78C552EF1669AA}

下表显示了哪些活动类型支持[!DNL Analytics]作为[!DNL Target](A4T)中的报告源：

| 活动类型 | 是否兼容 A4T？ | 注释（如果适用） |
|--- |--- |--- |
| 使用手动流量拆分的 A/B 活动 | 是 |  |
| 使用自动分配的 A/B 活动 | 是 | 请参阅[对自动分配和自动目标活动的](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa)目标分析(A4T)支持。 |
| 使用自动定位的 A/B 活动 | 是 | 请参阅[对自动分配和自动目标活动的](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa)目标分析(A4T)支持。 |
| 体验定位 (XT) | 是 |  |
| 多变量测试 (MVT) | 是 | 需要基于mbox的目标指标目标来获取[!UICONTROL 元素贡献]报告。  [!UICONTROL 元素贡献]报告当前不支持[!DNL Analytics]度量。 |
| 自动个性化 (AP) 活动 | 否 |  |
| “推荐”活动 | 是 |  |
| 移动设备应用程序 | 是 | 在 Mobile Services SDK 版本 4.13.1 或更高版本中受支持。有关更多信息，请参阅 [Mobile Services 文档](https://experienceleague.adobe.com/docs/mobile-services/using/home.html)。 |
| 电子邮件 | 否 |  |
| 服务器端交付 API | 是 | 有关更多信息，请参阅[服务器端：实施 Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md)。 |
| NodeJS SDK | 是 | 有关更多信息，请参阅[服务器端：实施 Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md)。 |
| AEM 6.1（或更低版本）云服务集成 | 否 |  |
| AEM 6.2（或更高版本）云服务集成 | 是 | 有关详细信息，请参阅[!DNL Adobe Experience Manager] 6.2文档中的[与Adobe Target](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html)集成。 |
| 使用重定向活动的任何优惠 | 是 | 要将重定向选件与 A4T 配合使用，需满足一些较为严格的最低要求。有关更多信息，请参阅[重定向选件 - A4T 常见问题解答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md)。 |
| Node.JS | 是 | 有关详细信息，请参阅&#x200B;*Adobe TargetSDK*&#x200B;指南中的[Node.js SDK](https://adobetarget-sdks.gitbook.io/docs/sdk-reference-guides/nodejs-sdk)。 |
| Java SDK | 是 | 有关详细信息，请参阅&#x200B;*Adobe Target* SDK指南中的[Java SDK](https://adobetarget-sdks.gitbook.io/docs/sdk-reference-guides/java-sdk)。 |

由于所有活动类型尚不支持A4T，建议您保留或实施重要的转换mbox，如`orderConfirmPage` mbox。

## A4T报告示例{#section_F0A43A1CB2F04E8282B909E4D7034361}

要视图[!DNL Target]中的A4T报告，请单击&#x200B;**[!UICONTROL 活动]**，从使用[!DNL Analytics]作为报告源的列表中单击所需的活动，然后单击&#x200B;**[!UICONTROL 报告]**&#x200B;选项卡。

>[!NOTE]
>
>您可以使用[!UICONTROL 活动]页面顶部的[!UICONTROL 报表源]下拉列表来仅显示使用 [!DNL Analytics] 作为报表源的活动。

单击报表右上方的相应图标，可在报表的[!UICONTROL 表视图]和[!UICONTROL 图视图]之间切换。

下图显示了 A4T 报表的“[!UICONTROL 图形视图]”，其中的“[!UICONTROL 报表量度]”下拉列表显示了可用的 [!DNL Analytics] 目标量度：

![](assets/a4t_report_graph1.png)

下图显示了 A4T 报表的“[!UICONTROL 图形视图]”，其中的“[!UICONTROL 受众”下拉列表显示了可用的 ][!DNL Analytics] 受众：

![](assets/a4t_report_graph2.png)

下图显示了 A4T 报表的“[!UICONTROL 表格视图]”：

![](assets/a4t_report_table.png)

要在 [!DNL Analytics] 而不是 [!DNL Target] 中查看报表，请单击报表顶部的&#x200B;****&#x200B;在 Analytics 中查看。

## Analytics 与 Target：分析最佳实践教程 {#section_3438E6E77A464424B717A4FD333B84B2}

打开[分析和目标:分析](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)教程的最佳实践，由[!DNL Adobe Experience League]提供。

## 培训视频：

以下视频包含有关本主题中讨论的概念的更多信息。

### 目标分析(A4T)(4:32)![概述徽章](/help/assets/overview.png)

此视频介绍如何在[!DNL Target]中将[!DNL Analytics]用作报告源，以推动优化项目的分析。

* 介绍什么是 A4T 以及为何要使用它
* 介绍 A4T 的工作原理
* 了解使用 A4T 之前需要满足的先决条件

>[!VIDEO](https://video.tv.adobe.com/v/17384)

### 分析/目标集成(A4T)(40:33)![教程徽章](/help/assets/tutorial.png)

此视频是“[办公时间](/help/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)”的录像，“办公时间”是 Adobe 客户关怀团队发起的一项计划。

* 如何设置集成并验证集成可正常工作
* 集成的工作原理
* 了解要在 Analytics 中使用的理想报表
* 关于 A4T 的常见问题解答

[分析/目标集成(A4T)办公时间](https://helpx.adobe.com/customer-care-office-hours/target/analytics-target-A4T-integration.html)