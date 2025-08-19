---
keywords: 自动流量分配；定位；递增计数并保持用户处于活动中；流量分配；自动分配
description: 了解如何在[!UICONTROL Auto-Allocate]中使用 [!DNL Adobe Target] 活动，该活动在两个或更多体验中标识入选者，并自动为入选者重新分配更多流量。
title: 什么是[!UICONTROL Auto-Allocate]活动？
feature: Auto-Allocate
exl-id: 2d1ddd71-2ca6-4f00-9d0c-eb25ede8fdb8
source-git-commit: 1b1b2271738d12f8da4e695900b70e280f50d8cf
workflow-type: tm+mt
source-wordcount: '3502'
ht-degree: 35%

---

# [!UICONTROL Auto-Allocate] 概述

[!UICONTROL Auto-Allocate]中的[!DNL Adobe Target]活动在两个或更多体验中标识一个入选者，并在测试继续运行和学习期间，自动为入选者重新分配更多流量以提高转化。

使用三步引导式工作流[创建A/B活动](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)时，请在&#x200B;**[!UICONTROL Auto-Allocate to best experience]**&#x200B;页面上选择&#x200B;**[!UICONTROL Targeting]**&#x200B;选项（步骤2）。

## 挑战 {#section_85D5A03637204BACA75E19646162ACFF}

标准 A/B 测试具有一定的固有成本。您必须花费流量来衡量每个体验的性能，并通过分析找出入选体验。即使在您认识到某些体验的性能优于其他体验之后，流量分配仍保持不变。此外，要算出样本量也很复杂，并且活动必须运行其整个过程，然后才能对入选者执行操作。而且，确定的赢家仍然有可能不是真正的赢家。

## 解决方案： [!UICONTROL Auto-Allocate] {#section_98388996F0584E15BF3A99C57EEB7629}

[!UICONTROL Auto-Allocate]活动可降低确定入选体验的成本和开销。 [!UICONTROL Auto-Allocate]监视所有体验的目标量度性能，并按比例将更多新参加者发送到高性能体验。 同时，也会保留足够的流量来探索其他体验。即使活动仍在运行，您也可以看到该测试对结果带来的好处：优化与学习并行进行。

[!UICONTROL Auto-Allocate]将访客逐步推向入选体验，而不是要求您等到活动结束才能确定入选者。 您可以更快地从提升度中受益，因为原本将被发送到不太成功的体验的活动参加者现在会看到潜在的入选体验。

[!DNL Target]中的正常A/B测试只显示挑战者与对照的配对比较。 例如，如果活动具有体验：A、B、C和D，其中A是对照组，则常规的[!DNL Target] A/B测试会比较A与B、A与C以及A与D。

在此类测试中，包括[!DNL Target]在内的大多数产品都使用[Welch的t检验](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank}来生成基于p值的置信度。 然后，使用该置信度值来确定挑战体验与控制体验之间是否存在足够的差异。但是，[!DNL Target]不会自动执行查找“最佳”体验所需的隐式比较（B与C、B与D、C与D）。 因此，营销人员必须手动分析结果来确定“最佳”体验。

[!UICONTROL Auto-Allocate]跨体验执行所有隐式比较并生成“真”入选者。 测试中没有“控制”体验的概念。

