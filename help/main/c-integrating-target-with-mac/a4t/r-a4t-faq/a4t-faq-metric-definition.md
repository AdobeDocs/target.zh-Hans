---
keywords: FAQ;常见问题解答;Analytics for Target;A4T;量度;量度定义
description: 查找有关量度定义和使用Analytics for [!DNL Target] (A4T)。 A4T允许您将Analytics报表与Adobe结合使用 [!DNL Target] 活动。
title: 在哪里可以找到有关A4T量度定义的信息？
feature: Analytics for Target (A4T)
exl-id: 97442622-ba6d-46f8-bfac-72638875d889
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 29%

---

# 量度定义 - A4T 常见问题解答

本主题包含有关量度定义和使用的常见问题解答 [!DNL Adobe Analytics] 作为报表源 [!DNL Adobe Target] (A4T)。

## 活动成员资格何时到期？访客进入活动后，如果再未看到活动，则在活动中计入其操作多长时间？ {#section_41B4958F33534E4B96DEE0C981227A79}

+++回答活动的默认过期时间为访客上次与活动交互后90天。 如果需要， ClientCare可以调整此设置。 但是，这是针对所有活动的全局设置，不能仅针对一个案例进行调整。

+++

## 在配置我的目标量度时，为什么无法访问高级设置选项？ {#adv-settings}

+++回答 [!UICONTROL 高级设置] 选项不适用于使用 [!DNL Analytics] 作为报表源(A4T)。

对于使用A4T的活动，目标量度始终使用[!UICONTROL 递增计数并保持用户处于活动中]&quot;和&quot;[!UICONTROL 每次展示时]“ ”设置。 这些设置包括 *not* 可配置。

对于非A4T活动，您可以使用 [“高级设置”选项](/help/main/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B) 来管理如何衡量成功。 选项包括添加依赖项、选择是将用户保留在活动中还是删除依赖项，以及是对每个参加者还是每次展示都将量度计数一次。 您可以访问 [!UICONTROL 高级设置] 选项（通过单击垂直省略号>） [!UICONTROL 高级设置]，如下所示：

![高级设置](/help/main/c-activities/r-success-metrics/assets/advanced-settings.png)

+++

## 什么是计算量度？它们是如何取代过去使用的 SiteCatalyst:Event mbox 的？ {#section_D59F4719E6B94758A2187427C17F8EF3}

+++答案计算量度允许您创建从区段或数学计算派生的自定义量度。 过去，您可能使用过 `SiteCatlayst:Event` mbox，例如其中 `evar27=shoes`，事件为 `purchase`；现在，您可以创建一个区段，其中 `evar27=shoes`，然后再创建一个计算量度，其中事件为 `purchase`，并且应用创建的区段。即使在活动开始后，也可以随时创建这些量度。 创建之后，便可以在 Analytics 的任何报表中使用此类量度。

+++

## A4T 是否可将转化归因于多个营销活动？ {#section_7F15C727206440CD86B3A8CE77087DF9}

+++回答是，使用“完全分配”设置。

+++