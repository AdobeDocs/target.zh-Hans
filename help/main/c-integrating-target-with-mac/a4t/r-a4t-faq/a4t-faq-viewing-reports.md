---
keywords: faq;常见问题解答;analytics for target;a4T;报表;报告;查看报表;查看报告;计数方法;展示次数;访客;访问次数;默认量度;活动转化;未指定
description: 查找有关在使用Analytics查看报表的常见问题解答 [!DNL Target] (A4T)。 A4T允许您将Analytics报表用于 [!DNL Target] 活动。
title: 查找有关使用A4T查看报表的问题答案？
feature: Analytics for Target (A4T)
exl-id: a02eeb34-3975-424b-a046-e51f10ae1823
source-git-commit: 79ae58377c9eea0faca1ade11f2ab53da56b7bc1
workflow-type: tm+mt
source-wordcount: '2714'
ht-degree: 29%

---

# 查看报表 - A4T 常见问题解答

本主题包含有关在使用时查看报表的常见问题解答 [!DNL Adobe Analytics] 作为的报表源 [!DNL Adobe Target] (A4T)。

## 我能否查看我的 [!DNL Target] 中的活动数据 [!DNL Analysis Workspace]？ {#workspace}

+++回答：您可以使用 [!DNL Analysis Workspace] 分析 [!DNL Target] 活动和体验。 此 [“Analytics for Target”面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=zh-Hans) 可让您查看最多三个成功量度的提升度和置信度。 您还可以使用表格和可视化图表深入了解。

有关详细信息和示例，请打开 [Analytics和Target：分析最佳实践教程](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)，提供者 [!UICONTROL Adobe Experience League].

+++

## 区段可以应用于何处 [!DNL Analysis Workspace]？ {#segmentation}

+++应答区段最常用于区段拖放区域中的面板顶部。 区段将应用于面板中的所有表和可视化图表。 此技术对于查看测试如何影响一部分人最有用（例如，此测试对英国人的表现如何）？

区段也可以直接在自由格式表中进行分层，但请注意，您必须在整个表中叠加该区段，以保留A4T面板中的提升度和置信度计算。 面板中当前不支持列级别区段。

+++

## 我是否可以在中应用“同一接触”Attribution IQ模型 [!DNL Analysis Workspace]？

+++使用时回答 [!DNL Target] 中的活动展示和转化 [!DNL Analysis Workspace]，将“同一接触”Attribution IQ模型应用于量度以确保准确计数。 要应用[非默认归因模型](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html?lang=zh-Hans)，请右键单击指标以&#x200B;**修改“列设置”> 启用“使用非默认归因模型”> 选择“同一次接触”模型**。如果不应用此模型，则指标将被夸大。

所有当前 [!DNL Adobe Analytics] 包可以添加此模型 [!UICONTROL Attribution IQ]. 如果您无权访问 [!UICONTROL Attribution IQ]，请依靠中的A4T数据 [!UICONTROL Reports &amp; Analytics].

+++

## 当我为特定应用点击区段时 [!DNL Target] 活动，为何会返回不相关的体验？ {#activity-segmentation}

+++回答 [!DNL Target] 变量发送至 [!DNL Analytics] 具有90天的默认有效期。 （注意：如果需要，客户关怀团队可以调整此到期期限）。 访客在整个过期时段中浏览网站时，属于许多过期时段 [!DNL Target] 活动，所有这些活动都在维度中收集。

当您对要显示在点击中的活动进行分段时，您将获得属于该活动的所有体验 *加* 任何在该点击中持续存在的其他体验。

+++

## 配置我的时 [!UICONTROL 目标量度]，为何无法访问 [!UICONTROL 高级设置]？

+++使用以下方式回答活动 [!DNL Analytics] 作为报表源(A4T)，目标量度使用“[!UICONTROL 增量计数并保持用户处于活动状态]“ ”和“ ”[!UICONTROL 每次展示时]”设置。 这些设置包括 *非* 可配置。

