---
keywords: FAQ;常见问题解答;Analytics for Target;A4T;量度;量度定义
description: 查找有关量度定义和使用Analytics for [!DNL Target] (A4T)的问题的答案。 A4T允许您将Analytics报表用于Adobe [!DNL Target] 活动。
title: 可在何处找到有关A4T的量度定义的信息？
feature: Analytics for Target (A4T)
exl-id: 97442622-ba6d-46f8-bfac-72638875d889
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 31%

---

# 量度定义 - A4T 常见问题解答

本主题包含有关量度定义和使用[!DNL Adobe Analytics]作为[!DNL Adobe Target] (A4T)报表源的常见问题解答。

## 活动成员资格何时到期？访客进入活动后，如果不再看到该活动，则其操作将在活动中计入多长时间？ {#section_41B4958F33534E4B96DEE0C981227A79}

+++回答
活动的默认过期时间是访客上次与活动交互后的90天。 如果需要，ClientCare可以调整此设置。 但是，这是针对所有活动的全局设置，不能仅针对一个案例进行调整。

+++

## 在配置目标量度时，为何无法访问高级设置选项？ {#adv-settings}

+++回答
[!UICONTROL Advanced Settings]选项不适用于使用[!DNL Analytics]作为报表源(A4T)的活动。

对于使用A4T的活动，目标量度始终使用“[!UICONTROL Increment Count & Keep User in Activity]”和“[!UICONTROL On Every Impression]”设置。 这些设置是&#x200B;*不可配置的*。

对于非A4T活动，您可以使用[高级设置选项](/help/main/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B)来管理衡量成功的方式。 选项包括添加依赖项、选择是将用户保留在活动中还是将其删除，以及是为每个参加者还是每次展示都计算一次量度。 在非A4T活动中通过单击垂直省略号> [!UICONTROL Advanced Settings]访问[!UICONTROL Advanced Settings]选项，如下所示：

![高级设置](/help/main/c-activities/r-success-metrics/assets/advanced-settings.png)

+++

## 什么是计算量度？它们是如何取代过去使用的 SiteCatalyst:Event mbox 的？ {#section_D59F4719E6B94758A2187427C17F8EF3}

+++回答
计算量度允许您创建从区段或数学计算派生的自定义量度。 过去，您可能使用过 `SiteCatlayst:Event` mbox，例如其中 `evar27=shoes`，事件为 `purchase`；现在，您可以创建一个区段，其中 `evar27=shoes`，然后再创建一个计算量度，其中事件为 `purchase`，并且应用创建的区段。这些量度可以随时创建，即使是在活动开始之后。 创建之后，便可以在 Analytics 的任何报表中使用此类量度。

+++

## A4T 是否可将转化归因于多个营销活动？ {#section_7F15C727206440CD86B3A8CE77087DF9}

+++回答
是，使用“完全分配”设置。

+++