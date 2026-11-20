---
keywords: 设置;优先级
description: 了解[!DNL Adobe Target]如何根据您使用的[!DNL Target]界面和活动创建功能，以不同的方式确定要交付给页面的活动（或多个活动）。
title: '[!DNL Target]如何为不同的活动分配优先级？'
feature: Activities
exl-id: c32f1699-e564-40dd-8ff1-7c75a672c6ef
TQID: 'https://experienceleague.adobe.com/KSkJ1CDkd4hgwnLQ1RKn8l8r2MDIO-6flcHcdN0c0oQ'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 7eede3484d524e87127de9147aa786484fc87c7d
workflow-type: tm+mt
source-wordcount: '1043'
ht-degree: 19%
---
# 优先级 {#priority}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解[!DNL Adobe Target]如何根据体验编辑器和正在使用的[!DNL Target]请求的类型，决定要将哪些活动交付到页面。

>[!ENDSHADEBOX]

[!DNL Adobe Target]根据您使用的[!DNL Target]界面和活动创建功能([**[!UICONTROL 可视化体验编辑器(VEC)]**](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md)或[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md))，以不同的方式确定要交付给页面的活动（一个或多个）。 下表汇总了三种情况，这些情况将在以下各节中详述。

| 场景 | 可以投放的活动 | 返回的内容 |
|---|---|---|
| 仅&#x200B;**[!UICONTROL 可视化体验编辑器]**，或仅具有全局[!DNL Target]请求的&#x200B;**[!UICONTROL 基于表单的体验编辑器]** | 多个 | 所有匹配活动的内容。 如果选择器重叠，则会显示优先级最高的活动的内容。 |
| **[!UICONTROL 基于表单的体验编辑器]**&#x200B;和&#x200B;**[!UICONTROL 可视化体验编辑器]** | 多个 | 如果基于表单的活动具有最高优先级，则包括其内容和所有匹配VEC活动的内容。 如果VEC活动具有最高优先级，则仅所有匹配VEC活动的内容。 |
| 具有非全局[!DNL Target]请求的&#x200B;**[!UICONTROL 基于表单的体验编辑器]** | 每个调用一个 | 最高优先级匹配活动的内容。 |

## VEC或带有全局请求的[!UICONTROL 基于表单的体验编辑器] {#section_4A0A317DFED345649B58B0CB5B410C8B}

如果贵公司专门使用VEC，则可以为同一调用返回来自多个活动的内容。 活动将使用以下决策流程来交付：

1. [!DNL Target]服务器调用达到[!DNL Target]。 调用中携带有有关所请求页面的URL的信息。
1. [!DNL Target]提取该URL上运行的每个活动。 这些活动是投放的候选对象。
1. [!DNL Target]尝试将访客与候选活动进行匹配。

   {{visitor-matching}}

1. 访客匹配的所有活动和体验的内容将返回到该页面，因此可以在同一调用中交付来自多个活动的内容。
1. [!DNL Target]比较每个活动内容引用的[CSS选择器](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md)。 如果活动引用不同的选择器，则会显示所有内容。
1. 如果选择器重叠或重复，则会显示最高优先级活动的内容。

   >[!IMPORTANT]
   >
   >[!DNL Target]返回页面上所有活动的内容（从具有最低优先级的内容开始），然后按优先级从最低到最高的顺序被每个活动覆盖。 通常，这会导致显示最高优先级的内容。 但是，如果较低优先级的活动更改了页面的DOM结构，则较高优先级的活动可能无法识别页面结构，因此会显示较低优先级的内容。

1. 如果多个活动共享一个优先级，则应用分层。 如果只有一个活动具有受众定位，则会显示该活动。 如果所有活动或没有任何活动具有定位，则会显示先批准的活动。
1. 页面上运行的所有活动的结果会进行计数，并反映在报表中。

## [!UICONTROL 基于表单的体验编辑器]和VEC {#section_4620253E1CE942DD830724C7822B175F}

