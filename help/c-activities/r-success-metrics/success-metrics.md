---
keywords: Targeting;success;conversion metric;page score metric;page views metric;revenue metrics;time on site metric;estimated value;advanced settings;success metrics;advanced settings;dependency;dependant;Increment Count & Keep User in Activity;Increment Count, Release user, & Allow Reentry;increment Count, Release User, & Bar from Reentry
description: 在Adobe Target，成功指标是用于衡量活动成功的参数。 成功量度包括关键业务衡量指标，可帮助您确定 Target 活动中的给定体验或选件是否成功。
title: Adobe Target成功指标
feature: success metrics
uuid: 24e9ae0f-099b-430b-b2bb-03b405f88929
translation-type: tm+mt
source-git-commit: 7078d8b613a0ba2ebad5a3698f72695d5dc3c93d
workflow-type: tm+mt
source-wordcount: '1129'
ht-degree: 47%

---


# 成功量度{#success-metrics}

In [!DNL Adobe Target] success metrics are parameters used to measure the success of an activity. Success metrics include key business measures that enable you to determine the success of a given experience or offer in a [!DNL Target] activity.

例如，您可以确定新的选件是否增加了每个访客带来的收入或是否吸引访客向购物车中添加物品。成功量度可用于发现注册、订购或购买漏斗等方面的问题，也可仅仅用于提高访客或客户参与度。

## 概述

在此 [!DNL Target]中，成功量度预配置了最佳选项，可同时用于报告和跟踪目的。

默认情况下，转换事件设置为“[!UICONTROL 增量计数并保持用户处于活动]”。 转换只计数一次，不计数重复的转换，访客始终可以看到活动内容。

Revenue metrics that are set to &quot;[!UICONTROL Increment count &amp; keep user in activity]&quot; log order details only for the first order made by the same visitor. All subsequent orders increase conversion count, but will not add revenue to RPV/AOV/Sales, and will not be included in the [!UICONTROL Order Details] report.

>[!NOTE]
>
>使用Analytics作为活动 [源(A4T](/help/c-integrating-target-with-mac/a4t/a4t.md) )的报告的默认行为是“增[!UICONTROL 量计数并保持用户活动]”，其中“每[!UICONTROL 个进入者一次]”。

可用的成功量度如下所示：

| 成功量度 | 测量方法 | 定义 |
|--- |--- |--- |
| 转化 | 基于转化 | 转换是指访客在您定义的站点上执行操作，如 <ul><li>单击了按钮</li><li>已查看页面</li><li>已完成调查</li><li>购买</li></ul>每个访客或每次访客完成转换时，都可以对转换计数一次。 |
| 收入 | 基于转化 | 由访问带来的收入。您可以选择以下收入量度：<ul><li>每位访客带来的收入 (RPV)</li><li>平均订单值 (AOV)</li><li>销售总额</li><li>订单数</li></ul> |
| 页面查看次数 | 基于参与度 | 将每次独特访问计为一次转化。 |
| 自定义得分 | 基于参与度 | Aggregated score based on the value assigned to pages visited on the site, from the point the visitor first sees the activity&#39;s first display [!DNL Target] request. |
| 网站逗留时间 | 基于参与度 | Time spent in the visit (in seconds) from the point the visitor sees the activity&#39;s first display [!DNL Target] request to the load of the final page with a request in the session. |

对于基于参与度的量度（与基于转化和基于收入的量度不同），访客必须在每次访问时重新获得活动参与资格，才会递增该会话的计数。关联的量度将在重新获得资格后开始递增，并在每个访客的会话结束时停止。会话若处于不活动状态超过 30 分钟便会结束。因此，测试过程中不会立即看到结果；但是，该会话的所有结果在会话结束后的几分钟内可用。

## 自定义成功指标

您也可以创建自定义成功量度。

选择成功量度后，请选择访客为实现目标所需执行的操作。For example, choose a [!UICONTROL Conversion] metric, set it to be counted once per visitor, then set whether success is achieved when a visitor views a certain page (or set of pages), views a specific [!DNL Target] request, or clicks a specific link.

