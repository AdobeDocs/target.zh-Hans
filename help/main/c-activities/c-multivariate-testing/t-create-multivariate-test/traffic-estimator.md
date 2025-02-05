---
keyword: traffic estimate;traffic estimator;estimate;traffic;confidence;statistical power;lift;bonferroni;conversion rate;visitors per day;duration
description: 了解如何使用流量估算器，该量度可让您知道您是否具有足够的流量以使 [!DNL Adobe Target] [!UICONTROL Multivariate Test]活动成功。
title: '[!UICONTROL Multivariate Test] (MVT)活动需要多少流量？'
feature: Multivariate Tests
exl-id: 2b32f4a7-b9b4-40bf-a17b-88225bc88787
source-git-commit: 8f9c0ea65197fd639d463628e54db79db993c2da
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 21%

---

# 估算成功的[!UICONTROL Multivariate Test]活动所需的流量

由于多变量测试会对多个体验进行比较，因此非常重要的一点是，您需要知道多少流量才能提供有意义的结果。[!UICONTROL Traffic Estimator]使用有关您的页面的统计信息和正在测试的体验数量来估计流量和测试成功所需的测试持续时间。

[!UICONTROL Traffic Estimator]预测所需的样本大小，以确保满足以下条件：

* 95%的置信度。 此统计数据意味着如果没有真正的提升，则报告误报的可能性为5%（100% — 置信水平）。
* 80%的统计能力。 此统计信息意味着该测试具有80%的概率来检测25%或更多的真实提升。
* 能够可靠检测到的最小提升度为25%。 [!DNL Target]计算在检测到25%或以上的真实提升度时，需要80%的流量量。

测试会使用 Bonferroni 校正法对多个比较进行校正。此方法已知具有保守性，但通过强制使用相对较高的最低可靠检测提升度与这一特性相抵消。

[!UICONTROL Traffic Estimator]还提供了反馈，让您知道您是否具有足够的流量可供设计成成功的测试。

1. 从[!UICONTROL Multivariate]活动中[!UICONTROL Visual Experience Composer]的[!UICONTROL Experiences]页面，单击[!UICONTROL Experiences]页面左上角的&#x200B;**[!UICONTROL Traffic]**&#x200B;图标（ ![流量估算器图标](/help/main/assets/icons/Gauge2.svg)）。

   将打开[!UICONTROL Traffic Estimator]。

   ![流量估算器用户界面](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-est.png)

   您可以再次单击该图标以隐藏[!UICONTROL Traffic Estimator]。

   在[!UICONTROL Traffic Estimator]顶部附近，计算您输入的值并显示结果。

1. （视情况而定）提供典型转化率、预计每日访客数和测试持续时间。

   * **[!UICONTROL Number of Content Combinations]**：根据在任何排除后作为活动的一部分创建的体验的数量自动进行计算。
   * **[!UICONTROL Typical Conversion Rate]**：转化率以百分比表示，根据估算或Analytics系统中的以往数据得出。
   * **[!UICONTROL Estimated Visitors Per Day]**：这是根据定位条件有可能会查看此页面的访客数量。 可以基于您的分析数据。
   * **[!UICONTROL Test Duration]**：您希望该活动运行的天数。

   [!UICONTROL Traffic Estimator]使用这些统计信息来确定运行成功的测试所需的调整。

   当您更改这些数字时，估算的结果也会相应改变。例如，如果您正在测试多个体验，而您的转化率和展示次数太低，则[!UICONTROL Traffic Estimator]会显示测试成功必须运行多久。 或者，如果您的流量较低，则[!UICONTROL Traffic Estimator]可能会建议使用较少的体验数量，以便您可以在所需的天数内运行测试。

   如果流量不足，您可以执行以下任一操作或同时执行以下两项操作：

   * 减少选件组合数量和位置数量。
   * 延长测试持续时间。

   调整这些数字，直到[!UICONTROL Traffic Estimator]指示您具有足够的流量，然后相应地设计测试。
