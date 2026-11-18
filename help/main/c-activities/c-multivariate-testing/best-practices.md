---
keywords: MVT;多变量测试;多变量测试最佳实践;MVT 最佳实践;MVT 组合;MVT 报表
description: 了解如何改进性能、避免问题以及纠正在[!DNL Adobe Target]中创建和运行[!UICONTROL 多变量测试]活动时可能发生的已知问题。
title: '[!UICONTROL 多变量测试]活动的最佳实践是什么？'
feature: Multivariate Tests
exl-id: bcd15517-1b5f-4425-9404-1d7dd0689e28
TQID: 'https://experienceleague.adobe.com/nQEf5GZ8-zVZakygPtMAYWk-xoJPdcycFbzCNKTqJ-k'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0ae6991a6a86854bd64a632070a1fcbe544cc606
workflow-type: tm+mt
source-wordcount: '868'
ht-degree: 30%
---
# [!UICONTROL 多变量测试]最佳实践 {#mvt-best-practices}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何规划、创建、分析和跟进&#x200B;**[!UICONTROL 多变量测试]**&#x200B;活动以获取可靠的结果。

>[!ENDSHADEBOX]

以下提示可帮助您在[!DNL Adobe Target]中创建和运行&#x200B;**[!UICONTROL 多变量测试]** (MVT)活动时提高性能、避免出现问题，并更正可能会出现的已知问题。

## 规划 {#plan}

* **在测试中至少使用三个元素。**

  如果要测试的元素比这少，则运行一组 A/B 测试。 有关详细信息，请参阅[何时使用多变量测试与A/B](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md#when-to-use-mvt)。

* **了解您通常获得的流量，包括展示次数和转化次数。**

  MVT需要足够的流量才能生成有用的结果，这些信息有助于降低设计所需流量超过网站流量的测试的可能性。

* **请注意页面上可能会产生显着结果的位置。**

  与页脚中的更改相比，横幅或主页图像可能会导致更多转化。 在测试中包含影响力较弱的位置只会增加测试页面上影响力较为显著的位置所需的流量和时间。

* **保持元素相互独立。**

  例如，不要在同一测试中对布局和内容这两方面都进行测试。

* **检查要测试的页面的HTML代码。**

  确保网站上的HTML元素没有重复的DOM ID。 重复的 ID 可能会导致将相同的内容交付到多个位置。

* **提前准备您的页面变体。**

  请注意各个选件的内容差异，并创建希望在 MVT 测试中使用的图像、文本和 HTML 选件。

* **计划额外的QA时间。**

  体验的数量会增加，因此QA需要更多时间。

## 创建 {#create}

* **不要包含测试所需的更多组合。**

  测试的组合每增加一个即会显著增加实现可接受结果所需的流量和时间。 例如，如果您有 3 个位置，每个位置具有 3 个产品建议，则总共会有 27 种可能的组合 (3x3x3)。 如果在 3 个位置中，有 2 个位置包含 3 个可能的产品建议，而另外 1 个位置具有 2 个产品建议，则总共会有 18 种可能的组合 (3x3x2)。 每增加一个位置和选件，组合的数量均会显著增多。

* **命名位置和选件。**

  您可以在测试中将每个位置和选件重命名为更有用的名称。 每个位置中的选件数量显示在位置标头中。 有用的名称可帮助您在检查报表时识别选件。

* **利用预览功能以避免不想要的内容组合。**

  在上线之前，需检查测试生成的所有体验。 请确保没有自相矛盾的声明或设计不兼容（例如，同一体验中优惠20%，优惠19美元）的组合，如同一颜色的背景和字体。

* **使用[流量估算器](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#traffic-estimator)确保设计的测试符合您的页面接收的流量。**

  确保&#x200B;**[!UICONTROL 流量估算器]**&#x200B;为您的测试配置提供绿灯，以便您获得所需的结果。

* **使每个元素的替代项明显不同。**

  虽然不要求如此，但每个元素都具有相同数量的替代项仍是一种良好做法。

## 分析 {#analyze}

* **经常使用[位置贡献报表](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md)**&#x200B;来监视每个位置和选件的性能。

* **在[体验性能报表](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md)中，根据使用[!UICONTROL 最佳5]和[!UICONTROL 最差5]筛选器显示的数据做出决策。**

  使用&#x200B;**[!UICONTROL 全部]**&#x200B;筛选器时，很难提取所需信息，而且并非所有体验都可以显示在图形中。 如果您想要查看的特定体验不在最佳或最差的5个体验之中，请使用&#x200B;**[!UICONTROL 全部]**&#x200B;筛选器。

## 跟进 {#follow-up}

* 虽然[!DNL Target]允许您编辑实时活动，但&#x200B;**编辑正在进行的活动可能会重置测试。** 报表可能无法识别某些更改。 只对选件库中的HTML选件进行更改是安全的。

  重置体验名称和报表的特定操作包括：

  * 添加新位置
  * 删除位置
  * 添加新选件或从现有位置删除选件
  * 编辑富文本选件
  * 编辑背景颜色选件

* **如果您编辑使用基于[!DNL Analytics]的量度的活动（显示旋转器）时未加载报表包，**&#x200B;请将量度切换为[!DNL Target]个量度，然后再次切换为基于[!DNL Analytics]的量度。 此时，报表包应该可以成功加载。

* **按照包含一项或多项A/B测试的MVT测试**&#x200B;来确定所需结果的最佳内容。 在确定哪些位置和内容最有助于您实现目标后，您便可以运行 A/B 测试以进一步细化结果。 例如，当您知道哪些位置最为重要时，请对照两个特定图像进行测试，或者比较call to action的措辞或颜色。
