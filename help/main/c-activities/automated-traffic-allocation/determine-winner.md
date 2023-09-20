---
keywords: 自动流量分配；定位；入选者；统计保证；置信度；确定入选者；提升度；置信度；默认；默认体验；自动分配；自动分配
description: 了解如何解释的结果 [!UICONTROL 自动分配] Adobe中的A/B活动 [!DNL Target] 包括提升度和置信度在内的重要指标。
title: 我该如何解释 [!UICONTROL 自动分配] 报告？
feature: Auto-Allocate
exl-id: 4ed00eee-8939-4958-9be6-b45a8c08afbc
source-git-commit: e9976135c46f6658030b07fce384364f0c9ff0ed
workflow-type: tm+mt
source-wordcount: '1206'
ht-degree: 29%

---

# 解释自动分配报表

解释的结果 [!UICONTROL 自动分配] 中的A/B活动 [!UICONTROL Adobe Target] 包括提升度和置信度在内的重要指标。

许多营销人员会在结果指示明确的入选者之前，过早地错误宣布入选体验。[!DNL Target] 使您更容易确定入选者。

有关声明入选者的一般信息，请参见 [A/B测试常见的十个隐患以及如何避免它们](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md).

## 确定入选的体验 {#section_24007470CF5B4D30A06610CE8DD23CE3}

使用[!UICONTROL 自动分配]功能时，[!DNL Target] 会在活动页面的顶部显示一个标记，在活动达到最低转化次数，且具有足够的置信度之前，该标记会一直指示“还没有入选者”。

![“没有入选者”标记](/help/main/c-activities/automated-traffic-allocation/assets/no-winner.png)

当宣布明确的赢家时， [!DNL Target] 显示“入选者：体验” *X*“

![入选者图像](assets/winner.png)

>[!NOTE]
>
>自动分配活动旨在从所有体验选项中找出最佳体验，而不仅仅是与控制体验进行两两比较。

## 自动分配的统计保证 {#section_7AF3B93E90BA4B80BC9FC4783B6A389C}

在A/B活动结束时， [!UICONTROL 自动分配] 确保已确定入选者的有效误报率为5%。 这意味着确定的入选者实际不是所有活动体验中的最佳体验的概率仅为 5%。对于 [A/A测试](/help/main/c-activities/t-test-ab/aa-testing.md) （具有相同的体验）， [!DNL Target] 完成测试的时间不到5%。 对于 A/A 测试（具有相同的体验），预期行为是无限期地运行，因此应该永远不会出现入选者标记。

[!DNL Target] 不使用基于p值的置信度 [!UICONTROL 自动分配].

