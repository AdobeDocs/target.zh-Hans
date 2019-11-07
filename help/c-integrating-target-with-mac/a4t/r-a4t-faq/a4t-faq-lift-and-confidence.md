---
keywords: FAQ;常见问题解答, Analytics for Target, A4T;提升度;Ad Hoc;Report Builder;置信度
description: 本主题包含有关在使用 Analytics 作为 Target 报表源 (A4T) 时的提升度和置信度的常见问题解答。
title: 提升度和置信度 - A4T 常见问题解答
topic: Standard
uuid: 7d0402f3-d6f2-422e-b69c-86e10120ac83
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 提升度和置信度 - A4T 常见问题解答{#lift-and-confidence-a-t-faq}

本主题包含有关在使用 Analytics 作为 Target 报表源 (A4T) 时的提升度和置信度的常见问题解答。

## 我能否为 A4T 执行离线计算？{#section_55B5B750E17D414CAECBEECE27B15D81}

您可以为 A4T 执行离线计算，但需要在 [!DNL Analytics] 中完成数据导出步骤。有关更多信息，请参阅[置信水平和置信区间](../../../c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B)中的“为 Analytics for Target (A4T) 执行离线计算”。

## 如何计算提升度？{#section_8CAE788EED5646C4B1D64A0D22070734}

提升度是指控制页面结果和成功测试变量之间的百分比差值。

## 如何计算置信度？ {#section_97DB24D833E742988318CA65DA65DAD9}

置信水平是指测量的转化率与最佳页面转化率之间因非偶然原因出现差异的概率。

## 我为何看不到计算量度的提升度和置信度？ {#section_D3E44E24782A409DBD88AE4D1595CB58}

目前还无法为计算量度生成提升度和置信度。但是，在大多数情况下，这应该不会引发问题，因为提升度将使用标准化量度进行标准化处理。例如，如果您选择订单量的提升度，且标准化量度为访问次数，则会根据订单量和访问次数的比率（即转化率）来计算提升度。

## A4T 如何处理置信度计算？ {#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

A4T 通过对数据求平方和来使用非二进制量度计算方法。差异使用数据的平方和进行计算。计算时将排除极端订单。

可以将任意 Analytics 区段应用到报表。通过这种方式，您可以从其他区段选项中找到“极端订单”。此外，还可以构建一个量度来限制访客的转化次数等项目。

## Ad Hoc 和 Report Builder 中是否会计算提升度和置信度？如果不会在本机计算，那么我能否自行计算？ {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

Ad Hoc 或 Report Builder 中不会计算提升度和置信度，而且您也无法为连续变量自行计算。但是，可以手动为二进制量度计算提升度和置信度。
