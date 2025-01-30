---
keywords: 定位；成功；转化量度；页面得分量度；页面查看次数量度；收入量度；网站逗留时间量度；预计值；高级设置；成功量度；高级设置；依赖项；依赖项；递增计数并保持用户处于活动中；递增计数、释放用户和允许再次进入；递增计数、释放用户和禁止再次进入
description: 了解Adobe [!DNL Target] 中帮助您确定活动是否成功的成功量度。 成功量度包括转化率、收入、页面查看次数、自定义评分和网站逗留时间。
title: 什么是成功量度？
feature: Success Metrics
hide: true
hidefromtoc: true
source-git-commit: 99ea312405e397e97e64e32d2685e8a6966d8928
workflow-type: tm+mt
source-wordcount: '1190'
ht-degree: 41%

---

# 成功量度

在[!DNL Adobe Target]个成功量度中，是用来衡量活动是否成功的参数。 成功量度包括关键业务度量，可帮助您确定[!DNL Target]活动中给定体验或选件是否成功。

例如，您可以确定新的产品建议是否增加了每个访客带来的收入或是否吸引访客向购物车中添加物品。成功量度可用于发现注册、订购或购买漏斗等方面的问题，也可仅仅用于提高访客或客户参与度。

## 概述

在[!DNL Target]中，已使用用于报告和跟踪的最佳选项预配置了成功量度。

默认情况下，转化事件设置为“[!UICONTROL Increment count & keep user in activity]”。 转化次数只计算一次，不计算重复转化次数，访客始终会看到活动内容。

设置为“[!UICONTROL Increment count & keep user in activity]”的收入量度仅记录同一访客首次订购的详细信息。 所有后续订单都会增加转化计数，但不会将收入添加到RPV/AOV/销售中，并且不会包含在[!UICONTROL Order Details]报表中。

>[!NOTE]
>
>对于使用[Analytics作为报表源](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)的活动，目标量度将始终使用“[!UICONTROL Increment Count & Keep User in Activity]”和“[!UICONTROL On Every Impression]”设置。 这是&#x200B;*不可配置的*。

可用的成功量度如下所示：

| 成功量度 | 测量方法 | 定义 |
|--- |--- |--- |
| 转化 | 基于转化 | 转化是指访客在您定义的网站上执行某项操作时，例如 <ul><li>已单击按钮</li><li>已查看页面</li><li>已完成调查</li><li>进行了购买</li></ul>每个访客或每次访客完成转化时，转化可以计为一次。 |
| 收入 | 基于转化 | 由访问带来的收入。您可以选择以下收入量度：<ul><li>每位访客带来的收入 (RPV)</li><li>平均订单值 (AOV)</li><li>销售总额</li><li>订单数</li></ul> |
| 页面查看次数 | 基于参与度 | 将每次独特访问计为一次转化。 |
| 自定义得分 | 基于参与度 | 汇总得分基于网站上已访问页面的分配值，从访客第一次看到活动的第一个展示区[!DNL Target]请求时算起。 |
| 网站逗留时间 | 基于参与度 | 从访客看到活动的第一个显示[!DNL Target]请求到加载会话中的请求的最后一页所用的访问逗留时间（以秒为单位）。 |

对于基于参与度的量度（与基于转化和基于收入的量度不同），访客必须在每次访问时重新获得活动参与资格，才会递增该会话的计数。关联的量度将在重新获得资格后开始递增，并在每个访客的会话结束时停止。会话若处于不活动状态超过 30 分钟便会结束。因此，在测试期间不会立即看到结果；但是，该会话的所有结果在会话结束后的几分钟内均可用。

## 自定义成功量度

您也可以创建自定义成功量度。

选择成功量度后，请选择访客为实现目标所需执行的操作。例如，选择一个[!UICONTROL Conversion]量度，将其设置为每个访客计数一次，然后设置当访客查看特定页面（或页面集）、查看特定[!DNL Target]请求或单击特定链接时是否获得成功。

如果启用，[!UICONTROL Estimated Value of one conversion]字段（不适用于[!UICONTROL Page Score]指标）会为您的目标提供一个值，但此值不适用于其他指标。 通过此值，[!DNL Target] 可以计算出预计收入提升。此字段为可选字段；但是，如果没有该字段，便无法计算所有非收入量度的增量收入。对于所有收入量度（[!UICONTROL Revenue per Visitor]、[!UICONTROL Average Order Value]、[!UICONTROL Total Sales]和[!UICONTROL Orders]），估计使用[!UICONTROL Revenue per Visitor]。 数据类型为货币。请参阅[预计收入提升](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)以了解更多信息。

