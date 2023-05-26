---
keywords: 报表；统计方法；统计计算；统计数据；平均值；转化率；每位访客带来的收入；rpv；置信区间；提升度；welch t-test；离线计算
description: 了解手动使用的统计计算 [!UICONTROL A/B测试] 中的活动 [!DNL Adobe Target].
title: 如何了解中使用的统计计算 [!UICONTROL A/B测试] 活动？
feature: Reports
exl-id: 5f7377b9-0567-4b6f-8968-4696b2088d0a
source-git-commit: f997b6a0ea9e0cebf7b414c029971d8520f8b95f
workflow-type: tm+mt
source-wordcount: '1091'
ht-degree: 5%

---

# A/Bn 测试中的统计计算

本文记录了在手动A/Bn测试中使用的详细统计计算 [!DNL Adobe Target]. 提供了以下内容的定义 [!UICONTROL 转化率]， [!UICONTROL 转化率的置信区间]， [!UICONTROL 提升]， [!UICONTROL 提升度的置信区间]、和 [!UICONTROL 置信度].

>[!NOTE]
>
>本文中的信息取代了&#x200B;*用于 A/B 测试的 Adobe Target 计算* pdf 文件，以前可在此站点上下载。

![显示 [!UICONTROL 转化率]， [!UICONTROL 平均提升度和置信区间]、和 [!UICONTROL 置信度] A/B测试活动的日志。](/help/main/c-reports/statistical-methodology/img/target_report.png)

## 平均性能

下节将说明上图中使用的计算。

### 转化率和每位访客带来的收入(RPV)活动

下图显示 [!UICONTROL 转化率]， [!UICONTROL 转化率的置信区间]，和的数量 [!UICONTROL 转化] 在 [!DNL Target] 报告。 例如，第一行代码显示对于体验A： [!UICONTROL 转化率] 为25.81%，带 [!UICONTROL 置信区间] ±7.7%，转化率为32次。 考虑到124位访客查看了体验，这相当于32/124 = 25.81%。

<p style="text-align:center;"><img width="25%" src="img/conv_rate.png"></p>

转换率或 **平均值**， *μ<sub>ν</sub>*，代表每个体验 *ν* 在实验中，被定义为量度总和相对于分配给该量度的单位数的比率， *N<sub>ν</sub>*：

<p style="text-align:center;"><img width="125px" src="img/mean_definition.png"></p>

这里，

* *Y<sub>iν</sub>* 是每个单位的量度值 *i*，已分配给给定体验 *ν*.

* 单位总和 *i* 取决于计数方法的选择。

   * 如果 *[!UICONTROL 访客]* 用作计数方法，每个单位都是独特访客，被定义为活动生命周期中的独特参与者。
   * 如果 *[!UICONTROL 访问次数]* 用作计数方法，每个单位都是独特访问，其定义为期间体验的唯一参与者。 [!DNL Target] 会话(具有唯一 `sessionId`)。 当 `sessionId` 如果发生更改，或者访客达到转化步骤，则会计为新访问。
   * 如果 *[!UICONTROL 活动展示次数]* 用作计数方法，每个单位都是一个唯一的展示次数，定义为每次访客加载活动的任何页面时。

## [!UICONTROL 平均值的置信区间]/[!UICONTROL 转化率]

转换率的置信区间直观地定义为与基础数据一致的可能转换率的范围。

运行实验时，给定体验的转化率为 *预估* “真”转化率的10%。 为量化该估计之不确定因素， [!DNL Target] 使用置信区间。 [!DNL Target] 始终报告95%的置信区间，这意味着最终，计算的95%置信区间将包括体验的真实转化率。

转化率的95%置信区间 *μ<sub>ν</sub>* 定义为值的范围：

<p style="text-align:center;"><img width="30%" src="img/confidence_interval.png"></p>

其中，平均数的标准误差定义为

<p style="text-align:center;"><img width="75px" src="img/se_conv_continuous.png"></p>

当使用样本标准差的无偏估计时：

<p style="text-align:center;"><img width="200px" src="img/stdev_definition.png"></p>

如果促销活动是转化率促销活动（即，转化量度是二进制的），则标准误差将减少为：

<p style="text-align:center;"><img width="150px" src="img/se_conv.png"></p>

## 提升度

下图显示 [!UICONTROL 提升] 和 [!UICONTROL 提升度的置信区间] 在 [!DNL Target] 报告。 数字表示提升度范围的平均值，箭头反映的是提升度是正值还是负值。 箭头以灰色显示，直到置信度超过95%。 置信度超过阈值后，箭头会根据提升度为正值或负值而变为绿色或红色。

