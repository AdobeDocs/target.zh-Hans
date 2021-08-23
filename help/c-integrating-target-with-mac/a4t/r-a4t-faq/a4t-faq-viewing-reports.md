---
keywords: faq;常见问题解答;analytics for target;a4T;报表;报告;查看报表;查看报告;计数方法;展示次数;访客;访问次数;默认量度;活动转化;未指定
description: 查找有关在 [!DNL Target] (A4T). A4T lets you use Analytics reporting for [!DNL Target] 活动中使用Analytics时查看报表的常见问题解答。
title: 查找有关使用A4T查看报表的问题解答？
feature: Analytics for Target (A4T)
exl-id: a02eeb34-3975-424b-a046-e51f10ae1823
source-git-commit: 8b8091557fc1df48830bfa3211aa789b2c987f2d
workflow-type: tm+mt
source-wordcount: '2538'
ht-degree: 36%

---

# 查看报表 - A4T 常见问题解答

本主题包含有关在使用[!DNL Adobe Analytics]作为[!DNL Adobe Target](A4T)的报表源时查看报表的常见问题解答。

## 能否在Analysis Workspace中查看[!DNL Target]活动数据？ {#workspace}

您可以使用[!DNL Analysis Workspace]来分析[!DNL Target]活动和体验。 通过[Analytics for Target面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=zh-Hans)，您可以查看多达三个成功量度的提升度和置信度。 您还可以使用表格和可视化图表来深入挖掘。

有关详细信息和示例，请打开[Analytics和Target:Analysis最佳实践教程](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)，由Adobe Experience League提供。

## 可在 Analysis Workspace 中的何处应用区段？ {#segmentation}

区段最常用于区段拖放区域中面板顶部。 该区段将应用于面板中的所有表和可视化图表。 此技术对于查看测试如何影响部分人员（例如，此测试对英国人员的表现如何）非常有用？

区段也可以直接在自由格式表中进行分层，但请注意，您必须将其覆盖整个表，以便在A4T面板中保留提升度和置信度计算。 面板中当前不支持列级别区段。

## 当我为特定[!DNL Target]活动应用点击区段时，为何返回不相关的体验？ {#activity-segmentation}

发送到 [!DNL Target] 的 [!DNL Analytics] 变量具有 90 天的默认有效期。(注：客户关怀团队可根据需要调整此过期期限)。 当访客在此过期时间范围内浏览网站时，他们属于许多[!DNL Target]活动的一部分，所有活动都在维度中收集。

当您对某个活动进行分段以使其显示在点击中时，您会获得该活动中所包含的所有体验（*加*）以及该点击中保留的任何其他体验。

## 在配置目标量度时，为何无法访问高级设置？

对于使用[!DNL Analytics]作为报表源(A4T)的活动，目标量度使用“[!UICONTROL 递增计数并保持活动中的用户]”和“[!UICONTROL 每次展示时]”设置。 这些设置可配置为&#x200B;*不*。

有关更多信息，请参阅“配置目标量度时，为何无法访问高级设置选项？” 在[量度定义 — A4T常见问题解答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md)中。

## 我是否应该使用访客数、访问次数或活动展示次数作为标准化量度（即计数方法）？ {#metrics}

在A4T报表中，有几个用于标准化量度的选项。 此量度（也称为计数方法）将成为提升计算的分母。 此外，它也会在应用置信度计算之前影响数据汇总的方式。

* ***独特访客数***&#x200B;在用户首次符合活动条件时递增一次。
* 每个会话的&#x200B;***访问次数***&#x200B;在用户（独特访客）进入活动时递增，即使该用户在后续访问中未查看该活动也是如此。
* ***活动展示次数***&#x200B;在每次提供活动内容时递增。（由[!DNL Target]测量）。

当访客查看包含活动的页面时，系统会为该访客设置一个变量以包含该活动的名称。有关每种计数方法的比较方式，请参阅下面的详细情景。

请考虑以下事项：

