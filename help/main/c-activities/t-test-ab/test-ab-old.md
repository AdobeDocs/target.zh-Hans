---
keywords: AB；A/B；AB...n；比较体验；定位；比较内容；自动定位；自动分配
description: 了解Adobe [!DNL Target] 中不同类型的A/B测试活动 — 手动、自动分配和自动定位。 选择适合您的版本。
title: Target中提供了哪种类型的A/B活动？
feature: A/B Tests
exl-id: e8ff8994-a0a9-4fc7-8fcb-e3a1b7697604
source-git-commit: 974746e25724abf0e5edd3884331ec0975e5352e
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 25%

---

# A/B测试概述

手动[!UICONTROL A/B Test]活动比较两个或更多版本的网站内容，以查看在预先指定的测试期间，哪个版本最有利于提高转化。

>[!NOTE]
>
>除了手动（默认） [!UICONTROL A/B Test]活动（在此部分中讨论）之外，[!DNL Target]还提供另外两种类型的[!UICONTROL A/B Test]活动：[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]。 有关详细信息，请参阅下面的[A/B测试活动类型](#types)。

手动[!UICONTROL A/B Test]活动（有时称为A/B...N测试）比较两个或更多版本的网站内容，以查看哪个版本最有利于提高您识别的转化、销售额或其他指标。 使用 A/B 测试还可以比较更改后的页面和默认页面设计，以确定哪个体验可以产生最佳效果。

当您根据成功量度或替代内容交付对提高页面性能的方法有一个明确的假设时，手动A/B测试很有用。

手动A/B测试非常适合涉及新布局或元素处理方式截然不同的大型更改。 如果您的测试设计不容易分解为单独的页面元素，则应当先运行A/B测试，然后再运行[多变量测试](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)。

在设置A/B测试时，您可以确定查看每个体验的访客百分比。 例如，您可以在控制体验和另一个体验之间平均拆分流量，也可以通过仅向 5% 的受众显示风险更高的新体验来测试该体验。

>[!NOTE]
>
>有关确定 A/B 测试最佳样本大小的详细信息，请参阅[规划 A/B 测试](/help/main/c-activities/t-test-ab/sample-size-determination.md)。

当不同体验的数量超过5个并跨越两个或更多位置时，最好在运行A/B测试之前先运行[MVT测试](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)。 多变量测试可显示页面中的哪些区域最有可能提高转化。这些区域是营销人员应重点关注的位置。 例如，多变量测试可能会显示促使用户采取行动的位置对达成目标最为重要。确定哪些位置和内容对帮助您实现目标最有用后，可以运行A/B测试以进一步优化结果。 例如，对两个特定图像进行相互测试，或者比较行动号召的措辞或颜色。 通过在 MVT 测试后使用一个或多个 A/B 测试，您可以确定达成所需结果的最佳内容。

## A/B测试活动的类型 {#types}

除了手动[!UICONTROL A/B Test]活动（在本节中讨论）之外，[!DNL Target]还提供另外两种类型的A/B测试活动： [!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]。

| 活动类型 | 描述 |
| --- | --- |
| [!UICONTROL Manual A/B Test] | 比较两个或更多体验，以查看在预先指定的测试期间，哪个最佳体验可提高转化。<P>本节介绍如何设置手动[!UICONTROL A/B Test]活动，但其他类型的[!UICONTROL A/B Test]活动的步骤类似。 |
| [!UICONTROL Auto-Allocate] | 从两个或更多体验中标识一个入选者，然后将流量重定向到该入选者，随着测试的运行和学习而提高转化。<P>若要了解使用[!UICONTROL Auto-Allocate]活动的好处，请参阅&#x200B;*中的[自动分配](/help/main/c-activities/t-test-ab/sample-size-determination.md#auto-allocate)A/B测试应该运行多久*&#x200B;和[自动分配概述](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)。 |
| ![高级徽章](/help/main/assets/premium.png) [!UICONTROL Auto-Target] | 使用先进的机器学习技术，通过识别多个高性能、营销人员定义的体验来个性化内容并促进转化。 然后，根据访客的各个客户配置文件和过去类似访客的行为，向访客提供量身定制的体验。<P>有关详细信息，请参阅[自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md)。 |

有关哪些[!UICONTROL A/B Test]活动适合您的详细信息，请参阅交互式[Adobe Target活动指南PDF](/help/main/c-activities/target-activities-guide.md)。

创建三种类型[!UICONTROL A/B Test]活动的步骤相似。 要创建[!UICONTROL Auto-Allocate]或[!UICONTROL Auto-Target]活动，请从[创建A/B测试活动](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)开始，但当您进入[!UICONTROL Targeting]页面时，请选择所需的流量分配方法，如下所示：

* [!UICONTROL Auto-allocate to best experience]
* [!UICONTROL Auto-target for personalized experience]

![流量分配方法设置](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method.png)

## 在A/B活动中包含推荐

您可以在[!UICONTROL A/B Test]、[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]活动(和[!UICONTROL Experience Targeting] (XT)活动)中包含推荐。 有关更多信息，请参阅[将推荐作为产品建议](/help/main/c-recommendations/recommendations-as-an-offer.md)。

要使用此功能，您需要拥有[Target Premium许可证](/help/main/c-intro/intro.md#premium)

## 培训视频：活动类型（9 分 3 秒）![概述徽章](/help/main/assets/overview.png)

以下视频介绍了 [!DNL Target Standard/Premium] 中可用的活动类型。

* 介绍 [!DNL Adobe Target] 中包含的活动类型
* 选择相应的活动类型以实现目标
* 介绍适用于所有活动类型的三步引导式工作流

>[!VIDEO](https://video.tv.adobe.com/v/17386)
