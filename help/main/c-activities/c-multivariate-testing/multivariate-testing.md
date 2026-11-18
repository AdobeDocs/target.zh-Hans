---
keywords: 多变量测试；mvt；全因子；mvt或a/b；多变量a/b；流量估算器；何时使用mvt；mvt注意事项；多变量；部分因子；部分因子；全因子
description: 了解如何在[!DNL Adobe Target]中使用[!UICONTROL 多变量测试] (MVT)来比较页面上元素中的选件组合，以确定哪个组合表现最佳。
title: 什么是[!UICONTROL 多变量测试]？
feature: Multivariate Tests
exl-id: c8b60011-cb3a-4e28-b84f-06910687b14b
TQID: 'https://experienceleague.adobe.com/JKmjIHJuRxAXlhvUOrrmLMVLnJFhA3T4xkahgH-ozHE'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0ae6991a6a86854bd64a632070a1fcbe544cc606
workflow-type: tm+mt
source-wordcount: '1382'
ht-degree: 24%
---
# 开始使用[!UICONTROL 多变量测试] {#get-started-mvt}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解&#x200B;**[!UICONTROL 多变量测试]**&#x200B;的工作方式，哪些术语[!DNL Target]使用它，何时使用它而不是A/B测试，以及部分因子测试如何降低流量要求。

>[!ENDSHADEBOX]

[!DNL Adobe Target]中的&#x200B;**[!UICONTROL 多变量测试]** (MVT)活动比较页面上元素中的选件组合，以确定哪个组合对特定受众的表现最好。 它还有助于确定哪个元素对活动取得成功的影响最大。 多变量测试可帮助您发现特定元素与页面上的其他元素相比，对转化具有的相对影响，并可帮助您优化已证明有效的元素组合。

与A/B测试相比，**[!UICONTROL 多变量测试]**&#x200B;具有两个优势：

* 它显示页面上的哪些元素对转化具有最大影响，也称为“主效应”。 例如，此信息可帮助您确定要将最受关注的内容放在何处。
* 它可以帮助您在页面上找到两个或多个元素之间的复合效果，也称为“交互效果”。 例如，与特定横幅或主题图像结合使用时，特定广告可能会产生更多转化。

[!DNL Target] 使用全因子多变量测试来帮助您优化内容。 全因子多变量测试以相同概率检查内容的所有可能组合。 例如，如果您有两个页面元素，每个页面元素包含三个选件，则共有九种可能的组合 (3x3)。 如果您有三个元素，其中两个包含三个可能的选件，另一个包含两个选件，则共有 18 个选项 (3x3x2)。

在[!DNL Target]中，每个组合都是一个体验。 **[!UICONTROL 多变量测试]**&#x200B;比较每个体验，以便您了解哪些组合最成功。 同时，[!DNL Target]收集和分析数据，以了解每个位置和选件对成功量度有何影响。

![多变量测试组合](assets/multivariate.png)

由于可生成的组合数量，**[!UICONTROL 多变量测试]**&#x200B;比A/B测试需要更多时间和流量。 页面必须获得足够的流量才能为每个体验产生具有统计意义的结果。 为了获得有用的结果，请了解您的页面接收的流量量，并在适当的时间段内测试最佳组合数量。

