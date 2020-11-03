---
keywords: AB;A/B;AB...n;compare experiences;Targeting;compare content
description: A/B 测试可比较两个或更多版本的网站内容，以查看在预先指定的测试期间，哪个版本最能提高转化。
title: A/B 测试
feature: ab
uuid: 154559cf-58bb-425d-bb2e-4eaf34c89451
translation-type: tm+mt
source-git-commit: 130edc89b2c324a0d892a4221f644248e23357a4
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 58%

---


# A/B 测试

手动A/B测试会比较网站内容的两个或多个版本，以查看哪个版本在预先指定的测试期内最能提高转化率。

>[!NOTE]
>
>除了手动（默认）A/B测试活动（在本节中讨论）之外，还 [!DNL Target] 提供了两种其他类型的A/B测试活动: [!UICONTROL 自动分配] 和 [!UICONTROL 自动目标]。
>
>请参 [阅以下A/B测试活动的类型](#types) ，以了解更多信息。

手动A/B测试（有时称为A/B...N测试）会比较网站内容的两个或多个版本，看看哪个版本能最好地提升您的转化率、销售额或您确定的其他指标。 使用 A/B 测试还可以比较更改后的页面和默认页面设计，以确定哪个体验可以产生最佳效果。

当您根据成功量度或替代内容假设验证明确了提高页面性能的方法时，手动A/B测试尤其有用。

手动A/B测试非常适合进行大型更改，这些更改可能涉及新布局或对元素进行完全不同的处理。 如果您的测试设计不便划分出独立的页面元素，则应在运行多变量测试之前运行 A/B 测试。

设置测试时，您可以确定查看各个体验的访客所占的百分比。例如，您可以在控制体验和另一个体验之间平均拆分流量，也可以通过仅向 5% 的受众显示风险更高的新体验来测试该体验。

>[!NOTE]
>
>有关确定 A/B 测试最佳样本大小的详细信息，请参阅[规划 A/B 测试](../../c-activities/t-test-ab/sample-size-determination.md#concept_2801F552DB874C20B8A17C1B774C0383)。

如果不同体验的数量超过 5 个，且这些体验位于两个或更多位置，则最好在运行 A/B 测试之前先运行 [MVT 测试](/help/c-activities/c-multivariate-testing/multivariate-testing.md)。多变量测试可显示页面中的哪些区域最有可能提高转化。这些是营销人员应该关注的位置。例如，多变量测试可能会显示促使用户采取行动的位置对达成目标最为重要。确定哪些位置和内容最有助于达成目标后，您可以运行 A/B 测试以进一步细化结果，例如对两个特定图像进行对比测试，或者比较可促使用户采取行动的措词或颜色。通过在 MVT 测试后使用一个或多个 A/B 测试，您可以确定达成所需结果的最佳内容。

## A/B测试活动的类型 {#types}

除了手动（默认）A/B测试活动（在本节中讨论）之外，还 [!DNL Target] 提供了两种其他类型的A/B测试活动: [!UICONTROL 自动分配] 和 [!UICONTROL 自动目标]。

| 活动类型 | 描述 |
| --- | --- |
| 手动 A/B 测试 | 比较两个或多个体验，以查看在预先指定的一段测试时间内，哪个体验最有利于提高转化。<br>本节介绍如何设置手动A/B测试活动，但其他类型的A/B测试活动的步骤相似。 |
| [!UICONTROL Auto-Allocate（自动分配）] | 从两个或多个体验中确定入选者，然后将流量重定向到该入选者，随着测试的运行和学习而提高转化。<br>有关更多信息，请参阅[自动分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)。 |
| ![高级徽章](/help/assets/premium.png)[!UICONTROL 自动目标] | 采用先进的机器学习技术，确定多个高性能、由营销人员定义的体验，然后根据访客各自的客户配置文件和过去类似访客的行为，为其提供量身定制的体验，从而实现内容的个性化并推动转化。<br>有关详细信息，请参 [阅自动目标](/help/c-activities/auto-target-to-optimize.md)。 |

有关这些A/B测试活动中哪些适合您的更多信息，请参阅交互式 [Adobe Target活动指南PDF](/help/c-activities/target-activities-guide.md)。

创建三种类型的A/B测试活动的步骤相似。 要创建自动 [!UICONTROL 分配] 或自动 [!UICONTROL 目标活动，请通] 过创建A/B测试活动来创 [建开始，但当您转到定位页时，请选](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) 择所需的流量分配方法：

* [!UICONTROL 自动分配到最佳体验]
* [!UICONTROL 自动目标，实现个性化体验]

![流量分配方法设置](/help/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method.png)

## 培训视频：活动类型(9:03) ![概述徽章](/help/assets/overview.png)

以下视频介绍了 [!DNL Target Standard/Premium] 中可用的活动类型。

* 介绍 [!DNL Adobe Target] 中包含的活动类型
* 选择相应的活动类型以实现目标
* 介绍适用于所有活动类型的三步引导式工作流

>[!VIDEO](https://video.tv.adobe.com/v/17386)
