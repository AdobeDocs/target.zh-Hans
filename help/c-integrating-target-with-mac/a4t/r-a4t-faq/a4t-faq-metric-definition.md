---
keywords: faq;frequently asked questions;analytics for target;a4T;metric;metric definitions
description: 本主题包含有关量度定义和使用 Analytics 作为 Target 报表源 (A4T) 的常见问题解答。
title: 量度定义 - A4T 常见问题解答
feature: a4t troubleshooting
topic: Standard
uuid: 41d41665-9057-479d-b0a8-7cffb90ca843
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 100%

---


# 量度定义 - A4T 常见问题解答{#metric-definitions-a-t-faq}

本主题包含有关量度定义和使用 Analytics 作为 Target 报表源 (A4T) 的常见问题解答。

## 活动成员资格何时到期？访客进入活动后，如果他们不再访问活动，系统会在多久之后停止在活动中计入访客的操作？ {#section_41B4958F33534E4B96DEE0C981227A79}

默认情况下，活动会在访客与活动进行最后一次交互后的第 90 天到期。如果需要，可以请求客户关怀团队调整该到期时间。但是，这是针对所有活动的全局设置，不能仅针对一个案例进行调整。

## Target 中的成功量度高级选项是否适用于 A4T？ {#section_F060E3438F4144258BB95813EDEABDAA}

这些选项目前并不适用于 A4T。

## 什么是计算量度？它们是如何取代过去使用的 SiteCatalyst:Event mbox 的？ {#section_D59F4719E6B94758A2187427C17F8EF3}

通过计算量度，您可以创建从区段或数学计算派生的自定义量度。过去，您可能使用过 `SiteCatlayst:Event` mbox，例如其中 `evar27=shoes`，事件为 `purchase`；现在，您可以创建一个区段，其中 `evar27=shoes`，然后再创建一个计算量度，其中事件为 `purchase`，并且应用创建的区段。使用计算量度的好处是此类量度可以随时创建，即使活动开始后也可以创建。创建之后，便可以在 Analytics 的任何报表中使用此类量度。

## A4T 是否可将转化归因于多个营销活动？ {#section_7F15C727206440CD86B3A8CE77087DF9}

是. 使用“完全分配”设置可实现这一点。
