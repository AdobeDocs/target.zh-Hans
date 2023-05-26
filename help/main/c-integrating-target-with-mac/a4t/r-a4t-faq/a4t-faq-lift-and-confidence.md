---
keywords: FAQ;常见问题解答, Analytics for Target, A4T;提升度;Ad Hoc;Report Builder;置信度
description: 查找将Analytics用于时的提升度和置信度相关问题的答案 [!DNL Target] (A4T)。 A4T允许您将Analytics报表用于 [!DNL Target] 活动。
title: 可在何处找到有关A4T的提升度和置信度的信息？
feature: Analytics for Target (A4T)
exl-id: 42fd179b-944a-4a0a-b299-85ea4a7ea244
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 15%

---

# 提升度和置信度 - A4T 常见问题解答

本主题包含有关使用时的提升度和置信度的常见问题解答 [!DNL Adobe Analytics] 作为的报表源 [!DNL Adobe Target] (A4T)。

## 我能否为 A4T 执行离线计算？ {#section_55B5B750E17D414CAECBEECE27B15D81}

+++答案您可以为A4T执行离线计算，但需要在中完成数据导出步骤 [!DNL Analytics]. 有关更多信息，请参阅 [A/Bn测试中的统计计算](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

+++

## 如何计算提升度？ {#section_8CAE788EED5646C4B1D64A0D22070734}

+++答案提升度是控制页面结果与成功测试变体之间的百分比差异。

+++

## 如何计算置信度？ {#section_97DB24D833E742988318CA65DA65DAD9}

+++答案置信水平是一个概率，以百分比表示，它等于 `1 - p-value`，其中 `p-value` 通过t检验计算得出。 参见 [A/Bn测试中的统计计算](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

+++

## 我为何看不到计算量度的提升度和置信度？ {#lift-confidence}

+++提升度和置信度函数当前不支持回答计算量度。 Analytics在聚合级别而不是访客级别计算指标。 置信度是一种访客级别的计算。

提升度和置信度支持非计算（标准）事件。 它们成为提升函数中的分子；分子不能是计算本身。 分母是标准化量度（展示次数、访问次数或访客）。 标准事件的一些示例包括订单、收入、活动转化、自定义事件1-1000等。 提升度和置信度支持常用优化量度，例如会话率（订单数/访客）和RPV（收入/访客）。

不支持的量度或用例示例包括：

* 平均订单值（收入/订单，每位访客）。 不支持AOV，因为分子是计算量度。 建议改为考虑两个影响AOV的量度 — 每位访客带来的收入和转化率。
* 计算指标，即标准事件的总和。 例如，您可以将10个不同的潜在客户表单跟踪到10个不同的事件中，然后将它们相加得到总潜在客户提交量。 跟踪这些事件的推荐方法是：在Analytics中实施单个潜在客户提交事件，然后使用eVar收集潜在客户表单的类型。 使用此方法所需的变量较少，并确保您可以在提升度和置信度函数中使用单个商机提交量度。

+++

## A4T 如何处理置信度计算？ {#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

+++回答
[!DNL Adobe Analytics] 将所有量度都视为非二进制，因此，计算置信度/p值的方式与在常规t测试中使用二进制量度有所不同。 具体而言，A4T使用的计算允许每个用户具有连续的量度结果（不仅仅对于每个用户为1或0），因此必须正确计算每个体验的方差（或相关的标准偏差）。 不考虑极端订单。 此外，置信度计算不会对多个选件应用Bonferroni校正。

+++

## Ad Hoc 和 Report Builder 中是否会计算提升度和置信度？如果不会在本机计算，那么我能否自行计算？ {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

+++答案提升度和置信度在Ad Hoc或Report Builder中不起作用，并且无法为连续变量自行计算。 但是，可以手动为二进制量度计算提升度和置信度。
+++
