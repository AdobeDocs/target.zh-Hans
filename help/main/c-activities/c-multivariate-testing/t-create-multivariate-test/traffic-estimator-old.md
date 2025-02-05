---
keyword: traffic estimate;traffic estimator;estimate;traffic;confidence;statistical power;lift;bonferroni;conversion rate;visitors per day;duration
description: 了解如何使用流量估算器，该量度可让您知道您是否具有足够的流量以使 [!DNL Adobe Target] [!UICONTROL Multivariate Test]活动成功。
title: '[!UICONTROL Multivariate Test] (MVT)活动需要多少流量？'
feature: Multivariate Tests
exl-id: 2b32f4a7-b9b4-40bf-a17b-88225bc88787
source-git-commit: 8f9c0ea65197fd639d463628e54db79db993c2da
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 53%

---

# 估算成功的[!UICONTROL Multivariate Test]活动所需的流量

由于多变量测试会对多个体验进行比较，因此非常重要的一点是，您需要知道多少流量才能提供有意义的结果。流量估算器会使用与您的页面相关的统计数据以及正在测试的体验数量，来估算需要多少流量以及需要多长时间的测试才能使测试成功。

流量估算器可预测确保获得以下结果所需的样本量：

* 95%的置信度。 此统计数据意味着如果没有真正的提升，则报告误报的可能性为5%（100% — 置信水平）。
* 80%的统计能力。 此统计信息意味着该测试具有80%的概率来检测25%或更多的真实提升。
* 能够可靠检测到的最小提升度为25%。 [!DNL Target]计算在检测到25%或以上的真实提升度时，需要80%的流量量。

测试会使用 Bonferroni 校正法对多个比较进行校正。此方法已知具有保守性，但通过强制使用相对较高的最低可靠检测提升度与这一特性相抵消。

流量估算器还可提供反馈，让您了解是否有足够的流量来确保您设计的测试取得成功。

1. 在[!UICONTROL Visual Experience Composer]中，单击&#x200B;**[!UICONTROL Traffic]**&#x200B;图标。

   此时将打开流量估算器。您可以再次单击&#x200B;**[!UICONTROL Traffic]**&#x200B;图标以隐藏流量估算器。

   ![estimatorempty图像](assets/estimatorempty.png)

1. 提供典型转化率、预计每日访客数和测试持续时间。

   * **[!UICONTROL Number of Content Combinations]**：根据在任何排除后作为活动的一部分创建的体验的数量自动进行计算。
   * **[!UICONTROL Typical Conversion Rate]**：转化率以百分比表示，根据估算或Analytics系统中的以往数据得出。
   * **[!UICONTROL Estimated Visitors Per Day]**：这是根据定位条件有可能会查看此页面的访客数量。 可以基于您的分析数据。
   * **[!UICONTROL Test Duration]**：您希望该活动运行的天数。

   流量估算器使用这些统计数据来确定运行一个成功的测试需要进行哪些调整。

   系统会计算您输入的值并在流量估算器的顶部区域附近显示计算结果。

   ![估算图像不足](assets/estimatorinsufficient.png)

   当您更改这些数字时，估算的结果也会相应改变。例如，如果您要测试多个体验，而您的转化率和展示次数太低，则流量估算器会显示测试成功必须运行多久。 或者，如果您的流量较低，流量估算器可能会建议您减少体验数量，以便能够将测试运行所需的天数。

   如果流量不足，您可以执行以下任一操作或同时执行以下两项操作：

   * 减少选件组合数量和位置数量。
   * 延长测试持续时间。

   调整数字直到流量估算器表示已有足够流量，然后对您的测试进行相应设计。

   ![estimatorok图像](assets/estimatorok.png)
