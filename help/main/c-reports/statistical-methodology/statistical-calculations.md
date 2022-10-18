---
keywords: 报表；统计方法；统计计算；统计数据；平均值；转化率；每位访客的收入；RPV；置信区间；提升度；Welch t测试；离线计算
description: 了解手动中使用的统计计算 [!UICONTROL A/B测试] 活动 [!DNL Adobe Target].
title: 如何了解 [!UICONTROL A/B测试] 活动？
feature: Reports
source-git-commit: 6857ba1a6410d3140a83a052efc50e9dd1776fd9
workflow-type: tm+mt
source-wordcount: '1091'
ht-degree: 5%

---

# A/Bn 测试中的统计计算

本文记录了A/Bn手动测试中使用的详细统计计算 [!DNL Adobe Target]. 定义已提供 [!UICONTROL 转化率], [!UICONTROL 转化率的置信区间], [!UICONTROL 提升度], [!UICONTROL 提升的置信区间]和 [!UICONTROL 置信度].

>[!NOTE]
>
>本文中的信息取代了&#x200B;*用于 A/B 测试的 Adobe Target 计算* pdf 文件，以前可在此站点上下载。

![显示 [!UICONTROL 转化率], [!UICONTROL 平均提升度和置信区间]和 [!UICONTROL 置信度] A/B测试活动。](/help/main/c-reports/statistical-methodology/img/target_report.png)

## 平均性能

下节介绍上图中使用的计算。

### 转化率和每位访客带来的收入(RPV)促销活动

下图显示了 [!UICONTROL 转化率], [!UICONTROL 转化率的置信区间]，以及 [!UICONTROL 转化] 在 [!DNL Target] 报表。 例如，第一行显示了体验A的以下内容：the [!UICONTROL 转化率] 为25.81%，带有 [!UICONTROL 置信区间] 记录了±7.7%和32次转化。 鉴于124位访客查看了体验，这等于32/124 = 25.81%。

<p style="text-align:center;"><img width="25%" src="img/conv_rate.png"></p>

转化率或 **均值**, *μ<sub>ν</sub>*，对应于每个体验 *ν* 在实验中，被定义为量度总和与分配给该量度的单位数之比， *N<sub>ν</sub>*:

<p style="text-align:center;"><img width="125px" src="img/mean_definition.png"></p>

这里，

* *Y<sub>iν</sub>* 是每个单位的量度值 *i*，则分配给给给定体验的访客 *ν*.

* 单位总和 *i* 取决于计数方法的选择。

   * 如果 *[!UICONTROL 访客]* 用作计数方法，则每个单位都是一个独特访客，在活动生命周期内定义为活动中的独特参与者。
   * 如果 *[!UICONTROL 访问次数]* 用作计数方法，则每个单位都是一个独特访问，定义为在 [!DNL Target] 会话(具有唯一 `sessionId`)。 当 `sessionId` 更改，或访客达到转化步骤，则计为一次新访问。
   * 如果 *[!UICONTROL 活动展示次数]* 用作计数方法，则每个单元都是一个唯一的展示，定义为每次访客加载活动的任何页面时。

## [!UICONTROL 平均置信区间]/[!UICONTROL 转化率]

转化率的置信区间被直观地定义为与基础数据一致的可能转化率范围。

运行实验时，给定体验的转化率是 *估计* “true”转化率的值。 为了量化这一估计的不确定性， [!DNL Target] 使用置信区间。 [!DNL Target] 始终报告95%的置信区间，这意味着最终，计算出的95%的置信区间包含体验的真实转化率。

转化率的95%置信区间 *μ<sub>ν</sub>* 定义为值范围：

<p style="text-align:center;"><img width="30%" src="img/confidence_interval.png"></p>

其中，平均值的标准错误定义为

<p style="text-align:center;"><img width="75px" src="img/se_conv_continuous.png"></p>

当使用样本标准偏差的无偏估计时：

<p style="text-align:center;"><img width="200px" src="img/stdev_definition.png"></p>

当促销活动为转化率促销活动（即，转化量度为二进制）时，标准错误会减小为：

<p style="text-align:center;"><img width="150px" src="img/se_conv.png"></p>

## 提升度

下图显示了 [!UICONTROL 提升度] 和 [!UICONTROL 提升的置信区间] 在 [!DNL Target] 报告。 数字表示提升度范围的平均值，箭头表示提升度是正值还是负值。 箭头以灰色显示，直到置信度超过95%为止。 置信度超过阈值后，箭头会根据正提升度或负提升度显示为绿色或红色。

