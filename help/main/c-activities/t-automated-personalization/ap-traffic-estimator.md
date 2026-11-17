---
keywords: 流量估算器；自动个性化；ap；估算流量
description: 使用[!UICONTROL 流量估算器]评估您是否有足够的流量使[!UICONTROL Automated Personalization]活动取得成功。
title: 成功的[!UICONTROL Automated Personalization]活动需要多少流量？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Automated Personalization
exl-id: 11f9e239-700b-45cd-bf77-39f7f8967a2e
TQID: 'https://experienceleague.adobe.com/rLjNgDlAWK-r9Zv7083vo-PdWTPy3aHGS4fXEGeTdnY'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: ddd4fa83540294ee229b87f041bc2245ba9a3464
workflow-type: tm+mt
source-wordcount: '802'
ht-degree: 8%
---
# 估算成功所需流量 {#traffic-estimator}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何使用&#x200B;**[!UICONTROL 流量估算器]**&#x200B;来检查您的&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动是否有足够的流量可以成功。

>[!ENDSHADEBOX]

[!DNL Adobe Target] **[!UICONTROL 流量估算器]**&#x200B;提供的反馈可让您知道您是否具有足够的流量以使&#x200B;**[!UICONTROL Automated Personalization]** (AP)活动成功。 AP活动使用多个选件组合，因此了解需要多少流量才能获得有意义的结果非常重要。 **[!UICONTROL 流量估算器]**&#x200B;使用有关您的页面的统计信息和正在测试的体验数量来估算流量和活动成功所需的测试持续时间。

**[!UICONTROL 流量估算器]**&#x200B;通过比较估算的页面展示次数和页面的典型转化率，确定是否有足够的流量来生成个性化模型。 对于成功的活动，在理想的情况下，正确的样本量可确保个性化内容在活动持续时间的一半时间或 14 天内（以较短者为准）准备就绪。 此过程留有充足的时间来获取个性化内容并了解要交付的内容。

[!DNL Target]会随机提供体验，直到生成个性化算法为止。 每个优惠旁边的复选标记图标显示该优惠的模型何时准备就绪，[!DNL Target]何时能够开始提供个性化内容。 只有在模型准备就绪后，才会出现提升预期，因此可视指示允许您设置正确的预期。 使用&#x200B;**[!UICONTROL 可视化体验编辑器]** (VEC)中的&#x200B;**[!UICONTROL 流量估算器]**&#x200B;获取模型准备就绪的指南。

>[!NOTE]
>
>并不总是部署个性化模型，即使您的流量足够。 [!DNL Target]构建和测试模型，但只有在性能优于随机选择的体验时才会部署模型。 如果模型并不比随机模型更好，则选件之间的差异可能并不足够。 在这种情况下，如果消息类似，则使选件在视觉上更加不同，或者更改消息本身即可。

## 使用流量估算器 {#use-traffic-estimator}

在构建&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动时，**[!UICONTROL 流量估算器]**&#x200B;允许您检查流向页面的流量是否足以让个性化模型及时准备就绪。 在启动活动之前运行此检查可帮助您避免测试无法联系到足够的访客以提供个性化内容，并向您展示如何在流量不足时调整选件组合数量或活动的持续时间。

1. 从您的&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动中，访问[!UICONTROL 可视化体验编辑器]的**2}体验&#x200B;]**页面。**[!UICONTROL 

1. 单击&#x200B;**[!UICONTROL 流量]**&#x200B;图标（![流量估算器图标](/help/main/assets/icons/Gauge2.svg)）。

   **[!UICONTROL 流量估算器]**&#x200B;打开。 要退出窗口，请再次单击图标。

   ![流量估算器用户界面](assets/ap-est.png)

1. 指定典型转化率（或此活动的预期转化率）、预计每日活动展示次数和测试持续时间。

   **[!UICONTROL 流量估算器]**&#x200B;使用这些量度来确定要运行成功的测试所需的调整。

   | 量度 | 描述 |
   | --- | --- |
   | **[!UICONTROL 选件数]** | 此量度是在执行任何排除之后，根据作为活动的一部分创建的体验数量自动计算的。 |
   | **[!UICONTROL 典型转化率]** | 此量度以百分比表示，根据估算或Analytics系统中的以往数据得出。 |
   | **[!UICONTROL 预计每日访问次数]** | 此量度是基于定位标准的每日访问次数，这些访问来自能够查看活动的访客。 此量度可以基于您的分析数据。 此数字必须是访问次数，而不是独特访客。 |
   | **[!UICONTROL 测试持续时间]** | 您希望该活动运行的天数。 |



1. 查看结果。 当您更改这些数字时，估算的结果也会相应改变。

   例如，如果您要测试多个组合，而您的转化率和展示次数太低，则&#x200B;**[!UICONTROL 流量估算器]**&#x200B;会显示测试成功必须运行多久。 或者，如果您的流量较低，则&#x200B;**[!UICONTROL 流量估算器]**&#x200B;可能会建议较少的选件组合数量，以便您可以在所需的天数内运行测试。

   ![显示值和结果的流量预估](assets/ap-est-no.png)

1. 如果流量不足，请考虑以下选项：

   * 使用[**[!UICONTROL 自动定位]**](/help/main/c-activities/auto-target/auto-target-to-optimize.md)活动而不是&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;创建在一个体验变量中进行多项选件更改的体验。
   * 减少&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动中的选件组合数量。
   * 延长活动持续时间。

1. 调整这些数字，直到&#x200B;**[!UICONTROL 流量估算器]**&#x200B;指示您有足够的流量，然后相应地设计测试。

   如果流量足够，**[!UICONTROL 流量]**&#x200B;图标会显示绿色复选标记。 如果流量不足，该图标会显示一个红色警告标签。

   ![流量估算器显示足够的流量消息](assets/ap-est-yes.png)
