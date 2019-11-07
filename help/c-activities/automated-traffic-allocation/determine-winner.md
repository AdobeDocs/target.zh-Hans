---
keywords: 自动流量分配;定位;入选者;统计保证;置信度;确定入选者
description: 通过查看 Target UI 中的指示器，可确定自动分配 A/B 活动中的入选者。
title: 确定入选者
topic: Standard
uuid: 0bcc11b2-44bd-450c-a504-a8ff7a4d72e6
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 确定入选者{#determine-a-winner}

通过查看 Target UI 中的指示器，可确定自动分配 A/B 活动中的入选者。

许多营销人员会在结果指示明确的入选者之前，过早地错误宣布入选体验。现在，我们可使您更轻松地确定入选者。

## 查看 Target UI 中的入选者标记 {#section_24007470CF5B4D30A06610CE8DD23CE3}

使用[!UICONTROL 自动分配]功能时，[!DNL Target] 会在活动页面的顶部显示一个标记，在活动达到最低转化次数，且具有足够的置信度之前，该标记会一直指示“还没有入选者”。

![“没有入选者”标记](/help/c-activities/automated-traffic-allocation/assets/no-winner.png)

在宣布明确的入选者后，[!DNL Target] 会显示“入选者: 体验 X。”

![](assets/auto_traffic_winner.png)

>[!NOTE]
>
>自动分配活动旨在从所有体验选项中找出最佳体验，而不仅仅是与控制体验进行两两比较。

## 自动分配的统计保证 {#section_7AF3B93E90BA4B80BC9FC4783B6A389C}

在 A/B 活动结束时，自动分配会保证确定的入选者具有 5% 的有效误报率。这意味着确定的入选者实际不是所有活动体验中的最佳体验的概率仅为 5%。对于 A/A 测试（包含相同的体验），我们可以断定测试的误报率低于 5%。对于 A/A 测试（具有相同的体验），预期行为是无限期地运行，因此应该永远不会出现入选者标记。

自动分配不使用基于 p 值的置信度。

自动分配活动的“置信度”列（如下图所示）显示了在 1% 的误差范围（即，算法使用的最高转化率与第二高转化率之间的最低可检测效果为 1%）内某个体验成为入选者的概率。请注意，算法使用 [Bernstein 不等式](https://en.wikipedia.org/wiki/Bernstein_inequalities_(probability_theory))来计算此概率。

常规 A/B 测试将基于 p 值计算置信度。自动分配则不使用 p 值。p 值可“大致”计算出某个特定体验与控制体验存在差异的概率。这些 p 值只能用于确定体验是否与控制体验存在差异。这些值不能用于确定体验是否与其他体验（非控制体验）存在差异。

下图显示了一个还没有入选者的活动：

![](assets/no_winner.png)

下图显示了一个已经有入选者的活动：

![](assets/winner_found.png)

## 常见问题解答 {#section_C8E068512A93458D8C006760B1C0B6A2}

**活动已经进行几天了。为何所有的置信度值仍显示为 0%？**

所有活动在报表的“[!UICONTROL 置信度]”列显示 0% 的原因如下：

* 手动 A/B 测试和自动分配使用不同的统计数据来显示置信度值。

   手动 A/B 测试使用的是基于 [Student t 检验](https://en.wikipedia.org/wiki/Student%27s_t-test)的 p 值。P 值是指在体验与控制体验之间找到观察到的差异（或更极端的差异）的概率（但实际上根本不存在这样的差异）。这些 P 值只能用于确定在给定体验与控制体验相同的情况下，观察到的数据是否一致。这些值不能用于确定体验是否与其他体验（非控制体验）存在差异。

   自动分配显示的是某个特定体验是所有活动体验中的入选者的真实性概率。这意味着只有入选体验（最有可能入选的体验）的置信度值将为非零数值。所有其他体验很有可能落选，因此将显示 0% 的置信度值。

* 仅当入选体验达到 60% 的置信度后，自动分配才会开始显示置信度。这些置信度级别通常出现在正常A/B测试完成所需时间的一半左右（尽管这并不保证）。 To determine how long a normal A/B test would run, please use a [sample size calculator](https://docs.adobe.com/content/target-microsite/testcalculator.html): plug control's conversion-rate in "Baseline conversion rate," "5%" for "Lift," and 95% for "Confidence." 通常情况下，在每个体验达到其所需样本量的至少 50% 之后，置信度便会开始显示。这可使您了解置信度将从何时开始显示。
* 如果报表中所有置信度值均显示为 0%，则有可能是进入活动的时间过早。