If enabled, the [!UICONTROL Estimated Value of one conversion] field (not available for the [!UICONTROL Page Score] metrics) provides a value for your goal, but not for other metrics. 通过此值，[!DNL Target] 可以计算出预计收入提升。此字段为可选字段；但是，如果没有该字段，便无法计算所有非收入量度的增量收入。For all revenue metrics ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales], and [!UICONTROL Orders]), the estimate uses [!UICONTROL Revenue per Visitor]. 数据类型为货币。请参阅[预计收入提升](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)以了解更多信息。

查看活动报表时，在报表设置中可以看到您为活动选择的成功量度。

Some metrics, such as [!UICONTROL Custom Scoring] and [!UICONTROL Revenue Per Visitor], require a customized implementation that passes in information such as order totals and order IDs.

## 高级设置 {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

可使用高级设置来管理成功的衡量方式。选项包括添加依赖项、选择是让用户处于活动中还是删除依赖项，以及是对每个进入者还是每次印象计数一次度量。

要访问“高 [!UICONTROL 级设置] ”选项，请单 **[!UICONTROL 击垂直椭圆]** > **[!UICONTROL “高]**&#x200B;级设置”。

![“高级设置”菜单](/help/c-activities/r-success-metrics/assets/advanced-settings.png)

>[!NOTE]
>
>如果您将 [!DNL Adobe Analytics] 用作报表源，则设置会由 [!DNL Analytics] 服务器来管理。The [!UICONTROL Advanced Settings] option will not be available. For more information, see [Adobe Analytics as the reporting source for Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md).

### 添加依赖关系

您可以使用高级设置创建依赖性成功量度，仅在访客先到达其他量度时，才会增加一个量度。

![添加依赖项](/help/c-activities/r-success-metrics/assets/UI_dep_success_metric.png)

例如，仅当访客在转化之前先点击了选件或访问了某个特定页面时，测试转化才可能有效。

Dependency functionality is *not* supported for the following:

* [!UICONTROL “推荐”活动。]其他所有活动类型均支持此功能。
* If you use [Analytics as your reporting source](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T).
* 量度类型为“已查看页面”。
* 可视化体验编辑器 (VEC) 活动的量度类型为“已单击元素”。

在以下情况下，具有依赖关系的成功量度将无法转化：

* 如果您创建了循坏依赖关系，例如量度 1 依赖于量度 2，而量度 2 又依赖于量度 1，则任何量度都无法转化。
* 实现转化量度后，自动个性化活动会释放用户并重新启动活动，因此，任何依赖于转化量度的量度都将无法转化。

### 用户遇到此目标量度后会出现什么情况？

可使用高级设置来决定用户实现目标量度后将发生的情况。下表显示了可用选项：

| 用户遇到此目标量度后 | 选项 |
|--- |--- |
| [!UICONTROL 增量计数并保持用户处于活动状态] | 指定计数的递增方式：<ul><li>每个参加者一次（默认）</li><li>每次展示时（页面刷新除外）</li><li>每次展示时</li></ul> |
| [!UICONTROL 增量计数、释放用户和允许重新进入] | 选择访客再次进入活动时将看到的体验：<ul><li>相同体验（默认）</li><li>随机体验</li><li>无形体验</li></ul> |
| [!UICONTROL 再入时的增量计数、释放用户和条] | 确定用户将看到什么内容来替代活动内容：<ul><li>相同体验（不含“跟踪”功能）（默认）</li><li>默认内容，或其他活动内容</li></ul> |

>[!NOTE]
>
>如果将度量配置为增量计数选 [!UICONTROL 项之一] （上文提到），则度量计数仅在访客级别按每个进入者正确递增一次。 在访问级别，每个新会话的度量计数每次访问都会增加一次。

### 计数将如何递增：

选择所需的行为：

* 每个参加者一次
* 每次印象时（不包括页面刷新）
* 每次展示时

## 培训视频：活动量度

以下视频演示了如何使用活动量度。

* 了解“目标”量度
* 了解和构建“转化”、“收入”及“参与度”量度
* 构建点击跟踪量度

>[!VIDEO](https://video.tv.adobe.com/v/17380)