---
keywords: faq;常见问题解答;analytics for target;a4T;报表;报告;查看报表;查看报告;计数方法;展示次数;访客;访问次数;默认量度;活动转化;未指定
description: 查找有关在使用Analytics for [!DNL Target] (A4T)时查看报表的常见问题解答。 A4T允许您对 [!DNL Target] 活动使用Analytics报表。
title: 查找有关使用A4T查看报表的问题答案？
feature: Analytics for Target (A4T)
exl-id: a02eeb34-3975-424b-a046-e51f10ae1823
source-git-commit: c747a8a0ed480130f254818e21b98addca16ca41
workflow-type: tm+mt
source-wordcount: '2539'
ht-degree: 26%

---

# 查看报表 - A4T 常见问题解答

本主题包含有关在使用[!DNL Adobe Analytics]作为[!DNL Adobe Target] (A4T)的报表源时查看报表的常见问题解答。

## 我能否在[!DNL Target]中查看我的[!DNL Analysis Workspace]活动数据？ {#workspace}

+++回答
您可以使用[!DNL Analysis Workspace]来分析您的[!DNL Target]活动和体验。 通过[Analytics for Target面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=zh-Hans)，最多可查看三个成功量度的提升度和置信度。 您还可以使用表格和可视化图表深入了解。

有关详细信息和示例，请打开由[提供的](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)Analytics &amp; Target：分析最佳实践教程[!UICONTROL Adobe Experience League]。

+++

## 在[!DNL Analysis Workspace]中可在何处应用区段？ {#segmentation}

+++回答
区段最常用于区段放置区域中面板的顶部。 区段将应用于面板中的所有表格和可视化图表。 此技术对于查看测试如何影响一部分人最有用（例如，此测试对英国人的表现如何）？

区段也可以直接在自由格式表中分层，但请注意，您必须将其叠加到整个表中，以便在A4T面板中保留提升和置信度计算结果。 面板中当前不支持列级区段。

+++

## [!DNL Analysis Workspace]中使用了哪个Attribution IQ模型？

+++回答
在[!DNL Target]中使用[!DNL Analysis Workspace]活动展示和转化时，“同一次接触”Attribution IQ模型是应用于量度的默认模型，以确保准确计数。 这种模式在99%的案例中效果很好。 但是，您可以在Attribution IQ中覆盖此标准归因。

+++

## 在为特定[!DNL Target]活动应用点击区段时，为何会返回不相关的体验？ {#activity-segmentation}

+++回答
发送到 [!DNL Target] 的 [!DNL Analytics] 变量具有 90 天的默认有效期。（注意：如果需要，客户关怀团队可以调整此到期期限）。 在此到期窗口内，当访客在网站中导航时，他们属于许多[!DNL Target]活动，这些活动都在维度中收集。

当您对要存在于点击中的活动进行分段时，您将获得属于该活动的所有体验&#x200B;*以及*&#x200B;保留在该点击上的任何其他体验。

+++

## 在配置我的[!UICONTROL Goal Metrics]时，为何无法访问[!UICONTROL Advanced Settings]？

+++回答
对于使用[!DNL Analytics]作为报表源(A4T)的活动，目标量度使用“[!UICONTROL Increment Count & Keep User in Activity]”和“[!UICONTROL On Every Impression]”设置。 这些设置是&#x200B;*不可配置的*。

有关更多信息，请参阅配置目标指标时为何无法访问高级设置选项？ 在[量度定义中 — A4T常见问题解答](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md)。

+++

## 是否应使用访客数、访问次数或活动展示次数作为我的标准化量度（即计数方法）？ {#metrics}

+++回答
有几个选项可用于在A4T报表中标准化量度。 此量度（也称为计数方法）将作为提升计算的分母。 此外，它也会在应用置信度计算之前影响数据汇总的方式。

* ***独特访客***&#x200B;在用户首次符合活动资格时递增一次。
* 用户（独特访客）进入活动后，即使后续访问中未查看该活动，每个会话的&#x200B;***访问次数***&#x200B;也会增加。
* 每次提供活动内容时，***活动展示次数***&#x200B;递增。 （由[!DNL Target]测量）。

当访客查看包含活动的页面时，系统会为该访客设置一个变量以包含该活动的名称。有关每种计数方法的比较方式，请参阅下面的详细情景。

请考虑以下事项：