有关更多信息，请参阅配置目标指标时，为何无法访问高级设置选项？ 在 [量度定义 — A4T常见问题解答](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

+++

## 是否应使用访客数、访问次数或活动展示次数作为我的标准化量度（即计数方法）？ {#metrics}

+++回答A4T报表中有几个用于标准化量度的选项。 此量度（也称为计数方法）将作为提升计算的分母。 此外，它也会在应用置信度计算之前影响数据汇总的方式。

* ***独特访客数***&#x200B;在用户首次符合活动条件时递增一次。
* 每个会话的&#x200B;***访问次数***&#x200B;在用户（独特访客）进入活动时递增，即使该用户在后续访问中未查看该活动也是如此。
* ***活动展示次数***&#x200B;在每次提供活动内容时递增。(测量方式 [!DNL Target])。

当访客查看包含活动的页面时，系统会为该访客设置一个变量以包含该活动的名称。有关每种计数方法的比较方式，请参阅下面的详细情景。

请考虑以下事项：

* 当用户符合活动条件并从返回内容时，上述量度会触发 [!DNL Target]. 这并不一定意味着用户查看了该选件。如果活动体验未显示且用户未向下滚动页面，则表示该选件由 [!DNL Target] 提供，但用户并未查看。
* 除非同一活动中的同一页面同时有多个 mbox 调用，否则“[!UICONTROL 活动展示次数]”（由 [!DNL Target] 测量）与“[!UICONTROL 实例数]”（由 [!DNL Analytics] 测量）相等。这会导致“[!UICONTROL 活动展示次数]”被计入多次，而“[!UICONTROL 实例]”只被计入一次。

有关更多信息，请参阅 [如何在Analysis Workspace中为自动定位活动设置A4T报表](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) 在 *Adobe TargetTutorials*.

+++

## 为什么“活动展示次数”和“活动转化次数”在中较高 [!DNL Analysis Workspace] 大于 [!UICONTROL Reports &amp; Analytics]？ {#sametouch}

+++回答
[!DNL Reports & Analytics] 将同一联系归因模型应用于“活动展示次数”和“活动转化”，而 [!DNL Analysis Workspace] 显示原始量度，由于持久存在，这些量度可能显示为夸大 [!DNL Target] 维度。

要精确评估 [!UICONTROL 活动展示次数] 和 [!UICONTROL 活动转化] 中的量度 [!DNL Analysis Workspace]，确保这两个量度都具有 [!UICONTROL 同一接触] 已应用归因模型。 可以通过单击列设置齿轮，启用[!UICONTROL 非默认归因模型]，然后选择[!UICONTROL 同一联系]来应用模型。在中了解有关归因的更多信息 [属性IQ概述](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/attribution.html) 在 *Analytics工具指南*.

+++

## 如果营销人员选择 [!DNL Analytics] 活动设置期间的量度？ {#section_F3EBACF85AF846E9B366A549AAB64356}

+++如果符合以下条件，则回答“活动转化”为空 [!DNL Analytics] 量度已选为活动的转化量度。

+++

## 为什么我在“ ”中看到“未指定” [!DNL Analytics] 报告？ 这是什么意思？ {#unspecified}

+++答案在其他报表中，“未指定”表示数据不符合分类规则，但在A4T中，这应该永远不会发生。 如果您看到“未指定”，则表示分类服务尚未运行。活动数据一般需要 24 到 72 小时才能显示在报表中。即使这些活动在此时间之前不会显示在报表中，但与这些活动关联的所有访客数据都会被捕获并在分类完成时显示。

分类期过后，数据会在从网站收集大约一小时后显示在这些报表中。报表中的所有量度、区段和值都来自您在设置活动时选择的报表包。

如果已对该活动进行分类，并且您仍然在报表中看到“未指定”行，请确保报表未使用非[!DNL Target] 用于显示数据的量度。 除非报表使用 [!DNL Target]特定于的量度，该“未指定”行包含与调用无关的事件 [!DNL Target]. 该行将不包含任何 [!DNL Target] — 关联的信息（例如，访客/访问次数/展示次数）。

+++

## 为什么 [!DNL Target] 量度发送至 [!DNL Analytics] 即使在活动被停用之后？ {#section_38AA8380A4D54A18972F1EF3E73E22EF}

+++回答 [!DNL Target] 变量发送至 [!DNL Analytics] 具有90天的默认有效期。 如果需要，客户关怀团队可以调整此期限。 该设置对于所有活动都是全局的；但是，不应只针对一种情况调整此设置。

您可能会看到 [!DNL Target] 变量发送至 [!DNL Analytics] 过期，因为过期时间为90天，但前提是该用户从未看到其他启用了A4T [!DNL Target] 活动。 如果用户在第 45 天返回网站并查看了另一个活动，则整个 A4T eVar 值会将其计数器重置为 90 天。这意味着从第 1 天开始的第一个营销活动可能会持续存在 45 + 90 = 135 天。如果用户不断回访，您可能会看到量度已发送到 [!DNL Analytics] （从更早的活动删除）的数量。 当用户删除Cookie且不再返回网站时，该活动中的数字会下降，但您仍然可以看到它们。

这意味着在活动结束后（对于在活动期间成为活动一部分的访客），活动仍会继续获得页面查看次数、访问次数等，最长可达90天。 不过，如果您查看的是“[!UICONTROL 活动展示次数]”量度，则在活动结束后您不会看到任何展示次数。

这是正常的预期行为。A4T 变量的运作与其他任何 eVar 相同 - 该值会与用户相关联，直到它到达过期期限（90 天）。因此，如果某个活动仅在2周内处于活动状态，则该值在至少接下来的90天内仍与用户相关联。

最佳做法是仅在活动上线的时间段内查看该活动的报表。默认情况下，当您在中查看活动时，日期应正确设置 [!DNL Analytics]因此，除非您手动延长了日期，否则从报表的角度来看，这应该不成问题。

例如，假设A4T变量在90天后过期，并且测试在1月1日至1月15日期间处于活动状态。

在 1 月 1 日，某个用户访问该网站，然后查看了活动 XYZ 一次，之后又查看了五个页面。在接下来的两周内，该用户未返回该网站。那么，此用户的数据应如下所示：

| 活动名称 | 实例（展示次数） | 页面查看次数 | 访问次数 | 独特访客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 5 | 1 | 1 |

用户在2月1日重新访问，又查看了5个页面，不会再遇到任何Target活动，并且原始活动不再处于活动状态。 即使该活动不再处于上线状态，它仍会通过 eVar 持久性跟踪该用户。现在，数据如下所示：

| 活动名称 | 实例（展示次数） | 页面查看次数 | 访问次数 | 独特访客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 10 | 2 | 1 |

3 月 1 日，该用户又返回网站，查看了一个新活动 ABC。另外，该用户也查看了五个页面。由于活动XYZ仍通过持久性跟踪用户，并且此用户设置了ABC，因此您将在报表中看到两个行项目：

| 活动名称 | 实例（展示次数） | 页面查看次数 | 访问次数 | 独特访客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 15 | 3 | 1 |
| ABC | 1 | 5 | 1 | 1 |

之后，该用户在 4 月 1 日再次返回网站，查看了另外 5 个页面，并进行了一次购买。第一个eVar值的90天过期时间将在4月1日重置，因此您会在报表中看到该信息。 该用户查看的所有 Target 活动都会收到转化点数，但在转化点数总和中，会将重复计算的点数删除：

| 活动名称 | 实例（展示次数） | 页面查看次数 | 访问次数 | 独特访客 | 订单数 |
|--- |--- |--- |--- |--- |--- |
| XYZ | 1 | 20 | 4 | 1 | 1 |
| ABC | 1 | 10 | 2 | 1 | 1 |
| 合计 | 2 | 20 | 3 | 1 | 1 |

由于这两种体验都是在转换之前看到的，因此它们都会获得订单的“点数”。 但在系统中只产生了一个订单，所以点数的总计值反映了这一点。对象 [!DNL Target] 报告，因为您没有 [!DNL Target] 针对其他活动的活动以查看哪个活动更成功，用户看到的所有活动获得点数并不重要。 您正在比较单个活动中两个项目的结果。用户不可能在同一活动中看到不同的体验，因此您不必担心订单信用交叉污染。

有关更多信息，请参阅 [转化变量(eVar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html))中 *Analytics管理指南*.

+++

## 为什么我的活动被停用后，我依旧会看到更多展示？ {#deactivated}

+++回答A4T活动报表在停用后的展示次数来源可以是QA模式流量。 Target通常不会记录已停用活动的事件，但Analytics无法知道展示来自QA模式。 从Analytics中检索Target活动报表时，它会显示这些展示次数。 这是按设计工作的，因为即使活动未使用QA模式激活，客户也需要一种检查A4T报表的方法。

+++

## 为什么 [!DNL Analytics] 和 [!UICONTROL Analytics for Adobe Target] (A4T)计算 [!UICONTROL 独特访客] 量度是否不同？ {#section_0C3B648AB54041F9A2AA839D51791883}

+++回答：运行A/B测试时，该测试使用 [韦尔奇t检验](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} （置信度量度）来选择一个测试的入选者，其中一个假设是存在固定的时间范围。 除非查看固定样本量，否则测试在统计上无效。

此 [!UICONTROL 独特访客] 量度在中不同 [!DNL Analytics] 和 [!DNL Target] 仅当查看的时段比实际测试短时。 如果尚未达到样本量，测试就不那么可靠。 有关详细信息，请参阅 [Evan Miller 的网站](https://www.evanmiller.org/index.html)上的[如何正确运行 A/B 测试](https://www.evanmiller.org/how-not-to-run-an-ab-test.html)。

此 [!UICONTROL 独特访客] 量度显示在指定时间段内接触过测试并访问过网站的人数。 那些人是测试的一部分，应该被计入。 如果您只想查看一周内接触过该测试的人数，则可以创建一个具有活动展示次数的访客区段并将其应用于报表。

您可以缩短 [!DNL Target] 变量会一直保留到某个会话；但是，对于转化事件不太可能在同一会话中发生的测试而言，存在此问题。

+++

## 为什么有时会在多个体验中统计同一访客 [!DNL Analytics]？ {#section_1397E972D31C4207A142E4D2D6D794A2}

+++答案以下列表说明了在中同一访客可以被计入多个体验的原因 [!DNL Analytics]：

* 此 [!DNL Target] 配置文件已过期，但 [!DNL Analytics] Cookie仍然存在。 在这种情况下， [!DNL Target] 重新评估用户但 [!DNL Analytics] 将访客视为同一个人。
* 如果访客正在使用 `mbox3rdPartyId`，当匿名访客与第三方ID配置文件合并时， [!DNL Target] 可能会将访客带入不同的体验以与第三方ID匹配。 有关更多信息，请参阅 [mbox3rdPartyID 的实时配置文件同步](/help/main/c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732)。
* [!DNL Analytics] 可能会以不同的方式将不同的设备作为同一访客跟踪 [!DNL Target] 跟踪这些设备：中的第三方ID设置 [!DNL Target] 与Analytics中的不同。

+++

## A4T 是否支持虚拟报表包？ {#virtual}

+++答案尽管虚拟报表包未包含在 [!UICONTROL 报表包] 列表，与中链接到虚拟报表包的报表包共享的任何A4T数据 [!DNL Analytics] 有权访问这些数据。 请注意，任何从虚拟报表包创建的受众都不能共享回 [!DNL Target].

+++

## 对于使用 A4T 的活动，我能否在激活活动后更改其中的流量分配百分比？

+++答案激活后更改活动中的流量分配百分比可能会导致中的报表不一致 [!DNL Analytics] 因为此更改只会影响新访客。 回访访客将不受影响。

作为最佳实践，您应停止现有活动，然后创建一个新活动，而不是在激活后更改百分比。新活动的报表从新访客开始，回访访客的数据不会导致报表不一致。

+++

## 访问次数如何计入 [!DNL Analytics] 换股贷方之公平值亏损/（收益） [!UICONTROL 自动定位] 使用A4T的活动？

+++答案当访客在A4T活动中符合、查看内容或转化时， [!DNL Target] 将事件数据发送到 [!DNL Analytics]. 此事件数据允许 [!DNL Analytics] 将页面上发生的转化事件和其他点击流事件归因于相关 [!DNL Target] 活动和体验。

查看时要记住以下几点 [!DNL Analytics] 报告：

* 通常，最佳做法是报告窗口从活动的开始日期开始。
* 如果转换发生在报表窗口之外，则该转换在中不可见 [!DNL Analytics].
* 当处于以下项的“目标”流量部分时 [!UICONTROL 自动定位] 活动时，访客可能会在不同会话中看到不同的体验。 例如，如果其用户档案或上下文已更改，并且 [!DNL Target]的机器学习算法决定，它们更有可能在新体验上转化。 随着访客从体验转移到体验，所看到的每个体验的访问计数都会递增。 这不同于常规的A/B测试活动，这些活动中的体验跨访问对访客来说是粘性的。
* 如果访客在访问中看到多个体验，则任何转化都始终归因于访客看到的最后一个体验。 如前所述，访客看到的每个体验的访问计数都会递增。 在“下查看体验时，这可能会人为地降低每个体验的转化率。[!UICONTROL 已定位]中的“ ”维度 [!DNL Adobe Analytics] 报告。

+++

## 使用 [!UICONTROL Analytics for Target] (A4T) 时如何跟踪 [!DNL Analysis Workspace] 中的活动印象？ {#activity-impressions}

+++回答

在中查看活动展示次数 [!DNL Analysis Workspace]：

1. 在 [!DNL Target] UI，单击 **[!UICONTROL 在Analytics中查看]**.
1. 添加 **[!UICONTROL 活动展示次数]** 列到 [[!DNL Analytics Workspace]](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html){target=_blank} 报告。
1. 在 **[!UICONTROL 活动展示次数]** 列中，单击 [!UICONTROL 齿轮] 图标。
1. 单击 **[!UICONTROL 使用非默认归因模型]**.
1. 选择 **[!UICONTROL 同一接触模型]** > **[!UICONTROL 应用]**.

+++