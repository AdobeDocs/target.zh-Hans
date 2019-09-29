---
description: 本主题包含有关在使用 Analytics 作为 Target 报表源 (A4T) 时查看报表的常见问题解答。
keywords: faq;常见问题解答;analytics for target;a4T;报表;报告;查看报表;查看报告;计数方法;展示次数;访客;访问次数;默认量度;活动转化;未指定
seo-description: 本主题包含有关在使用 Analytics 作为 Target 报表源 (A4T) 时查看报表的常见问题解答。
seo-title: 查看报表 - A4T 常见问题解答
solution: Target
title: 查看报表 - A4T 常见问题解答
topic: Standard
uuid: d51991f7-cdda-4a59-b64c-7ef1c3f8380d
translation-type: tm+mt
source-git-commit: 8dc94ca1ed48366e6b3ac7a75b03c214f1db71d9

---


# 查看报表 - A4T 常见问题解答{#view-reports-a-t-faq}

本主题包含有关在使用 Analytics 作为 Target 报表源 (A4T) 时查看报表的常见问题解答。

## 什么是计数方法？如何使用它？{#section_E9C21C47B5BE4E54BABF0CD7F03D3945}

计数方法指定了 Target 使用什么作为转化率的分母。选项包括：

* 展示次数
* 访客数
* 访问次数

## 我是否可以为 Target 报表设置默认量度？ {#section_50C20D286AA042CCA958184C9C0767DD}

对于“活动”报表，管理员可以更改默认量度，这样每次运行报表时都会显示相同的量度。否则，报表会将您在上一个报表中应用的最后一个量度作为默认量度。

For more information, see [Select default report metrics](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/metrics.html) in the *Analytics Analyze Guide*.

## 何时将区段应用于报表，以及何时将区段应用于量度（包含计算量度）？{#section_BC29DEE6D2734911A5CD6FBF1189EB89}

将区段应用于报表与在 Target Classic 中应用区段类似。如要查看测试会对某一类人产生什么影响（例如，此测试在英国人中表现如何），此技巧最为有用。

可以将区段应用于包含计算量度的量度。这通常是在您想要创建新类型的成功事件时完成的，例如：如果您想查看活动产生了多少位回访访客，或者查看了您的测试的访客中有多少人将来到了某个特定页面。请注意，目前无法生成适用于计算量度的提升度和置信度。

## 我是否应在查看报表时使用访客数、活动展示次数或访问次数？ {#metrics}

有几个选项可供选择，每个选项都有各自的优势：

* *独特访客数&#x200B;*****&#x200B;在用户首次符合活动条件时递增一次。
* 每个会话的&#x200B;*访问次数&#x200B;*****&#x200B;在用户（独特访客）进入活动时递增，即使该用户在后续访问中未查看该活动也是如此。
* *活动展示次数&#x200B;*****&#x200B;在每次提供活动内容时递增。（由 Target 测量）
* *实例&#x200B;*****&#x200B;在提供活动内容后，每页一次地递增。（由 Analytics 测量）

当访客查看包含活动的页面时，系统会为该访客设置一个变量以包含该活动的名称。有关每种计数方法的比较方式，请参阅下面的详细情景。

请考虑以下事项：

* 当用户符合活动条件并从 [!DNL Target] 返回内容时，所有上述量度都会触发。这并不一定意味着用户查看了该选件。如果活动体验未显示且用户未向下滚动页面，则表示该选件由 [!DNL Target] 提供，但用户并未查看。
* 除非同一活动中的同一页面同时有多个 mbox 调用，否则“[!UICONTROL 活动展示次数]”（由 [!DNL Target] 测量）与“[!UICONTROL 实例数]”（由 [!DNL Analytics] 测量）相等。这会导致“[!UICONTROL 活动展示次数]”被计入多次，而“[!UICONTROL 实例]”只被计入一次。
* When using Activity Impressions and Activity Conversions metrics in , ensure that both metrics have Same Touch attribution models applied. [!DNL Analysis Workspace]可通过单击列设置齿轮，启用“非默认”( [!UICONTROL Non-default)归因模型]，然后选择“相 [!UICONTROL 同触控”(Same Touch)应用模型]。 了解有关属性的更多信息， [请参阅分析工具指南](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution.html) ，了解属 *性IQ概述*。

