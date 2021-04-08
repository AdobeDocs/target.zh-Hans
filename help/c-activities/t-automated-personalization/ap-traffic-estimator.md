---
keywords: 流量估计器；自动个性化；ap；流量估计；自动目标
description: 使用Adobe Target流量估计器确定您是否有足够的流量使您的Automated Personalization活动成功。
title: 成功活动需要多少流量？
feature: 自动个性化
exl-id: 11f9e239-700b-45cd-bf77-39f7f8967a2e
translation-type: tm+mt
source-git-commit: 6ba670ef69fa23c0023636a1920eed15dcd9dd06
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 13%

---

# ![PREMIUM](/help/assets/premium.png) 估算成功所需流量

[!DNL Adobe Target] [!UICONTROL 流量估计器]提供反馈，让您了解您的[!UICONTROL Automated Personalization]活动是否具有足够的流量以获得成功。

由于[!UICONTROL Automated Personalization]活动使用多个优惠组合，因此了解提供有意义的结果需要多少流量非常重要。 [!UICONTROL 流量估计器]使用有关页面和正在测试的体验数的统计信息来估计流量量和确保活动成功所需的测试持续时间。

[!UICONTROL 流量估计器]通过比较估计的页面印象和页面的典型转化率，确定是否有足够的流量来生成个性化模型。 对于成功的活动，在理想的情况下，正确的样本量可确保个性化内容在活动持续时间的一半时间或 14 天内（以较短者为准）准备就绪。此过程为获得个性化内容和了解要交付的内容提供了充足的时间。

请记住，[!DNL Target]会随机提供体验，直到构建个性化算法。 每个优惠旁边的复选标记图标显示该优惠的模型准备就绪且[!DNL Target]能够开始提供个性化内容。 由于只有在个性化模型准备就绪后才会出现提升，因此显示的指示标记可帮助您设置正确的预期。使用[!UICONTROL  Visual Experience Composer](VEC)中的[!UICONTROL 流量估计器]获取模型准备就绪时的指导。

## 使用流量估计器

1. 在[!UICONTROL 可视体验书写器]中，单击&#x200B;**[!UICONTROL 流量]**。

   ![“流量”图标](/help/c-activities/t-automated-personalization/assets/icon-traffic.png)

   将打开[!UICONTROL 流量评估器]。 您可以再次单击&#x200B;**[!UICONTROL 流量]**&#x200B;以隐藏[!UICONTROL 流量评估器]。

   ![流量评估器用户界面](assets/ap_est.png)

1. 指定典型转化率(或您期望此活动的转化率)、估计的每天活动印象和测试持续时间。

   | 量度 | 描述 |
   | --- | --- |
   | **[!UICONTROL 优惠数]** | 此量度会根据在任何排除后作为活动的一部分创建的体验数自动计算。 |
   | **[!UICONTROL 典型转化率]** | 此量度根据您的估计或分析系统的过去数据以百分比表示。 |
   | **[!UICONTROL 预计每日访问次数]** | 此量度是根据定位条件，访客每天能够视图活动的访问次数。 此量度可能基于您的分析数据。 此数字必须是访问，而不是唯一访客。 |
   | **[!UICONTROL 测试持续时间]** | 您希望该活动运行的天数。 |

   [!UICONTROL 流量估计器]使用这些量度确定运行成功测试需要哪些调整。

   在[!UICONTROL 流量估计器]顶部附近，将计算您输入的值并显示结果。

   ![显示值和结果的流量估计](assets/ap_est_no.png)

   当您更改这些数字时，估算的结果也会相应改变。例如，如果您正在测试许多组合，且转化率和印象太低，[!UICONTROL 流量估计器]将显示测试成功必须运行多长时间。 或者，如果您的流量较低，[!UICONTROL 流量估计器]可能建议使用较少的优惠组合，以便您能够运行所需天数的测试。

   如果流量不足，请考虑以下事项：

   * 请考虑使用[自动目标](/help/c-activities/auto-target/auto-target-to-optimize.md)活动而不是[!UICONTROL Automated Personalization]创建体验，在一个体验变量中对优惠进行多次更改。
   * 减少[!UICONTROL Automated Personalization]优惠活动中的组合数。
   * 延长活动持续时间。

   调整数字，直到[!UICONTROL 流量估计器]指示您有足够的流量，然后相应地设计测试。

   ![显示足够流量消息的流量估计器](assets/ap_est_yes.png)

   如果流量足够，[!UICONTROL 流量]图标将显示绿色检查。 如果流量不足，该图标会显示一个红色警告标签。

## 有关流量估计器的常见问题

使用[!UICONTROL 流量评估器]时，请考虑以下常见问题：

### 为什么即使我的AP活动拥有足够的流量，个性化模型也无法构建？

在某些情况下，您的流量足够大，可以构建个性化模型，但该流量可能会通知[!DNL Target]个性化模型与随机模型之间没有有意义的差异。 虽然模型在[!DNL Target]中构建并经过测试，但并未部署，因为模型并不比随机模型好。

模型不如随机的一个可能原因是优惠之间的差异不够大。 如果是，您可以尝试在消息相似的情况下使优惠在视觉上更加不同，也可以尝试更改消息本身。
