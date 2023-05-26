---
keywords: FAQ;常见问题解答;Analytics for Target;A4T;夸大;访问;访客;局部点击;孤立;孤立项;局部点击
description: 查找有关在使用Analytics for时夸大的访问和访客计数问题的答案 [!DNL Target] (A4T)。 了解如何最小化“部分数据”。
title: 可在何处找到有关A4T夸大的访问和访客计数的常见问题解答？
feature: Analytics for Target (A4T)
exl-id: e936b1f6-dc72-4ab2-9bb5-169d1710edbe
source-git-commit: 0be54d82e25eb919102f6098c1b1db76ab291675
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 45%

---

# 夸大的访问和访客计数 - A4T 常见问题解答

本主题包含有关在使用 Analytics 作为 Target 报表源 (A4T) 时出现夸大的访问和访客计数的常见问题解答。

## 我可以看到访问次数的峰值。如何判断这些访问是否由局部数据点击引起？ {#section_28506672C6224ED18AC74F6A02F6F811}

+++回答：您可以联系 [Adobe客户关怀](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) 以检索局部数据报表。 无法直接在 [!DNL Analytics] UI 中获取此信息。

+++

## 不完整数据点击可能会由哪些因素引起？ {#section_C4BB9925CE6444BE8CB9FBEFE5085546}

+++应答局部数据点击通常是实施不当所致，例如报表包ID未对齐。 但是，也可能是由一些合理原因引起的，包括页面加载速度缓慢、页面出现错误、活动中存在重定向选件，或库版本已过期。

+++

## 是否有任何特定类型的 [!DNL Target] 更有可能导致不完整数据点击的活动？ {#section_69837442A9B84366BEFDA4588B31E574}

+++应答重定向选件会立即将用户发送到其他页面，这意味着 [!DNL Analytics] 调用不会在第一个页面上触发。

+++