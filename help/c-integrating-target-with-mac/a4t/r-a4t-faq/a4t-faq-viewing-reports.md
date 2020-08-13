---
keywords: faq;frequently asked questions;analytics for target;a4T;report;reports;view reports;reporting;counting methodology;impressions;visitors;visits;default metric;activity conversions;unspecified
description: 本主题包含有关在使用 Analytics 作为 Target 报表源 (A4T) 时查看报表的常见问题解答。
title: 查看报表 - A4T 常见问题解答
feature: a4t troubleshooting
topic: Standard
uuid: d51991f7-cdda-4a59-b64c-7ef1c3f8380d
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '1992'
ht-degree: 63%

---


# 查看报表 - A4T 常见问题解答{#view-reports-a-t-faq}

This topic contains answers to questions that are frequently asked about viewing reports when using [!DNL Analytics] as the reporting source for [!DNL Target] (A4T).

## Can I view my Target activity data in Analysis Workspace? {#workspace}

您可以使 [!DNL Analysis Workspace] 用来分析 [!DNL Target] 活动和体验。 “目标 [分析”面板](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/a4t-panel.html) ，您可以查看多达三个成功指标的提升度和信心。 您还可以使用表格和可视化功能更深入地了解。

For detailed information and examples, open the [Analytics &amp; Target: Best Practices for Analysis tutorial](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), provided by Adobe Experience League.

## 在Analysis Workspace，可在何处应用细分？ {#segmentation}

区段最常应用于区段拖放区域中面板的顶部。 该段将应用于面板中的所有表和可视化。 此技术对于查看测试如何影响一部分人（例如，此测试对英国人的表现如何）最有用？

## 当我为特定目标活动应用点击区段时，为何会看到返回的不相关体验？ {#activity-segmentation}

发送到 [!DNL Target] 的 [!DNL Analytics] 变量具有 90 天的默认有效期。(注：到期期限可由客户服务部根据需要进行调整)。 当访客在此过期窗口中导航站点时，他们是许多的一部分 [!DNL Target] ，所有这些活动都在维中收集。

因此，当您对活动进行细分以使其出现在点击中时，您将获得该活动的所有体验，以 *及* 任何坚持该点击的其他体验。

## 我是否应将访客、访问或活动印象用作我的标准化指标（即计数方法）? {#metrics}

在A4T报告中，有多种标准化指标的选项。 该指标也称为计数方法，成为提升计算的分母。 此外，它也会在应用置信度计算之前影响数据汇总的方式。

* ***独特访客数***&#x200B;在用户首次符合活动条件时递增一次。
* 每个会话的&#x200B;***访问次数***&#x200B;在用户（独特访客）进入活动时递增，即使该用户在后续访问中未查看该活动也是如此。
* ***活动展示次数***&#x200B;在每次提供活动内容时递增。(按 [!DNL Target])。

当访客查看包含活动的页面时，系统会为该访客设置一个变量以包含该活动的名称。有关每种计数方法的比较方式，请参阅下面的详细情景。

请考虑以下事项：

* All of the above metrics trigger when a user qualifies for an activity and content is returned from [!DNL [!DNL Target]]. 这并不一定意味着用户查看了该选件。如果活动体验未显示且用户未向下滚动页面，则表示该选件由 [!DNL Target] 提供，但用户并未查看。
* 除非同一活动中的同一页面同时有多个 mbox 调用，否则“[!UICONTROL 活动展示次数]”（由 [!DNL Target] 测量）与“[!UICONTROL 实例数]”（由 [!DNL Analytics] 测量）相等。这会导致“[!UICONTROL 活动展示次数]”被计入多次，而“[!UICONTROL 实例]”只被计入一次。

## 为什么Analysis Workspace的“活动印象”和“活动转化率”高于Reports &amp; Analytics? {#sametouch}

[!DNL Reports & Analytics] 对“活动印象”和“活动转换”应用同触归因模型，而 [!DNL Analysis Workspace] 显示原始指标，该指标可能因维的持久性而 [!DNL Target] 膨胀。

To evaluate accurate [!UICONTROL Activity Impressions] and [!UICONTROL Activity Conversions] metrics in [!DNL Analysis Workspace], ensure that both metrics have [!UICONTROL Same Touch] attribution models applied. 可以通过单击列设置齿轮，启用[!UICONTROL 非默认归因模型]，然后选择[!UICONTROL 同一联系]来应用模型。了解有关属性IQ概 [述中归因的更多信息](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution.html) ，请参 *阅《分析工具指南》*。

## 如果营销人员在活动设置期间选择了一个 Analytics 量度，则“活动转化”意味着什么？{#section_F3EBACF85AF846E9B366A549AAB64356}

&quot;Activity conversions&quot; will be empty if an [!DNL Analytics] metric was selected as the conversion metric for the activity.

## 为什么我会在 Analytics 报表中看到“未指定”？这是什么意思？ {#unspecified}

在其他报表中，“未指定”意味着数据不符合分类规则，但在 A4T 中，不应出现此种情况。如果您看到“未指定”，则表示分类服务尚未运行。活动数据一般需要 24 到 72 小时才能显示在报表中。即使这些活动在此时间之前并未显示在报表中，但与这些活动绑定的所有访客数据都已被捕获，将在分类完成时显示出来。

分类期过后，数据会在从网站收集大约一小时后显示在这些报表中。报表中的所有量度、区段和值都来自您在设置活动时选择的报表包。