* 当用户符合活动条件并从[!DNL Target]返回内容时，上述量度会触发。 这并不一定意味着用户查看了该产品建议。如果活动体验未显示且用户未向下滚动页面，则表示该产品建议由 [!DNL Target] 提供，但用户并未查看。
* [!UICONTROL Activity Impressions] （由[!DNL Target]测量）和[!UICONTROL Instances] （由[!DNL Analytics]测量）相等，除非同一活动中的同一页面同时有多个mbox调用。 这会导致多个[!UICONTROL Activity Impressions]被计数，但只有一个[!UICONTROL Instance]。

有关详细信息，请参阅[Analysis Workspace教程](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=zh-Hans)中的&#x200B;*如何在Adobe Target中为自动定位活动设置A4T报告*。

+++

## 为什么[!DNL Analysis Workspace]中的“活动展示次数”和“活动转化次数”高于[!UICONTROL Reports & Analytics]？ {#sametouch}

+++回答
[!DNL Reports & Analytics]将同接触归因模型应用于“活动展示次数”和“活动转化次数”，而[!DNL Analysis Workspace]显示原始量度，由于[!DNL Target]维度的持久性，这些量度可能会虚增。

要评估[!UICONTROL Activity Impressions]中的准确[!UICONTROL Activity Conversions]和[!DNL Analysis Workspace]量度，请确保这两个量度都应用了[!UICONTROL Same Touch]归因模型。 可以通过单击列设置齿轮，启用[!UICONTROL Non-default attribution models]，然后选择[!UICONTROL Same Touch]来应用模型。 在[Analytics工具指南](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/attribution.html)的&#x200B;*Attributes IQ概述*&#x200B;中了解有关归因的更多信息。

+++

## 如果营销人员在活动设置期间选择了[!DNL Analytics]量度，则“活动转化”意味着什么？ {#section_F3EBACF85AF846E9B366A549AAB64356}

+++回答
如果选择[!DNL Analytics]指标作为活动的转化指标，则“活动转化”为空。

+++

## 为什么我在[!DNL Analytics]报表中看到“未指定”？ 这是什么意思？ {#unspecified}

+++回答
在其他报表中，“未指定”意味着数据不符合分类规则，但在 A4T 中，不应出现此种情况。如果您看到“未指定”，则表示分类服务尚未运行。活动数据一般需要 24 到 72 小时才能显示在报表中。即使这些活动在此时间之前并未显示在报表中，但与这些活动关联的所有访客数据都会被捕获，并在分类完成时显示。

分类期过后，数据会在从网站收集大约一小时后显示在这些报表中。报表中的所有量度、区段和值都来自您在设置活动时选择的报告包。

如果已对该活动进行分类，并且您仍然在报表中看到“未指定”行，请确保报表未使用非[!DNL Target]指标显示数据。 除非报表使用特定于[!DNL Target]的量度，否则该“未指定”行包含与[!DNL Target]无关的调用事件。 该行将不包含任何与[!DNL Target]关联的信息（例如，访客数/访问次数/展示次数）。

+++

## 为什么即便在停用活动之后，仍会将[!DNL Target]个量度发送到[!DNL Analytics]？ {#section_38AA8380A4D54A18972F1EF3E73E22EF}

+++回答
发送到 [!DNL Target] 的 [!DNL Analytics] 变量具有 90 天的默认有效期。如果需要，客户关怀团队可以调整此到期期限。 该设置对于所有活动都是全局的；但是，不应针对一种情况调整该设置。

您可能会看到在过期后发送到[!DNL Target]的[!DNL Analytics]变量，因为过期时间为90天，但前提是该用户从未看到其他启用A4T的[!DNL Target]活动。 如果用户在第 45 天返回网站并查看了另一个活动，则整个 A4T eVar 值会将其计数器重置为 90 天。这意味着从第 1 天开始的第一个营销活动可能会持续存在 45 + 90 = 135 天。如果用户不断返回，您可能会看到报表中的指标从较旧的活动发送到[!DNL Analytics]。 当用户删除Cookie且不再返回网站时，该活动中的数字会下降，但您仍然可以看到它们。

这意味着在活动结束后（对于在活动处于活动状态时成为活动一部分的访客），活动将继续获取页面查看次数、访问次数等，时间可长达90天。 但是，如果查看[!UICONTROL Activity Impressions]量度，则不应在活动结束之后看到任何展示次数。

这是正常的预期行为。A4T 变量的运作与其他任何 eVar 相同 - 该值会与用户相关联，直到它到达过期期限（90 天）。因此，如果某个活动仅在2周内处于活动状态，则该值在至少接下来的90天内仍与用户相关联。

