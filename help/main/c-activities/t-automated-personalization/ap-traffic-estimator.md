---
keywords: 流量估算器；自动个性化；ap；估算流量
description: 使用 [!DNL Adobe Target] [!UICONTROL 流量估算器] 以确定您的网络是否具有足够的流量， [!UICONTROL Automated Personalization] 活动才能成功。
title: 获得成功需要多少流量 [!UICONTROL Automated Personalization] 活动？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="请参阅Target Premium中包含的内容。"
feature: Automated Personalization
exl-id: 11f9e239-700b-45cd-bf77-39f7f8967a2e
source-git-commit: eacee6f353aa685d17b781ac82d3f79574384dfe
workflow-type: tm+mt
source-wordcount: '779'
ht-degree: 10%

---

# 估算成功所需流量

此 [!DNL Adobe Target] [!UICONTROL 流量估算器] 提供反馈，让您知道自己的流量是否足够 [!UICONTROL Automated Personalization] (AP)活动成功。

因为 [!UICONTROL Automated Personalization] 活动使用多个选件组合，了解需要多少流量才能获得有意义的结果非常重要。 此 [!UICONTROL 流量估算器] 使用有关您的页面和所测试体验数量的统计信息来估计流量量和成功完成活动所需的测试持续时间。

此 [!UICONTROL 流量估算器] 通过比较页面的估计页面展示次数和典型转化率，确定是否有足够的流量来生成个性化模型。 对于成功的活动，在理想的情况下，正确的样本量可确保个性化内容在活动持续时间的一半时间或 14 天内（以较短者为准）准备就绪。此过程留有充足的时间来获取个性化内容并了解要交付的内容。

请记住 [!DNL Target] 随机提供体验，直到构建个性化算法为止。 每个选件旁边的复选标记图标会显示该选件的模型何时准备就绪，并且 [!DNL Target] 能够开始提供个性化内容。 由于提升仅在模型准备就绪后才属于预期提升度，因此，通过视觉指示可设置正确的预期。 使用 [!UICONTROL 流量估算器] 在 [!UICONTROL 可视化体验编辑器] (VEC)，以获取模型准备就绪的指南。

## 使用流量估算器

1. 从 [!UICONTROL 体验] 第页，共 [!UICONTROL 可视化体验编辑器] 在 [!UICONTROL Automated Personalization] 活动，请单击  **[!UICONTROL 流量]** 图标。

   ![“流量”图标](/help/main/c-activities/t-automated-personalization/assets/icon-traffic.png)

   此 [!UICONTROL 流量估算器] 打开。 您可以单击 **[!UICONTROL 流量]** 再次隐藏 [!UICONTROL 流量估算器].

   ![流量估算器用户界面](assets/ap_est.png)

1. 指定典型转化率（或此活动的预期转化率）、预计每日活动展示次数和测试持续时间。

   | 量度 | 描述 |
   | --- | --- |
   | **[!UICONTROL 选件数量]** | 此量度是在执行任何排除之后，根据作为活动的一部分创建的体验数量自动计算的。 |
   | **[!UICONTROL 典型转化率]** | 此量度以百分比表示，根据估算或Analytics系统中的以往数据得出。 |
   | **[!UICONTROL 预计每日访问次数]** | 此量度是基于定位标准的每日访问次数，这些访问来自能够查看活动的访客。 此量度可以基于您的分析数据。 此数字必须是访问次数，而不是独特访客。 |
   | **[!UICONTROL 测试持续时间]** | 您希望该活动运行的天数。 |

   此 [!UICONTROL 流量估算器] 使用这些量度来确定需要做出哪些调整才能运行成功的测试。

   在顶部附近 [!UICONTROL 流量估算器]，则会计算输入的值并显示结果。

   ![显示值和结果的流量预估](assets/ap_est_no.png)

   当您更改这些数字时，估算的结果也会相应改变。例如，如果您要测试多个组合，而您的转化率和展示次数太低，则 [!UICONTROL 流量估算器] 显示测试成功必须运行的时长。 或者，如果您的流量很低， [!UICONTROL 流量估算器] 可以建议较少的选件组合数量，以便您可以在所需的天数内运行测试。

   如果流量不足，请考虑以下事项：

   * 考虑使用 [自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md) 活动，而不是 [!UICONTROL Automated Personalization] 以在一个体验变量中进行多次选件更改来创建体验。
   * 减少您的选件组合数量 [!UICONTROL Automated Personalization] 活动。
   * 延长活动持续时间。

   调整数字，直到 [!UICONTROL 流量估算器] 表示您拥有足够的流量，然后相应地设计测试。

   ![流量估算器显示足够的流量消息](assets/ap_est_yes.png)

   如果流量足够， [!UICONTROL 流量] 图标显示绿色复选标记。 如果流量不足，该图标会显示一个红色警告标签。

## 关于流量估算的常见问题解答

在使用时，请考虑以下常见问题 [!UICONTROL 流量估算器]：

### 即使我的AP活动具有足够的流量，为何仍无法构建个性化模型？

在某些情况下，您的流量足够大，可以构建个性化模型，但该流量可能会通知 [!DNL Target] 即个性化的模型与随机性之间没有有意义的区别。 尽管模型是内置的 [!DNL Target] 并且经过测试，没有部署，因为该模型并不比随机模型好多少。

此模型没有优于随机模型的一个可能原因可能是选件之间的差异不足。 如果是这样的话，您可以尝试在消息相似的情况下使选件在视觉上更加不同，也可以尝试更改消息本身。