[!UICONTROL Auto-Allocate]智能地为新访客分配体验，直到最佳体验的置信区间与任何其他体验的置信区间不重叠。 通常此过程可能会产生误报，但[!UICONTROL Auto-Allocate]使用基于[Bernstein不等式](https://en.wikipedia.org/wiki/Bernstein_inequalities_%28probability_theory%29){target=_blank}的置信区间来补偿重复评估。 此时，就会有真正的赢家。 当[!UICONTROL Auto-Allocate]停止时，如果访问页面的访客不存在实质性时间依赖关系，则至少有95%的可能性是[!UICONTROL Auto-Allocate]返回其真实响应不比入选体验的真实响应差1%（相对）的体验。

## 何时使用[!UICONTROL Auto-Allocate]而非[!UICONTROL A/B Test]或[!UICONTROL Automated Personalization]活动 {#section_3F73B0818A634E4AAAA60A37B502BFF9}

* 当您想要从头开始优化活动并尽快确定入选体验时，请使用&#x200B;**[!UICONTROL Auto-Allocate]**。 通过更频繁地提供高性能体验，可以提高整体活动性能。
* 当您想要在优化网站之前表征所有体验的性能时，请使用标准&#x200B;**[A/B测试](/help/main/c-activities/t-test-ab/test-ab.md#task_05E33EB15C4D4459B5EAFF90A94A7977)**。 A/B测试有助于您对所有体验进行排名，而[!UICONTROL Auto-Allocate]可以找到表现最好的体验，但无法保证区分表现较差的体验。
* 如果您希望使用最复杂的优化算法，例如根据个人配置文件属性构建预测的机器学习模型，请使用[Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9)。 [!UICONTROL Auto-Allocate]查看体验的总体行为（与标准A/B测试类似），并且不区分访客。

## [!UICONTROL Auto-Allocate]的主要优势 {#section_0913BF06F73C4794862561388BBDDFF0}

* 保持 A/B 测试的严格性
* 与手动 A/B 测试相比，能够更快地找到统计上显著的成功活动
* 与手动 A/B 测试相比，能够实现更高的平均营销活动提升

## 术语 {#section_670F8785BA894745B43B6D4BFF953188}

讨论[!UICONTROL Auto-Allocate]时，以下术语很有用：

**多臂老虎机：**&#x200B;[多臂老虎机](https://en.wikipedia.org/wiki/Multi-armed_bandit){target=_blank}优化方法可在探索性学习与对该学习的利用之间实现平衡。

## 算法的工作原理 {#section_ADB69A1C7352462D98849F2918D4FF7B}

[!UICONTROL Auto-Allocate]之后的整体逻辑包含累积数据的测量性能（如转化率）和置信区间。 与流量在体验之间平均分配的标准A/B测试不同，[!UICONTROL Auto-Allocate]会更改跨体验的流量分配。

* 80% 的访客会使用下面所述的智能逻辑进行分配。
* 20%的访客被随机分配到所有体验，以适应不断变化的访客行为。

多臂老虎机方法会留出一些体验以供探索，同时又会利用性能良好的体验。更多的新访客会被分配到性能较好的体验，同时又保持能够对不断变化的情况做出反应。这些模型每小时至少更新一次，以确保模型可对最新数据做出反应。

随着越来越多的访客进入活动，有些体验开始变得较为成功，并且更多的流量也会被发送到成功的体验。系统会继续随机提供 20% 的流量以探索所有体验。如果某个性能较差的体验性能开始提升，则会增加为该体验分配的流量。或者，如果高性能活动的成功率下降，则会减少为该体验分配的流量。例如，如果某个事件使访客在您的媒体网站上查找不同的信息，或者您的零售网站上的周末销售产生了不同的结果。

下图显示了算法在具有四种体验（单击展开图）的测试过程中可能表现出的性能：

![自动分配图像](assets/auto-allocate.png){width="600" zoomable="yes"}

该图显示了在确定明确的入选者之前，分配给每个体验的流量在活动生命周期的几个轮次中是如何变化的。

| 轮次 | 描述 |
|--- |--- |
| ![预热轮](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-0.png){width="200" zoomable="yes"} | **预热轮 (0)**：在预热轮期间，每个体验均会分配同等的流量，直到活动中的每个体验都至少具有 1,000 位访客和 50 次转化为止。<ul><li>体验 A=25%</li><li>体验 B=25%</li><li>体验 C=25%</li><li>体验 D=25%</li></ul>每个体验获得1,000位访客和50次转化后，[!DNL Target]将开始自动流量分配。 在这些轮次中会进行所有分配，且每轮会选取两个体验。<br>只有两个体验进入下一轮： D和C。<br>进入下一轮意味着这两个体验平均分配了80%的流量。 另外两个体验会继续参与，但只有在新访客进入活动时，才会提供这两个体验，以用于随机分配20%的流量。<br>所有分配每小时更新一次（如上面 x 轴的轮次所示）。每轮结束后，会比较累计数据。 |
| ![第 1 轮](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-1.png){width="200" zoomable="yes"} | **第 1 轮**：在本轮中，80% 的流量会分配给体验 C 和 D（各 40%）。20% 的流量会随机分配给体验 A、B、C 和 D（各 5%）。在本轮中，体验 A 展现良好性能。<ul><li>算法挑选出体验D进入下一轮，因为它具有最高的转化率（由每个活动的垂直比例尺表示）。</li><li>算法还挑选出体验 A 进入下一轮，因为在其余三个体验中，它具有最高的 Bernstein 95% 置信区间上限。</li></ul>体验 D 和 A 进入下一轮。 |
| ![第 2 轮](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-2.png){width="200" zoomable="yes"} | **第 2 轮**：在本轮中，80% 的流量会分配给体验 A 和 D（各 40%）。20% 的流量会随机分配，也就意味着 A、B、C 和 D 各获得 5% 的流量。在本轮中，体验 B 展现良好性能。<ul><li>算法挑选出体验D进入下一轮，因为它具有最高的转化率（由每个活动的垂直比例尺表示）。</li><li>算法还挑选出体验 B 进入下一轮，因为在其余三个体验中，它具有最高的 Bernstein 95% 置信区间上限。</li></ul>体验 D 和 B 进入下一轮。 |
| ![第 3 轮](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-3.png){width="200" zoomable="yes"} | **第 3 轮**：在本轮中，80% 的流量会分配给体验 B 和 D（各 40%）。20% 的流量会随机分配，也就意味着 A、B、C 和 D 各获得 5% 的流量。在本轮中，体验 D 继续展现良好性能，体验 C 的性能也不错。<ul><li>算法挑选出体验D进入下一轮，因为它具有最高的转化率（由每个活动的垂直比例尺表示）。</li><li>算法还挑选出体验 C 进入下一轮，因为在其余三个体验中，它具有最高的 Bernstein 95% 置信区间上限。</li></ul>体验 D 和 C 进入下一轮。 |
| ![第 4 轮](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-4.png){width="200" zoomable="yes"} | **第 4 轮**：在本轮中，80% 的流量会分配给体验 C 和 D（各 40%）。20% 的流量会随机分配，也就意味着 A、B、C 和 D 各获得 5% 的流量。在本轮中，体验 C 展现良好性能。<ul><li>算法挑选出体验C进入下一轮，因为它具有最高的转化率（由每个活动的垂直比例尺表示）。</li><li>算法还挑选出体验 D 进入下一轮，因为在其余三个体验中，它具有最高的 Bernstein 95% 置信区间上限。</li></ul>体验 C 和 D 进入下一轮。 |
| ![第 n 轮](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-n.png){width="200" zoomable="yes"} | **第&#x200B;*n***轮：随着活动继续运行，高性能体验开始显现，并且此过程会一直持续到确定入选体验为止。 如果具有最高转化率的体验的置信区间与任何其他体验的置信区间不重叠，则会将其标记为入选者。 [徽章显示在入选活动的页面](/help/main/c-activities/automated-traffic-allocation/determine-winner.md)和[!UICONTROL Activity]列表中。<ul><li>算法挑选出体验 C 作为明确的入选者。</li></ul>此时，算法会将 80% 的流量分配给体验 C，而将 20% 的流量继续随机分配给所有体验（A、B、C 和 D）。体验 C 总共获得 85% 的流量。如果入选者的置信区间再次开始重叠（这种情况不太可能出现），算法会重新执行上述第 4 轮的行为。<P>**重要信息**：如果您在此过程中提早手动选择入选者，则将容易选择错误的体验。 因此，最好的做法是一直等到算法确定入选体验为止。 |

>[!NOTE]
>
>如果某个活动只有两个体验，则两个体验会获得相等的流量，直到[!DNL Target]找到具有75%置信度的入选体验。 到那时，三分之二的流量会分配给入选者，三分之一分配给失败者。 之后，当体验达到95%的置信度时，90%的流量会分配给入选者，10%的流量会分配给失败者。 [!DNL Target]始终向“丢失”体验发送一些流量，以避免最终出现误报（即，继续进行一些探索）。

激活[!UICONTROL Auto-Allocate]活动后，不允许从Target UI中进行以下操作：

* 将“流量分配”模式切换为“手动”
* 更改目标量度类型
* 更改“[!UICONTROL Advanced Settings]”面板中的选项

## 了解自动分配的工作方式

有关详细信息，请参阅[自动分配比手动测试产生测试结果更快和收入更高](/help/main/c-activities/automated-traffic-allocation/faster-results-higher-revenue.md)。

## 注意事项 {#section_5C83F89F85C14FD181930AA420435E1D}

在使用[!UICONTROL Auto-Allocate]时请考虑以下信息：

### [!UICONTROL Auto-Allocate]功能仅对一个高级量度设置起作用： [!UICONTROL Increment Count and Keep User in Activity]

不支持以下高级量度设置： [!UICONTROL Increment Count]、[!UICONTROL Release User]、[!UICONTROL Allow Reentry and Increment Count]和[!UICONTROL Release User and Bar from Reentry]。

### 频繁回访的旧访客可能会夸大体验转化率。

如果查看体验 A 的访客经常回访并进行多次转化，则体验 A 的转化率 (CR) 会被人为地提高。将此结果与体验B进行比较，体验B中的访客发生转化，但不经常回访。 因此，体验A的CR看起来比体验B的CR更好，因此新访客更有可能分配到A而不是B。如果选择对每个参加者计数一次，则A的CR与B的CR可能相同。

如果旧访客是随机分配的，他们对转化率的影响更可能趋于均匀化。要减轻这种影响，可考虑将目标量度的计数方法更改为每位参加者仅计数一次。

### 区分表现好的人，而不是表现差的人。

[!UICONTROL Auto-Allocate]擅长区分表现优异的体验（和查找入选者）。 可能有些时候，您并没有充分区分性能较差的体验。

如果要在所有体验之间产生统计上的显着差异，您可能需要考虑使用手动流量分配模式。

### 时间相关（或上下文不同）的转化率可能会导致分配数量存在偏差。

在标准A/B测试中因同等影响所有体验而可忽略的某些因素在[!UICONTROL Auto-Allocate]活动中无法忽略。 该算法对观察到的转换率非常敏感。

下面列举了一些对体验性能产生不均等影响的因素：

* 具有不同情境（时间、位置、性别等）相关性的体验。

  例如：

   * “感谢上帝，今天是星期五”导致周五的转化率上升。
   * “Jump-start your Monday”周一的转化率更高。
   * “Gear up for a East-coast winter”（为东海岸的冬季做好准备）在东海岸或受冬季影响的地点提供了更高的转化率。

  使用具有不同上下文相关性的体验可能会使[!UICONTROL Auto-Allocate]测试中的结果比A/B测试中的结果产生更大的偏差，因为A/B测试对结果的分析会持续较长时间。

* 可能由于信息的紧迫性而导致转化发生不同延迟的体验。

  例如，“七折促销今天截止”表示访客今天要进行转化，但“首次购买五折优惠”并不会产生这种紧迫感。

## 常见问题解答 {#section_0E72C1D72DE74F589F965D4B1763E5C3}

在使用[!UICONTROL Auto-Allocate]活动时查询以下常见问题和答案：

### [!UICONTROL Analytics for Target] (A4T)是否支持[!UICONTROL Auto-Allocate]活动？

是. 有关详细信息，请参阅自动分配和自动定位活动支持[A4T](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)。

### 是否会自动将旧访客重新分配给高性能体验？

否. 只会自动分配新访客。为了保护A/B测试的有效性，旧访客将继续看到其原始体验。

### 算法如何处理误报？

如果您一直等到入选标记显示，则算法可保证 95% 的置信度或 5% 的误报率。

### [!UICONTROL Auto-Allocate]何时开始分配流量？

活动中的所有体验都至少具有 1,000 位访客和 50 次转化后，算法才开始工作。

### 算法的利用程度如何？

使用[!UICONTROL Auto-Allocate]提供80%的流量，随机提供20%的流量。 确定入选者后，80%的流量会流向该入选者，而所有体验仍会在该20%的流量中获取一些流量，包括入选体验。

### 是否会显示落选体验？

是. 多臂老虎机方法可确保至少保留 20% 的流量用于在所有体验中探索不断变化的模式或转化率。

### 如果活动的转化延迟时间较长，会出现什么情况？

只要所有要优化的体验都面临类似的延迟，其行为就与转化周期较快的活动相同。 但是，在流量分配过程开始之前，达到50次转化阈值需要更长的时间。

### [!UICONTROL Auto-Allocate]与[!UICONTROL Automated Personalization]有何不同？

[!UICONTROL Automated Personalization]使用每位访客的配置文件属性来确定最佳体验。 这样做不仅可以优化活动，还可以为该用户提供个性化活动。

另一方面，[!UICONTROL Auto-Allocate]是一个A/B测试，它将生成一个汇总入选者（最受欢迎的体验，但不一定是每个访客最有效的体验）。

### 旧访客是否会夸大成功量度的转化率？

目前，逻辑倾向于快速转化或访问更频繁的访客，因为此类访客会暂时夸大其所属体验的整体转化率。 算法会不断自行调整，因此每次生成快照时转化率的提高程度都会被放大。如果网站获得大量回访访客，则这些访客的转化可能会导致其所属体验的整体转化率虚增。 旧访客很有可能会随机分配，在这种情况下，总体影响（增加的提升）会趋于均匀化。要减轻这种影响，可考虑将成功量度的计数方法更改为每位参加者仅计数一次。

### 使用[!UICONTROL Auto-Allocate]时，我能否使用样本量计算器来估算活动确定入选者所需的时间？

您可以使用现有的[!DNL Adobe Target] [样本量计算器](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)来估计测试运行的时长。 （与传统A/B测试一样，如果您测试多个选件或多个转化量度/假设验证，请应用Bonferroni校正。） 该计算器专为传统的定界A/B测试而设计，仅提供估计值。 为[!UICONTROL Auto-Allocate]活动使用计算器是可选的，因为[!UICONTROL Auto-Allocate]为您声明了一个入选者。 您不需要挑选固定的时间点来查看测试结果。 提供的值在统计上始终有效。

内部[!DNL Adobe]试验发现以下内容：

* 当仅测试两个体验时，当体验之间的性能差异较大时，[!UICONTROL Auto-Allocate]比固定时间范围测试（即样本量计算器建议的时间范围）更快地找到入选者。 但是，当体验之间的性能差异很小时，[!UICONTROL Auto-Allocate]可能需要额外的时间来识别入选者。 在这些情况下，固定时程测试通常会在没有统计上显着结果的情况下结束。
* 当测试两个以上的体验时，如果单个体验的效果远远超过所有其他体验，[!UICONTROL Auto-Allocate]会比固定水平线测试（即样本量计算器建议的时间范围）更快地找到入选者。 当两个或更多体验都“入选”其他体验，但彼此紧密匹配时，[!UICONTROL Auto-Allocate]可能需要额外时间来确定哪个体验更优秀。 在这些情况下，固定范围测试通常会得出结论认为“入选”体验优于表现较差的体验，但未确定哪个体验更优秀。

### 我是否应该从[!UICONTROL Auto-Allocate]活动中移除性能不佳的体验，以加快确定入选者的过程？

确实没有必要删除性能不佳的体验。 [!UICONTROL Auto-Allocate]会自动更频繁地提供高性能的体验，而不太频繁地提供性能不佳的体验。 在活动中保留性能不佳的体验不会显着影响确定入选者的速度。

20% 的访客将被随机分配给所有体验。提供给性能不佳体验的流量很少（20%除以体验数量）。

### 能否在[!UICONTROL Auto-Allocate]活动中途更改目标指标？ {#change-metric}

[!DNL Adobe]不建议您在活动中途更改目标指标。 虽然可在活动期间使用 [!DNL Target] UI 更改目标指标，但总是应开始新的活动。[!DNL Adobe]无法保证您在活动运行后更改其中的目标量度会发生什么情况。

此推荐适用于使用[!UICONTROL Auto-Allocate]或[!UICONTROL Auto-Target] (A4T)作为报表源的[!UICONTROL Automated Personalization]、[!DNL Target]和[!DNL Analytics]活动。

### 能否在[!UICONTROL Auto-Allocate]活动中途更改报表源？ {#change-reporting}

[!DNL Adobe]不建议您在活动中途更改报表源。 虽然在使用[!DNL Target] UI的活动期间可能会将报表源（从[!DNL Target]更改为A4T或反之）更改，但您应始终开始一个新活动。 [!DNL Adobe]无法保证在运行活动后更改活动中的报表源时会发生什么情况。

此推荐适用于使用[!UICONTROL Auto-Allocate]或[!UICONTROL Auto-Target] (A4T)作为报表源的[!UICONTROL Automated Personalization]、[!DNL Target]和[!DNL Analytics]活动。

### 运行[!UICONTROL Reset Report Data]活动时能否使用[!UICONTROL Auto-Allocate]选项？

建议不要对[!UICONTROL Reset Report Data]活动使用[!UICONTROL Auto-Allocate]选项。 虽然它删除可见的报表数据，但此选项并不从[!UICONTROL Auto-Allocate]模型中删除所有训练记录。 不要对[!UICONTROL Reset Report Data]活动使用[!UICONTROL Auto-Allocate]选项，请创建新活动并停用原始活动。 （本指导还适用于[!UICONTROL Auto-Target]和[!UICONTROL Automated Personalization]活动。）

### [!UICONTROL Auto-Allocate]如何构建环境相关模型？

[!UICONTROL Auto-Allocate]仅基于默认环境中记录的流量和转化行为构建模型。 默认情况下，[!UICONTROL Production]是默认环境，但可以在[!DNL Target]中更改默认环境（[管理>环境](/help/main/administrating-target/environments.md)）。

如果点击发生在其他（非默认）环境中，则根据默认环境中观察到的转化行为来分配流量。 该点击的结果（转化或非转化）会进行记录以用于报表目的，但在[!UICONTROL Auto-Allocate]模型中不会考虑这些结果。

选择其他环境时，报表会显示该环境的流量和转化率。 报表的默认选定环境是选定的帐户范围的默认环境。 无法为每个活动设置默认环境。

### [!UICONTROL Auto-Allocate]活动能否在测试过程中调整回看窗口以考虑随时间变化趋势？

例如，活动是否可以考虑12月份来决定如何分配流量，而不是查看9月份的访客数据（测试开始的时间）？

否，[!UICONTROL Auto-Allocate]考虑整个活动的性能。

### 如果获胜体验与访客在获得活动资格时看到的不同，[!UICONTROL Auto-Allocate]是否向回访访客显示获胜体验？

[!UICONTROL Auto-Allocate]使用粘性决策的原因与[!UICONTROL A/B Test]活动具有粘性相同。 流量分配仅适用于新访客。

## 培训视频 {#section_893E5B36DC4A415C9B1D287F51FCCB83}

以下视频包含有关本文中所讨论概念的详细信息。

### 活动工作流 — 定位(2:14) ![教程徽章](/help/main/assets/tutorial.png)

以下视频包含有关设置流量分配的信息。

* 为活动分配受众
* 增加或减少流量
* 选择流量分配方法
* 在不同的体验之间分配流量

>[!VIDEO](https://video.tv.adobe.com/v/17385)

### 创建A/B测试(8:36) ![教程徽章](/help/main/assets/tutorial.png)

以下视频演示了如何使用 Target 三步引导式工作流创建 A/B 测试。从4[!UICONTROL Auto-Allocate]开始讨论:45。

* 在[!DNL Adobe Target]中创建A/B活动
* 使用手动拆分或自动流量分配来分配流量

>[!VIDEO](https://video.tv.adobe.com/v/17391)