* 当用户符合活动条件并从[!DNL Target]返回内容时，将触发上述量度。 这并不一定意味着用户查看了该选件。如果活动体验未显示且用户未向下滚动页面，则表示该选件由 [!DNL Target] 提供，但用户并未查看。
* 除非同一活动中的同一页面同时有多个 mbox 调用，否则“[!UICONTROL 活动展示次数]”（由 [!DNL Target] 测量）与“[!UICONTROL 实例数]”（由 [!DNL Analytics] 测量）相等。这会导致“[!UICONTROL 活动展示次数]”被计入多次，而“[!UICONTROL 实例]”只被计入一次。

有关更多信息，请参阅&#x200B;*Adobe TargetTutorials*&#x200B;中的[如何在Analysis Workspace中为自动定位活动设置A4T报表](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html)。

## Analysis Workspace中的“活动展示次数”和“活动转化次数”为何高于Reports &amp; Analytics? {#sametouch}

[!DNL Reports & Analytics] 将同一联系归因模型应用于“活动展示次数”和“活动转化次数”，而 [!DNL Analysis Workspace] 则显示原始量度，由于维度的持久性，这些量度可能会被夸 [!DNL Target] 大。

要评估和[!UICONTROL [!DNL Analysis Workspace]中的]活动转化量度，请确保两个量度均应用了[!UICONTROL 同一接触]归因模型。 可以通过单击列设置齿轮，启用[!UICONTROL 非默认归因模型]，然后选择[!UICONTROL 同一联系]来应用模型。在&#x200B;*Analytics工具指南*&#x200B;的[属性IQ概述](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/attribution.html)中了解有关归因的更多信息。

## 如果营销人员在活动设置期间选择了一个 Analytics 量度，则“活动转化”意味着什么？ {#section_F3EBACF85AF846E9B366A549AAB64356}

如果选择[!DNL Analytics]量度作为活动的转化量度，则“活动转化”为空。

## 为什么我会在 Analytics 报表中看到“未指定”？这是什么意思？ {#unspecified}

在其他报表中，“未指定”意味着数据不符合分类规则，但在 A4T 中，不应出现此种情况。如果您看到“未指定”，则表示分类服务尚未运行。活动数据一般需要 24 到 72 小时才能显示在报表中。即使这些活动在此时间之前并未显示在此报表中，但与这些活动关联的所有访客数据都会被捕获，并在分类完成时显示出来。

分类期过后，数据会在从网站收集大约一小时后显示在这些报表中。报表中的所有量度、区段和值都来自您在设置活动时选择的报表包。

如果已对该活动进行分类，并且您仍在报表中看到“未指定”行，请确保报表未使用非[!DNL Target]量度来显示数据。 除非报表使用特定于[!DNL Target]的量度，否则“未指定”行包含与[!DNL Target]不关联的调用事件。 该行将不包含任何[!DNL Target]关联信息（例如，访客/访问/展示次数）。

## 为什么即便在停用活动后，[!DNL Target]量度仍会被发送到Analytics? {#section_38AA8380A4D54A18972F1EF3E73E22EF}

发送到 [!DNL Target] 的 [!DNL Analytics] 变量具有 90 天的默认有效期。如果需要，客户关怀团队可以调整此过期期限。 但是，这是针对所有活动的全局设置，不能仅针对一个案例进行调整。

您可能会在过期期限后看到[!DNL Target]变量发送到[!DNL Analytics]，因为过期时间为90天，但前提是该用户从未看到其他启用了A4T的[!DNL Target]活动。 如果用户在第 45 天返回网站并查看了另一个活动，则整个 A4T eVar 值会将其计数器重置为 90 天。这意味着从第 1 天开始的第一个营销活动可能会持续存在 45 + 90 = 135 天。如果用户不断回访，您可能会看到从旧活动发送到报表中的量度。 [!DNL Analytics]当用户删除Cookie且未返回网站时，该活动中的数字会下降，但您仍可以看到这些Cookie。

