---
keywords: FAQ;常见问题解答, Analytics for Target, A4T;提升度;Ad Hoc;Report Builder;置信度
description: 在 [!DNL Target] (A4T). A4T lets you use Analytics reporting for [!DNL Target] 活动使用Analytics时，查找有关提升度和信心的问题的解答。
title: 在哪里可以找到有关A4T提升和置信度的信息？
feature: Analytics for Target (A4T)
exl-id: 42fd179b-944a-4a0a-b299-85ea4a7ea244
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 41%

---

# 提升度和置信度 - A4T 常见问题解答

本主题包含有关使用[!DNL Adobe Analytics]作为[!DNL Adobe Target](A4T)的报告源时的提升度和置信度的常见问题解答。

## 我能否为 A4T 执行离线计算？{#section_55B5B750E17D414CAECBEECE27B15D81}

您可以为 A4T 执行离线计算，但需要在 [!DNL Analytics] 中完成数据导出步骤。有关更多信息，请参阅[置信水平和置信区间](/help/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B)中的“为 Analytics for Target (A4T) 执行离线计算”。

## 如何计算提升度？{#section_8CAE788EED5646C4B1D64A0D22070734}

提升度是指控制页面结果和成功测试变量之间的百分比差值。

## 如何计算置信度？ {#section_97DB24D833E742988318CA65DA65DAD9}

置信水平是指测量的转化率与最佳页面转化率之间因非偶然原因出现差异的概率。

## 我为何看不到计算量度的提升度和置信度？  {#lift-confidence}

提升和置信度函数当前不支持计算量度。 Analytics在聚合级别而不是访客级别计算量度。 信心尤其是访客级计算。

以提升和置信度支持非计算（标准）事件。 他们在升力函数中成为分子；分子不能是计算本身。 标准化指标(展示次数、访问次数或访客)是分母。 标准事件的一些示例包括订单、收入、活动转换、自定义事件1-1000等。 支持通用优化指标，如对话率(订单/访客)和RPV(收入/访客)，提升客户信心。

不支持的量度或用例示例包括：

* 平均订单值(收入/订单，每访客)。 不支持AOV，因为分子是计算量度。 相反，建议考虑AOV的两个影响指标 — 每访客和转化率收入。
* 计算的量度是标准事件的总和。 例如，您可以将十个不同的潜在客户表单跟踪到十个不同的事件，然后将它们相加以获得总的潜在客户提交。 跟踪这些事件的推荐方法是在Analytics中实施单个潜在客户提交事件，然后使用eVar收集潜在客户表单的类型。 使用此方法需要的变量较少，并确保您可以在提升和置信度函数中使用单个潜在客户提交量度。

## A4T 如何处理置信度计算？{#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

A4T 通过对数据求平方和来使用非二进制量度计算方法。差异使用数据的平方和进行计算。不考虑极端订单。 此外，置信度计算不适用于多个优惠的Bonferroni校正。

## Ad Hoc 和 Report Builder 中是否会计算提升度和置信度？如果不会在本机计算，那么我能否自行计算？  {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

Ad Hoc 或 Report Builder 中不会计算提升度和置信度，而且您也无法为连续变量自行计算。但是，可以手动为二进制量度计算提升度和置信度。
