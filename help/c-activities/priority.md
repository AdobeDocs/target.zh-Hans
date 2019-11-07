---
keywords: 设置;优先级
description: Adobe Target根据您使用的Target界面和活动创建功能（可视体验书写器或基于表单的书写器），以不同方式确定要传送到页面的活动（或活动）。
title: Adobe Target中的优先级
topic: Standard
uuid: 114cd625-2716-4c4c-983b-a7f677717b07
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 优先级{#priority}

Target 根据您使用的 Target 界面和活动创建功能（可视化体验编辑器或基于表单的编辑器），以不同的方式来确定要交付给页面的活动（一个或多个）。

## 仅 Target Standard/Premium 可视化体验编辑器或仅使用全局 mbox 的基于表单的编辑器 {#section_4A0A317DFED345649B58B0CB5B410C8B}

如果贵公司仅使用 Target Standard/Premium 和可视化体验编辑器，则可以对同一个调用返回多个活动的内容。活动将使用以下决策流程来交付：

1. Target 服务器调用到达 Target，并提供有关 URL 的信息。
1. Target 提取该 URL 上运行的所有活动。
1. Target 尝试将访客匹配到活动。

   如果访客已经处于 A/B 测试或多变量测试中，则会将他们匹配到该测试，直至他们实现转化为止。如果访客之前处于体验定位活动中，则必须将他们再次匹配到该活动。如果访客符合相应的受众规则，则他们将进入这些活动和特定的体验。

1. 访客匹配的所有活动和体验的内容会返回到页面。
1. 如果每个活动的内容引用了不同的 [CSS 选择器](../c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337)，则会显示所有内容。

   如果 CSS 选择器出现重叠或重复，则会显示具有最高优先级的活动内容。页面上运行的所有活动的结果会进行计数，并反映在报表中。

   >[!IMPORTANT]
   >
   >Target 会返回页面上所有活动的内容（从具有最低优先级的内容开始），而返回的内容随后会按优先级从最低到最高的顺序被每个活动覆盖。因此，在大多数情况下，会显示具有最高优先级的内容。但是，如果具有较低优先级的活动更改了页面的 DOM 结构，则具有较高优先级的活动可能无法识别页面结构，因此会显示具有较低优先级的内容。页面上运行的所有活动的结果会进行计数，并反映在报表中。

1. 如果多个活动具有相同的优先级，则会按以下两种规则确定要显示的活动：

   * 如果只有一个活动具有受众定位，则会显示该活动。
   * 如果所有活动都具有或都不具有定位，则会显示最先获得批准的活动。

## Target Standard/Premium 基于表单的编辑器和 Target Standard/Premium 可视化体验编辑器 {#section_4620253E1CE942DD830724C7822B175F}

>[!NOTE]
>
>此信息还适用于之前在 [!DNL Target Classic] 中创建的所有营销活动。

如果贵公司同时使用 Target Standard/Premium 基于表单的编辑器和 Target Standard/Premium 可视化体验编辑器，则可以交付多个可视化体验编辑器活动的内容，但只能交付基于表单的工作流中的一个活动。活动交付使用以下决策流程来确定：

1. Target 服务器调用到达 Target，并提供有关 mbox 和 URL 的信息。
1. Target Classic 和 Standard 提取该 mbox 中运行的所有活动。
1. Target 尝试将访客匹配到活动。

   如果访客已经处于 A/B 测试或多变量测试中，则会将他们匹配到该测试，直至他们实现转化为止。如果访客之前处于体验定位活动中，则必须将他们再次匹配到该活动。如果访客符合相应的受众规则，则他们将进入这些活动和特定的体验。

1. 如果基于表单的活动具有最高优先级，则会返回该活动内容，以及可视化体验编辑器活动中所有匹配的活动内容。
1. 如果可视化体验编辑器活动具有最高优先级，则会返回所有匹配的可视化体验编辑器活动的内容，但不会返回任何 Target Classic 活动或基于表单的活动。

   页面上运行的所有活动的结果会进行计数，并反映在报表中。

**示例**

如果您有两个活动，一个定位品牌搜索关键词 Nike，而另一个定位非品牌关键词“运动鞋”，则会检查两个活动的优先级。如果“Nike”活动具有较高优先级，则会显示该活动内容。如果“运动鞋”活动具有较高优先级，则会显示该活动内容。

如果这两个定位活动具有相同的优先级，则会显示两个活动中最近查看过的活动。如果访客是第一次访问页面，则会显示两个活动中最近激活的活动。

## 使用非全局 mbox 的 Target Standard/Premium 基于表单的编辑器 {#section_C3F5F09B0B2D4EF795C5929D5C426A8C}

>[!NOTE]
>
>此信息还适用于之前在 Target Classic 中创建的所有营销活动。

如果贵公司在基于表单的编辑器中使用全局 mbox 以外的 mbox，则每次调用只能返回一个活动的内容。活动交付使用以下决策流程来确定：

1. Target 服务器调用到达 Target，并提供有关 mbox 和 URL 的信息。
1. Target 提取该 mbox 中运行的所有活动。
1. Target 尝试将访客匹配到具有最高优先级的活动。

   如果访客已经处于 A/B 测试或多变量测试中，则会将他们匹配到该测试，直至他们实现转化为止。如果访客之前处于体验定位活动中，则必须将他们再次匹配到该活动。如果访客符合相应的受众规则，则他们将进入这些活动和特定的体验。

1. 如果多个活动具有相同的优先级，则会按以下两种规则确定要显示的活动：

   * 如果只有一个活动具有受众定位，则会显示该活动。
   * 如果所有活动都具有或都不具有定位，则会显示最先获得批准的活动。

## 示例 {#section_F6A788AAC3884A2FA03E47F0557A1213}

>[!NOTE]
>
>根据您的设置，优先级值会有所不同。您可以使用“低”、“中”或“高”的传统优先级设置，也可以启用 0 至 999 的细粒度优先级设置。有关更多信息，请参阅[活动设置](../c-activities/activity-settings.md#task_C6B2FF8374724933BE79A83549B9CD02)。

**两个 Target Classic 营销活动使用非全局 mbox**

* 营销活动 1：homePageHero，offer1，高优先级
* 营销活动 2：homePageHero，offer2，低优先级

响应：offer1

**两个活动在不同的选择器中仅使用在可视化体验编辑器中创建的选件**

* 活动 1：target-global-mbox，selector1，visualExpCompOffer1，低优先级
* 活动 2：target-global-mbox，selector2，visualExpCompOffer2，高优先级

响应：visualExpCompOffer1，visualExpCompOffer2

**两个活动在同一个选择器中仅使用在可视化体验编辑器中创建的选件**

* 活动 1：target-global-mbox，selector1，visualExpCompOffer1，低优先级
* 活动 2：target-global-mbox，selector1，visualExpCompOffer2，高优先级

响应：visualExpCompOffer1，visualExpCompOffer2

>[!NOTE]
>
>此响应与上面第二个用例中的响应相同，这是因为 Target Classic 无法处理选择器冲突。如果选择器在 DOM 和显示方面可能发生冲突，Target Standard 可捕获此类行为及其他用例（通常是在体验编辑器级别或营销活动模拟模式下捕获）。

**两个活动使用在可视化体验编辑器中创建的选件，并且还具有两个 Target Classic 营销活动**

* 活动 1：target-global-mbox，selector1，visualExpCompOffer1，中高优先级
* 活动 2：target-global-mbox，selector2，visualExpCompOffer2，低优先级
* 营销活动 1：target-global-mbox，offer1，高优先级
* 营销活动 2：target-global-mbox，offer2，低优先级

响应：offer1，visualExpCompOffer2，visualExpCompOffer1

>[!NOTE]
>
>组合响应的顺序是：先响应 Classic 内容（如在用例 1 中一样，仅会提供一个 Classic 响应），然后按优先级从低到高的顺序依次响应可视化体验编辑器选件。

## 培训视频：活动设置 (3:02)

以下视频包含有关活动设置的信息。

* 输入活动的目的
* 设置活动的优先级
* 计划活动的开始和结束时间
* 添加报表受众以创建报表筛选器
* 输入活动的注释

>[!VIDEO](https://video.tv.adobe.com/v/17381?captions=chi_hans)