查看活动报表时，在报表设置中可以看到您为活动选择的成功量度。

某些量度（如[!UICONTROL Custom Scoring]和[!UICONTROL Revenue Per Visitor]）需要自定义实施，该实施需要传递订单合计和订单ID等信息。

## 高级设置 {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

可使用高级设置来管理成功的衡量方式。选项包括添加依赖项、选择是将用户保留在活动中还是将其删除，以及是为每个参加者还是每次展示都计算一次量度。

要访问[!UICONTROL Advanced Settings]选项，请单击&#x200B;**[!UICONTROL More Actions]**&#x200B;图标（![更多操作图标](/help/main/assets/icons/MoreSmallListVert.svg) ），然后单击&#x200B;**[!UICONTROL Advanced Settings]**。

![“高级设置”菜单](/help/main/c-activities/r-success-metrics/assets/advanced-settings-refresh.png)

>[!NOTE]
>
>如果您将 [!DNL Adobe Analytics] 用作报表源，则设置会由 [!DNL Analytics] 服务器来管理。[!UICONTROL Advanced Settings]选项将不可用。 有关详细信息，请参阅将[Adobe Analytics作为Adobe Target (A4T)的报表源](/help/main/c-integrating-target-with-mac/a4t/a4t.md)。

### 添加依赖项

您可以使用高级设置创建依赖的成功量度，仅当访客先实现某个量度时才递增另一个量度。

例如，仅当访客在转化之前先点击了选件或访问了某个特定页面时，测试转化才可能有效。

依赖项功能&#x200B;*不支持以下*：

* [!UICONTROL Recommendations]活动。 其他所有活动类型均支持此功能。
* 如果您使用[Analytics作为报表源](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)。
* “查看了某个页面”量度类型。
* 可视化体验编辑器(VEC)活动的“已单击元素”量度类型。

在以下情况下，具有依赖关系的成功量度将无法转化：

* 如果您创建了循坏依赖关系，例如量度 1 依赖于量度 2，而量度 2 又依赖于量度 1，则任何量度都无法转化。
* [!UICONTROL Automated Personalization]个活动将释放用户，并在达到转化量度时重新启动该活动，因此依赖该转化量度的任何量度都将无法转化。

### 用户遇到此目标量度后会出现什么情况？

可使用高级设置来决定用户实现目标量度后将发生的情况。下表显示了可用的选项：

| 用户遇到此目标量度后 | 选项 |
|--- |--- |
| [!UICONTROL Increment Count & Keep User in Activity] | 指定计数的递增方式：<ul><li>每个参加者一次（默认）</li><li>每次展示时（页面刷新除外）</li><li>每次展示时</li></ul> |
| [!UICONTROL Increment Count, Release user, & Allow Reentry] | 选择访客再次进入活动时将看到的体验：<ul><li>相同体验（默认）</li><li>随机体验</li><li>无形体验</li></ul> |
| [!UICONTROL Increment Count, Release User, & Bar from Reentry] | 确定用户将看到什么内容来替代活动内容：<ul><li>相同体验（不含“跟踪”功能）（默认）</li><li>默认内容，或其他活动内容</li></ul> |

>[!NOTE]
>
>如果将某个量度配置为[!UICONTROL Increment Count]选项（如上所述）之一，则量度计数仅在访客级别按每个参加者正确递增一次。 指标计数在访问级别针对每个新会话每次访问递增一次。

### 计数将如何递增：

选择所需的行为：

* 每个参加者一次
* 每次展示时（页面刷新除外）
* 每次展示时

## 已知问题

* 其高级选项“计数将如何递增”被设置为“每次展示”或“每次展示（不包括刷新）”的成功指标无法用作另一指标所依赖的成功指标。

将成功量度设置为每次展示递增时，[!DNL Target]会在每次访客访问此成功量度时再次计入访客。 然后，[!DNL Target]将成功量度“成员资格”重置为0，以便在下次展示时再次对其计数。 因此，如果另一个量度要求首先看到此量度，[!DNL Target]从不识别用户已看到第一个量度。

## 培训视频：活动量度

以下视频演示了如何使用活动量度。

* 了解“目标”量度
* 了解和构建“转化”、“收入”及“参与度”量度
* 构建点击跟踪量度

>[!VIDEO](https://video.tv.adobe.com/v/17380)
