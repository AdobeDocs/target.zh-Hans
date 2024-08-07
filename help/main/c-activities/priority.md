---
keywords: 设置;优先级
description: 了解 [!DNL Adobe Target] 如何根据您使用的 [!DNL Target] 界面和活动创建功能，以不同的方式确定要交付给页面的活动（或多个活动）。
title: ' [!DNL Target] 如何为不同的活动分配优先级？'
feature: Activities
exl-id: c32f1699-e564-40dd-8ff1-7c75a672c6ef
source-git-commit: be6e45ff301f549eb5be24a65b05c4a9c1cd6089
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 37%

---

# 优先级

[!DNL Adobe Target]根据您使用的[!DNL Target]界面和活动创建功能（[[!UICONTROL Visual Experience Composer (VEC)]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md)或[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)），以不同的方式确定要交付给页面的活动（一个或多个）。

## 仅[!UICONTROL Visual Experience Composer]或仅使用全局[!DNL Target]请求的[!UICONTROL Form-Based Experience Composer] {#section_4A0A317DFED345649B58B0CB5B410C8B}

如果贵公司专门使用VEC，则可以为同一调用返回来自多个活动的内容。 活动将使用以下决策流程来交付：

1. [!DNL Target]服务器调用到达包含有关URL信息的[!DNL Target]。
1. [!DNL Target]提取该URL上运行的每个活动。
1. [!DNL Target]次尝试将访客匹配到活动中。

   如果访客已经在[!UICONTROL A/B Test]或[!UICONTROL Multivariate Test]活动中，则它们将与该活动匹配，直到它们转换。 如果它们以前处于[!UICONTROL Experience Targeting]活动中，则必须再次匹配该活动。 如果访客符合相应的受众规则，则他们将进入这些活动和特定的体验。

1. 访客匹配的所有活动和体验的内容会返回到页面。
1. 如果每个活动的内容引用不同的[CSS选择器](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337)，则会显示所有内容。

   如果 CSS 选择器出现重叠或重复，则会显示具有最高优先级的活动内容。页面上运行的所有活动的结果会进行计数，并反映在报表中。

   >[!IMPORTANT]
   >
   >[!DNL Target]返回页面上所有活动的内容（从具有最低优先级的内容开始），然后按优先级从最低到最高的顺序被每个活动覆盖。 通常，这会导致显示最高优先级的内容。 但是，如果较低优先级的活动更改了页面的DOM结构，则较高优先级的活动可能不会识别页面结构，因此会显示较低优先级的内容。 页面上运行的所有活动的结果会进行计数，并反映在报表中。

1. 如果多个活动共享优先级，则有两个分界符：

   * 如果只有一个活动具有受众定位，则会显示该活动。
   * 如果所有活动或无活动具有定位，则会显示首先批准的活动。

## [!UICONTROL Form-Based Experience Composer] 和 [!UICONTROL Visual Experience Composer] {#section_4620253E1CE942DD830724C7822B175F}

如果您的公司使用[!UICONTROL Form-Based Experience Composer] *和* VEC，则来自多个[!UICONTROL Form-Based Experience Composer]和VEC活动的内容可以交付。 以前，基于表单的工作流中只能交付一个活动。 可投放的基于表单的活动数量不再有限制。

活动交付使用以下决策流程来确定：

1. [!DNL Target]服务器调用针对[!DNL Target]，其中包含有关[!DNL Target]请求和URL的信息。
1. [!DNL Target]提取该[!DNL Target]请求中运行的每个活动。
1. [!DNL Target]次尝试将访客匹配到活动中。

   如果访客已经在[!UICONTROL A/B Test]或[!UICONTROL Multivariate Test]活动中，则它们将与该测试匹配，直到它们转换。 如果它们以前处于[!UICONTROL Experience Targeting]活动中，则必须再次匹配该活动。 如果访客符合相应的受众规则，则他们将进入这些活动和特定的体验。

1. 如果基于表单的活动具有最高优先级，则该活动内容会与VEC活动中的所有匹配活动内容一起返回。
1. 如果某个VEC活动具有最高优先级，则会返回所有匹配VEC活动中的内容，但不会返回任何基于表单的活动内容。

   页面上运行的所有活动的结果会进行计数，并反映在报表中。

**示例**

如果您有两个活动，一个针对品牌搜索关键词“Nike”，另一个针对非品牌关键词“运动鞋”，则会检查这两个活动的优先级。 如果“Nike”活动具有较高优先级，则会显示该活动内容。如果“运动鞋”活动具有较高优先级，则会显示该活动内容。

如果这两个定位活动具有相同的优先级，则会显示两个活动中最近查看过的活动。如果访客是第一次访问页面，则会显示两个活动中最近激活的活动。

## 具有非全局[!DNL Target]请求的[!UICONTROL Form-Based Experience Composer] {#section_C3F5F09B0B2D4EF795C5929D5C426A8C}

如果您的公司在基于表单的编辑器中使用[!DNL Target]请求而不是全局[!DNL Target]请求，则每次调用只能返回一个活动中的内容。 活动交付使用以下决策流程来确定：

1. [!DNL Target]服务器调用到达了[!DNL Target]，其中包含有关[!DNL Target]请求和URL的信息。
1. [!DNL Target]提取该[!DNL Target]请求中运行的每个活动。
1. [!DNL Target]尝试将访客与最高优先级的活动进行匹配。

   如果访客已经在[!UICONTROL A/B Test]或[!UICONTROL Multivariate Test]活动中，则它们将与该活动匹配，直到它们转换。 如果它们以前处于[!UICONTROL Experience Targeting]活动中，则必须再次匹配该活动。 如果访客符合相应的受众规则，则他们将进入这些活动和特定的体验。

1. 如果多个活动共享优先级，则有两个分界符：

   * 如果只有一个活动具有受众定位，则会显示该活动。
   * 如果所有活动或无活动具有定位，则会显示首先批准的活动。

## 示例 {#section_F6A788AAC3884A2FA03E47F0557A1213}

>[!NOTE]
>
>根据您的设置，优先级值会有所不同。您可以使用[!UICONTROL Low]、[!UICONTROL Medium]或[!UICONTROL High]的旧版设置，也可以启用0到999的细粒度优先级。 有关详细信息，请参阅[活动设置](/help/main/c-activities/activity-settings.md#task_C6B2FF8374724933BE79A83549B9CD02)。

响应：offer1

**两个活动仅使用在[!UICONTROL Visual Experience Composer]中为不同的选择器创建的选件**

* 活动 1：target-global-mbox，selector1，visualExpCompOffer1，低优先级
* 活动 2：target-global-mbox，selector2，visualExpCompOffer2，高优先级

响应：visualExpCompOffer1，visualExpCompOffer2

**两个活动仅使用在[!UICONTROL Visual Experience Composer]中为同一选择器创建的选件**

* 活动 1：target-global-mbox，selector1，visualExpCompOffer1，低优先级
* 活动 2：target-global-mbox，selector1，visualExpCompOffer2，高优先级

响应：visualExpCompOffer1，visualExpCompOffer2

## 培训视频：活动设置 (3:02)

以下视频包含有关活动设置的信息。

* 输入活动的目的
* 设置活动的优先级
* 计划活动的开始和结束时间
* 添加报表受众以创建报表筛选器
* 输入活动的注释

>[!VIDEO](https://video.tv.adobe.com/v/17381)
