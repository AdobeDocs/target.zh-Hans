---
keywords: 自动流量分配；定位；递增计数并保持用户处于活动中；流量分配；自动分配；自动分配
description: 了解如何在Adobe中使用自动分配活动 [!DNL Target] 可在两个或更多体验中标识入选者，并自动为入选者重新分配更多流量。
title: 什么是自动分配活动？
feature: Auto-Allocate
exl-id: 2d1ddd71-2ca6-4f00-9d0c-eb25ede8fdb8
source-git-commit: 4564e0b95bbd19f20c75e5e83d452d12a5403083
workflow-type: tm+mt
source-wordcount: '3565'
ht-degree: 50%

---

# [!UICONTROL 自动分配] 概述

安 [!UICONTROL 自动分配] 活动 [!DNL Adobe Target] 在两个或更多体验中标识一个入选者，并在测试继续运行和学习期间自动为入选者重新分配更多流量以提高转化。

使用三步引导式工作流创建A/B活动时，您可以选择 [!UICONTROL 自动分配到最佳体验] 选项。

## 挑战 {#section_85D5A03637204BACA75E19646162ACFF}

标准 A/B 测试具有一定的固有成本。您必须花费流量来衡量每个体验的性能，并通过分析找出入选体验。即使在您认识到某些体验的性能优于其他体验之后，流量分配仍保持不变。此外，要算出样本量也很复杂，并且活动必须运行其整个过程，然后才能对入选者执行操作。而且，确定的入选者可能不是真正的入选者。

## 解决方案： [!UICONTROL 自动分配] {#section_98388996F0584E15BF3A99C57EEB7629}

[!UICONTROL 自动分配可降低确定入选体验的成本和开销。][!UICONTROL 自动分配会监控所有体验的目标量度性能，并按比例将更多新参加者发送到高性能体验。]同时，也会保留足够的流量来探索其他体验。即使活动仍在运行，您也可以看到该测试对结果带来的好处：优化与学习并行进行。

[!UICONTROL 自动分配会逐渐将访客移到入选体验，而无需您等到活动结束才确定入选者。]您可以更快地从提升度中受益，因为原本将被发送到不太成功的体验的活动参加者现在会看到潜在的入选体验。

中的常规A/B测试 [!DNL Target] 仅显示与控制对象的两两比较。 例如，如果活动包含体验：A、B、C和D，其中A是控制，正常 [!DNL Target] A/B测试将比较A与B、A与C、A与D。

在此类测试中，大多数产品，包括 [!DNL Target]，使用 [韦尔奇的T检验](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank}生成基于p值的置信度。 然后，使用该置信度值来确定挑战体验与控制体验之间是否存在足够的差异。但是， [!DNL Target] 不会自动执行查找“最佳”体验所需的隐式比较（B与C、B与D、C与D）。 因此，营销人员必须手动分析结果来确定“最佳”体验。

[!UICONTROL 自动分配可执行各体验之间的隐式比较并得出“真实”入选者。]测试中没有“控制”体验的概念。

