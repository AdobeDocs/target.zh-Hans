---
keywords: faq;常见问题解答;analytics for target;a4T;报表;报告;查看报表;查看报告;计数方法;展示次数;访客;访问次数;默认量度;活动转化;未指定
description: 查找有关在 [!DNL Target] (A4T). A4T lets you use Analytics reporting for [!DNL Target] 活动使用Analytics时查看报告时经常出现的问题的解答。
title: 查找有关使用A4T查看报表的问题的解答？
feature: Analytics for Target (A4T)
exl-id: a02eeb34-3975-424b-a046-e51f10ae1823
translation-type: tm+mt
source-git-commit: 0136e1a17181ed6bc39b112ee464eff5af7785b0
workflow-type: tm+mt
source-wordcount: '2512'
ht-degree: 37%

---

# 查看报表 - A4T 常见问题解答

本主题包含有关在将[!DNL Adobe Analytics]用作[!DNL Adobe Target](A4T)的报告源时查看报告时经常询问的问题的解答。

## 是否可以在Analysis Workspace中视图[!DNL Target]活动数据？{#workspace}

您可以使用[!DNL Analysis Workspace]分析[!DNL Target]活动和体验。 [“目标分析”面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html)可让您查看多达三个成功量度的提升度和置信度。 您还可以使用表格和可视化功能更深入地了解。

有关详细信息和示例，请打开[分析和目标:分析教程的最佳实践](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)，由Adobe Experience League提供。

## 在Analysis Workspace中可在何处应用区段？{#segmentation}

区段最常用于区段拖放区域中面板顶部。 该段将应用于面板中的所有表和可视化。 此技术对于查看测试如何影响部分人群（例如，此测试对英国人民的效果如何）非常有用？

段也可以直接分层到自由形式表中，但请注意，必须将它覆盖到整个表中，以在A4T面板中保留提升和置信度计算。 面板中当前不支持列级段。

## 当我为特定[!DNL Target]活动应用点击区段时，为何返回不相关的体验？{#activity-segmentation}

发送到 [!DNL Target] 的 [!DNL Analytics] 变量具有 90 天的默认有效期。(注：到期期限可由客户服务部门根据需要进行调整)。 当访客在此过期窗口中导航站点时，它们是许多[!DNL Target]活动的一部分，所有这些都在维中收集。

当您对活动进行细分以使其显示在点击中时，您会获得该活动&#x200B;*中的所有体验，加上*&#x200B;所有在该点击上持续的其他体验。

## 配置我的目标量度时，为什么无法访问高级设置？

对于使用[!DNL Analytics]作为报告源(A4T)的活动，目标量度使用“[!UICONTROL 活动中的增量计数和保持用户”和“[!UICONTROL 每次印象]”设置。 ]这些设置&#x200B;*不可配置*。

有关详细信息，请参阅“配置目标量度时，为何无法访问高级设置选项？” 在[量度定义 — A4T常见问题解答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md)中。

## 我是否应将访客、访问或活动印象用作我的标准化量度（即计数方法）？{#metrics}

在A4T报告中，有多种用于标准化量度的选项。 此量度也称为计数方法，它成为提升计算的分母。 此外，它也会在应用置信度计算之前影响数据汇总的方式。

* ***独特访客数***&#x200B;在用户首次符合活动条件时递增一次。
* 每个会话的&#x200B;***访问次数***&#x200B;在用户（独特访客）进入活动时递增，即使该用户在后续访问中未查看该活动也是如此。
* ***活动展示次数***&#x200B;在每次提供活动内容时递增。（由[!DNL Target]测量）。

当访客查看包含活动的页面时，系统会为该访客设置一个变量以包含该活动的名称。有关每种计数方法的比较方式，请参阅下面的详细情景。

请考虑以下事项：