<p style="text-align:center;"><img width="35%" src="img/lift.png"></p>

体验之间的提升  *ν*&#x200B;和控制体验 *ν<sub>0</sub>* 是转化率中的相对“增量”，其定义如下

<p style="text-align:center;"><img width="15%" src="img/lift_definition.png"></p>

个别兑换率定义见上文。 更简单地说，

```
Lift(Experience N) = (Performance_Experience_N - Performance_Control)/ Performance_Control
```

如果控制体验的转化率 *ν<sub>0</sub>* 为0，没有电梯。

## [!DNL Confidence Interval of Lift]

中的箱形图 [!UICONTROL 平均提升度和置信区间] 列表示平均值和95% [!UICONTROL 提升度的置信区间]. 当给定非控制体验的置信区间与控制体验的置信区间存在任何重叠时，盒形图呈灰色。 当给定体验的置信区间范围高于或低于控制体验的置信区间时，箱形图呈绿色或红色。

体验之间提升的标准误差  *ν*&#x200B;和控制体验  *ν<sub>0</sub>* 定义为：

<p style="text-align:center;"><img width="35%" src="img/se_lift.png" alt="metric-mean"></p>

那么提升度的95%置信区间为：

<p style="text-align:center;"><img width="40%" src="img/lift_CI.png"></p>

此计算使用“Delta”方法，并对此进行了说明 [详情请参阅本文档](/help/main/assets/confidence_interval_lift.pdf)

## [!UICONTROL 置信度]

最后一列显示置信度 [!DNL Target] 报告。 体验的置信度是指在零假设为真的情况下，获得比观察到的结果更少极端的结果的概率（以百分比表示）。 就p值而言，显示的置信度为 *1 - p值*. 直觉上，较高的置信度意味着控制体验和非控制体验具有相等转化率的可能性较小。

In [!DNL Target]，双尾 **韦尔奇t检验** 在测试体验和控制体验之间执行，以测试测试手段和控制体验是否相同。 因为通常在试验前不知道两组样本量及方差是否相同，并且 [!DNL Target] 还允许您发送到每个体验的流量百分比不等，我们并不假设每个体验的方差相等。 因此，韦尔奇的t检验被选作学生的t检验。

为了进行Welch的t检验，首先计算t统计量和自由度，然后进行双尾t检验以生成p值。 最后，根据p值计算出置信度。

此 *t*-statistic被定义为任意两个独立随机变量均值的差值， *ν* 和 *ν<sub>0</sub>*，除以标准误差之差：

<p style="text-align:center;"><img width="100px" src="img/t_value.png"></p>

位置 *μ<sub>v</sub>* 和 *μ<sub>v0</sub>* 是手段 *ν*  和 *ν<sub>0</sub>* 分别给出了和标准误差之间的差值 *μ<sub>v</sub>* 和 *μ<sub>v0</sub>* 提供者：

<p style="text-align:center;"><img width="150px" src="img/standard_error_diff.png"></p>

位置 *σ<sup>2</sup><sub>v</sub>* 和 *σ<sup>2</sup><sub>v<sub>0</sub></sub>* 是两种体验的差异 *ν*  和 *ν<sub>0</sub>* 分别，和 *N<sub>v</sub>* 和 *N<sub>v<sub>0</sub></sub>* 的样本大小 *ν* 和 *ν<sub>0</sub>* 的量度。

对于Welch的t检验，自由度计算如下：

<p style="text-align:center;"><img width="180px" src="img/degree_of_freedom.png"></p>

和自由度 *ν*  和 *ν<sub>0</sub>* 定义为：

<p style="text-align:center;"><img width="100px" src="img/df_v.png"></p>

<p style="text-align:center;"><img width="100px" src="img/df_v0.png"></p>

然后p值可以从尾部的区域计算 *t*-distribution：

<p style="text-align:center;"><img width="20%" src="img/p_value.png"></p>

最后，置信度报告于 [!DNL Target] 定义为：

<p style="text-align:center;"><img width="20%" src="img/confidence.png"></p>

## 脱机执行计算

[下载的 CSV 报表](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md)仅包含原始数据，而不包含计算量度，如 A/B 测试中使用的每位访客带来的收入、提升度或置信度。

要计算这些统计量，请下载 [!DNL Target] [完全置信度计算器](/help/main/assets/complete_confidence_calculator.xlsx) 用于输入活动值的Excel文件。
