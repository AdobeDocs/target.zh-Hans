---
description: Adobe“Analytics for Target”(A4T) 是一种跨解决方案的集成，通过该集成，您可以基于 Analytics 转化量度和受众区段来创建活动。该集成使您能够使用 Analytics 报表来检查结果。如果您使用 Analytics 作为活动的报表源，则该活动的所有报表和分段都将基于 Analytics 数据收集。
keywords: A4T;Analytics;Analytics for Target;Analytics 报表源;Adobe Analytics 作为 Target 报表源
seo-description: Adobe“Analytics for Target”(A4T) 是一种跨解决方案的集成，通过该集成，您可以基于 Analytics 转化量度和受众区段来创建活动。该集成使您能够使用 Analytics 报表来检查结果。如果您使用 Analytics 作为活动的报表源，则该活动的所有报表和分段都将基于 Analytics 数据收集。
seo-title: 将 Adobe Analytics 作为 Adobe Target 报表源 (A4T)
solution: Target
subtopic: 多变量测试
title: 将 Adobe Analytics 作为 Adobe Target 报表源 (A4T)
topic: Standard
uuid: 616798a6-1587-410f-9ac6-473beb39e3fc
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 将 Adobe Analytics 作为 Adobe Target 报表源 (A4T){#adobe-analytics-as-the-reporting-source-for-adobe-target-a-t}

Adobe“Analytics for Target”(A4T) 是一种跨解决方案的集成，通过该集成，您可以基于 Analytics 转化量度和受众区段来创建活动。A4T 集成使您能够使用 Analytics 报表来检查结果。如果您使用 Analytics 作为活动的报表源，则该活动的所有报表和分段都将基于 Analytics 数据收集。

## A4T 概述 {#section_92B66069210C40DBA937790E8CC596CF}

Analytics 和 Target 之间的 Analytics for Target 集成为您的优化计划提供了强大的分析和省时工具。

在 Target 中使用 Analytics 数据主要有以下三个好处：

* 营销人员可以随时将 Analytics 成功量度或报表区段动态应用到 Target 活动报表。在运行活动之前不需要指定各项内容。
* 单一数据源可消除在两个不同的系统中收集数据时出现的差异。
* 您现有的 Adobe Analytics 实施可收集所有必需的数据。不需要专门为了收集报表数据而在页面上实施相关 mbox。尽管如此，仍建议您为自动个性化 (AP) 活动实施订单确认 mbox。

>[!IMPORTANT]
>
>在开始使用 A4T 之前，您需要请求对您的帐户进行配置，以便使用该集成。可使用[此表单](https://www.adobe.com/go/audiences)提交配置请求。
>
>可启用 Adobe Analytics 作为 Adobe Target 数据源 (A4T) 的集成代表了新一代 Test&amp;Target 与 SiteCatalyst 集成插件。虽然此插件已被弃用，但已使用它的客户仍可获得支持。

如果您使用 Analytics 作为活动的报表源，则该活动的所有报表和分段都将基于 Analytics。

所有 Analytics 量度（包括计算量度）均可在 Target Standard/Premium 中以及 Analytics 的 Target 活动报表中使用。同样，Analytics 中提供的任何区段也均可应用于这两种解决方案。您可以在测试开始后，甚至在测试完成后，将量度或受众应用到 Target Standard/Premium 中的报表。

每个量度均会包含在内，包括 Analytics 中内置的所有客户或计算量度。

分类期过后，数据会在从网站收集大约一小时后显示在这些报表中。报表中的所有量度、区段和值都来自您在设置活动时选择的报表包。

在考虑使用 A4T 时，请牢记以下几点：

* 要使用 Adobe Analytics 作为 Adobe Target 报表源，您和贵公司都必须有权访问 Adobe Analytics 和 Adobe Target。[请联系您的帐户代表](../../cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB)，以便使用这些解决方案。
* 为每个活动设置报表源。Target 会继续收集要用于报表的数据，如果您希望使活动基于由 Target 收集的数据，则仍然可以使用 Target 数据。
* 您只能使用一个报表源。您无法从两个报表源为单个活动收集数据。
* 使用 A4T 时，可用于您的活动的所有成功量度都是 Analytics 量度。但是，您的目标量度可以基于 mbox 调用。例如，您可以将 Target 的现成点击跟踪功能与 A4T 配合使用，而无需实施 Analytics 点击跟踪代码。
* 在 Target UI 中查看 A4T 活动报表时，您查看的是 Analytics 数据。例如，如果您在 Target 中使用访客量度，则您使用的是 Analytics 访客量度，而不是 Target 访客量度（现称为“参加者”）。这种差异对基本流量量度（访客、访问次数、页面查看次数）和转化量度尤为重要。
* 任何现有的 Target 活动都将继续使用 Target 数据收集，启用 A4T 后并不会影响这些活动。
* 使用 Analytics 作为报表源时，只允许使用一个基于 mbox 的量度。
* 从 Target 到 Analytics 的服务器到服务器调用会向 Analytics 发送活动和体验信息。此集成不会为 Target 或 Analytics 生成其他服务器调用。

## 支持的活动类型 {#section_F487896214BF4803AF78C552EF1669AA}

下表显示了哪些活动类型支持将 Analytics 作为报表源 (A4T)：

| 活动类型 | 是否兼容 A4T？ | 注释（如果适用） |
|--- |--- |--- |
| 使用手动流量拆分的 A/B 活动 | 是 |  |
| 使用自动分配的 A/B 活动 | 否 |  |
| 使用自动定位的 A/B 活动 | 否 |  |
| 体验定位 (XT) | 是 |  |
| 多变量测试 (MVT) | 是 | 需要基于 mbox 的目标量度来获取元素贡献报表。元素贡献报表目前不支持 Analytics 量度。 |
| 自动个性化 (AP) 活动 | 否 |  |
| “推荐”活动 | 是 |  |
| 移动设备应用程序 | 是 | 在 Mobile Services SDK 版本 4.13.1 或更高版本中受支持。有关更多信息，请参阅 [Mobile Services 文档](https://marketing.adobe.com/resources/help/en_US/mobile/)。 |
| 电子邮件 | 否 |  |
| 服务器端交付 API | 是 | 有关更多信息，请参阅[服务器端：实施 Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md)。 |
| NodeJS SDK | 是 | 有关更多信息，请参阅[服务器端：实施 Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md)。 |
| AEM 6.1（或更低版本）云服务集成 | 否 |  |
| AEM 6.2（或更高版本）云服务集成 | 是 | 有关更多信息，请参阅 Adobe Experience Manager 6.2 文档中的[与 Adobe Target 集成](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html)。 |
| 任何使用重定向选件的活动 | 是 | 要将重定向选件与 A4T 配合使用，需满足一些较为严格的最低要求。有关更多信息，请参阅[重定向选件 - A4T 常见问题解答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md)。 |
| Node.JS | 是 |  |

由于所有活动类型尚不支持 A4T，因此建议您保留或实施重要的转化 mbox，例如“orderConfirmPage”mbox。

## A4T 报表的示例 {#section_F0A43A1CB2F04E8282B909E4D7034361}

要在 [!DNL Target]**中查看 A4T 报表，请单击[!UICONTROL 活动]**，在列表中单击使用 [!DNL Analytics] 作为报表源的所需活动，然后单击 **[!UICONTROL 报表]选项卡。**

>[!NOTE]
>
>您可以使用[!UICONTROL 活动]页面顶部的[!UICONTROL 报表源]下拉列表来仅显示使用 [!DNL Analytics] 作为报表源的活动。

您可以单击报表右上方的相应图标，在报表的“表格视图”和“[!UICONTROL 图形视图]”之间进行切换。

下图显示了 A4T 报表的“[!UICONTROL 图形视图]”，其中的“[!UICONTROL 报表量度]”下拉列表显示了可用的 [!DNL Analytics] 目标量度：

![](assets/a4t_report_graph1.png)

下图显示了 A4T 报表的“[!UICONTROL 图形视图]”，其中的“[!UICONTROL 受众”下拉列表显示了可用的 ][!DNL Analytics] 受众：

![](assets/a4t_report_graph2.png)

下图显示了 A4T 报表的“[!UICONTROL 表格视图]”：

![](assets/a4t_report_table.png)

要在 [!DNL Analytics] 而不是 [!DNL Target] 中查看报表，请单击报表顶部的 **[!UICONTROL ]在 Analytics 中查看**。

## Analytics 与 Target：分析最佳实践教程 {#section_3438E6E77A464424B717A4FD333B84B2}

打开由 Adobe Experience League 提供的 [Analytics 与 Target：分析最佳实践](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)教程。

## 培训视频：

以下视频包含有关本文中所讨论概念的详细信息。

### Analytics for Target (A4T) (4:32)

以下视频介绍了如何在 Adobe Target 中使用 Adobe Analytics 作为报表源来促进对优化计划的分析。

* 介绍什么是 A4T 以及为何要使用它
* 介绍 A4T 的工作原理
* 了解使用 A4T 之前需要满足的先决条件

>[!VIDEO](https://video.tv.adobe.com/v/17384?captions=chi_hans)

### Analytics 与 Target 集成 (A4T) (40:33)

此视频是“[办公时间](../../cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)”的录像，“办公时间”是 Adobe 客户关怀团队发起的一项计划。

* 如何设置集成并验证集成可正常工作
* 集成的工作原理
* 了解要在 Analytics 中使用的理想报表
* 关于 A4T 的常见问题解答

>[!VIDEO](https://video.tv.adobe.com/v/22223/?captions=chi_hans)