这意味着活动在活动结束后，如果访客在活动处于活跃状态时成为活动的一部分，则访客可继续获取页面查看次数、访问次数等内容，持续90天。 不过，如果您查看的是“[!UICONTROL 活动展示次数]”量度，则在活动结束后您不会看到任何展示次数。

这是正常的预期行为。A4T 变量的运作与其他任何 eVar 相同 - 该值会与用户相关联，直到它到达过期期限（90 天）。因此，如果某个活动仅处于活动状态两周，则该值至少在接下来的90天内仍会与用户关联。

最佳做法是仅在活动上线的时间段内查看该活动的报表。在[!DNL Analytics]中查看活动时，默认情况下应正确设置日期，因此除非您手动延长日期，否则从报表角度来看，这不应该是问题。

例如，假设A4T变量在90天后过期，并且测试在1月1日至1月15日期间处于活动状态。

在 1 月 1 日，某个用户访问该网站，然后查看了活动 XYZ 一次，之后又查看了五个页面。在接下来的两周内，该用户未返回该网站。那么，此用户的数据应如下所示：

| 活动名称 | 实例（展示次数） | 页面查看次数 | 访问次数 | 独特访客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 5 | 1 | 1 |

2 月 1 日，该用户返回了网站，查看了其他 5 个页面，并且未体验任何其他 Target 活动，而此时原来的活动已不再上线。即使该活动不再处于上线状态，它仍会通过 eVar 持久性跟踪该用户。现在，数据如下所示：

| 活动名称 | 实例（展示次数） | 页面查看次数 | 访问次数 | 独特访客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 10 | 2 | 1 |

3 月 1 日，该用户又返回网站，查看了一个新活动 ABC。另外，该用户也查看了五个页面。由于活动XYZ仍通过持久性跟踪用户，并且该用户随后设置了ABC，因此您将在报表中看到两个行项目：

| 活动名称 | 实例（展示次数） | 页面查看次数 | 访问次数 | 独特访客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 15 | 3 | 1 |
| ABC | 1 | 5 | 1 | 1 |

之后，该用户在 4 月 1 日再次返回网站，查看了另外 5 个页面，并进行了一次购买。第一个eVar值的90天到期将在4月1日重置，以便您在报表中看到该值。 该用户查看的所有 Target 活动都会收到转化点数，但在转化点数总和中，会将重复计算的点数删除：

| 活动名称 | 实例（展示次数） | 页面查看次数 | 访问次数 | 独特访客 | 订单数 |
|--- |--- |--- |--- |--- |--- |
| XYZ | 1 | 20 | 4 | 1 | 1 |
| ABC | 1 | 10 | 2 | 1 | 1 |
| 合计 | 2 | 20 | 1 | 1 | 1 |

由于两个体验都是在转化之前查看的，因此它们都会获得订单的“点数”。 但在系统中只产生了一个订单，所以点数的总计值反映了这一点。对于[!DNL Target]报表，由于您没有针对其他活动放置[!DNL Target]活动来查看哪个活动更成功，因此用户看到的所有活动都获得点数并不重要。 您要比较单个活动中两个项目的结果。用户不可能在同一活动中看到不同的体验，因此您不必担心订单信用的交叉污染。

有关更多信息，请参阅《Analytics管理指南》*中的[转化变量(eVar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html))。*

## 为什么我的活动被停用后，我依旧会看到更多展示？ {#deactivated}

停用后A4T活动报表的展示次数来源可以是QA模式流量。 Target通常不会记录已停用活动的事件，但Analytics无法了解展示次数来自QA模式。 从Analytics中检索Target活动报表时，会显示这些展示次数。 此报表的工作原样是，因为客户需要一种方法来检查A4T报表，即使该活动未在使用QA模式时处于活动状态。

## 为什么Analytics和Analytics for Adobe Target(A4T)在计算“独特访客”量度时得到的数字不同？ {#section_0C3B648AB54041F9A2AA839D51791883}

当您运行的 A/B 测试使用“学生 t 检验”（置信度量度）来选择测试的入选者时，其假设之一是存在固定的时间范围。因此，除非您查看的是固定样本量，否则该测试不具有统计意义。

