---
keywords: AB;A/B;AB...n;compare experiences;Targeting;compare content;auto-target;auto-allocate
description: 手动A/B测试活动会比较网站内容的两个或多个版本，以查看哪个版本在预先指定的测试期内能够最佳地提高转化率。
title: A/B测试概述
feature: ab
uuid: 154559cf-58bb-425d-bb2e-4eaf34c89451
translation-type: tm+mt
source-git-commit: e18f18e6d6e0b8fc6eb5ada845e2fe5377d6c5d0
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 38%

---


# A/B测试概述

A manual [!UICONTROL A/B Test] activity compares two or more versions of your website content to see which version best improves your conversions during a pre-specified test period.

>[!NOTE]
>
>除了手动（默认）A/ [!UICONTROL B测试活动] （在本节中讨论）之外，还 [!DNL Target] 提供了两种其他类型的  A/B测试活动: [!UICONTROL 自动分配] 和 [!UICONTROL 自动目标]。
>
>请参 [阅以下A/B测试活动的类型](#types) ，以了解更多信息。

A manual [!UICONTROL A/B Test] activity (sometimes referred to as an A/B...N test) compares two or more versions of your Web site content to see which best lifts your conversions, sales, or other metrics you identify. 使用 A/B 测试还可以比较更改后的页面和默认页面设计，以确定哪个体验可以产生最佳效果。

当您根据成功量度或替代内容假设验证明确了提高页面性能的方法时，手动A/B测试尤其有用。

手动A/B测试非常适合进行大型更改，这些更改可能涉及新布局或对元素进行完全不同的处理。 If your test design does not easily break down into individual page elements, you should run an A/B test before a [multivariate test](/help/c-activities/c-multivariate-testing/multivariate-testing.md).

设置A/B测试时，可确定查看每个体验的访客百分比。 例如，您可以在控制体验和另一个体验之间平均拆分流量，也可以通过仅向 5% 的受众显示风险更高的新体验来测试该体验。

>[!NOTE]
>
>有关确定 A/B 测试最佳样本大小的详细信息，请参阅[规划 A/B 测试](../../c-activities/t-test-ab/sample-size-determination.md)。

如果不同体验的数量超过 5 个，且这些体验位于两个或更多位置，则最好在运行 A/B 测试之前先运行 [MVT 测试](/help/c-activities/c-multivariate-testing/multivariate-testing.md)。多变量测试可显示页面中的哪些区域最有可能提高转化。这些是营销人员应该关注的位置。例如，多变量测试可能会显示促使用户采取行动的位置对达成目标最为重要。确定哪些位置和内容对帮助您实现目标最有用后，您可以运行A/B测试以进一步优化结果，例如测试两个特定图像，或比较行动号召的措辞或颜色。 通过在 MVT 测试后使用一个或多个 A/B 测试，您可以确定达成所需结果的最佳内容。

## A/B测试活动的类型 {#types}

除了手动A/B [!UICONTROL 测试活动] （本节讨论）外， [!DNL Target] 还提供了两种额外的A/B测试活动: [!UICONTROL 自动分配] 和 [!UICONTROL 自动目标]。

| 活动类型 | 描述 |
| --- | --- |
| [!UICONTROL 手动 A/B 测试] | 比较两个或多个体验，以查看在预先指定的一段测试时间内，哪个体验最有利于提高转化。<br>本节介绍如何设置手 [!UICONTROL 动A/B测试活动] ，但其他类型的A/B测 [!UICONTROL 试活动的步骤相] 似。 |
| [!UICONTROL Auto-Allocate（自动分配）] | 从两个或多个体验中确定入选者，然后将流量重定向到该入选者，随着测试的运行和学习而提高转化。<br>要了解使用自动分配活动的优势，请参 [阅运行A](/help/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) /B测试和自动分配 *概* 览中的自动分配 [](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)。 |
| ![高级徽章](/help/assets/premium.png)[!UICONTROL 自动目标] | 采用先进的机器学习技术，确定多个高性能、由营销人员定义的体验，然后根据访客各自的客户配置文件和过去类似访客的行为，为其提供量身定制的体验，从而实现内容的个性化并推动转化。<br>有关详细信息，请参 [阅自动目标](/help/c-activities/auto-target/auto-target-to-optimize.md)。 |

有关这些A/B测试 [!UICONTROL 活动中哪些适合您] ，请参阅交互式 [Adobe Target活动指南PDF](/help/c-activities/target-activities-guide.md)。

创建三种类型的A/B测 [!UICONTROL 试活动的步骤] 类似。 要创建自动 [!UICONTROL 分配] 或自动 [!UICONTROL 目标] 活动，请通过创 [建A/B测试活动来进行开始，但是当您到达定](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) 位页时，请选择所需的流量分配方法，如下所示：

* [!UICONTROL 自动分配到最佳体验]
* [!UICONTROL 自动目标，实现个性化体验]

![流量分配方法设置](/help/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method.png)

## 培训视频：活动类型(9:03) ![概述徽章](/help/assets/overview.png)

以下视频介绍了 [!DNL Target Standard/Premium] 中可用的活动类型。

* 介绍 [!DNL Adobe Target] 中包含的活动类型
* 选择相应的活动类型以实现目标
* 介绍适用于所有活动类型的三步引导式工作流

>[!VIDEO](https://video.tv.adobe.com/v/17386)