* 当用户符合活动条件并从[!DNL Target]返回内容时，上述量度将触发。 这并不一定意味着用户查看了该选件。如果活动体验未显示且用户未向下滚动页面，则表示该选件由 [!DNL Target] 提供，但用户并未查看。
* 除非同一活动中的同一页面同时有多个 mbox 调用，否则“[!UICONTROL 活动展示次数]”（由 [!DNL Target] 测量）与“[!UICONTROL 实例数]”（由 [!DNL Analytics] 测量）相等。这会导致“[!UICONTROL 活动展示次数]”被计入多次，而“[!UICONTROL 实例]”只被计入一次。

有关详细信息，请参阅[如何在Analysis Workspace中为&#x200B;*Adobe TargetTutorials*&#x200B;中的自动目标活动](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html)设置A4T报告。

## Analysis Workspace中的“活动印象”和“活动转换”为何高于Reports &amp; Analytics?{#sametouch}

[!DNL Reports & Analytics] 对“活动印象”和“活动转换”应用同触归因模型，而 [!DNL Analysis Workspace] 显示原始量度，由于维度的持久性，原始量度可能显得 [!DNL Target] 虚高。

要评估[!DNL Analysis Workspace]中准确的[!UICONTROL 活动印象]和[!UICONTROL 活动转换]量度，请确保这两个量度均应用了[!UICONTROL 相同的Touch]归因模型。 可以通过单击列设置齿轮，启用[!UICONTROL 非默认归因模型]，然后选择[!UICONTROL 同一联系]来应用模型。了解有关&#x200B;*分析工具指南*&#x200B;中[属性IQ概述](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/attribution.html)中归因的更多信息。

## 如果营销人员在活动设置期间选择了一个 Analytics 量度，则“活动转化”意味着什么？{#section_F3EBACF85AF846E9B366A549AAB64356}

如果选择[!DNL Analytics]量度作为活动的转换量度，则“活动转换”为空。

## 为什么我会在 Analytics 报表中看到“未指定”？这是什么意思？ {#unspecified}

在其他报表中，“未指定”意味着数据不符合分类规则，但在 A4T 中，不应出现此种情况。如果您看到“未指定”，则表示分类服务尚未运行。活动数据一般需要 24 到 72 小时才能显示在报表中。即使活动在此之前不显示在此报表中，所有与这些访客关联的活动数据也会被捕获并在分类完成时显示。

分类期过后，数据会在从网站收集大约一小时后显示在这些报表中。报表中的所有量度、区段和值都来自您在设置活动时选择的报表包。

如果对该活动进行了分类，并且报表中仍显示“未指定”行，请确保报表未使用非[!DNL Target]量度显示数据。 除非报表使用特定于[!DNL Target]的量度，否则“未指定”行包含与未与[!DNL Target]关联的调用的事件。 该行不包含任何与[!DNL Target]相关的信息(例如，访客/访问/展示次数)。

## 为什么[!DNL Target]量度会在取消激活活动后发送到Analytics?{#section_38AA8380A4D54A18972F1EF3E73E22EF}

发送到 [!DNL Target] 的 [!DNL Analytics] 变量具有 90 天的默认有效期。如有需要，可由客户服务部门调整此过期期限。 但是，这是针对所有活动的全局设置，不能仅针对一个案例进行调整。

到期期结束后，您可能会看到[!DNL Target]变量发送到[!DNL Analytics]，因为到期时间为90天，但仅当该用户从未看到另一个启用A4T的[!DNL Target]活动时。 如果用户在第 45 天返回网站并查看了另一个活动，则整个 A4T eVar 值会将其计数器重置为 90 天。这意味着从第 1 天开始的第一个营销活动可能会持续存在 45 + 90 = 135 天。如果用户不断回访，您可能会看到许多旧活动将量度发送到您报告中的[!DNL Analytics]。 当用户删除Cookies且不返回网站时，该活动中的数字会下降，但您仍然可以看到它们。

这意味着活动在活动结束后90天内仍可继续获得页面视图、访问等，这些访客在活动时成为活动的一部分。 不过，如果您查看的是“[!UICONTROL 活动展示次数]”量度，则在活动结束后您不会看到任何展示次数。

这是正常的预期行为。A4T 变量的运作与其他任何 eVar 相同 - 该值会与用户相关联，直到它到达过期期限（90 天）。因此，如果活动仅活动两周，则该值至少在接下来90天内仍与用户关联。

最佳做法是仅在活动上线的时间段内查看该活动的报表。默认情况下，在[!DNL Analytics]中视图活动时，应正确设置日期，因此除非您手动延长日期，否则从报告的角度来看，这不应是问题。

例如，假设A4T变量在90天后过期，且测试在1月1日到1月15日期间处于活动状态。

在 1 月 1 日，某个用户访问该网站，然后查看了活动 XYZ 一次，之后又查看了五个页面。在接下来的两周内，该用户未返回该网站。那么，此用户的数据应如下所示：

| 活动名称 | 实例（展示次数） | 页面查看次数 | 访问次数 | 独特访客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 5 | 3 | 3 |

2 月 1 日，该用户返回了网站，查看了其他 5 个页面，并且未体验任何其他 Target 活动，而此时原来的活动已不再上线。即使该活动不再处于上线状态，它仍会通过 eVar 持久性跟踪该用户。现在，数据如下所示：

| 活动名称 | 实例（展示次数） | 页面查看次数 | 访问次数 | 独特访客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 10 | 2 | 1 |

3 月 1 日，该用户又返回网站，查看了一个新活动 ABC。另外，该用户也查看了五个页面。由于活动 XYZ仍通过持久性跟踪用户，并且此用户随后设置了ABC，您将在报告中看到两个行项目：

| 活动名称 | 实例（展示次数） | 页面查看次数 | 访问次数 | 独特访客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 15 | 3 | 1 |
| ABC | 1 | 5 | 1 | 1 |

之后，该用户在 4 月 1 日再次返回网站，查看了另外 5 个页面，并进行了一次购买。第一个eVar值的90天到期将在4月1日重置，因此您可以在报告中看到这一点。 该用户查看的所有 Target 活动都会收到转化点数，但在转化点数总和中，会将重复计算的点数删除：

| 活动名称 | 实例（展示次数） | 页面查看次数 | 访问次数 | 独特访客 | 订单数 |
|--- |--- |--- |--- |--- |--- |
| XYZ | 1 | 20 | 4 | 1 | 1 |
| ABC | 1 | 10 | 2 | 1 | 1 |
| 合计 | 2 | 20 | 1 | 1 | 1 |

由于两种体验在转换前均可看到，因此它们都会获得订单的“信用”。 但在系统中只产生了一个订单，所以点数的总计值反映了这一点。对于[!DNL Target]报告，由于您没有将[!DNL Target]活动放在其他活动上以查看哪个更成功，因此用户看到的所有活动都获得信用并不重要。 您将比较单个活动中两个项目的结果。用户不可能在同一活动看到不同的体验，因此您不必担心订单信用的交叉污染。

有关详细信息，请参阅&#x200B;*Analytics管理指南*&#x200B;中的[转换变量(eVar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html))。

## 为什么在取消激活活动后继续查看更多印象？{#deactivated}

取消激活后A4T活动报表的展示源可以是QA模式流量。 目标通常不会记录已停用活动的事件，但Analytics无法了解展示次数来自QA模式。 从Analytics检索目标活动报表时，将显示这些印象。 这是按设计运行的，因为即使活动未使用QA模式处于活动状态，客户也需要检查A4T报表的方法。

## Adobe Target(A4T)的Analytics和Analytics为何以不同方式计算“唯一访客”量度的数字？{#section_0C3B648AB54041F9A2AA839D51791883}

当您运行的 A/B 测试使用“学生 t 检验”（置信度量度）来选择测试的入选者时，其假设之一是存在固定的时间范围。因此，除非您查看的是固定样本量，否则该测试不具有统计意义。

[!UICONTROL 唯一访客]量度仅在查看比实际测试短的时段时在[!DNL Analytics]和[!DNL Target]中有所不同。 如果您未达到样本量，则测试并不可靠。有关详细信息，请参阅 [Evan Miller 的网站](https://www.evanmiller.org/index.html)上的[如何正确运行 A/B 测试](https://www.evanmiller.org/how-not-to-run-an-ab-test.html)。

[!UICONTROL 唯一访客]量度显示在指定时间段内访问过站点的测试人员的数量。 这些人是测试的一部分，应该被计数。 如果您只想查看一周内接触过该测试的人数，则可以创建一个具有活动展示次数的访客区段并将其应用于报表。

您可以缩短[!DNL Target]变量持续到会话的时间；但是，对于转换事件在同一会话中不太可能发生的测试，这是有问题的。

## 为什么同一访客有时会计入到 Analytics 的多个体验中？{#section_1397E972D31C4207A142E4D2D6D794A2}

以下列表解释了为什么在[!DNL Analytics]中可以将同一访客计入多个体验的原因：

* [!DNL Target]用户档案已过期，但[!DNL Analytics] Cookie仍在。 在这种情况下，[!DNL Target]会重新评估用户，但[!DNL Analytics]会认为访客是同一人。
* 如果访客使用`mbox3rdPartyId`，则当匿名访客与第三方ID用户档案合并时，[!DNL Target]可以将该访客置于不同的体验中，以与第三方ID匹配。 有关更多信息，请参阅 [mbox3rdPartyID 的实时配置文件同步](/help/c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732)。
* [!DNL Analytics] 跟踪不同设备时，可能采用不同的方式跟踪同一访客，而 [!DNL Target] 不是跟踪这些设备：中的第三方ID设置与 [!DNL Target] Analytics中的不同。

## A4T 是否支持虚拟报表包？

虚拟报表包&#x200B;*未*&#x200B;包含在“报表包”列表中，并且 A4T 报表不支持虚拟报表包中的受众。

## 对于使用 A4T 的活动，我能否在激活活动后更改其中的流量分配百分比？

在激活后更改活动中的流量分配百分比可能导致[!DNL Analytics]中的报告不一致，因为更改仅影响新访客。 回访访客将不受影响。

作为最佳实践，您应停止现有活动，然后创建一个新活动，而不是在激活后更改百分比。报告具有新访客的新活动开始和来自返回访客的数据不会导致不一致的报告。

## 在使用A4T的自动目标活动中，如何在Analytics中计入访问量和转化信用？

当访客符合条件、视图内容或在A4T活动中转换时，[!DNL Target]会向[!DNL Analytics]发送事件数据。 此事件数据允许[!DNL Analytics]将页面上发生的转换事件和其他点击流事件归因于相关的[!DNL Target]活动和体验。

以下是查看[!DNL Analytics]报告时要牢记的几点：

* 通常，作为最佳实践，您的报告窗口应从活动的开始日期开始。
* 如果在报表窗口之外发生转换，则转换在[!DNL Analytics]中不可见。
* 当位于[!UICONTROL 自动目标]活动的“目标”流量部分时，访客可能会看到不同的体验，不同的会话。 例如，如果用户档案或上下文已发生更改，且[!DNL Target]的机器学习算法认为他们更有可能根据新体验进行转换。 当访客在体验之间移动时，每次查看的体验的访问次数都会增加。 这与常规A/B测试活动不同，在常规A/B测试中，不同访问的访客体验会相互粘滞。
* 如果访客在访问中看到多个体验，则任何转化均始终归因于访客看到的上次体验。 如前所述，访客查看的每个体验的访问计数都会增加。 在查看[!DNL Adobe Analytics]报表中“[!UICONTROL 目标]”维度下的体验时，这可能会人为地降低每个体验的转化率。
