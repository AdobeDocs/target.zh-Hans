---
keywords: FAQ;常见问题解答;Analytics for Target;A4T;量度;量度定义
description: 查找有关量度定义和使用Analytics for 目标(A4T)的问题的答案。 A4T允许您将Analytics报告用于Adobe Target活动。
title: 在哪里可以找到有关A4T量度定义的信息？
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: e45f0d2d2370f9c7aba2c2bd26afdd4c0e401db8
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 39%

---


# 量度定义 - A4T 常见问题解答

本主题包含有关量度定义和使用[!DNL Adobe Analytics]作为[!DNL Adobe Target](A4T)的报告源的常见问题解答。

## 活动成员资格何时到期？访客进入活动后多久，如果他们再未看到该活动，他们的操作将计入该视频？{#section_41B4958F33534E4B96DEE0C981227A79}

默认情况下，活动会在访客与活动进行最后一次交互后的第 90 天到期。如果需要，ClientCare可以调整此设置。 但是，这是针对所有活动的全局设置，不能仅针对一个案例进行调整。

## 配置我的目标量度时，为什么无法访问高级设置选项？{#adv-settings}

[!UICONTROL 高级设置]选项对于使用[!DNL Analytics]作为报告源(A4T)的活动不可用。

对于使用A4T的活动，目标量度始终使用“[!UICONTROL 活动中的增量计数和保持用户”和“[!UICONTROL 每次印象]”设置。 ]这些设置&#x200B;*不可配置*。

对于非A4T活动，可使用[高级设置选项](/help/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B)管理衡量成功的方式。 选项包括添加依赖项、选择是让用户保持活动还是删除依赖项，以及是每位进入者还是每次印象中对量度计数一次。 单击垂直椭圆> [!UICONTROL 高级设置]，可以在非A4T活动中访问[!UICONTROL 高级设置]选项，如下所示：

![高级设置](/help/c-activities/r-success-metrics/assets/advanced-settings.png)

## 什么是计算量度？它们是如何取代过去使用的 SiteCatalyst:Event mbox 的？{#section_D59F4719E6B94758A2187427C17F8EF3}

通过计算量度，您可以创建从区段或数学计算派生的自定义量度。过去，您可能使用过 `SiteCatlayst:Event` mbox，例如其中 `evar27=shoes`，事件为 `purchase`；现在，您可以创建一个区段，其中 `evar27=shoes`，然后再创建一个计算量度，其中事件为 `purchase`，并且应用创建的区段。可随时创建这些量度，即使在活动开始后。 创建之后，便可以在 Analytics 的任何报表中使用此类量度。

## A4T 是否可将转化归因于多个营销活动？ {#section_7F15C727206440CD86B3A8CE77087DF9}

是，使用“完全分配”设置。