最佳做法是仅在活动上线的时间段内查看该活动的报表。在[!DNL Analytics]中查看活动时，默认情况下应正确设置日期，因此，除非您已手动延长日期，否则从报表的角度来看，这应该不成问题。

例如，假设A4T变量在90天后过期，并且测试从1月1日到1月15日处于活动状态。

在 1 月 1 日，某个用户访问该网站，然后查看了活动 XYZ 一次，之后又查看了五个页面。在接下来的两周内，该用户未返回该网站。那么，此用户的数据应如下所示：

| 活动名称 | 实例（展示次数） | 页面查看次数 | 访问次数 | 独特访客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 5 | 1 | 1 |

用户将在2月1日返回并查看另外五个页面，不会再遇到任何Target活动，并且原始活动不再处于活动状态。 即使该活动不再处于上线状态，它仍会通过 eVar 持久性跟踪该用户。现在，数据如下所示：

| 活动名称 | 实例（展示次数） | 页面查看次数 | 访问次数 | 独特访客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 10 | 2 | 1 |

3 月 1 日，该用户又返回网站，查看了一个新活动 ABC。另外，该用户也查看了五个页面。由于活动XYZ仍通过持久性跟踪用户，并且此用户随后设置了ABC，因此您将在报表中看到两行项目：

| 活动名称 | 实例（展示次数） | 页面查看次数 | 访问次数 | 独特访客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 15 | 3 | 1 |
| ABC | 1 | 5 | 1 | 1 |

之后，该用户在 4 月 1 日再次返回网站，查看了另外 5 个页面，并进行了一次购买。第一个eVar值的90天过期日期将在4月1日重置，因此您会在报表中看到该信息。 该用户查看的所有 Target 活动都会收到转化点数，但在转化点数总和中，会将重复计算的点数删除：

| 活动名称 | 实例（展示次数） | 页面查看次数 | 访问次数 | 独特访客 | 订单数 |
|--- |--- |--- |--- |--- |--- |
| XYZ | 1 | 20 | 4 | 1 | 1 |
| ABC | 1 | 10 | 2 | 1 | 1 |
| 合计 | 2 | 20 | 3 | 1 | 1 |

由于这两种体验均在转换之前被看到，因此它们都会获得订单的“点数”。 但在系统中只产生了一个订单，所以点数的总计值反映了这一点。对于[!DNL Target]报表，由于您不是针对其他活动放置[!DNL Target]活动以查看哪个活动更成功，因此用户看到的所有活动都获得点数并不重要。 您正在比较单个活动中两个项目的结果。 用户不可能在同一活动中看到不同的体验，因此您不必担心订单信用交叉污染。

有关详细信息，请参阅[Analytics管理指南](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html)中的&#x200B;*转化变量(eVar*)。

+++

## 为什么我的活动被停用后，我依旧会看到更多展示？ {#deactivated}

+++回答
A4T活动报表在停用后的展示次数来源可以是QA模式流量。 Target通常不会记录已停用活动的事件，但Analytics无法知道展示次数来自QA模式。 从Analytics中检索Target活动报表时，它会显示这些展示次数。 这是按设计工作的，因为即使活动未使用QA模式处于活动状态，客户也需要一种检查A4T报表的方法。

+++

## 为什么[!DNL Analytics]和[!UICONTROL Analytics for Adobe Target] (A4T)计算[!UICONTROL Unique Visitors]量度的数字不同？ {#section_0C3B648AB54041F9A2AA839D51791883}

+++回答
运行A/B测试(使用[Welch的t检验](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank}（置信度量度）来选择测试的入选者)时，其中一个假设是存在固定的时间范围。 除非您查看固定样本量，否则测试在统计上无效。

