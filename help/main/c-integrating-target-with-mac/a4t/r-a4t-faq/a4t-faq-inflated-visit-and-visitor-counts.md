---
keywords: FAQ;常见问题解答;Analytics for Target;A4T;夸大;访问;访客;局部点击;孤立;孤立项;局部点击
description: 查找有关在使用Analytics for [!DNL Target] (A4T)。 了解如何最大限度地减少“局部数据”。
title: 在哪里可以找到有关A4T夸大的访问和访客计数的常见问题解答？
feature: Analytics for Target (A4T)
exl-id: e936b1f6-dc72-4ab2-9bb5-169d1710edbe
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 49%

---

# 夸大的访问和访客计数 - A4T 常见问题解答

本主题包含有关在使用 Analytics 作为 Target 报表源 (A4T) 时出现夸大的访问和访客计数的常见问题解答。

## 我的 Analytics 数据显示的访问为何没有页面查看次数或其他变量值？ {#section_4D8C2C2D766842E6B12F3ECC774A64D5}

+++在 [!DNL Adobe Analytics] 用于测量 [!DNL Target] 活动（称为A4T）、 [!DNL Analytics] 收集没有 [!DNL Target] 活动。 之所以会出现这种情况，是因为 [!DNL Target] 活动会在页面顶部触发调用，而 [!DNL Analytics] 通常会在页面底部触发数据收集调用。在迄今为止的 A4T 实施中，只要有活跃的 [!DNL Target] 活动，Adobe 即包括这些额外数据。

有关更多信息，请参阅[在 A4T 中最大限度地减少夸大的访问和访客计数](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

+++

## 什么是不完整数据点击？ {#section_59A203E289564576BF6821F96B0B9E11}

+++回答在 [!DNL Target] 标记，但 [!DNL Analytics] 标记时，不会触发。 出现这种情况的原因有多种。 在 [!DNL A4T] 迄今为止，Adobe在 [!DNL Target] 活动处于活动状态。 今后，Adobe仅在 [!DNL Target] 和 [!DNL Analytics] 标记已触发。

有关更多信息，请参阅[在 A4T 中最大限度地减少夸大的访问和访客计数](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

+++

## 我可以看到访问次数的峰值。如何判断这些访问是否是由不完整数据点击造成的？ {#section_28506672C6224ED18AC74F6A02F6F811}

+++回答您可以联系的问题 [Adobe客户关怀](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) 来检索局部数据报表。 无法直接在 [!DNL Analytics] UI 中获取此信息。

+++

## 不完整数据点击可能会由哪些因素引起？ {#section_C4BB9925CE6444BE8CB9FBEFE5085546}

+++回答不完整数据点击量通常是由于实施不当（例如报表包ID未对齐）所致。 但是，也可能是由一些合理原因引起的，包括页面加载速度缓慢、页面出现错误、活动中存在重定向选件，或库版本已过期。

有关更多信息，请参阅“不完整数据的导致因素”，此内容位于[在 A4T 中最大限度地减少夸大的访问和访客计数](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

+++

## 我的数据中存在不完整数据点击。如何清理我的数据？ {#section_CBE778A9D07A469E8FF98F68BACC7124}

+++答案您可以创建一个虚拟报表包，以从报表中排除历史局部数据。

有关更多信息，请参阅“如何查看排除不完整数据后所呈现的历史趋势？”，此内容位于此内容位于[在 A4T 中最大限度地减少夸大的访问和访客计数](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

+++

## 我可以采取哪些措施来阻止页面生成不完整数据点击？ {#section_4B00E7E618444BE98A0798DE98F08B21}

+++回答2016年11月14日之后，Adobe仅在 [!DNL Target] 和 [!DNL Analytics] 标记已触发。 此更改不可追溯。如果历史报表显示夸大的计数，则可以通过创建虚拟报表包从报表中排除这些计数。 请参阅“如何查看不含局部数据的历史趋势？” in [在A4T中最大限度地减少夸大的访问和访客计数](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

您还可以执行一些步骤，来最大程度地减少不完整数据点击。有关更多信息，请参阅“减少不完整数据的最佳实践有哪些？”，此内容位于[在 A4T 中最大限度地减少夸大的访问和访客计数](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

+++

## 如果从报表中删除了不完整数据点击，那么我不会丢失有价值的数据 [!DNL Target] 还是Analytics数据？ {#section_EBC39E8A0F6A40E58F51E776936F7D9E}

+++答案，包括 [!DNL Analytics] 报表确实会提供更多信息，但也会造成与没有 [!DNL Target] 活动正在运行。 包含不完整点击数据可能会导致 [!DNL Analytics] 正在分析随时间呈现的趋势的用户。

您可以执行一些步骤，来最大程度地减少不完整数据点击。有关更多信息，请参阅“减少不完整数据的最佳实践有哪些？”，此内容位于[在 A4T 中最大限度地减少夸大的访问和访客计数](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

+++

## 是否有任何特定类型的 [!DNL Target] 更可能导致不完整数据点击的活动？ {#section_69837442A9B84366BEFDA4588B31E574}

+++应答重定向选件会立即将用户发送到其他页面，这意味着 [!DNL Analytics] 调用不会在第一个页面上触发。

+++