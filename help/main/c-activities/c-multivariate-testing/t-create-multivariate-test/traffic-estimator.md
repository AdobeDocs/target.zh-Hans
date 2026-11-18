---
keywords: 流量估算；流量估算器；估算；流量；置信度；统计功效；提升度；bonferroni；转化率；每日访客数；持续时间
description: 了解如何使用流量估算器，该量度可让您知道您是否具有足够的流量以使[!DNL Adobe Target] [!UICONTROL 多变量测试]活动成功。
title: '[!UICONTROL 多变量测试] (MVT)活动需要多少流量？'
feature: Multivariate Tests
exl-id: 2b32f4a7-b9b4-40bf-a17b-88225bc88787
TQID: 'https://experienceleague.adobe.com/XHBXV7Jtvp87ve4NTd-016E2dFkHTbPu-8-nY8GE-VM'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0ae6991a6a86854bd64a632070a1fcbe544cc606
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 8%
---
# 估算成功的[!UICONTROL 多变量测试]活动所需的流量 {#traffic-estimator}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何使用&#x200B;**[!UICONTROL 流量估算器]**&#x200B;来检查您的&#x200B;**[!UICONTROL 多变量测试]**&#x200B;活动是否具有足够的流量以成功。

>[!ENDSHADEBOX]

多变量测试会比较多个体验，因此了解需要多少流量才能获得有意义的结果非常重要。 **[!UICONTROL 流量估算器]**&#x200B;使用有关您的页面的统计信息和正在测试的体验数量来估算流量和测试成功所需的测试持续时间。 它还提供反馈，让您知道您是否具有足够的流量进行您旨在成功的测试。

**[!UICONTROL 流量估算器]**&#x200B;预测所需的样本大小，以确保满足以下要求：

* **95%置信度。** 此统计数据意味着如果没有真正的提升，则报告误报的可能性为5%（100% — 置信水平）。
* **80%统计功效。** 此统计信息意味着该测试具有80%的概率来检测25%或更多的真实提升。
* 最低可靠检测提升度&#x200B;**25%。** [!DNL Target]计算在检测到25%或以上的真实提升度时，需要80%的流量量。

测试会使用 Bonferroni 校正法对多个比较进行校正。 此方法已知具有保守性，但通过强制使用相对较高的最低可靠检测提升度与这一特性相抵消。

## 使用流量估算器 {#use-traffic-estimator}

当您设计&#x200B;**[!UICONTROL 多变量测试]**&#x200B;时，**[!UICONTROL 流量估算器]**&#x200B;允许您检查进入页面的流量是否足以容纳您计划测试的体验数量。 在启动测试之前运行此检查有助于避免测试无法吸引足够访客来产生有意义的结果，并说明了如何在流量不足时调整测试组合数量或测试持续时间。

1. 在&#x200B;**[!UICONTROL 多变量]**&#x200B;活动的&#x200B;**[!UICONTROL 可视化体验编辑器]**&#x200B;的&#x200B;**[!UICONTROL 体验]**&#x200B;页面中，单击页面左上角的&#x200B;**[!UICONTROL 流量]**&#x200B;图标（ ![流量估算器图标](/help/main/assets/icons/Gauge2.svg)）。

   **[!UICONTROL 流量估算器]**&#x200B;打开。 要隐藏它，请再次单击图标。

   ![流量估算器用户界面](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-est.png)

   在&#x200B;**[!UICONTROL 流量估算器]**&#x200B;的顶部附近，计算您输入的值并显示结果。

1. （可选）提供典型转化率、预计每日访客数和测试持续时间。

   **[!UICONTROL 流量估算器]**&#x200B;使用这些统计信息来确定运行成功的测试所需的调整。

   | 量度 | 描述 |
   | --- | --- |
   | **[!UICONTROL 内容组合数量]** | 此量度是在执行任何排除后根据作为活动的一部分创建的体验数量自动计算的。 |
   | **[!UICONTROL 典型转化率]** | 此量度以百分比表示，根据估算或Analytics系统中的以往数据得出。 |
   | **[!UICONTROL 预计每日访客数]** | 此量度是基于定位标准有可能会查看此页面的访客数量。 此数字可基于您的分析数据。 |
   | **[!UICONTROL 测试持续时间]** | 您希望该活动运行的天数。 |

1. 查看结果。 当您更改这些数字时，估算的结果也会相应改变。

   例如，如果您正在测试多个体验，而您的转化率和展示次数太低，则&#x200B;**[!UICONTROL 流量估算器]**&#x200B;会显示测试成功必须运行多久。 或者，如果您的流量较低，则&#x200B;**[!UICONTROL 流量估算器]**&#x200B;可能会建议较少的体验数量，以便您可以在所需的天数内运行测试。

1. 如果流量不足，请执行以下一项或两项操作：

   * 减少选件组合数量和位置数量。
   * 延长测试持续时间。

1. 调整这些数字，直到&#x200B;**[!UICONTROL 流量估算器]**&#x200B;指示您有足够的流量，然后相应地设计测试。
