---
keywords: AB;A/B;AB...n；比较体验；定位；比较内容；自动定位；自动分配
description: 了解Adobe中不同类型的A/B测试活动 [!DNL Target]  — 手动、自动分配和自动定位。 选择适合你的。
title: Target中提供哪种类型的A/B活动？
feature: A/B Tests
exl-id: e8ff8994-a0a9-4fc7-8fcb-e3a1b7697604
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 39%

---

# A/B测试概述

手册 [!UICONTROL A/B测试] 活动会比较网站内容的两个或多个版本，以查看在预先指定的测试期间，哪个版本最能提高转化。

>[!NOTE]
>
>除了手动（默认） [!UICONTROL A/B测试] 活动（在此部分中讨论）、 [!DNL Target] 提供了另外两种类型 [!UICONTROL A/B测试] 活动： [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位].
>
>请参阅 [A/B测试活动的类型](#types) 下面以了解更多信息。

手册 [!UICONTROL A/B测试] 活动（有时称为A/B...N测试）会比较网站内容的两个或更多版本，以了解哪个版本最能提升转化率、销售额或您识别的其他量度。 使用 A/B 测试还可以比较更改后的页面和默认页面设计，以确定哪个体验可以产生最佳效果。

如果您根据成功量度或替代内容交付对提高页面性能的方法有明确的假设，则手动A/B测试尤其有用。

手动A/B测试非常适合进行大型更改，这些更改可能涉及新的布局或完全不同的元素处理方法。 如果测试设计不容易划分为各个页面元素，则应在 [多变量测试](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md).

在设置A/B测试时，您可以确定查看每个体验的访客百分比。 例如，您可以在控制体验和另一个体验之间平均拆分流量，也可以通过仅向 5% 的受众显示风险更高的新体验来测试该体验。

>[!NOTE]
>
>有关确定 A/B 测试最佳样本大小的详细信息，请参阅[规划 A/B 测试](/help/main/c-activities/t-test-ab/sample-size-determination.md)。

如果不同体验的数量超过 5 个，且这些体验位于两个或更多位置，则最好在运行 A/B 测试之前先运行 [MVT 测试](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)。多变量测试可显示页面中的哪些区域最有可能提高转化。这些是营销人员应该关注的位置。例如，多变量测试可能会显示促使用户采取行动的位置对达成目标最为重要。确定哪些位置和内容对帮助您实现目标最有用后，您可以运行A/B测试以进一步优化结果，例如测试两个特定图像，或比较行动动员的措辞或颜色。 通过在 MVT 测试后使用一个或多个 A/B 测试，您可以确定达成所需结果的最佳内容。

## A/B测试活动的类型 {#types}

除手册外 [!UICONTROL A/B测试] 活动（在此部分中讨论）、 [!DNL Target] 提供了另外两种类型的A/B测试活动： [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位].

| 活动类型 | 描述 |
| --- | --- |
| [!UICONTROL 手动 A/B 测试] | 比较两个或多个体验，以查看在预先指定的一段测试时间内，哪个体验最有利于提高转化。<br>本节介绍如何设置手册 [!UICONTROL A/B测试] 活动，但是其他类型的 [!UICONTROL A/B测试] 活动类似。 |
| [!UICONTROL 自动分配] | 从两个或多个体验中确定入选者，然后将流量重定向到该入选者，随着测试的运行和学习而提高转化。<br>要了解使用自动分配活动的好处，请参阅 [自动分配](/help/main/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) in *A/B测试应该持续多长时间* 和 [自动分配概述](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| ![Premium徽章](/help/main/assets/premium.png) [!UICONTROL 自动定位] | 采用先进的机器学习技术，确定多个高性能、由营销人员定义的体验，然后根据访客各自的客户配置文件和过去类似访客的行为，为其提供量身定制的体验，从而实现内容的个性化并推动转化。<br>有关更多信息，请参阅 [自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md). |

有关其中哪项的详细信息 [!UICONTROL A/B测试] 活动非常适合您，请参阅交互式 [Adobe Target Activities指南PDF](/help/main/c-activities/target-activities-guide.md).

创建以下三种类型的 [!UICONTROL A/B测试] 活动类似。 创建 [!UICONTROL 自动分配] 或 [!UICONTROL 自动定位] 活动，开头者 [创建A/B测试活动](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)，但是当您 [!UICONTROL 定位] ，请选择所需的流量分配方法，如下所示：

* [!UICONTROL 自动分配到最佳体验]
* [!UICONTROL 自动定位以提供个性化体验]

![流量分配方法设置](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method.png)

## 培训视频：活动类型（9 分 3 秒）![概述徽章](/help/main/assets/overview.png)

以下视频介绍了 [!DNL Target Standard/Premium] 中可用的活动类型。

* 介绍 [!DNL Adobe Target] 中包含的活动类型
* 选择相应的活动类型以实现目标
* 介绍适用于所有活动类型的三步引导式工作流

>[!VIDEO](https://video.tv.adobe.com/v/17386)
