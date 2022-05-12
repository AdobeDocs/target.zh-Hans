---
keywords: 随机林；决策树；AP;Automated Personalization
description: 了解如何Adobe [!DNL Target] 在Automated Personalization(AP)和自动定位活动中均使用随机林算法。
title: 操作方法 [!DNL Target] 是否使用随机林算法？
feature: Automated Personalization
exl-id: 07a89525-4071-4434-ac96-c59a4f4422ad
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1417'
ht-degree: 95%

---

# ![PREMIUM](/help/main/assets/premium.png) 随机林算法

Target 在自动个性化和自动定位中使用的主要个性化算法是随机林算法。相较于从任何组成学习算法获得的性能而言，诸如随机林之类的组合方法可使用多种学习算法获得更好的预测性能。自动个性化中的随机林算法是一种分类或回归分析方法，该方法通过在训练时构建大量的决策树来执行运算。

提到统计数据时，您可能会想到使用单个回归分析模型来预测结果。最新的数据科学研究显示，与基于单个模型进行预测相比较，“组合方法”（基于同一数据集创建多个模型，然后对这些模型进行智能合并）可产生更好的结果。

随机林算法是自动个性化和自动定位活动中使用的关键基础个性化算法。随机林可将数百个决策树合并到一起，以便得出比单独使用一个决策树更好的预测结果。

## 什么是决策树？ {#section_7F5865D8064447F4856FED426243FDAC}

决策树的目标是划分系统可学习的所有可用访问数据，然后对这些数据进行分组，其中每个组内的访问相互之间在目标量度方面尽可能相似。但是，各组之间的访问在目标量度（如转化率）方面尽可能不同。决策树着眼于它在训练集中拥有的不同变量，来确定如何通过“相互独立、完全穷尽”(Mutually-Exclusive-Collectively-Exhaustive, MECE) 方式将数据拆分到这些组（或“叶子”）中，从而最大化此目标。

举个简单的例子，假设我们有两个输入变量：

* 性别（具有两个可能的值：男性或女性）
* 邮政编码（在我们的小数据集中具有五个可能的值：11111、22222、33333、44444 或 55555）

如果我们的目标量度是转化，那么决策树会首先确定我们两个变量中的哪个变量可以解释访问数据转化率中的最大变化量。

假设邮政编码最具预测性。这样此变量就构成了决策树的第一个“分支”。接着，决策树会确定如何拆分访问数据，如每个拆分中的记录转化率尽可能相似，各拆分之间的转化率尽可能不同。在我们的示例中，我们将假定 11111、22222、33333 属于第一个拆分，44444 和 55555 属于第二个拆分。

此操作会产生我们决策树的第一层：

![](assets/decsion_tree_1.png)

决策树会询问“哪个变量最具预测性？”。在我们的示例中，只有两个变量，因此答案显然是性别。决策树现在将完成类似的操作来拆分“每个分支中”**&#x200B;的数据。我们首先考虑 11111、22222 和 33333 分支。在这些邮政编码中，如果男性与女性之间的转化存在差异，则形成两个叶子（男性和女性），此分支完成。在另一个分支（44444 和 55555）中，我们假定男性与女性的转化方式之间不存在任何统计差异。在这种情况下，第一个分支变为最后一个拆分。

我们的示例会生成以下树：

![](assets/decsion_tree_2.png)

## 随机林如何使用决策树？ {#section_536C105EF9F540C096D60450CAC6F627}

决策树可堪称是强大的统计工具。但是，它们也存在一些缺陷。最为关键的是，它们可能会“过度拟合”数据，因此单个树不能很好地预测在构建初始决策树时未用到的将来数据。这一难题在统计学习中被称为[偏差-方差权衡](https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff)。随机林可帮助克服这一过度拟合难题。在最高层次上，随机林就是决策树的一个集合，这些决策树基于同一个数据集构建但又略有不同，它们一起“投票”来产生一个比单个树更好的模型。这些决策树通过以下方式来构建：通过替换法（称为套袋法）随机选择访问记录的子集，并且还随机选择属性的子集，以使随机林包含略有不同的决策树。这种方法可为随机林中创建的决策树引入一些小的差异。通过加入这些数量可控的差异，可帮助提高算法的预测准确性。