仅当您查看的时段短于实际测试的时段时，[!UICONTROL Unique Visitors]量度在[!DNL Analytics]和[!DNL Target]中不同。 如果尚未达到样本量，测试就不那么可靠。 有关详细信息，请参阅 [Evan Miller 的网站](https://www.evanmiller.org/index.html)上的[如何正确运行 A/B 测试](https://www.evanmiller.org/how-not-to-run-an-ab-test.html)。

[!UICONTROL Unique Visitors]量度显示了在指定时间段内接触过测试并访问过网站的人数。 这些人是测试的一部分，应该被计入。 如果您只想查看一周内接触过该测试的人数，则可以创建一个具有活动展示次数的访客区段并将其应用于报表。

您可以缩短[!DNL Target]变量持续保留到会话的时间；但是，对于转化事件不太可能在同一会话中发生的测试而言，这会产生问题。

+++

## 为什么在[!DNL Analytics]中有时会在多个体验中统计同一访客？ {#section_1397E972D31C4207A142E4D2D6D794A2}

+++回答
以下列表说明了在[!DNL Analytics]中可以将同一访客计入多个体验的原因：

* [!DNL Target]配置文件已过期，但[!DNL Analytics] Cookie仍然存在。 在此情况下，[!DNL Target]会重新评估用户，但[!DNL Analytics]会将该访客视为同一个人。
* 如果访客使用`mbox3rdPartyId`，则当匿名访客与第三方ID配置文件合并时，[!DNL Target]可能会将该访客带入不同的体验以与第三方ID匹配。 有关更多信息，请参阅 [mbox3rdPartyID 的实时轮廓同步](/help/main/c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732)。
* [!DNL Analytics]可能以不同于[!DNL Target]的方式作为同一访客跟踪不同的设备，以跟踪这些设备： [!DNL Target]中的第三方ID设置不同于Analytics中的设置。

+++

## A4T 是否支持虚拟报表包？ {#virtual}

+++回答
尽管虚拟报表包未包含在[!UICONTROL Report Suite]列表中，但与链接到[!DNL Analytics]中虚拟报表包的报表包共享的任何A4T数据都可以访问该数据。 请注意，任何从虚拟报表包创建的受众都不能共享回[!DNL Target]。

+++

## 对于使用 A4T 的活动，我能否在激活活动后更改其中的流量分配百分比？

+++回答
在激活后更改活动中的流量分配百分比可能会导致[!DNL Analytics]中的报表不一致，因为此更改仅影响新访客。 回访访客将不受影响。

作为最佳实践，您应停止现有活动，然后创建一个新活动，而不是在激活后更改百分比。新活动的报表会从新访客开始，而回访访客的数据不会导致报表不一致。

+++

## 在使用A4T的[!DNL Analytics]活动中，访问次数如何计入[!UICONTROL Auto-Target]，转化功劳如何分配？

+++回答
当访客在A4T活动中符合、查看内容或转化时，[!DNL Target]将事件数据发送到[!DNL Analytics]。 此事件数据允许[!DNL Analytics]将页面上发生的转化事件和其他点击流事件归因于相关的[!DNL Target]活动和体验。

查看[!DNL Analytics]报告时要牢记以下几点：

* 通常，作为最佳实践，您的报告窗口应从活动的开始日期开始。
* 如果转换发生在报表窗口之外，则该转换在[!DNL Analytics]中不可见。
* 当处于[!UICONTROL Auto-Target]活动流量的“目标”部分时，访客可能会在不同会话间看到不同的体验。 例如，如果他们的配置文件或上下文已更改，[!DNL Target]的机器学习算法决定他们更有可能在新体验上转化。 随着访客从体验移至体验，所看到的每个体验的访问计数都会增加。 这不同于常规的A/B测试活动，这些活动中的体验跨访问对访客来说是粘性的。
* 如果访客在多次访问中看到多个体验，则任何转化始终会归因于访客看到的最后一次体验。 如前所述，访客看到的每个体验的访问计数都会递增。 在[!UICONTROL Targeted]报表的“[!DNL Adobe Analytics]”维度下查看体验时，这可能会人为降低每个体验的转化率。

+++

## 使用[!DNL Analysis Workspace] (A4T)时，我如何在[!UICONTROL Analytics for Target]中跟踪活动展示次数？ {#activity-impressions}

+++回答

要在[!DNL Analysis Workspace]中查看活动展示次数，请执行以下操作：

1. 在[!DNL Target]用户界面中，单击&#x200B;**[!UICONTROL View in Analytics]**。
1. 将&#x200B;**[!UICONTROL Activity Impressions]**&#x200B;列添加到[[!DNL Analytics Workspace]](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html){target=_blank}报表。
1. 在&#x200B;**[!UICONTROL Activity Impressions]**&#x200B;列上，单击[!UICONTROL Gear]图标。
1. 单击 **[!UICONTROL Use non-default attribution model]**。
1. 选择&#x200B;**[!UICONTROL Same Touch Model]** > **[!UICONTROL Apply]**。

+++