仅当您查看的时段比实际测试的时段短时，[!UICONTROL 独特访客]量度在[!DNL Analytics]和[!DNL Target]中才会有所不同。 如果您未达到样本量，则测试并不可靠。有关详细信息，请参阅 [Evan Miller 的网站](https://www.evanmiller.org/index.html)上的[如何正确运行 A/B 测试](https://www.evanmiller.org/how-not-to-run-an-ab-test.html)。

[!UICONTROL 独特访客]量度显示在指定时间段内访问过网站的测试对象数量。 这些人是测试的一部分，应该被计数。 如果您只想查看一周内接触过该测试的人数，则可以创建一个具有活动展示次数的访客区段并将其应用于报表。

您可以缩短[!DNL Target]变量在会话中持续的时间；但是，对于在同一会话中发生转化事件的可能性不大的测试，这存在问题。

## 为什么同一访客有时会计入到 Analytics 的多个体验中？ {#section_1397E972D31C4207A142E4D2D6D794A2}

以下列表说明了在[!DNL Analytics]中将同一访客计入多个体验的原因：

* [!DNL Target]配置文件已过期，但[!DNL Analytics] Cookie仍然存在。 在这种情况下，[!DNL Target]会重新评估用户，但[!DNL Analytics]会认为访客是同一个人。
* 如果访客使用的是`mbox3rdPartyId`，则当匿名访客与第三方ID配置文件合并时，[!DNL Target]可能会将该访客带入不同的体验以与第三方ID匹配。 有关更多信息，请参阅 [mbox3rdPartyID 的实时配置文件同步](/help/c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732)。
* [!DNL Analytics] 可能会以不同的方式作为同一访客跟踪不同的设备，而不 [!DNL Target] 是跟踪这些设备：中的第三方ID设置与 [!DNL Target] Analytics中的不同。

## A4T 是否支持虚拟报表包？ {#virtual}

尽管虚拟报表包未包含在[!UICONTROL 报表包]列表中，但与链接到[!DNL Analytics]中虚拟报表包的报表包共享的任何A4T数据都有权访问该数据。 请注意，从虚拟报表包创建的任何受众都无法共享回[!DNL Target]。

## 对于使用 A4T 的活动，我能否在激活活动后更改其中的流量分配百分比？

在激活后更改活动中的流量分配百分比可能会导致[!DNL Analytics]中的报表不一致，因为此更改仅影响新访客。 回访访客将不受影响。

作为最佳实践，您应停止现有活动，然后创建一个新活动，而不是在激活后更改百分比。新活动的报表从新访客开始，而回访访客的数据不会导致报表不一致。

## 在使用A4T的自动定位活动中，如何将访问计入Analytics并分配转化点数？

当访客符合A4T活动的条件、查看内容或进行转化时，[!DNL Target]会向[!DNL Analytics]发送事件数据。 此事件数据允许[!DNL Analytics]将页面上发生的转化事件和其他点击流事件归因于相关的[!DNL Target]活动和体验。

在查看[!DNL Analytics]报表时，请牢记以下几点：

* 通常，作为最佳实践，报表窗口应从活动的开始日期开始。
* 如果在报表窗口外发生转化，则该转化在[!DNL Analytics]中不可见。
* 当在[!UICONTROL 自动定位]活动的“目标”流量部分中，访客可能会在一个会话到下一个会话中看到不同的体验。 例如，如果配置文件或上下文已发生更改，且[!DNL Target]的机器学习算法确定它们更有可能在新体验上进行转换。 随着访客在体验之间移动，所看到的每个体验的访问计数都会递增。 这与常规A/B测试活动不同，在这些活动中，体验在每次访问时都对访客具有粘滞性。
* 如果访客在每次访问中看到多个体验，则任何转化始终都会归因于访客最近查看的体验。 如前所述，访客查看的每个体验的访问计数都会递增。 在[!DNL Adobe Analytics]报表的“[!UICONTROL 目标]”维度下查看体验时，这可能会人为地降低每个体验的转化率。
