---
keywords: FAQ;常见问题解答;Analytics for Target;A4T;夸大;访问;访客;局部点击;孤立;孤立项;局部点击
description: 使用Analytics for 目标(A4T)时，查找有关夸大访问和访客计数的问题的答案。 了解如何将“部分数据”降至最低。
title: 在哪里可以找到有关A4T夸大访问和访客计数的常见问题解答？
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: e45f0d2d2370f9c7aba2c2bd26afdd4c0e401db8
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 63%

---


# 夸大的访问和访客计数 - A4T 常见问题解答{#inflated-visit-and-visitor-counts-a-t-faq}

本主题包含有关在使用 Analytics 作为 Target 报表源 (A4T) 时出现夸大的访问和访客计数的常见问题解答。

## 我的 Analytics 数据显示的访问为何没有页面查看次数或其他变量值？{#section_4D8C2C2D766842E6B12F3ECC774A64D5}

当使用[!DNL Adobe Analytics]测量[!DNL Target]活动（称为A4T）时， [!DNL Analytics]会收集当页面上没有[!DNL Target]活动时不可用的数据。 之所以会出现这种情况，是因为 [!DNL Target] 活动会在页面顶部触发调用，而 [!DNL Analytics] 通常会在页面底部触发数据收集调用。在迄今为止的A4T实施中，当[!DNL Target]活动处于活动状态时，Adobe将包含此附加数据。

有关更多信息，请参阅[在 A4T 中最大限度地减少夸大的访问和访客计数](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

## 什么是不完整数据点击？{#section_59A203E289564576BF6821F96B0B9E11}

如果位于页面顶部的 [!DNL Target] 标记触发，而位于页面底部的 [!DNL Analytics] 标记未触发，则会生成不完整数据点击。出现这种情况的原因有多种。 在迄今为止的[!DNL A4T]实现中，当[!DNL Target]活动处于活动状态时，Adobe将包含有关这些点击的部分数据。 今后，Adobe将仅在[!DNL Target]和[!DNL Analytics]标签已触发时才包含此附加数据。

有关更多信息，请参阅[在 A4T 中最大限度地减少夸大的访问和访客计数](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

## 我可以看到访问次数的峰值。如何判断这些访问是否是由部分数据点击造成的？{#section_28506672C6224ED18AC74F6A02F6F811}

您可以联系 [Adobe 客户关怀团队](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)以检索局部数据报表。无法直接在 [!DNL Analytics] UI 中获取此信息。

## 不完整数据点击可能会由哪些因素引起？{#section_C4BB9925CE6444BE8CB9FBEFE5085546}

不完整数据点击通常是由实施不当（例如报表包 ID 不一致）引起的。但是，也可能是由一些合理原因引起的，包括页面加载速度缓慢、页面出现错误、活动中存在重定向选件，或库版本已过期。

有关更多信息，请参阅“不完整数据的导致因素”，此内容位于[在 A4T 中最大限度地减少夸大的访问和访客计数](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

## 我的数据中存在不完整数据点击。如何清理我的数据？ {#section_CBE778A9D07A469E8FF98F68BACC7124}

您可以创建一个虚拟报表包，以便从报表中排除不完整历史数据。

有关更多信息，请参阅“如何查看排除不完整数据后所呈现的历史趋势？”，此内容位于此内容位于[在 A4T 中最大限度地减少夸大的访问和访客计数](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

## 我可以采取哪些措施来阻止页面生成不完整数据点击？{#section_4B00E7E618444BE98A0798DE98F08B21}

在2016年11月14日之后，Adobe将仅在[!DNL Target]和[!DNL Analytics]标签都已触发时才包含数据。 此更改不具有可回溯性。如果历史报表显示虚增的计数，则可以通过创建虚拟报表包从报表中排除这些计数。 请参阅“如何在不使用部分数据的情况下视图历史趋势？” 在[中，最小化A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)中的夸大访问和访客计数。

您还可以执行一些步骤，来最大程度地减少不完整数据点击。有关更多信息，请参阅“减少不完整数据的最佳实践有哪些？”，此内容位于[在 A4T 中最大限度地减少夸大的访问和访客计数](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

## 如果从报告中删除了部分目标点击数据，我是否会丢失有价值的数据或Analytics数据？{#section_EBC39E8A0F6A40E58F51E776936F7D9E}

在[!DNL Analytics]报告中包括部分数据确实提供了其他信息，但它也会导致与未运行[!DNL Target]活动的期间的历史数据不一致。 包含部分点击数据可能会导致[!DNL Analytics]用户在分析趋势随时间变化的问题。

您可以执行一些步骤，来最大程度地减少不完整数据点击。有关更多信息，请参阅“减少不完整数据的最佳实践有哪些？”，此内容位于[在 A4T 中最大限度地减少夸大的访问和访客计数](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

## 是否有任何特定类型的 Target 活动可能更容易产生不完整数据点击？{#section_69837442A9B84366BEFDA4588B31E574}

重定向选件会立即将用户发送到另一个页面，这意味着 [!DNL Analytics] 调用不会在第一个页面上触发。
