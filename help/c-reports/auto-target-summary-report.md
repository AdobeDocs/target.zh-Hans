---
keywords: reports;auto-target;auto target;AT;report
description: 有关如何解释Adobe Target自动目标摘要报告的信息。
title: 自动定位摘要报表
feature: reports
subtopic: Multivariate Test
topic: Standard
uuid: a30fa886-e8df-408f-bbc9-11a917a592d8
translation-type: tm+mt
source-git-commit: 56c77e1a7b5dd4e64f59b0416a16c3039a649ba3
workflow-type: tm+mt
source-wordcount: '666'
ht-degree: 55%

---


# ![“ PREMIUM](/help/assets/premium.png) Auto-目标摘要”报告{#auto-target-summary-report}

Information about how to interpret the [!UICONTROL Auto-Target Summary] reports in [!DNL Adobe Target].

>[!NOTE]
>
>[!UICONTROL 自动定位]作为 [!DNL Target Premium] 解决方案的一部分提供。It is not included with [!DNL Target Standard] without a [Target Premium license](/help/c-intro/intro.md#premium).

要显示“自动 [!UICONTROL 目标摘要”报表] ，请执行以下操作：

1. 在活动 [!UICONTROL 页面中] ，单击所需的 [!UICONTROL 自动目标] 活动。

   If you have many activities, you can filter the list by selecting options from the [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Property], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type], and [!UICONTROL Activity Source] drop-down lists.

1. 单击报 [!UICONTROL 表] 选项卡，然后单击所需的图标：

   * 表格视图
   * 图形视图
   * 自动化区段
   * 重要属性

## 表格视图

下图显示查看自动视图目标报 [!UICONTROL 表时] ，典型 [!UICONTROL 摘要报表的] 外观如何：

![自动目标表视图报告](/help/c-reports/assets/at-table-view.png)

Some tips and considerations as you interpret your [!UICONTROL Auto-Target] reports:

* 表中的各行有助于您了解活动性能。

   * 在报表页面中，表格的前两行显示以下两种访客之间的 A/B 测试结果：分配到控制体验（即随机提供的体验）的访客，以及分配到个性化算法的访客。此信息可以用来测量与随机提供的控制体验相比，个性化算法有多少性能优势。
   * 其余的行显示体验级别的结果。对于每个体验，系统会将以下两类访客的平均响应进行比较：向其显示随机提供控制体验的访客，以及向其显示使用了个性化算法的体验的访客。

* 报表中每个体验旁边的绿色复选标记表示已为该体验生成个性化的机器学习模型。时钟图标表示用于构建模型的流量不足。

   * 由于该模型是根据每个体验构建的，因此可以根据绿色复选标记查看其中部分体验的模型，并使用时钟图标查看其他体验的模型。
   * 在这种情况下，要提高为所有体验构建模型的活动的速度，需将额外流量发送到未构建模型的体验。
   * 要开始进行个性化，必须至少具有两个已构建模型的体验（绿色复选标记）。

* Comparing the conversion rate of experience A with that of experience B is not the right comparison in [!UICONTROL Auto-Target]. 问题在于，与随机提供体验 A 的方式相比（换言之，与控制体验相比），以智能方式提供体验 A 时，体验 A 的性能是否更好。此外，营销人员还应谨慎解读个人体验的提升，因为个性化算法会尝试优化整个活动的成功量度，而不是针对每一个个人体验进行优化。
* 可以这样理解：具有最高提升度的体验在人群中具有最大的差异。也就是说，算法已找到一个最喜欢该特定体验的区段。
* 表中的各列显示访问次数、转化率、平均提升和信心级别以及信心。 有关更多信息，请参阅[平均提升度、提升度范围和置信区间](/help/c-reports/c-report-settings/average-lift-bounds-and-confidence-interval.md)。

## 图形视图

下图显示了在查看自动视图 [!UICONTROL 活动报表时] ，图形 [!UICONTROL 目标中典型的概] 要报表的外观：

![自动目标图视图报告](/help/c-reports/assets/at-graph-view.png)

如下所示，您可以使用两个下拉列表来选择所需的指标、计数方法等。 有关详 [细信息，请参阅](/help/c-reports/c-report-settings/report-settings.md) “报告设置”概述：

![自动目标图视图报告](/help/c-reports/assets/at-graph-view-2.png)

## 自动化区段

单击“自 [!UICONTROL 动化区段] ”图标。 此报告显示不同访客对AP/AT活动中的优惠/体验的响应方式。 此报表可显示 Target 的个性化模型定义的不同自动化区段如何响应活动中的选件/体验。

![自动细分图标](/help/c-reports/assets/icon-automated-sements.png)

有关详细信息，请参阅 [自动化细分报告](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md)。

## 重要属性

单击“重 [!UICONTROL 要属性] ”图标。 此报告显示不同活动中不同属性对模型决定如何个性化的重要性如何。 此报表可显示影响模型的排名靠前的属性及其相对重要性。

![重要属性图标](/help/c-reports/assets/icon-important-attributes.png)

有关详细信息，请参阅 [重要属性报告](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md)。