[流量估算器](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#traffic-estimator)可以帮助您设计适用于您的流量的测试。 在使用它之前，您应该有良好的统计数据，显示网站通常收到的展示次数和转化次数，并考虑每天的流量水平。 某个活动拥有的体验越多，该活动必须包含的流量就越多或运行的时间就越长。 如果流量不是很高，请测试几种组合。 否则，产生有意义的测试结果所需的时间可能太长而无法使用。

## MVT术语 {#mvt-terminology}

业界以不同方式使用了多个术语。 下表定义了在您设置多变量测试时[!DNL Target]使用的术语。

| 术语 | 定义 |
|--- |--- |
| 组合 | 在多个位置测试多个内容选项时创建的内容变体。 例如，如果要测试三个位置，每个位置具有三个内容选项，则总共会有27种可能的组合(3x3x3)。 您网站的访客会看到一个组合，也称为体验。 |
| 内容 | 构成某个位置中测试变体的文本或图像。 在多变量测试中，会比较多个位置中的多个内容选项。 在 MVT 方法中，有时将内容称为“级”**。 |
| 元素 | 包含要在MVT测试中测试的内容变体的DOM元素。 另请查看“位置”**。 |
| 位置 | 页面上的特定内容区域，通常包含在单个 DOM 元素中。 在 MVT 方法中，有时将内容称为“因子”**。 全因子多变量测试会比较您的位置中所有可能的选件组合。 |

## 何时使用[!UICONTROL 多变量测试]与A/B {#when-to-use-mvt}

下表显示何时同时使用&#x200B;**[!UICONTROL 多变量测试]**&#x200B;和/或A/B测试来优化您的页面。

| 情况 | 要做什么 | 详细信息 |
|--- |--- |--- |
| 要测试的元素少于三个。 | 运行一系列A/B测试。 | 当您至少有三个元素要进行测试时，请使用 MVT 测试。 |
| 您希望同时优化页面的布局和内容。 | 使用A/B测试优化页面布局，接着使用MVT测试确定页面上每个元素的最佳内容。 | A/B测试可以提供关于布局的重要反馈，而MVT测试则擅长测试页面设计中元素的内容。 在测试多个内容选项之前对布局运行A/B测试可帮助您确定最佳布局和最具影响力的内容。 |
| 不同体验的数量超过5个，并跨越两个或更多元素。 | 使用 MVT 测试来确定最重要的元素，然后对该元素进行更集中的 A/B 测试。 | MVT 测试可显示页面中的哪些区域最有可能提高转化。 这些是营销人员应关注的元素。 例如，MVT 测试可能表明，行为召唤 (call to action) 是实现目标的最重要元素。 然后，您可以运行A/B测试以进一步优化结果，例如，通过测试两个特定图像来相互对比，或者通过比较call to action的措辞或颜色。 通过执行包含一项或多项A/B测试的MVT测试，可以确定最适合所需结果的内容。 |

有关更多考虑事项，例如要包含多少元素以及如何规划测试，请参阅[多变量测试最佳实践](/help/main/c-activities/c-multivariate-testing/best-practices.md)。

## 部分因子测试 {#partial-factorial}

[!DNL Target] 提供全因子多变量测试作为内置活动选项。 在统计学中，“实验设计”提供了多种方法或设计来确定哪些因素会影响结果。 其中一种方法是用于部分因子测试的[田口方法](https://en.wikipedia.org/wiki/Taguchi_methods)。 “田口方法”使营销人员能够制定一套假设，减少必须测试的体验的排列数量，从而降低多变量测试的流量需求。 您可以使用此[脱机电子表格](/help/main/assets/MVT-Taguchi-Partial-Factorial-Design-02102017.xlsx)在[!DNL Target]中应用此方法。

如果您的团队使用其他试验设计方法，您可以将电子表格用作自定义试验设计的参考实施。

在您使用该离线计算电子表格时，请考虑以下提示：

* 选取要更改的元素以及每个元素的版本号（3x2、4x3等）。
* 保持编号一致。 例如，如果按钮是元素 1，选项是蓝色、绿色和黄色，则蓝色按钮为 1-1，绿色按钮为 1-2，黄色按钮为 1-3。
* 该离线电子表格提供了所需的相应数量的体验（3x2 是 4 个、4x3 是 9 个，等等）。
* 使用[可视化体验编辑器 (VEC)](/help/main/c-experiences/experiences.md) 在 A/B 工作流中构建体验。 您可以使用自定义代码、编辑 HTML、WYSIWYG 或任意组合。
* 活动结束后（基于样本量计算器），通过电子表格运行结果以获取其他详细信息。

## 培训视频 {#training-videos}

以下视频包含有关本页面上讨论的概念的更多信息。

### 活动类型(9:03) ![概述徽章](/help/main/assets/overview.png)

此概述视频介绍[!DNL Target]中可用的活动类型。 对多变量测试的讨论开始于 4:20。 在本视频中，您将学习如何：

* 描述[!DNL Adobe Target]中包含的活动类型。
* 选择适当的活动类型以实现您的目标。
* 描述适用于所有活动类型的三步引导式工作流。

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### 正在创建多变量测试(9:25) ![教程徽章](/help/main/assets/tutorial.png)

此视频介绍如何使用[!DNL Target]三步引导式工作流来了解、规划和创建多变量测试。 在本视频中，您将学习如何：

* 定义并设计多变量测试。
* 创建多变量测试。

>[!VIDEO](https://video.tv.adobe.com/v/17395)