<p style="text-align:center;"><img width="35%" src="img/lift.png"></p>

体验之间的提升度  *ν*，以及控制体验 *ν<sub>0</sub>* 是转化率中的相对“增量”，定义为

<p style="text-align:center;"><img width="15%" src="img/lift_definition.png"></p>

如上文所定义的个别兑换率。 更简单地说，

```
Lift(Experience N) = (Performance_Experience_N - Performance_Control)/ Performance_Control
```

如果控制体验的转化率 *ν<sub>0</sub>* 为0时，没有提升度。

## [!DNL Confidence Interval of Lift]

中的箱形图 [!UICONTROL 平均提升度和置信区间] 列表示平均值和95% [!UICONTROL 提升的置信区间]. 当给定非控制体验的置信区间与控制体验的置信区间存在重叠时，箱形图将呈灰色。 当给定体验的置信区间范围高于或低于控制体验的置信区间时，框图为绿色或红色。

体验之间提升度的标准错误  *ν*，以及控制体验  *ν<sub>0</sub>* 定义为：

<p style="text-align:center;"><img width="35%" src="img/se_lift.png" alt="量度均值"></p>

然后，提升度的95%置信区间为：

<p style="text-align:center;"><img width="40%" src="img/lift_CI.png"></p>

此计算使用“Delta”方法，并对其进行了说明 [在本文档中有更详细的内容](/help/main/assets/confidence_interval_lift.pdf)

## [!UICONTROL 置信度]

最后一列显示 [!DNL Target] 报表。 体验的置信度是指在假设空假设为真的情况下，获得比观察到的结果更不极端的结果的概率（以百分比表示）。 对于p值，显示的置信度为 *1 - p值*. 直观而言，较高的置信度意味着控制体验和非控制体验具有相同转化率的可能性较小。

在 [!DNL Target]，双尾 **韦尔奇的T检验** 在测试体验和控制体验之间执行，以测试测试和控制体验的方式是否相同。 因为在运行实验之前，我们通常不知道两组样本的大小和差异是否相同， [!DNL Target] 此外，我们还允许您拥有发送到每个体验的不同流量百分比，我们不假定每个体验的差异相等。 因此，选择韦尔奇的t型考试，而不是学生的t型考试。

为了进行Welch的t检验，首先计算t统计量和自由度，然后运行双侧t检验，生成p值。 最后，根据p值计算置信度。

的 *t* — 统计量被定义为任意两个独立随机变量的均值之差， *ν* 和 *ν<sub>0</sub>*，除以差异的标准误差：

<p style="text-align:center;"><img width="100px" src="img/t_value.png"></p>

其中 *μ<sub>v</sub>* 和 *μ<sub>v0</sub>* 是 *ν*  和 *ν<sub>0</sub>* 差的标准误差 *μ<sub>v</sub>* 和 *μ<sub>v0</sub>* 由提供：

<p style="text-align:center;"><img width="150px" src="img/standard_error_diff.png"></p>

其中 *σ<sup>2</sup><sub>v</sub>* 和 *σ<sup>2</sup><sub>v<sub>0</sub></sub>* 是两个体验的差异 *ν*  和 *ν<sub>0</sub>* 和 *N<sub>v</sub>* 和 *N<sub>v<sub>0</sub></sub>* 的样本大小 *ν* 和 *ν<sub>0</sub>* 分别进行。

对于Welch的t检验，其自由度计算如下：

<p style="text-align:center;"><img width="180px" src="img/degree_of_freedom.png"></p>

自由度 *ν*  和 *ν<sub>0</sub>* 定义为：

<p style="text-align:center;"><img width="100px" src="img/df_v.png"></p>

<p style="text-align:center;"><img width="100px" src="img/df_v0.png"></p>

然后，可以从 *t*-distribution:

<p style="text-align:center;"><img width="20%" src="img/p_value.png"></p>

最后， [!DNL Target] 定义为：

<p style="text-align:center;"><img width="20%" src="img/confidence.png"></p>

## 脱机执行计算

[下载的 CSV 报表](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md)仅包含原始数据，而不包含计算量度，如 A/B 测试中使用的每位访客带来的收入、提升度或置信度。

要计算这些统计数量，请下载 [!DNL Target] [完整置信度计算器](/help/main/assets/complete_confidence_calculator.xlsx) 用于输入活动值的Excel文件。