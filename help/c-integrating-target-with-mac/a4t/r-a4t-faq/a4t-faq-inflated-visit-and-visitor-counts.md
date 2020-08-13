---
keywords: faq;frequently asked questions;analytics for target;a4T;inflated;visit;visitor;partial hit;orphaned;orphan;partial-hit
description: 本主题包含有关在使用 Analytics 作为 Target 报表源 (A4T) 时出现夸大的访问和访客计数的常见问题解答。
title: 夸大的访问和访客计数 - A4T 常见问题解答
feature: a4t troubleshooting
topic: Standard
uuid: 5d1b77bb-9053-4533-bd01-d6f53f0751e9
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 100%

---


# 夸大的访问和访客计数 - A4T 常见问题解答{#inflated-visit-and-visitor-counts-a-t-faq}

本主题包含有关在使用 Analytics 作为 Target 报表源 (A4T) 时出现夸大的访问和访客计数的常见问题解答。

## 我的 Analytics 数据显示的访问为何没有页面查看次数或其他变量值？{#section_4D8C2C2D766842E6B12F3ECC774A64D5}

使用 [!DNL Adobe Analytics] 衡量 [!DNL Target] 活动（称为 A4T）时，[!DNL Analytics] 会收集到页面上并没有 [!DNL Target] 活动时的一些不可用的额外数据。之所以会出现这种情况，是因为 [!DNL Target] 活动会在页面顶部触发调用，而 [!DNL Analytics] 通常会在页面底部触发数据收集调用。迄今为止，在 A4T 实施中，只要 [!DNL Target] 活动处于活跃状态，我们便会收集这种不可用的额外数据。

有关更多信息，请参阅[在 A4T 中最大限度地减少夸大的访问和访客计数](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

## 什么是不完整数据点击？{#section_59A203E289564576BF6821F96B0B9E11}

如果位于页面顶部的 [!DNL Target] 标记触发，而位于页面底部的 [!DNL Analytics] 标记未触发，则会生成不完整数据点击。出现此情况的原因有很多。迄今为止，在 [!DNL A4T] 实施中，只要 [!DNL Target] 活动处于活跃状态，我们便会收集这种不完整数据。今后，仅当 [!DNL Target] 标记和 [!DNL Analytics] 标记均触发时，我们才会收集这种额外数据。

有关更多信息，请参阅[在 A4T 中最大限度地减少夸大的访问和访客计数](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

## 我可以看到访问次数的峰值。我如何判断这些峰值是否由不完整数据点击而引起？ {#section_28506672C6224ED18AC74F6A02F6F811}

您可以联系 [Adobe 客户关怀团队](../../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)以检索局部数据报表。无法直接在 [!DNL Analytics] UI 中获取此信息。

## 不完整数据点击可能会由哪些因素引起？{#section_C4BB9925CE6444BE8CB9FBEFE5085546}

不完整数据点击通常是由实施不当（例如报表包 ID 不一致）引起的。但是，也可能是由一些合理原因引起的，包括页面加载速度缓慢、页面出现错误、活动中存在重定向选件，或库版本已过期。

有关更多信息，请参阅“不完整数据的导致因素”，此内容位于[在 A4T 中最大限度地减少夸大的访问和访客计数](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

## 我的数据中存在不完整数据点击。如何清理我的数据？ {#section_CBE778A9D07A469E8FF98F68BACC7124}

您可以创建一个虚拟报表包，以便从报表中排除不完整历史数据。

有关更多信息，请参阅“如何查看排除不完整数据后所呈现的历史趋势？”，此内容位于此内容位于[在 A4T 中最大限度地减少夸大的访问和访客计数](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

## 我可以采取哪些措施来阻止页面生成不完整数据点击？{#section_4B00E7E618444BE98A0798DE98F08B21}

2016 年 11 月 14 日之后，仅当 [!DNL Target] 标记和 [!DNL Analytics] 标记均触发时，我们才会收集这种额外数据。此更改不具有可回溯性。如果您的历史报表显示了夸大的计数，并且您想要从报表中排除这些数据，则可以创建一个虚拟报表包（请参阅“如何查看排除不完整数据后所呈现的历史趋势？”，此内容位于[在 A4T 中最大限度地减少夸大的访问和访客计数](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

您还可以执行一些步骤，来最大程度地减少不完整数据点击。有关更多信息，请参阅“减少不完整数据的最佳实践有哪些？”，此内容位于[在 A4T 中最大限度地减少夸大的访问和访客计数](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

## 如果从报表中删除了不完整数据点击，我们会不会丢失有价值的 Target 数据或 Analytics 数据？{#section_EBC39E8A0F6A40E58F51E776936F7D9E}

在 [!DNL Analytics] 报表中包含不完整数据确实会提供更多信息，但同时也会造成与没有 [!DNL Target] 活动运行期间收集到的历史数据不一致。这可能会给正在分析随时间呈现的趋势的 [!DNL Analytics] 用户带来问题。

您可以执行一些步骤，来最大程度地减少不完整数据点击。有关更多信息，请参阅“减少不完整数据的最佳实践有哪些？”，此内容位于[在 A4T 中最大限度地减少夸大的访问和访客计数](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

## 是否有任何特定类型的 Target 活动可能更容易产生不完整数据点击？{#section_69837442A9B84366BEFDA4588B31E574}

重定向选件会立即将用户发送到另一个页面，这意味着 [!DNL Analytics] 调用不会在第一个页面上触发。
