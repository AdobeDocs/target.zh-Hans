---
keywords: faq;frequently asked questions;analytics for target;a4T;metric;metric definitions
description: 本主题包含有关量度定义和使用 Analytics 作为 Target 报表源 (A4T) 的常见问题解答。
title: 量度定义 - A4T 常见问题解答
feature: a4t troubleshooting
translation-type: tm+mt
source-git-commit: a12eea60aa3e66cdb54ab284fa3f942be4d56178
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 65%

---


# 量度定义 - A4T 常见问题解答

本主题包含有关量度定义和使用 Analytics 作为 Target 报表源 (A4T) 的常见问题解答。

## 活动成员资格何时到期？访客进入活动后，如果他们不再访问活动，系统会在多久之后停止在活动中计入访客的操作？ {#section_41B4958F33534E4B96DEE0C981227A79}

默认情况下，活动会在访客与活动进行最后一次交互后的第 90 天到期。如果需要，可以请求客户关怀团队调整该到期时间。但是，这是针对所有活动的全局设置，不能仅针对一个案例进行调整。

## 在配置我的目标模型时，为什么无法访问“高级设置”选项？ {#adv-settings}

“ [!UICONTROL 高级设置] ”选项不适用于用 [!DNL Analytics] 作报告源(A4T)的活动。

对于使用A4T的活动，目标度量将始终使用“增[!UICONTROL 量计数并保持活动中的用户]”和“[!UICONTROL 每次印象]”设置。 这是不可 *配置的* 。

对于非A4T活动，您可以使用“高级 [设置”选项](/help/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B) ，管理衡量成功的方式。 选项包括添加依赖项、选择是让用户处于活动中还是删除依赖项，以及是对每个进入者还是每次印象计数一次度量。 通过单击 [!UICONTROL 垂直椭圆] >高级设置，在非A4T活动中访问 [!UICONTROL 高级设置选项]，如下所示：

![高级设置](/help/c-activities/r-success-metrics/assets/advanced-settings.png)

## 什么是计算量度？它们是如何取代过去使用的 SiteCatalyst:Event mbox 的？{#section_D59F4719E6B94758A2187427C17F8EF3}

通过计算量度，您可以创建从区段或数学计算派生的自定义量度。过去，您可能使用过 `SiteCatlayst:Event` mbox，例如其中 `evar27=shoes`，事件为 `purchase`；现在，您可以创建一个区段，其中 `evar27=shoes`，然后再创建一个计算量度，其中事件为 `purchase`，并且应用创建的区段。使用计算量度的好处是此类量度可以随时创建，即使活动开始后也可以创建。创建之后，便可以在 Analytics 的任何报表中使用此类量度。

## A4T 是否可将转化归因于多个营销活动？ {#section_7F15C727206440CD86B3A8CE77087DF9}

是. 使用“完全分配”设置可实现这一点。
