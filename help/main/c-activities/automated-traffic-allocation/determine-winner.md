---
keywords: 自动流量分配；定位；入选者；统计保证；置信度；确定入选者；提升度；置信度；默认；默认体验；自动分配；自动分配
description: 了解如何解释[!UICONTROL Auto-Allocate]个A/B活动结果，并侧重于提升度和置信度等关键指标。
title: 如何解释[!UICONTROL Auto-Allocate]报表？
feature: Auto-Allocate
exl-id: 4ed00eee-8939-4958-9be6-b45a8c08afbc
source-git-commit: 32a91a41cd182d3a55ded7dea8c1c6ea6f46aa71
workflow-type: tm+mt
source-wordcount: '1163'
ht-degree: 20%

---

# 解释[!UICONTROL Auto-Allocate]报告

通过检查重要指标（包括提升度和置信度）来解释[!UICONTROL Auto-Allocate]中的[!UICONTROL Adobe Target] A/B活动的结果。

许多营销人员会在结果指示明确的入选者之前，过早地错误宣布入选体验。[!DNL Target]使您更容易确定入选者。

有关声明入选者的一般信息，请参阅[A/B测试常见的十个隐患以及如何避免它们](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md)。

## 确定入选的体验 {#section_24007470CF5B4D30A06610CE8DD23CE3}

使用[!UICONTROL Auto-Allocate]功能时，[!DNL Target]会在活动页面的顶部显示一个标记，在活动达到最低转化次数，且具有足够的置信度之前，该标记会一直指示“还没有入选者”。

![“没有入选者”标记](/help/main/c-activities/automated-traffic-allocation/assets/no-winner-new.png)

在宣布明确的入选者后，[!DNL Target]会显示“入选者：体验&#x200B;*X*”徽章。

![入选者徽章](/help/main/c-activities/automated-traffic-allocation/assets/winner-new.png)

>[!NOTE]
>
>[!UICONTROL Auto-Allocate]活动旨在从所有选项中找出最佳体验，而不仅仅是与控制体验进行两两比较。

## [!UICONTROL Auto-Allocate]的统计保证 {#section_7AF3B93E90BA4B80BC9FC4783B6A389C}

在A/B活动结束时，[!UICONTROL Auto-Allocate]确保确定的入选者的有效误报率为5%。 这意味着确定的入选者实际不是所有活动体验中的最佳体验的概率仅为 5%。对于[A/A测试](/help/main/c-activities/t-test-ab/aa-testing.md) （具有相同的体验），[!DNL Target]结束测试的时间不到5%。 对于 A/A 测试（具有相同的体验），预期行为是无限期地运行，因此应该永远不会出现入选者标记。

[!DNL Target]没有对[!UICONTROL Auto-Allocate]使用基于p值的置信度。