## Target的个性化算法如何使用随机林？ {#section_32FB53CAD8DF40FB9C0F1217FBDBB691}

**如何构建模型**

下图总结了如何为自动定位或自动个性化活动构建模型：

![](assets/random_forest_flow.png)

1. Target 在随机提供体验/选件的同时收集有关访客的数据
1. Target 在达到临界数据量时执行功能工程化
1. Target 为每个体验/选件构建随机林模型
1. Target 检查模型是否达到质量分数阈值
1. Target 将模型投入生产以个性化将来的流量

Target 使用它自动收集的数据以及您提供的自定义数据来构建其个性化算法。这些模型可预测要向访客显示的最佳体验或选件。通常，可为每个体验（自动定位活动）或每个选件（自动个性化活动）构建一个模型。然后，Target 会选择显示可产生最高预测成功量度（例如转化率）的体验或选件。这些模型在用于进行预测之前，必须针对随机提供的访问进行训练。因此，在活动最初开始时，甚至会向个性化组内的访客随机显示不同的体验或选件，这种情况会一直持续到个性化算法准备就绪为止。

每个模型在用于活动之前，必须先进行验证，以确保它能够很好地预测访客的行为。模型将基于 AUC（曲线下面积）进行验证。由于需要进行验证，因此模型将开始提供个性化体验的确切时间取决于数据的详细信息。实际上，出于流量规划目的，在每个模型生效之前，模型所使用的转化次数通常远高于最小转化次数。

当模型开始对体验或选件生效时，体验/选件名称左侧的时钟图标会变为绿色复选框。当至少有两个体验/选件存在有效模型时，就开始对某些访问进行个性化。

**特性转换**

在数据遍历个性化算法之前，需要进行特性转换，可将此过程视为准备训练记录中收集的数据以供个性化模型使用。

特性转换取决于属性的类型。主要有两种类型的属性（数据科学家有时称之为“特性”）：

* **类别：**&#x200B;类别特性无法计数，但可以划分为不同的组。类别特性包括国家/地区、性别或邮政编码。
* **数字：**&#x200B;数字特性可以测量或计数，如年龄、收入等。

对于类别特性，会保留所有可能的特性集，可使用概率转换来减小数据量。对于数字特性，可通过校正来确保这些特性都具有普遍可比性。

**使用多臂老虎机平衡学习与个性化**

在 Target 构建了可个性化流量的个性化模型之后，对于将来的活动访客，您需要做出明确的权衡：应当基于当前模型个性化所有流量，还是应当继续向新访客提供随机选件以向他们学习？您需要确保个性化算法在个性化大部分流量的同时，不断学习访客的新趋势。

Target 可通过多臂老虎机来帮助您实现这一目标。多臂老虎机可确保模型经常“消耗”一小部分流量，以便在整个活动学习的生命周期内不断学习，同时防止过度利用先前已学习过的趋势。

在数据科学领域，多臂老虎机 (MAB) 问题是探索与利用困境的一个典型示例，这里可以将多臂老虎机视为一个单臂老虎机的集合，而且每个老虎机都具有未知的奖赏概率。关键思想是制定一种策略，得出按下哪个摇臂可获得最高成功概率，从而获得最大化的奖赏总额。系统在构建在线模型后进行在线评分时会使用多臂老虎机。这有助于在探索过程中进行在线学习。当前的多臂算法是 ε 贪婪算法。在此算法中，使用概率 1 - ε 来选择最佳摇臂。使用概率 ε 随机选择任何其他摇臂。