## 为什么即便在停用活动之后，Target 量度仍会被发送到 Analytics？{#section_38AA8380A4D54A18972F1EF3E73E22EF}

发送到 [!DNL Target] 的 [!DNL Analytics] 变量具有 90 天的默认有效期。如果需要，可由客户服务部调整此有效期。 但是，这是针对所有活动的全局设置，不能仅针对一个案例进行调整。

You might see [!DNL Target] variables sent to [!DNL Analytics] after the expiration period because the expiration is 90 days, but only if that user never sees another A4T-enabled [!DNL Target] activity. 如果用户在第 45 天返回网站并查看了另一个活动，则整个 A4T eVar 值会将其计数器重置为 90 天。这意味着从第 1 天开始的第一个营销活动可能会持续存在 45 + 90 = 135 天。If the user keeps coming back, you might get to the point where you see metrics sent to [!DNL Analytics] in your reporting from much older activities. 当用户删除 Cookie 并且不回到网站时，该活动中的数字将会下降，但您仍可以看到它们。

这意味虽然对于那些在活动有效时参与其中的访客来说活动已经结束，但这些活动仍会继续获取页面查看次数、访问次数等数据，时间长达 90 天。不过，如果您查看的是“[!UICONTROL 活动展示次数]”量度，则在活动结束后您不会看到任何展示次数。

这是正常的预期行为。A4T 变量的运作与其他任何 eVar 相同 - 该值会与用户相关联，直到它到达过期期限（90 天）。因此，如果某个活动仅有两周时间处于上线状态，但至少在未来 90 天内，该值仍将与用户相关联。

最佳做法是仅在活动上线的时间段内查看该活动的报表。The dates should be set correctly by default when you view the activity in [!DNL Analytics], so unless you have manually extended the date this shouldn’t be an issue from a reporting standpoint.

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

因为这两个体验都是在转化之前查看的，所以它们都获得了该订单的“点数”。但在系统中只产生了一个订单，所以点数的总计值反映了这一点。For [!DNL Target] reporting, because you aren’t putting a [!DNL Target] activity against another activity to see which is more successful, it doesn’t matter that all activities the user saw got credit. 因为您比较的是一个活动中的两个项目所得到的结果，而用户不可能在同一活动中看到不同的体验，因此您不必顾虑订单点数会造成相互之间的混淆。

For more information, see [Conversion Variables (eVar](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html)) in the *Analytics Admin Guide*.

## 为什么 Analytics 和 Analytics for Target (A4T) 在计算“独特访客”量度时得到的数字不同？{#section_0C3B648AB54041F9A2AA839D51791883}

当您运行的 A/B 测试使用“学生 t 检验”（置信度量度）来选择测试的入选者时，其假设之一是存在固定的时间范围。因此，除非您查看的是固定样本量，否则该测试不具有统计意义。

The [!UICONTROL Unique Visitors] metric is different in [!DNL Analytics] and [!DNL Target] only when you are looking at a period of time that is shorter than the actual test. 如果您未达到样本量，则测试并不可靠。有关详细信息，请参阅 [Evan Miller 的网站](https://www.evanmiller.org/index.html)上的[如何正确运行 A/B 测试](https://www.evanmiller.org/how-not-to-run-an-ab-test.html)。

The [!UICONTROL Unique Visitors] metric displays the number of people who have been exposed to the test who have visited the site during the specified time period. 这些人仍是测试的一部分，应计入在内。如果您只想查看一周内接触过该测试的人数，则可以创建一个具有活动展示次数的访客区段并将其应用于报表。

You can shorten the amount of time the [!DNL Target] variable persists down to a session; however, that is usually problematic for tests where the conversion event isn’t as likely to happen within the same session.

## 为什么同一访客有时会计入到 Analytics 的多个体验中？{#section_1397E972D31C4207A142E4D2D6D794A2}

The following list explains reasons why the same visitor could be counted in multiple experiences in [!DNL Analytics]:

* The [!DNL Target] profile expired but the [!DNL Analytics] cookie is still there. In this situation, [!DNL Target] re-evaluates the user but [!DNL Analytics] considers the visitor to be the same person.
* 如果访客正在使用 `mbox3rdPartyId`，则当匿名访客与其第三方 ID 配置文件合并时， 可能会将该访客带入不同的体验以与第三方 ID 匹配。[!DNL Target]有关更多信息，请参阅 [mbox3rdPartyID 的实时配置文件同步](../../../c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732)。
* [!DNL Analytics] 跟踪不同设备时，可能采用与跟踪这些设备不同的方 [!DNL Target] 式跟踪同一访客:中的第三方ID设置与 [!DNL Target] 分析中的设置不同。

## A4T 是否支持虚拟报表包？

虚拟报表包&#x200B;*未*&#x200B;包含在“报表包”列表中，并且 A4T 报表不支持虚拟报表包中的受众。

## 对于使用 A4T 的活动，我能否在激活活动后更改其中的流量分配百分比？

Changing the traffic allocation percentage in an activity after activation can cause inconsistent reporting in [!DNL Analytics] because the change impacts only new visitors. 回访访客将不受影响。

作为最佳实践，您应停止现有活动，然后创建一个新活动，而不是在激活后更改百分比。新活动的报表会从新访客开始，而回访访客的数据并不会导致报表不一致。
