---
keywords: reports;auto-target;auto target;AT;report
description: 有关如何解释Adobe Target自动目标摘要报告的信息。
title: 自动定位摘要报表
feature: Reports
translation-type: tm+mt
source-git-commit: 7b86db4b45f93a3c6169caf81c2cd52236bb5a45
workflow-type: tm+mt
source-wordcount: '666'
ht-degree: 55%

---


# ![Premiuma自](/help/assets/premium.png) 动目标摘要报告{#auto-target-summary-report}

有关如何解释[!DNL Adobe Target]中的[!UICONTROL 自动目标摘要]报告的信息。

>[!NOTE]
>
>[!UICONTROL 自动定位]作为 [!DNL Target Premium] 解决方案的一部分提供。没有[目标高级许可证](/help/c-intro/intro.md#premium)，它不包含在[!DNL Target Standard]中。

要显示[!UICONTROL 自动目标摘要]报告，请执行以下操作：

1. 从[!UICONTROL 活动]页面，单击所需的[!UICONTROL 自动目标]活动。

   如果您有许多活动，则可以从[!UICONTROL 类型]、[!UICONTROL 状态]、[!UICONTROL 属性]、[!UICONTROL 报告源]、[!UICONTROL 体验书写器]、[!UICONTROL 类型度量中选择选项来过滤列表]和[!UICONTROL 活动源]下拉列表。

1. 单击[!UICONTROL 报告]选项卡，然后单击所需的图标：

   * 表格视图
   * 图形视图
   * 自动化区段
   * 重要属性

## 表格视图

下图显示了在查看[!UICONTROL 自动视图]活动报告时，[!UICONTROL 表格目标]中典型的摘要报告的外观：

![自动目标表视图报告](/help/c-reports/assets/at-table-view.png)

解释[!UICONTROL 自动目标]报告时的一些提示和注意事项：

* 表中的各行有助于您了解活动性能。

   * 在报表页面中，表格的前两行显示以下两种访客之间的 A/B 测试结果：分配到控制体验（即随机提供的体验）的访客，以及分配到个性化算法的访客。此信息可以用来测量与随机提供的控制体验相比，个性化算法有多少性能优势。
   * 其余的行显示体验级别的结果。对于每个体验，系统会将以下两类访客的平均响应进行比较：向其显示随机提供控制体验的访客，以及向其显示使用了个性化算法的体验的访客。

* 报表中每个体验旁边的绿色复选标记表示已为该体验生成个性化的机器学习模型。时钟图标表示用于构建模型的流量不足。

   * 由于该模型是根据每个体验构建的，因此可以根据绿色复选标记查看其中部分体验的模型，并使用时钟图标查看其他体验的模型。
   * 在这种情况下，要提高为所有体验构建模型的活动的速度，需将额外流量发送到未构建模型的体验。
   * 要开始进行个性化，必须至少具有两个已构建模型的体验（绿色复选标记）。

* 在[!UICONTROL 自动目标]中，将体验A的转化率与体验B的进行比较并不正确。 问题在于，与随机提供体验 A 的方式相比（换言之，与控制体验相比），以智能方式提供体验 A 时，体验 A 的性能是否更好。此外，营销人员还应谨慎解读个人体验的提升，因为个性化算法会尝试优化整个活动的成功量度，而不是针对每一个个人体验进行优化。
* 可以这样理解：具有最高提升度的体验在人群中具有最大的差异。也就是说，算法已找到一个最喜欢该特定体验的区段。
* 表中的各列显示访问次数、转化率、平均提升和信心级别以及信心。 有关更多信息，请参阅[平均提升度、提升度范围和置信区间](/help/c-reports/c-report-settings/average-lift-bounds-and-confidence-interval.md)。

## 图形视图

下图显示了在查看[!UICONTROL 自动视图]活动报告时，在[!UICONTROL 图形目标]中典型的摘要报告的外观：

![自动目标图视图报告](/help/c-reports/assets/at-graph-view.png)

如下所示，您可以使用两个下拉列表来选择所需的指标、计数方法等。 有关详细信息，请参阅[报告设置概述](/help/c-reports/c-report-settings/report-settings.md):

![自动目标图视图报告](/help/c-reports/assets/at-graph-view-2.png)

## 自动化区段

单击[!UICONTROL 自动化区段]图标。 此报告显示不同访客对AP/AT活动中的优惠/体验的响应方式。 此报表可显示 Target 的个性化模型定义的不同自动化区段如何响应活动中的选件/体验。

![自动细分图标](/help/c-reports/assets/icon-automated-sements.png)

有关详细信息，请参阅[自动细分报告](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md)。

## 重要属性

单击[!UICONTROL 重要属性]图标。 此报告显示不同活动中不同属性对模型决定如何个性化的重要性如何。 此报表可显示影响模型的排名靠前的属性及其相对重要性。

![重要属性图标](/help/c-reports/assets/icon-important-attributes.png)

有关详细信息，请参阅[重要属性报告](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md)。