此 [!UICONTROL 置信度] 中的列 [!UICONTROL 自动分配] 活动（如下图所示）显示体验在1%的错误幅度内成为入选者的概率。 该算法在最佳和次最佳转化率之间使用1%的最小可检测效果。 算法使用 [Bernstein不等式](https://en.wikipedia.org/wiki/Bernstein_inequalities_%28probability_theory%29) 计算此概率。

常规 A/B 测试将基于 p 值计算置信度。[!UICONTROL 自动分配则不使用 p 值。]p 值可“大致”计算出某个特定体验与控制体验存在差异的概率。这些 p 值只能用于确定体验是否与控制体验存在差异。这些值不能用于确定体验是否与其他体验（非控制体验）存在差异。

>[!IMPORTANT]
>
>[!DNL Target] 在预定义的最小转化次数后显示入选者；但是，确定入选者的最终决定应始终取决于的结果 [!DNL Adobe Target] 样本量计算器。 [!DNL Target] 不考虑站点的基本转化率以及用于确定活动持续时间的计算器输入的其他重要方面。 因此， [!DNL Target] 可能会根据最小转化次数显示比保证更早的入选者。 有关更多信息，请参阅 [样本量计算器](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

## 了解中的提升度和置信度报表 [!UICONTROL 自动分配] 活动 {#lift-confidence}

在 [!UICONTROL 自动分配] 在活动中，第一个体验（默认情况下名为体验A）始终被定义为 [!UICONTROL 报表] 选项卡。 在用于确定体验性能的建模中，此体验不会被视为真正的统计控制，而是会被视为报表中某些数字的参考或基准。

每次体验的“提升度”数值和95%界限都是根据定义的“控制”体验来计算的。 定义的“控制”体验无法具有相对于自身的提升，因此将报告此体验的空白“ — ”值。 与A/B测试不同，在 [!UICONTROL 自动分配] 测试中，如果体验的执行效果比定义的控制体验差，则不会报告提升度为负值，而是会显示“ — ”。

显示的 [!UICONTROL 置信区间] 条形图表示在体验转化率的平均估计值周围的95%置信区间。 这些栏也按照定义的“控制”体验进行了颜色编码。 “控制”体验的栏始终为灰色。 置信区间在“控制”体验的置信区间之下的部分显示为红色，而置信区间在“控制”体验之上的部分显示为绿色。

当领先体验的95%时，将会找到入选者 [!UICONTROL 置信区间] 未与任何其他体验重叠。 入选体验会在体验名称左侧和“入选者”横幅中指定绿色星形标记。 如果没有可见星标，横幅会显示“还没有入选者”，并且尚未找到入选者。

当前领先或入选的体验旁边也会报告“置信度”数字。 此数字仅报告到主要体验的 [!UICONTROL 置信度] 至少达到60%。 如果有两个体验同时存在于中 [!UICONTROL 自动分配] 活动，此数字表示体验表现优于其他体验的置信水平。 如果存在两个以上的体验 [!UICONTROL 自动分配] 活动，此数字表示体验表现优于定义的“控制”体验的置信水平。 如果“控制”体验获胜，则不会报告“置信度”数字。

## 常见问题解答 {#section_C8E068512A93458D8C006760B1C0B6A2}

请仔细研究下列常见问题解答：

### 活动已经进行几天了。为何所有的置信度值仍显示为 0%？

所有活动在报表的“[!UICONTROL 置信度]”列显示 0% 的原因如下：

* 手动A/B测试和 [!UICONTROL 自动分配] 使用不同的统计信息显示 [!UICONTROL 置信度] 值。

  手动A/B测试使用基于的p值 [韦尔奇t检验](https://en.wikipedia.org/wiki/Welch%27s_t-test). P 值是指在体验与控制体验之间找到观察到的差异（或更极端的差异）的概率（但实际上根本不存在这样的差异）。这些 P 值只能用于确定在给定体验与控制体验相同的情况下，观察到的数据是否一致。这些值不能用于确定体验是否与其他体验（非控制体验）存在差异。

  [!UICONTROL 自动分配] 显示给定体验在活动中成为所有体验的真正入选者的概率。 只有获胜的体验（最有可能成为获胜者）具有非零置信值。 其他所有人最有可能是输家，显示为0%。

* [!UICONTROL 仅当入选体验达到 60% 的置信度后，自动分配才会开始显示置信度。]这些置信度级别通常出现在正常A/B测试完成所需时间的大约一半的时间中（但不保证会超过此时间范围）。 要确定常规A/B测试运行的时长，请使用 [!DNL Adobe Target] [样本量计算器](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)：将控制体验的转化率插入“基准转化率”，“5%”插入“提升度”，95%插入“置信度”。 通常情况下，在每个体验达到其所需样本量的至少 50% 之后，置信度便会开始显示。这可以让您了解何时开始出现信心。

* 如果报表中所有置信度值均显示为 0%，则有可能是进入活动的时间过早。

### 对于使用 [!UICONTROL Analytics 作为报表源] (A4T) 的[!UICONTROL 自动分配]活动，是否有“无入选项目”、“入选项目”和“星标”徽章可用？

“尚未有入选者”和“入选者”徽章当前在中不可用 [!UICONTROL A4T] 面板位于 [!DNL Analysis Workspace]. 如果在中查看同一报表，则这些徽章也将不可用 [!DNL Target]. 中显示的入选者“star”徽章 [!DNL Target] 报表 [!UICONTROL 自动分配] 应忽略使用A4T的活动。

有关此限制及其他限制和注释的更多信息，请参阅 [自动分配](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#aa) 在 *的A4T支持 [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位] 活动*.


