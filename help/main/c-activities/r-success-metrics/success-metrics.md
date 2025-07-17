---
keywords: 定位；成功；转化量度；页面得分量度；页面查看次数量度；收入量度；网站逗留时间量度；预计值；高级设置；成功量度；高级设置；依赖项；依赖项；递增计数并保持用户处于活动中；递增计数、释放用户和允许再次进入；递增计数、释放用户和禁止再次进入
description: 了解帮助您确定活动是否成功的成功量度。 成功量度包括转化率、收入、页面查看次数、自定义评分和网站逗留时间。
title: 什么是成功量度？
feature: Success Metrics
exl-id: 38d5314d-4950-4106-a058-0d221faf5a24
source-git-commit: ad26684d40ccb5239a345da73adfa924a04189ef
workflow-type: tm+mt
source-wordcount: '1367'
ht-degree: 22%

---

# [!UICONTROL Success metrics]

[!DNL Adobe Target]中的成功量度是帮助衡量活动性能的关键指标。 这些量度可捕获重要的业务结果，例如转化率、每位访客带来的收入和客户参与度，从而让您能够评估特定体验或选件的影响。

例如，您可以跟踪新的促销活动是增加每位访客带来的收入，还是导致更多项目添加到购物车。 成功量度还有助于识别用户流（如注册、结账或购买流程）中的问题，同时提供有关访客整体行为的洞察。

## 概述

在[!DNL Target]中，为成功量度预配置了建议的设置，以确保准确的报告和有效跟踪。

默认情况下，转换事件使用设置&#x200B;**[!UICONTROL Increment count & keep user in activity]。**&#x200B;此设置意味着每个访客仅被计为一次转化。 不计算重复转化。 这些访客在整个会话期间将继续查看活动内容。

对于使用相同设置的收入量度，只有访客的第一笔订单会记录订单详细信息。 虽然后续订单会增加转化计数，但它们不会计入基于收入的量度，如[!UICONTROL Revenue per Visitor (RPV)]、[!UICONTROL Average Order Value (AOV)]或[!DNL Total Sales]。 这些附加订单也从[!UICONTROL Order Details]报表中排除。

>[!NOTE]
>
>对于使用[Analytics作为报表源](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)的活动，目标量度始终使用“[!UICONTROL Increment Count & Keep User in Activity]”和“[!UICONTROL On Every Impression]”设置。 这些设置是&#x200B;*不可配置的*。

可以在[!UICONTROL Reporting Settings]的[!UICONTROL Activity Settings page]部分中的[!UICONTROL Goals & Settings]步骤下配置以下成功量度：