[!UICONTROL Confidence]活动中的[!UICONTROL Auto-Allocate]列显示体验在1%的错误容限内成为入选者的概率。 该算法在最佳和次最佳转化率之间使用1%的最小可检测效果。 算法使用[Bernstein不等式](https://en.wikipedia.org/wiki/Bernstein_inequalities_%28probability_theory%29)来计算此概率。

常规 A/B 测试将基于 p 值计算置信度。[!UICONTROL Auto-Allocate]不使用p值。 p 值可“大致”计算出某个特定体验与控制体验存在差异的概率。这些 p 值只能用于确定体验是否与控制体验存在差异。这些值不能用于确定体验是否与其他体验（非控制体验）存在差异。

>[!IMPORTANT]
>
>[!DNL Target]在预定义的最小转化次数后显示入选者；但是，最终决定挑选入选者应始终基于[!DNL Adobe Target]样本量计算器的结果。 [!DNL Target]不考虑站点的基本转化率以及输入计算器以确定活动持续时间的其它重要方面。 因此，根据最低转化次数，[!DNL Target]可能显示比保修更早的入选者。 有关详细信息，请参阅[样本量计算器](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)。

## 了解[!UICONTROL Auto-Allocate]活动中的提升和置信度报表 {#lift-confidence}

在[!UICONTROL Auto-Allocate]活动中，第一个体验（默认情况下名为体验A）始终定义为[!UICONTROL Reports]选项卡上的“控制”体验。 在用于确定体验性能的建模中，此体验不会被视为真正的统计控制，而是会被视为报表中某些数字的参考或基准。

每次体验的“提升度”数值和95%界限都是根据定义的“控制”体验来计算的。 定义的“控制”体验无法具有相对于自身的提升，因此将报告此体验的空白“ — ”值。 与A/B测试不同，在[!UICONTROL Auto-Allocate]测试中，如果体验的执行效果比定义的控制更好，则不会报告提升度为负值，而是显示“ — ”。

显示的[!UICONTROL Confidence Interval]条表示体验转化率平均估计值的95%置信区间。 这些栏也按照定义的“控制”体验进行了颜色编码。 “控制”体验的栏始终为灰色。 置信区间在“控制”体验的置信区间之下的部分显示为红色，而置信区间在“控制”体验之上的部分显示为绿色。

当领先体验的95% [!UICONTROL Confidence Interval]与任何其他体验不重叠时，将找到入选者。 入选体验会在体验名称左侧和“入选者”横幅中指定绿色星形标记。 如果没有可见星标，横幅会显示“还没有入选者”，并且尚未找到入选者。

当前领先或入选的体验旁边也会报告“置信度”数字。 此数字仅会在领导体验的[!UICONTROL Confidence]达到至少60%时报告。 如果[!UICONTROL Auto-Allocate]活动中存在两个体验，则此数字表示该体验的执行效果优于其他体验的置信水平。 如果[!UICONTROL Auto-Allocate]活动中存在两个以上的体验，则该数字表示体验比定义的“控制”体验表现更好的置信水平。 如果“控制”体验获胜，则不会报告“置信度”数字。

## 常见问题解答 {#section_C8E068512A93458D8C006760B1C0B6A2}

请仔细研究下列常见问题解答：

### 这个活动已经进行了几天。 为何所有置信度值仍显示0%？

以下任何原因描述了为什么在所有活动的0%都显示在报表的[!UICONTROL Confidence]列中：

* 手动A/B测试和[!UICONTROL Auto-Allocate]使用不同的统计信息来显示[!UICONTROL Confidence]值。

  手动A/B测试使用基于[Welch的t测试](https://en.wikipedia.org/wiki/Welch%27s_t-test)的p值。 P 值是指在体验与控制体验之间找到观察到的差异（或更极端的差异）的概率（但实际上根本不存在这样的差异）。这些 P 值只能用于确定在给定体验与控制体验相同的情况下，观察到的数据是否一致。这些值不能用于确定体验是否与其他体验（非控制体验）存在差异。

  [!UICONTROL Auto-Allocate]显示给定体验成为活动中所有体验的真正入选者的概率。 只有获胜的体验（最有可能成为获胜者）具有非零置信值。 其他所有人最有可能是输家，显示为0%。

* 只有在入选体验收集了60%的置信度后，[!UICONTROL Auto-Allocate]才开始显示置信度。 这些置信度级别通常出现在正常A/B测试完成所需时间的大约一半的时间中（但不保证会超过此时间范围）。 要确定常规A/B测试运行的时长，请使用[!DNL Adobe Target] [样本量计算器](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)：将控制体验的转化率插入“基准转化率”，将“5%”插入“提升度”，并将95%插入“置信度”。 通常情况下，在每个体验达到其所需样本量的至少 50% 之后，置信度便会开始显示。这可以让您了解何时开始出现信心。

* 如果报表中所有置信度值均显示为 0%，则有可能是进入活动的时间过早。

### “无入选者”、“入选者”和“星星”徽章是否适用于使用[!UICONTROL Auto-Allocate] (A4T)的[!UICONTROL Analytics as the reporting source]活动？

“尚未有入选者”和“入选者”徽章当前在[!UICONTROL A4T]的[!DNL Analysis Workspace]面板中不可用。 如果在[!DNL Target]中查看了同一报告，则这些徽章也将不可用。 使用A4T的[!DNL Target]活动的[!UICONTROL Auto-Allocate]报表中显示的入选者“星”徽章应当被忽略。

有关此限制及其他限制和注释的更多信息，请参阅[和](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#aa)活动&#x200B;*的[!UICONTROL Auto-Allocate]A4T支持[!UICONTROL Auto-Target]自动分配*。