## 如果营销人员在活动设置期间选择了一个 Analytics 量度，则“活动转化”意味着什么？{#section_F3EBACF85AF846E9B366A549AAB64356}

如果将 Analytics 量度选作该活动的转化量度，则“活动转化”将为空。

## 为什么我会在 Analytics 报表中看到“未指定”？这是什么意思？ {#unspecified}

![](assets/unspecified.png)

在其他报表中，“未指定”意味着数据不符合分类规则，但在 A4T 中，不应出现此种情况。如果您看到“未指定”，则表示分类服务尚未运行。活动数据通常需要24到72小时才能显示在报告中。 即使这些活动在此时间之前并未显示在报表中，但与这些活动绑定的所有访客数据都已被捕获，将在分类完成时显示出来。

分类期过后，数据会在从网站收集大约一小时后显示在这些报表中。报表中的所有量度、区段和值都来自您在设置活动时选择的报表包。

## 为什么即便在停用活动之后，Target 量度仍会被发送到 Analytics？{#section_38AA8380A4D54A18972F1EF3E73E22EF}

发送到 [!DNL Target] 的 [!DNL Analytics] 变量具有 90 天的默认有效期。如果需要，客户关怀团队可调整此有效期。但是，这是针对所有活动的全局设置，不能仅针对一个案例进行调整。

因为 Target 变量具有 90 天的过期期限，因此您可能会在过期期限后看到已发送到 Analytics 的 Target 变量，但只有当该用户从未查看其他启用 A4T 的 Target 活动时才会如此。如果用户在第 45 天返回网站并查看了另一个活动，则整个 A4T eVar 值会将其计数器重置为 90 天。这意味着从第 1 天开始的第一个营销活动可能会持续存在 45 + 90 = 135 天。如果该用户不断返回网站，则您可能会看到从很早的活动的报表中发送到 Analytics 的量度。当用户删除 Cookie 并且不回到网站时，该活动中的数字将会下降，但您仍可以看到它们。

这意味虽然对于那些在活动有效时参与其中的访客来说活动已经结束，但这些活动仍会继续获取页面查看次数、访问次数等数据，时间长达 90 天。不过，如果您查看的是“[!UICONTROL 活动展示次数]”量度，则在活动结束后您不会看到任何展示次数。

这是正常的预期行为。A4T 变量的运作与其他任何 eVar 相同 - 该值会与用户相关联，直到它到达过期期限（90 天）。因此，如果某个活动仅有两周时间处于上线状态，但至少在未来 90 天内，该值仍将与用户相关联。

最佳做法是仅在活动上线的时间段内查看该活动的报表。默认情况下，在 Analytics 中查看活动时，日期应已设置正确，因此除非您手动延长日期，否则从报表的角度来看这不会成为问题。

例如，我们假设某个 A4T 变量在 90 天后过期，我们的测试上线时间是从 1 月 1 日到 1 月 15 日。

在 1 月 1 日，某个用户访问该网站，然后查看了活动 XYZ 一次，之后又查看了五个页面。在接下来的两周内，该用户未返回该网站。那么，此用户的数据应如下所示：

| 活动名称 | 实例（展示次数） | 页面查看次数 | 访问次数 | 独特访客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 5 | 1 | 1 |

2 月 1 日，该用户返回了网站，查看了其他 5 个页面，并且未体验任何其他 Target 活动，而此时原来的活动已不再上线。即使该活动不再处于上线状态，它仍会通过 eVar 持久性跟踪该用户。现在，数据如下所示：

| 活动名称 | 实例（展示次数） | 页面查看次数 | 访问次数 | 独特访客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 10 | 2 | 1 |

3 月 1 日，该用户又返回网站，查看了一个新活动 ABC。另外，该用户也查看了五个页面。由于活动 XYZ 仍通过持久性跟踪用户，并且此用户已有了 ABC 设置，因此我们会在报表中看到两行项目：

| 活动名称 | 实例（展示次数） | 页面查看次数 | 访问次数 | 独特访客 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 15 | 3 | 1 |
| ABC | 1 | 5 | 1 | 1 |


