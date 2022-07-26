---
keywords: FAQ;常见问题解答, Analytics for Target, A4T;提升度;Ad Hoc;Report Builder;置信度
description: 查找有关使用Analytics for [!DNL Target] (A4T)。 A4T允许您将Analytics报表用于 [!DNL Target] 活动。
title: 在哪里可以找到有关A4T提升度和置信度的信息？
feature: Analytics for Target (A4T)
exl-id: 42fd179b-944a-4a0a-b299-85ea4a7ea244
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 15%

---

# 提升度和置信度 - A4T 常见问题解答

本主题包含有关在使用 [!DNL Adobe Analytics] 作为报表源 [!DNL Adobe Target] (A4T)。

## 我能否为 A4T 执行离线计算？ {#section_55B5B750E17D414CAECBEECE27B15D81}

+++回答您可以为A4T执行离线计算，但需要在中完成数据导出步骤 [!DNL Analytics]. 有关更多信息，请参阅 [A/Bn测试中的统计计算](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

+++

## 如何计算提升度？ {#section_8CAE788EED5646C4B1D64A0D22070734}

+++答案提升度是控制页面结果与成功测试变体之间的百分比差异。

+++

## 如何计算置信度？ {#section_97DB24D833E742988318CA65DA65DAD9}

+++答案置信水平是一个概率，以百分比表示，等于 `1 - p-value`，其中 `p-value` 从t测试计算。 请参阅 [A/Bn测试中的统计计算](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

+++

## 我为何看不到计算量度的提升度和置信度？ {#lift-confidence}

+++提升度和置信度函数当前不支持答案计算量度。 Analytics在汇总级别计算量度，而不是在访客级别计算量度。 置信度尤其是访客级别的计算。

提升度和置信度支持非计算（标准）事件。 他们成为提升函数中的分子；分子不能是计算本身。 分母是标准化量度（展示次数、访问次数或访客数）。 标准事件的一些示例包括订单、收入、活动转化、自定义事件1-1000，等等。 提升度和置信度支持常见的优化量度，例如对话率（订单/访客）和RPV（收入/访客）。

不支持的量度或用例示例包括：

* 平均订单值（收入/订单、每位访客）。 不支持AOV，因为分子是计算量度。 相反，建议考虑AOV的两个影响量度 — 每位访客带来的收入和转化率。
* 是标准事件总和的计算量度。 例如，您可以将十个不同的潜在客户表单跟踪为十个单独的事件，然后将它们相加以获取总的潜在客户提交。 跟踪这些事件的推荐方法是在Analytics中实施单个潜在客户提交事件，然后使用eVar收集潜在客户表单类型。 使用此方法需要的变量较少，并且可确保在提升度和置信度函数中使用单个潜在客户提交量度。

+++

## A4T 如何处理置信度计算？ {#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

+++回答
[!DNL Adobe Analytics] 将所有量度都视为非二进制，因此，会以与在常规t测试中使用二进制量度不同的方式计算置信度/p值。 具体而言，A4T使用的计算允许每个用户产生连续的量度结果（而不是每个用户仅有1或0个），因此必须相应地计算每个体验的方差（或相关的标准偏差）。 不考虑极端订单。 此外，置信度计算不会对多个选件应用Bonferroni校正。

+++

## Ad Hoc 和 Report Builder 中是否会计算提升度和置信度？如果不会在本机计算，那么我能否自行计算？ {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

+++在Ad Hoc或Report Builder中，答案提升度和置信度不起作用，并且无法针对连续变量自行计算。 但是，可以手动为二进制量度计算提升度和置信度。
+++
