---
keywords: MVT;多变量测试;多变量测试最佳实践;MVT 最佳实践;MVT 组合;MVT 报表
description: 了解如何改进性能、避免问题以及更正在 [!DNL Adobe Target]中创建和运行[!UICONTROL Multivariate Test]活动时可能发生的已知问题。
title: 有关[!UICONTROL Multivariate Test]活动的最佳实践是什么？
feature: Multivariate Tests
exl-id: bcd15517-1b5f-4425-9404-1d7dd0689e28
source-git-commit: 0d73a062f70080057c3323f5150af067e3a2e27e
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 57%

---

# [!UICONTROL Multivariate Test]最佳实践

以下提示可帮助您在[!DNL Adobe Target]中创建和运行[!UICONTROL Multivariate Test] (MVT)活动时提高性能、避免出现问题，并更正可能会出现的已知问题。

## 规划 {#section_4D4A1F6226F042379BF48DB753608579}

* 注意页面上可能会产生显著结果的位置。

  例如，与在页脚中做出更改相比，横幅或主页图像可能会促进更多转化。在测试中包含影响力较弱的位置只会增加测试页面上影响力较为显著的位置所需的流量和时间。
* 提前准备页面变体。

  请注意各个选件的内容差异，并创建希望在 MVT 测试中使用的图像、文本和 HTML 选件。

## 创建 {#section_C59C722CA82E48ABA58A4A7FA758F193}

* 在测试中仅包含所需数量的组合，切勿包含多余组合。

  测试的组合每增加一个即会显著增加实现可接受结果所需的流量和时间。例如，如果您有 3 个位置，每个位置具有 3 个选件，则总共会有 27 种可能的组合 (3x3x3)。如果在 3 个位置中，有 2 个位置包含 3 个可能的选件，而另外 1 个位置具有 2 个选件，则总共会有 18 种可能的组合 (3x3x2)。每增加一个位置和选件，组合的数量均会显著增多。

* 为位置和选件命名。

  您可以在测试中将每个位置和选件重命名为更有用的名称。每个位置中的选件数量显示在位置标头中。有用的名称可帮助您在检查报表时识别选件。

* 利用预览功能可以避免不需要的内容组合。

  在上线之前，需检查测试生成的所有体验。请确保没有自相矛盾的声明的组合（例如，同一体验中优惠20%，优惠19美元）或设计不兼容，如使用同一颜色的背景和字体。

* 使用[流量估算器](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md)确保设计的测试符合您的页面接收的流量。

  确保流量估算器为您的测试配置开了绿灯，以便您能获得所需的结果。

* 每个元素的替代项应彼此有显着差异。

## 分析 {#section_9A2118CF1039451681C13D9AE79A58AB}

* 经常使用[位置贡献报表](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md)来监视每个位置和选件的性能。
* 在[体验性能报表](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md)中，根据使用[!UICONTROL Best 5]和[!UICONTROL Worst 5]筛选器显示的数据做出决策。

  使用[!UICONTROL All]筛选器很难提取所需信息，而且并非所有体验都可以显示在图形中。 如果要查看的特定体验不在最佳或最差的5个体验之中，请使用[!UICONTROL All]筛选器。

## 其他信息 {#section_1C44A767F6AB4441A3EAA8AC995F46B0}

* 虽然[!DNL Target]允许您编辑实时活动，但编辑正在进行的活动可能会重置测试。 报表可能无法识别某些更改。 只有在选件库中更改 HTML 选件才是安全的。

  重置体验名称和报表的特定操作包括：

   * 添加新位置
   * 删除位置
   * 添加新选件或从现有位置删除选件
   * 编辑富文本选件
   * 编辑背景颜色选件

* 通过在 MVT 测试后使用一个或多个 A/B 测试，您可以确定达成所需结果的最佳内容。

  在确定哪些位置和内容最有助于您实现目标后，您便可以运行 A/B 测试以进一步细化结果。例如，当您知道哪些位置最重要时，请将两个特定图像相互进行对比测试，或者比较行动号召的措辞或颜色。