之后，该用户在 4 月 1 日再次返回网站，查看了另外 5 个页面，并进行了一次购买。第一个 eVar 值的 90 天有效期已在 4 月 1 日重置，我们会在报表中看到这一点。该用户查看的所有 Target 活动都会收到转化点数，但在转化点数总和中，会将重复计算的点数删除：

| 活动名称 | 实例（展示次数） | 页面查看次数 | 访问次数 | 独特访客 | 订单数 |
|--- |--- |--- |--- |--- |--- |
| XYZ | 1 | 20 | 4 | 1 | 1 |
| ABC | 1 | 10 | 2 | 1 | 1 |
| 合计 | 2 | 20 | 3 | 1 | 1 |

因为这两个体验都是在转化之前查看的，所以它们都获得了该订单的“点数”。但在系统中只产生了一个订单，所以点数的总计值反映了这一点。对于 Target 报表，由于您没有将 Target 活动相互进行比较以查看哪个活动更成功，因此不用担心用户查看的所有活动都获得点数。因为您比较的是一个活动中的两个项目所得到的结果，而用户不可能在同一活动中看到不同的体验，因此您不必顾虑订单点数会造成相互之间的混淆。

For more information, see [Conversion Variables (eVar](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html)) in the *Analytics Admin Guide*.

## 为什么 Analytics 和 Analytics for Target (A4T) 在计算“独特访客”量度时得到的数字不同？{#section_0C3B648AB54041F9A2AA839D51791883}

当您运行的 A/B 测试使用“学生 t 检验”（置信度量度）来选择测试的入选者时，其假设之一是存在固定的时间范围。因此，除非您查看的是固定样本量，否则该测试不具有统计意义。

只有当您查看的时间段比实际测试时间短时，Analytics 和 Target 中的“独特访客”量度才会有所不同。如果您未达到样本量，则测试并不可靠。有关详细信息，请参阅 [Evan Miller 的网站](https://www.evanmiller.org/index.html)上的[如何正确运行 A/B 测试](https://www.evanmiller.org/how-not-to-run-an-ab-test.html)。

“独特访客”量度显示的是在指定时间段内，访问过该网站且接触过该测试的人数。这些人仍是测试的一部分，应计入在内。如果您只想查看一周内接触过该测试的人数，则可以创建一个具有活动展示次数的访客区段并将其应用于报表。

您可以缩短 Target 变量在会话中持续存在的时间长度；但是，对于转化事件不可能在同一会话中发生的测试而言，这通常是有问题的。

## 为什么同一访客有时会计入到 Analytics 的多个体验中？ {#section_1397E972D31C4207A142E4D2D6D794A2}

下面几点对此进行了解释：

* Target 配置文件已过期，但 Analytics Cookie 仍然存在。在这种情况下，Target 会重新评估用户，但 Analytics 会认为该访客是同一个人。
* 如果访客正在使用 `mbox3rdPartyId`，则当匿名访客与其第三方 ID 配置文件合并时，Target 可能会将该访客带入不同的体验以与第三方 ID 匹配。有关更多信息，请参阅 [mbox3rdPartyID 的实时配置文件同步](../../../c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732)。
* Analytics 可能会将不同设备作为同一访客来跟踪，这与 Target 跟踪这些设备的方式不同，因为 Target 中的第三方 ID 设置与 Analytics 中的设置不同。

## A4T 是否支持虚拟报表包？

虚拟报表包&#x200B;*未*&#x200B;包含在“报表包”列表中，并且 A4T 报表不支持虚拟报表包中的受众。

## 对于使用 A4T 的活动，我能否在激活活动后更改其中的流量分配百分比？

如果在激活后更改活动中的流量分配百分比，可能会导致 Analytics 中的报表出现不一致，因为此更改仅对新访客产生影响。回访访客将不受影响。

作为最佳实践，您应停止现有活动，然后创建一个新活动，而不是在激活后更改百分比。新活动的报表会从新访客开始，而回访访客的数据并不会导致报表不一致。

## 我能否在 Adobe Analysis Workspace 中查看 Target 活动数据？

您可以使用 [!DNL Adobe Analysis Workspace] 来深入挖掘并可视化数据，或揭示表面下隐藏的洞察。

For detailed information and examples, open the [Analytics &amp; Target: Best Practices for Analysis tutorial](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), provided by Adobe Experience League.