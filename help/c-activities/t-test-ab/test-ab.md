---
keywords: AB;A/B;AB...n;compare experiences;Targeting;compare content;auto-target;auto-allocate
description: 手动A/B测试活动会比较网站内容的两个或多个版本，以查看哪个版本在预先指定的测试期内能够最佳地提高转化率。
title: A/B测试概述
feature: A/B Tests
translation-type: tm+mt
source-git-commit: 8110807a73e4d6d9848a52224db04faba033c98c
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 38%

---


# A/B测试概述

手册[!UICONTROL A/B测试]活动比较网站内容的两个或多个版本，以查看哪个版本在预先指定的测试期内最能提高转化率。

>[!NOTE]
>
>除手册（默认）[!UICONTROL A/B测试]活动（本节讨论）外，[!DNL Target]还提供了两种附加类型的[!UICONTROL A/B测试]活动:[!UICONTROL 自动分配]和[!UICONTROL 自动目标]。
>
>有关详细信息，请参阅下面的[ A/B测试活动的类型](#types)。

手册[!UICONTROL A/B测试]活动（有时称为A/B...N测试）会比较网站内容的两个或多个版本，看看哪个版本能最好地提升您所识别的转换、销售或其他指标。 使用 A/B 测试还可以比较更改后的页面和默认页面设计，以确定哪个体验可以产生最佳效果。

当您根据成功量度或替代内容假设验证明确了提高页面性能的方法时，手动A/B测试尤其有用。

手动A/B测试非常适合进行大型更改，这些更改可能涉及新布局或对元素进行完全不同的处理。 如果您的测试设计不能轻松分解为各个页面元素，您应在[多变量测试](/help/c-activities/c-multivariate-testing/multivariate-testing.md)之前运行A/B测试。

设置A/B测试时，可确定查看每个体验的访客百分比。 例如，您可以在控制体验和另一个体验之间平均拆分流量，也可以通过仅向 5% 的受众显示风险更高的新体验来测试该体验。

>[!NOTE]
>
>有关确定 A/B 测试最佳样本大小的详细信息，请参阅[规划 A/B 测试](/help/c-activities/t-test-ab/sample-size-determination.md)。

如果不同体验的数量超过 5 个，且这些体验位于两个或更多位置，则最好在运行 A/B 测试之前先运行 [MVT 测试](/help/c-activities/c-multivariate-testing/multivariate-testing.md)。多变量测试可显示页面中的哪些区域最有可能提高转化。这些是营销人员应该关注的位置。例如，多变量测试可能会显示促使用户采取行动的位置对达成目标最为重要。确定哪些位置和内容对帮助您实现目标最有用后，您可以运行A/B测试以进一步优化结果，例如测试两个特定图像，或比较行动号召的措辞或颜色。 通过在 MVT 测试后使用一个或多个 A/B 测试，您可以确定达成所需结果的最佳内容。

## A/B测试活动的类型{#types}

除手册[!UICONTROL A/B测试]活动（本节讨论）外，[!DNL Target]还提供两种额外的A/B测试活动:[!UICONTROL 自动分配]和[!UICONTROL 自动目标]。

| 活动类型 | 描述 |
| --- | --- |
| [!UICONTROL 手动 A/B 测试] | 比较两个或多个体验，以查看在预先指定的一段测试时间内，哪个体验最有利于提高转化。<br>本节介绍如何设置手 [!UICONTROL 动A/B] 测试活动，但其他类型A/B测试 [!UICONTROL 活动的] 步骤相似。 |
| [!UICONTROL Auto-Allocate（自动分配）] | 从两个或多个体验中确定入选者，然后将流量重定向到该入选者，随着测试的运行和学习而提高转化。<br>要了解使用自动分配活动的优势，请参 [阅自](/help/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) 动分 *配运行A/B测试自* 动分配概览的 [时长](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)。 |
| ![高级](/help/assets/premium.png) [!UICONTROL 徽章自动目标] | 采用先进的机器学习技术，确定多个高性能、由营销人员定义的体验，然后根据访客各自的客户配置文件和过去类似访客的行为，为其提供量身定制的体验，从而实现内容的个性化并推动转化。<br>有关详细信息，请参 [阅自动目标](/help/c-activities/auto-target/auto-target-to-optimize.md)。 |

有关这些[!UICONTROL A/B测试]活动中哪些活动适合您的详细信息，请参阅交互式[Adobe Target指南PDF](/help/c-activities/target-activities-guide.md)。

创建三种类型的[!UICONTROL A/B测试]活动的步骤相似。 要创建[!UICONTROL 自动分配]或[!UICONTROL 自动目标]活动，由[创建A/B测试活动](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)进行开始，但当您进入[!UICONTROL 定位]页面时，请选择所需的流量分配方法，如下所示：

* [!UICONTROL 自动分配到最佳体验]
* [!UICONTROL 自动目标，实现个性化体验]

![流量分配方法设置](/help/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method.png)

## 培训视频：活动类型(9:03)![概述徽章](/help/assets/overview.png)

以下视频介绍了 [!DNL Target Standard/Premium] 中可用的活动类型。

* 介绍 [!DNL Adobe Target] 中包含的活动类型
* 选择相应的活动类型以实现目标
* 介绍适用于所有活动类型的三步引导式工作流

>[!VIDEO](https://video.tv.adobe.com/v/17386)
