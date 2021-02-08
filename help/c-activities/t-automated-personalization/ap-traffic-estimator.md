---
keywords: 流量估计器；自动个性化；ap；流量估计
description: 了解如何使用流量估计器，它可让您了解是否有足够的流量使您的Adobe TargetAutomated Personalization活动取得成功。
title: Automated Personalization活动需要多少流量？
feature: Automated Personalization
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 24%

---


# ![PREMIUM](/help/assets/premium.png) 估算成功所需流量

[!UICONTROL 流量估计器]提供反馈，让您知道您是否有足够的流量使[!DNL Adobe Target]活动成功。

由于[!UICONTROL Automated Personalization]活动使用多个优惠组合，因此了解提供有意义的结果需要多少流量非常重要。 [!UICONTROL 流量估计器]使用有关页面和正在测试的体验数的统计信息来估计流量量和确保活动成功所需的测试持续时间。

[!UICONTROL 流量估计器]通过比较估计的页面印象和页面的典型转化率，确定是否有足够的流量来生成个性化模型。 对于成功的活动，在理想的情况下，正确的样本量可确保个性化内容在活动持续时间的一半时间或 14 天内（以较短者为准）准备就绪。这样便可以有充足的时间来获取个性化内容，并学习要交付哪些内容。

请记住，[!DNL Target]在构建个性化算法之前会随机提供体验。 每个优惠旁的复选标记图标显示该优惠的模型准备就绪且[!DNL Target]能够开始提供个性化内容。 由于只有在个性化模型准备就绪后才会出现提升，因此显示的指示标记可帮助您设置正确的预期。使用[!UICONTROL 可视体验书写器](VEC)中的[!UICONTROL 流量估计器]获取模型准备就绪的指南。

## 使用流量估计器

1. 在[!UICONTROL 可视体验书写器]中，单击&#x200B;**[!UICONTROL 流量]**。

   ![“流量”图标](/help/c-activities/t-automated-personalization/assets/icon-traffic.png)

   将打开[!UICONTROL 流量估计器]。 您可以再次单击&#x200B;**[!UICONTROL 流量]**&#x200B;以隐藏[!UICONTROL 流量估计器]。

   ![](assets/ap_est.png)

1. 提供典型转化率（或此活动的预期转化率）、预计每日活动展示次数，及测试持续时间。

   * **优惠数**:根据在任何排除后作为活动的一部分创建的体验数自动计算。
   * **典型转化率**：转化率以百分比表示，根据估算或 Analytics 系统中的以往数据得出.
   * **估计每日访问量**:这是根据定位标准，能够视图活动的访客每天的访问次数。可以基于您的分析数据。请注意，此数值应为访问次数，而不是独特访客数。
   * **测试持续时间**：您希望该活动运行的天数。

   [!UICONTROL 流量估计]r使用这些统计信息来确定运行成功测试需要哪些调整。

   在[!UICONTROL 流量估计器]的顶部附近，将计算您输入的值并显示结果。

   ![](assets/ap_est_no.png)

   当您更改这些数字时，估算的结果也会相应改变。例如，如果您正在测试大量组合，并且转化率和印象太低，[!UICONTROL 流量估计器]将显示测试成功需要多长时间。 或者，如果流量较低，[!UICONTROL 流量估计器]可能建议使用较少的优惠组合，这样您就可以运行测试所需的天数。

   如果流量不足，您可以执行以下任一或所有操作：

   * 考虑使用[自动目标](/help/c-activities/auto-target/auto-target-to-optimize.md)活动而不是[!UICONTROL Automated Personalization]创建体验，在一个体验变量中进行多次优惠更改。
   * 减少[!UICONTROL Automated Personalization]活动中的优惠组合数。
   * 延长活动持续时间。

   调整数字，直到[!UICONTROL 流量估计器]表示您拥有足够的流量，然后相应地设计测试。

   ![](assets/ap_est_yes.png)

   如果流量足够，[!UICONTROL 流量]图标将显示绿色检查。 如果流量不足，该图标会显示一个红色警告标签。

## 有关流量估计器的常见问题

使用[!UICONTROL 流量估计器]时，请考虑以下常见问题：

### 为什么[!DNL Target]在我的AP活动拥有足够流量时不构建个性化模型？

在某些情况下，您的流量可能足够大，足以构建个性化模型，但该流量可能会通知[!DNL Target]个性化模型与随机模型之间没有任何有意义的差异。 虽然模型是在[!DNL Target]中构建并经过测试的，但它不会被部署，因为该模型并不明显优于随机模型。

模型不如随机的一个可能原因可能是优惠之间没有明显的差异。 如果是这种情况，您可以尝试在消息相似的情况下使优惠的视觉效果更加不同，也可以尝试更改消息本身。