如果您的公司使用[!UICONTROL 基于表单的体验编辑器] *和* VEC，则可以交付多个[!UICONTROL 基于表单的体验编辑器]和VEC活动中的内容。 以前，基于表单的工作流中只能交付一个活动。 可投放的基于表单的活动数量不再有限制。

活动交付使用以下决策流程来确定：

1. [!DNL Target]服务器调用达到[!DNL Target]。 调用中携带有关[!DNL Target]请求和URL的信息。
1. [!DNL Target]提取该[!DNL Target]请求中运行的每个活动。 这些活动是投放的候选对象。
1. [!DNL Target]尝试将访客与候选活动进行匹配。

   {{visitor-matching}}

1. [!DNL Target]检查哪些匹配的活动具有最高优先级，以及该活动是在[!UICONTROL 基于表单的体验编辑器]中还是在在VEC中创建。
1. 如果基于表单的活动具有最高优先级，则其内容将与所有匹配VEC活动的内容一起返回。
1. 如果VEC活动具有最高优先级，则会返回所有匹配VEC活动的内容，但不会返回任何基于表单的活动内容。
1. 页面上运行的所有活动的结果会进行计数，并反映在报表中。

**示例**

存在两个活动：一个针对品牌搜索关键词“耐克”，另一个针对非品牌关键词“运动鞋”。 检查两个活动的优先级。 如果Nike活动的优先级较高，则会显示其内容。 如果“运动鞋”活动具有较高优先级，则会显示该活动内容。

如果这两个定位活动具有相同的优先级，则会显示两个活动中最近查看过的活动。 如果访客是第一次访问页面，则会显示两个活动中最近激活的活动。

## 具有非全局请求的[!UICONTROL 基于表单的体验编辑器] {#section_C3F5F09B0B2D4EF795C5929D5C426A8C}

如果您的公司在基于表单的编辑器中使用[!DNL Target]请求而不是全局[!DNL Target]请求，则每次调用只能返回一个活动中的内容。 活动交付使用以下决策流程来确定：

1. [!DNL Target]服务器调用达到[!DNL Target]。 调用中携带有关[!DNL Target]请求和URL的信息。
1. [!DNL Target]提取该[!DNL Target]请求中运行的每个活动。 这些活动是投放的候选对象。
1. [!DNL Target]尝试将访客与最高优先级的候选活动进行匹配。

   {{visitor-matching}}

1. 如果多个活动共享一个优先级，则应用分层。 如果只有一个活动具有受众定位，则会显示该活动。 如果所有活动或没有任何活动具有定位，则会显示先批准的活动。
1. 该单个活动的内容将返回到页面。

## 示例 {#section_F6A788AAC3884A2FA03E47F0557A1213}

>[!NOTE]
>
>根据您的设置，优先级值会有所不同。 您可以使用&#x200B;**[!UICONTROL 低]**、**[!UICONTROL Medium]**&#x200B;或&#x200B;**[!UICONTROL 高]**&#x200B;的旧设置，也可以启用0到999的细粒度优先级。 有关详细信息，请参阅[活动设置](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_DCBDC354261F420EBD4B43EA34947BAC)。

**两个活动只使用在[!UICONTROL 可视化体验编辑器]中为不同选择器创建的选件**

* 活动 1：target-global-mbox，selector1，visualExpCompOffer1，低优先级
* 活动 2：target-global-mbox，selector2，visualExpCompOffer2，高优先级

响应：visualExpCompOffer1，visualExpCompOffer2

**两个活动只使用在[!UICONTROL 可视化体验编辑器]中为同一选择器创建的选件**

* 活动 1：target-global-mbox，selector1，visualExpCompOffer1，低优先级
* 活动 2：target-global-mbox，selector1，visualExpCompOffer2，高优先级

响应：visualExpCompOffer1，visualExpCompOffer2

## 培训视频：活动设置(3:02)

以下视频包含有关活动设置的信息。

* 输入活动的目的
* 设置活动的优先级
* 计划活动的开始和结束时间
* 添加报表受众以创建报表筛选器
* 输入活动的注释

>[!VIDEO](https://video.tv.adobe.com/v/17381)
