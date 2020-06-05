---
keywords: faq;frequently asked questions;analytics for target;a4T;lift;ad hoc;report builder;confidence
description: 本主题包含有关在使用 Analytics 作为 Target 报表源 (A4T) 时的提升度和置信度的常见问题解答。
title: 提升度和置信度 - A4T 常见问题解答
topic: Standard
uuid: 7d0402f3-d6f2-422e-b69c-86e10120ac83
translation-type: tm+mt
source-git-commit: 894954ef73c0f65468d5c406ac1040d532e74b17
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 55%

---


# 提升度和置信度 - A4T 常见问题解答{#lift-and-confidence-a-t-faq}

本主题包含有关在使用 Analytics 作为 Target 报表源 (A4T) 时的提升度和置信度的常见问题解答。

## 我能否为 A4T 执行离线计算？{#section_55B5B750E17D414CAECBEECE27B15D81}

您可以为 A4T 执行离线计算，但需要在 [!DNL Analytics] 中完成数据导出步骤。有关更多信息，请参阅[置信水平和置信区间](../../../c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B)中的“为 Analytics for Target (A4T) 执行离线计算”。

## 如何计算提升度？{#section_8CAE788EED5646C4B1D64A0D22070734}

提升度是指控制页面结果和成功测试变量之间的百分比差值。

## 如何计算置信度？ {#section_97DB24D833E742988318CA65DA65DAD9}

置信水平是指测量的转化率与最佳页面转化率之间因非偶然原因出现差异的概率。

## 我为何看不到计算量度的提升度和置信度？ {#lift-confidence}

提升和置信度函数当前不支持计算度量。 这是由于Analytics在聚合级别而不是访客级别计算指标。 信心尤其是访客级计算。

非计算（标准）事件以提升和置信度受支持。 他们成为电梯功能中的分子； 分子不能是计算本身。 标准化指标(展示次数、访问次数或访客数)。 标准事件的一些示例包括订单、收入、活动转换、自定义事件1-1000等。 这意味着支持通用优化指标，如对话率(订单/访客)和RPV(收入/访客)，从而提升客户信心。

不支持的指标或用例包括：

* 平均订单值(每访客收入／订单)。 不支持AOV，因为分子是计算度量。 相反，建议考虑AOV的两个影响指标——每访客和转化率的收入。
* 计算的度量是标准事件的总和。 例如，您可以将十种不同的潜在客户表单跟踪到十种不同的事件，然后将它们相加以获得总的潜在客户提交。 跟踪这些事件的推荐方法是在Analytics中实施单个潜在客户提交事件，然后使用eVar收集潜在客户表单的类型。 使用此方法需要的变量较少，并确保在提升和置信度函数中可以使用单个潜在客户提交度量。

## A4T 如何处理置信度计算？{#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

A4T 通过对数据求平方和来使用非二进制量度计算方法。差异使用数据的平方和进行计算。计算时将排除极端订单。

可以将任意 Analytics 区段应用到报表。通过这种方式，您可以从其他区段选项中找到“极端订单”。此外，还可以构建一个量度来限制访客的转化次数等项目。

## Ad Hoc 和 Report Builder 中是否会计算提升度和置信度？如果不会在本机计算，那么我能否自行计算？ {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

Ad Hoc 或 Report Builder 中不会计算提升度和置信度，而且您也无法为连续变量自行计算。但是，可以手动为二进制量度计算提升度和置信度。