[!UICONTROL 自动分配] 智能地为体验分配新访客，直到最佳体验的置信区间与任何其他体验的置信区间不重叠为止。 通常，此过程可能会产生误报，但 [!UICONTROL 自动分配] 使用基于 [Bernstein不等式](https://en.wikipedia.org/wiki/Bernstein_inequalities_%28probability_theory%29) 对重复评估的补偿。 目前，有一个真正的赢家。 When [!UICONTROL 自动分配] 停止，前提是访问页面的访客没有实质性的时间依赖关系，则至少有95%的可能性 [!UICONTROL 自动分配] 返回其真实响应不低于入选体验真实响应的1%（相对）的体验。

## 何时使用 [!UICONTROL 自动分配] 与A/B或 [!UICONTROL Automated Personalization] {#section_3F73B0818A634E4AAAA60A37B502BFF9}

* 如果您希望从一开始就优化活动并尽快确定入选体验，则使用&#x200B;**[!UICONTROL 自动分配]**。通过更频繁地提供高性能体验，可以提高整体活动性能。
* 如果您希望在优化网站之前鉴定所有体验的性能，则使用标准 **[A/B 测试](/help/main/c-activities/t-test-ab/test-ab.md#task_05E33EB15C4D4459B5EAFF90A94A7977)**。A/B测试可帮助您对所有体验进行排名，而 [!UICONTROL 自动分配] 查找表现最佳者，但无法保证表现较差者之间的差异。
* 使用 [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) 当您希望获得最高复杂度的优化算法时，例如机器学习模型，该模型可根据单个用户档案属性构建预测。 [!UICONTROL 自动分配] 查看体验的总行为（与标准A/B测试类似），并且不区分访客。

## 主要优势 {#section_0913BF06F73C4794862561388BBDDFF0}

* 保持 A/B 测试的严格性
* 与手动 A/B 测试相比，能够更快地找到统计上显著的成功活动
* 与手动 A/B 测试相比，能够实现更高的平均营销活动提升

## 术语 {#section_670F8785BA894745B43B6D4BFF953188}

在讨论 [!UICONTROL 自动分配]:

**多臂老虎机：**[多臂老虎机](https://en.wikipedia.org/wiki/Multi-armed_bandit)优化方法可在探索性学习与对该学习的利用之间实现平衡。

## 算法的工作原理 {#section_ADB69A1C7352462D98849F2918D4FF7B}

背后的总体逻辑 [!UICONTROL 自动分配] 综合了累积数据的测量性能（如转化率）和置信区间。 与在标准A/B测试中，流量在体验之间平均拆分不同， [!UICONTROL 自动分配] 更改了各体验之间的流量分配。

* 80% 的访客会使用下面所述的智能逻辑进行分配。
* 20% 的访客会在所有体验中随机分配，以适应不断变化的访客行为。

多臂老虎机方法会留出一些体验以供探索，同时又会利用性能良好的体验。更多的新访客会被分配到性能较好的体验，同时又保持能够对不断变化的情况做出反应。这些模型每小时至少更新一次，以确保模型可对最新数据做出反应。

随着越来越多的访客进入活动，有些体验开始变得较为成功，并且更多的流量也会被发送到成功的体验。系统会继续随机提供 20% 的流量以探索所有体验。如果某个性能较差的体验性能开始提升，则会增加为该体验分配的流量。或者，如果高性能活动的成功率下降，则会减少为该体验分配的流量。例如，如果某个事件使访客在您的媒体网站上查找不同的信息，或者您的零售网站上的周末销售产生了不同的结果。

下图显示了算法如何在包含四个体验的测试中执行运算：

![自动分配图像](assets/auto-allocate.png)

该图显示了在确定明确的入选者之前，分配给每个体验的流量在活动生命周期的几个轮次中是如何变化的。

| 轮次 | 描述 |
|--- |--- |
| ![预热轮](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-0.png) | **预热轮 (0)**：在预热轮期间，每个体验均会分配同等的流量，直到活动中的每个体验都至少具有 1,000 位访客和 50 次转化为止。<ul><li>体验 A=25%</li><li>体验 B=25%</li><li>体验 C=25%</li><li>体验 D=25%</li></ul>在每个体验获得 1,000 位访客和 50 次转化后，Target 会开始自动分配流量。在这些轮次中会进行所有分配，且每轮会选取两个体验。<br>只有两个体验进入下一轮：D和C。<br>向前移动意味着这两个体验均等地分配了80%的流量。其他两个体验将继续参与活动，但只有在新访客进入活动时，才会作为20%随机流量分配的一部分提供。<br>所有分配每小时更新一次（如上面 x 轴的轮次所示）。每轮结束后，会比较累计数据。 |
| ![第 1 轮](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-1.png) | **第 1 轮**：在本轮中，80% 的流量会分配给体验 C 和 D（各 40%）。20% 的流量会随机分配给体验 A、B、C 和 D（各 5%）。在本轮中，体验 A 展现良好性能。<ul><li>算法挑选出体验 D 进入下一轮，因为它具有最高的转化率（在每个活动的垂直比例尺上由 表示）。</li><li>算法还挑选出体验 A 进入下一轮，因为在其余三个体验中，它具有最高的 Bernstein 95% 置信区间上限。</li></ul>体验 D 和 A 进入下一轮。 |
| ![第 2 轮](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-2.png) | **第 2 轮**：在本轮中，80% 的流量会分配给体验 A 和 D（各 40%）。20% 的流量会随机分配，也就意味着 A、B、C 和 D 各获得 5% 的流量。在本轮中，体验 B 展现良好性能。<ul><li>算法挑选出体验 D 进入下一轮，因为它具有最高的转化率（在每个活动的垂直比例尺上由  表示）。</li><li>算法还挑选出体验 B 进入下一轮，因为在其余三个体验中，它具有最高的 Bernstein 95% 置信区间上限。</li></ul>体验 D 和 B 进入下一轮。 |
| ![第 3 轮](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-3.png) | **第 3 轮**：在本轮中，80% 的流量会分配给体验 B 和 D（各 40%）。20% 的流量会随机分配，也就意味着 A、B、C 和 D 各获得 5% 的流量。在本轮中，体验 D 继续展现良好性能，体验 C 的性能也不错。<ul><li>算法挑选出体验 D 进入下一轮，因为它具有最高的转化率（在每个活动的垂直比例尺上由  表示）。</li><li>算法还挑选出体验 C 进入下一轮，因为在其余三个体验中，它具有最高的 Bernstein 95% 置信区间上限。</li></ul>体验 D 和 C 进入下一轮。 |
| ![第 4 轮](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-4.png) | **第 4 轮**：在本轮中，80% 的流量会分配给体验 C 和 D（各 40%）。20% 的流量会随机分配，也就意味着 A、B、C 和 D 各获得 5% 的流量。在本轮中，体验 C 展现良好性能。<ul><li>算法挑选出体验 C 进入下一轮，因为它具有最高的转化率（在每个活动的垂直比例尺上由  表示）。</li><li>算法还挑选出体验 D 进入下一轮，因为在其余三个体验中，它具有最高的 Bernstein 95% 置信区间上限。</li></ul>体验 C 和 D 进入下一轮。 |
| ![第 n 轮](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-n.png) | **第 n** 轮：随着活动继续运行，高性能体验开始显现，并且此过程会一直持续到确定入选体验为止。如果具有最高转化率的体验的置信区间与任何其他体验的置信区间不重叠，则会将其标记为入选者。 A [标记会显示在入选活动的页面上](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) 和 [!UICONTROL 活动] 列表。<ul><li>算法挑选出体验 C 作为明确的入选者</li></ul>此时，算法会将 80% 的流量分配给体验 C，而将 20% 的流量继续随机分配给所有体验（A、B、C 和 D）。体验 C 总共获得 85% 的流量。如果入选者的置信区间再次开始重叠（这种情况不太可能出现），算法会重新执行上述第 4 轮的行为。<br>**重要信息**：如果您在该过程中提早手动选择入选者，则将容易选择错误的体验。因此，最好的做法是一直等到算法确定入选体验为止。 |

>[!NOTE]
>
>如果活动只有两个体验，则两个体验的流量会相等，直到 [!DNL Target] 找到具有75%置信度的入选体验。 此时，三分之二的流量会分配给入选者，三分之一的流量会分配给失败者。 之后，当体验达到95%的置信度时，90%的流量会分配给入选者，10%的流量会分配给失败者。 [!DNL Target] 始终维护一些被发送到“正在丢失”体验的流量，以避免最终出现误报（即维护一些探索）。

在 [!UICONTROL 自动分配] 活动时，不允许从UI中执行以下操作：

* 将“流量分配”模式切换为“手动”
* 更改目标量度类型
* 更改“高级设置”面板中的选项

## 了解自动分配的工作原理

有关更多信息，请参阅 [与手动测试相比，自动分配可以为您提供更快的测试结果和更高的收入](/help/main/c-activities/automated-traffic-allocation/faster-results-higher-revenue.md)

## 注意事项 {#section_5C83F89F85C14FD181930AA420435E1D}

**的 [!UICONTROL 自动分配] 功能仅适用于一个高级量度设置： [!UICONTROL 递增计数并保持用户处于活动中]**

不支持以下高级量度设置： [!UICONTROL 递增计数], [!UICONTROL 发行用户], [!UICONTROL 允许再次进入和递增计数]和 [!UICONTROL 释放用户和阻止再次进入].

**频繁回访的访客可能会夸大体验转化率。**

如果查看体验 A 的访客经常回访并进行多次转化，则体验 A 的转化率 (CR) 会被人为地提高。将此结果与体验B进行比较，在体验B中，访客进行转化，但不经常回访。 因此，体验A的CR看起来比体验B的CR好，因此新访客更有可能被分配到A而不是B。如果您选择为每个参加者计数一次，则A的CR和B的CR可能是相同的。

如果旧访客是随机分配的，他们对转化率的影响更可能趋于均匀化。要减轻这种影响，可考虑将目标量度的计数方法更改为每位参加者仅计数一次。

**区分性能较高的体验，而不区分性能较低的体验。**

[!UICONTROL 自动分配善于区分性能较高的体验（并找到入选者）。]可能有些时候，您并没有充分区分性能较差的体验。

如果要在所有体验之间产生具有统计意义的显着差异，则可能需要考虑使用手动流量分配模式。

**时间相关（或上下文不同）的转化率可能会导致分配数量存在偏差。**

在标准A/B测试期间可以忽略的一些因素，因为它们对所有体验的影响均等，因此在 [!UICONTROL 自动分配] 测试。 算法易受观察到的转化率的影响。下面列举了一些对体验性能产生不均等影响的因素：

* 具有不同情境（时间、位置、性别等）相关性的体验。

   例如：

   * “狂热星期五”导致周五具有更高的转化率
   * “美好一周从星期一开始”导致周一具有更高的转化率
   * 在东海岸或冬季受灾地区，“为东海岸的冬季做好准备”的转换率更高

使用具有不同上下文相关性的体验可能会使 [!UICONTROL 自动分配] 测试比A/B测试更多，因为A/B测试会在较长的时间段内分析结果。

* 可能由于信息的紧迫性而导致转化发生不同延迟的体验。

   例如，“七折促销今天截止”表示访客今天要进行转化，但“首次购买五折优惠”并不会产生这种紧迫感。

## 常见问题解答 {#section_0E72C1D72DE74F589F965D4B1763E5C3}

使用时，请参阅以下常见问题解答和答案 [!UICONTROL 自动分配] 活动：

### 是 [!UICONTROL Analytics for Target] (A4T)支持 [!UICONTROL 自动分配] 活动？

是. 有关更多信息，请参阅[自动分配和自动定位活动支持 A4T](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)。

### 是否会自动将旧访客重新分配给高性能体验？

否. 只会自动分配新访客。回访访客可继续查看其原始体验，以保护A/B测试的有效性。

### 算法如何处理误报？

如果您一直等到入选标记显示，则算法可保证 95% 的置信度或 5% 的误报率。

### 何时 [!UICONTROL 自动分配] 开始分配流量？

活动中的所有体验都至少具有 1,000 位访客和 50 次转化后，算法才开始工作。

### 算法的利用程度如何？

使用 [!UICONTROL 自动分配] 20%的流量是随机提供的。 在确定入选者后，80% 的流量全都会分配给该体验，而 20% 的流量将继续分配给所有体验（包括入选体验）。

### 是否会显示落选体验？

是. 多臂老虎机方法可确保至少保留 20% 的流量用于在所有体验中探索不断变化的模式或转化率。

### 如果活动的转化延迟时间较长，会出现什么情况？

只要所有要优化的体验都面临相似的延迟，其行为便会与具有更快转化周期的活动相同。 但是，在流量分配流程开始之前，达到50次转化阈值需要更长的时间。

### 如何 [!UICONTROL 自动分配] 不同 [!UICONTROL Automated Personalization]?

[!UICONTROL 自动个性化使用每位访客的配置文件属性来确定最佳体验。]这样做不仅可以优化活动，还可以为该用户提供个性化活动。

[!UICONTROL 自动分配]另一方面，是一种A/B测试，可生成一个总入选者（最受欢迎的体验，但不一定是每个访客最有效的体验）。

### 旧访客是否会夸大成功量度的转化率？

目前，逻辑支持快速转化或更频繁访问的访客，因为此类访客会暂时夸大其所属体验的整体转化率。 算法会不断自行调整，因此每次生成快照时转化率的提高程度都会被放大。如果网站获得大量回访访客，则他们的转化可能会夸大他们所属的体验的整体转化率。 旧访客很有可能会随机分配，在这种情况下，总体影响（增加的提升）会趋于均匀化。要减轻这种影响，可考虑将成功量度的计数方法更改为每位参加者仅计数一次。

### 使用 [!UICONTROL 自动分配] 要估计活动确定入选者所花费的时长？

您可以使用现有 [!DNL Adobe Target] [样本量计算器](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6) 以估算测试运行的时长。 （与传统A/B测试一样，如果您测试的选件超过两个或多个转化量度/假设，则应用Bonferroni校正。） 此计算器专为传统的固定水平A/B测试而设计，仅提供估算。 使用计算器 [!UICONTROL 自动分配] 活动是可选的，因为 [!UICONTROL 自动分配] 宣布入选者。 您无需选择固定的时间点来查看测试结果。 提供的值始终具有统计学上的有效性。

在我们的实验中，我们发现了以下内容：

* 在仅测试两个体验时， [!UICONTROL 自动分配] 当体验之间的性能差异较大时，比固定水平测试（即样本量计算器建议的时间范围）更快地找到入选者。 但是， [!UICONTROL 自动分配] 当体验之间的性能差异较小时，可能需要额外时间来确定入选者。 在这些情况下，固定水平测试通常会在没有统计意义显着结果的情况下结束。
* 在测试两个以上的体验时， [!UICONTROL 自动分配] 当单个体验的效果远远超出所有其他体验时，比固定水平测试（即样本量计算器建议的时间范围）更快地找到入选者。 当两个或两个以上的体验都“胜出”于其他体验，但彼此之间又紧密匹配时， [!UICONTROL 自动分配] 可能需要额外的时间来确定哪个更优秀。 在这些情况下，固定视野测试通常会通过以下结论结束： “入选”体验优于性能较低的体验，但没有确定哪个体验更优。

### 是否应从 [!UICONTROL 自动分配] 活动来加快确定入选者的过程？

确实没有理由删除性能不佳的体验。 [!UICONTROL 自动分配] 自动更频繁地提供高性能体验，而较少地提供性能不佳的体验。 在活动中保留性能不佳的体验不会显着影响确定入选者的速度。

20% 的访客将被随机分配给所有体验。向性能不佳的体验提供的流量很少（20%除以体验数量）。

### 我是否可以在 [!UICONTROL 自动分配] 活动？ {#change-metric}

[!DNL Adobe] 不建议您在活动中途更改目标量度。 虽然可在活动期间使用 [!DNL Target] UI 更改目标指标，但总是应开始新的活动。[!DNL Adobe] 无法保证在活动运行目标量度后更改该活动中的目标量度会发生什么情况。

此建议适用于使用 [!DNL Target] 或 [!DNL Analytics] (A4T) 作为报表源的[!UICONTROL 自动分配]、[!UICONTROL 自动定位]和[!UICONTROL 自动个性化]活动。

### 能否在[!UICONTROL 自动分配]活动期间更改报表源？ {#change-reporting}

[!DNL Adobe] 不建议您在活动中途更改报表源。 尽管可以更改报表源(从 [!DNL Target] （或反之） [!DNL Target] UI中，您应始终启动新活动。 [!DNL Adobe] 不保证在活动运行后更改活动中的报表源时会发生什么情况。

此建议适用于使用 [!DNL Target] 或 [!DNL Analytics] (A4T) 作为报表源的[!UICONTROL 自动分配]、[!UICONTROL 自动定位]和[!UICONTROL 自动个性化]活动。

### 我能否使用 [!UICONTROL 重置报表数据] 选项 [!UICONTROL 自动分配] 活动？

使用 [!UICONTROL 重置报表数据] 选项 [!UICONTROL 自动分配] 不建议使用活动。 尽管会删除可见的报表数据，但此选项不会从 [!UICONTROL 自动分配] 模型。 而不是使用 [!UICONTROL 重置报表数据] 选项 [!UICONTROL 自动分配] 活动时，创建新活动并取消激活原始活动。 (本指南也适用于 [!UICONTROL 自动定位] 和 [!UICONTROL Automated Personalization] 活动。)

### 如何 [!UICONTROL 自动分配] 是否构建与环境有关的模型？

[!UICONTROL 自动分配] 仅根据默认环境中记录的流量和转化行为构建模型。 默认情况下， [!UICONTROL 生产] 是默认环境，但默认环境可以在 [!DNL Target] [管理>环境](/help/main/administrating-target/environments.md).

如果点击发生在其他（非默认）环境中，则流量会根据默认环境中观察到的转化行为进行分配。 该点击的结果（转化或非转化）会为报告目的而记录，但不会在 [!UICONTROL 自动分配] 模型。

选择其他环境时，报表会显示该环境的流量和转化。 报表的默认选定环境是所选帐户范围的默认环境。 默认环境不能基于每个活动进行设置。

### [!UICONTROL 自动分配] 活动能否在测试过程中调整回看窗口，以考虑随时间变化的趋势？

例如，活动是否可以考虑12月份的月份来决定如何分配流量，而不是查看9月份的访客数据（测试开始时）？

不， [!UICONTROL 自动分配] 考虑整个活动的绩效。

### 如果获胜体验与访客在获得活动资格时看到的不同，那么 [!UICONTROL 自动分配] 是否向回访访客显示获胜体验？

[!UICONTROL 自动分配] 出于与 [!UICONTROL A/B测试] 活动具有粘滞性。 流量分配仅适用于新访客。

## 培训视频 {#section_893E5B36DC4A415C9B1D287F51FCCB83}

以下视频包含有关本文中所讨论概念的详细信息。

### 活动工作流 - 定位 (2:14) ![教程徽章](/help/main/assets/tutorial.png)

以下视频包含有关设置流量分配的信息。

* 为活动分配受众
* 增加或减少流量
* 选择流量分配方法
* 在不同的体验之间分配流量

>[!VIDEO](https://video.tv.adobe.com/v/17385)

### 创建A/B测试(8:36) ![教程徽章](/help/main/assets/tutorial.png)

以下视频演示了如何使用 Target 三步引导式工作流创建 A/B 测试。[!UICONTROL 自动分配] 对的讨论开始于4:45。

* 在中创建A/B活动 [!DNL Adobe Target]
* 使用手动拆分或自动流量分配来分配流量

>[!VIDEO](https://video.tv.adobe.com/v/17391)