| 成功量度 | 测量方法 | 定义 |
|--- |--- |--- |
| [!UICONTROL Con]版本 | 基于转化 | 转化是指访客在您定义的网站上执行某项操作时，例如 <ul><li>已查看页面</li><li>已查看 mbox</li><li>已单击元素</li></ul>每个访客或每次访客完成转化时，转化可以计为一次。 |
| [!UICONTROL Revenue] | 基于转化 | 由访问带来的收入。您只能选择一个收入量度：<ul><li>已查看 mbox</li></ul>有关更新的[!DNL Target] UI中与收入成功量度相关的更改的详细信息，请参阅下面的[与成功量度相关的UI更改](#changes)。 |
| [!UICONTROL Engagement] | 基于参与度 | 访问生成的参与度。 您可以从以下参与量度中进行选择：<UL><li>页面查看次数：每次独特访问均会计为一次转化。</li><li>[!UICONTROL Custom Scoring]：从访客第一次看到活动的第一个展示区[!DNL Target]请求开始，根据网站上已访问页面的分配值得出汇总分数。</li>[!DNL Time on Site]：从访客看到活动的第一个显示[!DNL Target]请求到加载会话中具有请求的最后一页所花费的时间（以秒为单位）。</UL> |

对于基于参与度的量度（与基于转化和基于收入的量度不同），访客必须重新获得每次访问时活动的资格，才能递增该会话的计数。 关联的量度将在重新获得资格后开始递增，并在每个访客的会话结束时停止。会话若处于不活动状态超过 30 分钟便会结束。因此，在测试期间不会立即看到结果；但是，从该会话获得的所有结果在会话结束后的几分钟内均可用。

## 自定义成功量度

您也可以创建自定义成功量度。

选择成功量度后，请选择访客为实现目标所需执行的操作。例如，选择一个[!UICONTROL Conversion]量度，将其设置为每个访客计数一次，然后设置当访客查看特定页面（或页面集）、查看特定[!DNL Target]请求或单击特定链接时是否获得成功。

如果启用，[!UICONTROL Estimated Value of one conversion]字段（不适用于[!UICONTROL Page Score]指标）会为您的目标提供一个值，但此值不适用于其他指标。 通过此值，[!DNL Target] 可以计算出预计收入提升。此字段为可选字段；但是，如果没有该字段，便无法计算所有非收入量度的增量收入。对于所有收入量度（[!UICONTROL Revenue per Visitor]、[!UICONTROL Average Order Value]、[!UICONTROL Total Sales]和[!UICONTROL Orders]），估计使用[!UICONTROL Revenue per Visitor]。 数据类型为货币。请参阅[预计收入提升](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)以了解更多信息。

当您查看活动的报表时，您为活动选择的成功量度会显示在报表设置中。

某些量度（如[!UICONTROL Custom Scoring]和[!UICONTROL Revenue Per Visitor]）需要传递信息（如订单合计和订单ID）的自定义实施。

## 高级设置 {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

可使用高级设置来管理成功的衡量方式。选项包括添加依赖项、选择是将用户保留在活动中还是将其删除，以及是为每个参加者还是每次展示都计算一次量度。

要访问[!UICONTROL Advanced Settings]选项，请单击&#x200B;**[!UICONTROL More Actions]**&#x200B;图标（![更多操作图标](/help/main/assets/icons/MoreSmallListVert.svg) ），然后单击&#x200B;**[!UICONTROL Advanced Settings]**。

![“高级设置”菜单](/help/main/c-activities/r-success-metrics/assets/advanced-settings-refresh.png)

有关[!UICONTROL Advanced Settings]选项（“[!UICONTROL What will happen after a user encounters this goal]”和“[!UICONTROL How will the count be incremented]”）的详细信息，请参阅[用户遇到此目标量度后会出现什么情况](#what-happens)？

>[!NOTE]
>
>如果您将 [!DNL Adobe Analytics] 用作报表源，则设置会由 [!DNL Analytics] 服务器来管理。[!UICONTROL Advanced Settings]选项不可用。 有关详细信息，请参阅将[Adobe Analytics作为Adobe Target (A4T)的报表源](/help/main/c-integrating-target-with-mac/a4t/a4t.md)。

### 添加依赖项

您可以使用高级设置创建依赖的成功量度，仅当访客先实现某个量度时才递增另一个量度。

例如，仅当访客在转化之前先点击了选件或访问了某个特定页面时，测试转化才可能有效。

依赖项功能&#x200B;*不支持以下*：

* [!UICONTROL Recommendations]活动。 其他所有活动类型均支持此功能。
* 如果您使用[Analytics作为报表源](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)。
* “查看了某个页面”量度类型。
* 可视化体验编辑器(VEC)活动的“已单击元素”量度类型。

在以下情况下，依赖的成功量度不会转化：

* 如果您创建了循坏依赖关系，例如量度 1 依赖于量度 2，而量度 2 又依赖于量度 1，则任何量度都无法转化。
* [!UICONTROL Automated Personalization]活动在达到转化量度时释放用户并重新启动活动，因此依赖该转化量度的任何量度都不会转化。

### 用户遇到此目标量度后会出现什么情况？ {#what-happens}

可使用高级设置来决定用户实现目标量度后将发生的情况。下表显示了可用的选项：

| 用户遇到此目标量度后 | 选项 |
|--- |--- |
| [!UICONTROL Increment Count & Keep User in Activity] | 指定计数的递增方式：<ul><li>每个参加者一次（默认）</li><li>每次展示时（页面刷新除外）</li><li>每次展示时</li></ul> |
| [!UICONTROL Increment Count, Release user, & Allow Reentry] | 选择访客重新进入活动时看到的体验：<ul><li>相同体验（默认）</li><li>随机体验</li><li>无形体验</li></ul> |
| [!UICONTROL Increment Count, Release User, & Bar from Reentry] | 确定用户将看到什么内容来替代活动内容：<ul><li>相同体验（不含“跟踪”功能）（默认）</li><li>默认内容，或其他活动内容</li></ul> |

>[!NOTE]
>
>如果将某个量度配置为[!UICONTROL Increment Count]选项（如上所述）之一，则量度计数仅在访客级别按每个参加者正确递增一次。 指标计数在访问级别针对每个新会话每次访问递增一次。

### 计数如何递增：

选择所需的行为：

* 每个参加者一次
* 每次展示时（页面刷新除外）
* 每次展示时

## 已知问题

* 其高级选项“计数将如何递增”被设置为“每次展示”或“每次展示（不包括刷新）”的成功指标无法用作另一指标所依赖的成功指标。

  将成功量度设置为每次展示递增时，[!DNL Target]会在每次访客访问此成功量度时再次计入访客。 然后，[!DNL Target]将成功量度“成员资格”重置为0，以便在下次展示时再次对其计数。 因此，如果另一个量度要求首先看到此量度，[!DNL Target]从不识别用户已看到第一个量度。

## 更新了Target UI更改

于2015年2月17日启动的[[!DNL Target Standard/Premium] 25.2.1版本](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2)引入了更新的[!DNL Target]和[!UICONTROL Visual Experience Composer] (VEC) UI。 此部分概述了旧版和更新版UI之间的主要差异，特别是这些差异与配置和管理成功量度相关的差异。

### 与[!UICONTROL Revenue]成功量度相关的UI更改 {#changes}

在更新的[!DNL Target]界面中，[!UICONTROL Default View for Reporting]下拉列表已被删除。 此字段是多余的，因为它之前在旧版UI中的[!DNL Overview] > [!UICONTROL Reports]下保存了默认报表视图。

使用更新的UI，默认报表量度现在始终设置为[!UICONTROL Revenue per Visitor (RPV)]。 您仍然可以自定义[!UICONTROL Reports]部分中的视图以显示与您的分析最相关的量度。

此更改不会影响投放量度。 此更改仅影响报表视图中显示的默认筛选器。 由于RPV是客户中最常用的量度，因此选择此默认值以简化报表工作流。 您可以随时在[!UICONTROL Reports]部分内切换到其他量度。