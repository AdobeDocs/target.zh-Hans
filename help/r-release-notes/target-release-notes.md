---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解 Adobe Target 即将发布的版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的版本中包括什么新功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: df00a36ea3440ebd959351fcfc6a24f6bd9fe8b8
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Target 发行说明（预发行版本）

本文包含预发行版本信息。发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新日期：2022 年 1 月 6 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

>[!IMPORTANT]
>
>**mbox.js 生命周期结束**：从 2021 年 3 月 31 日起，[!DNL Adobe Target] 将不再支持 mbox.js 库。2021 年 3 月 31 日之后，所有从 mbox.js 进行的调用都会失败，并影响您通过提供默认内容而运行 [!DNL Target] 活动的页面。
>
>请迁移到新 [!DNL Adobe Experience Platform Web SDK] 或 at.js JavaScript 库的最新版本，以避免您的网站出现任何潜在问题。有关更多信息，请参阅[概述：为客户端 Web 实现 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

## [!DNL Target Standard/Premium] 22.1.1（2022年1月6日）

此版本包含以下新功能：

| 功能 | 详细信息 |
| --- | --- |
| 在Target活动中使用选件决策 | 您现在可以使用 [!DNL Adobe Journey Optimizer] 优惠决策 [!DNL Adobe Target] A/B测试和体验定位(XT)活动，确定并在Web和移动设备上为访客提供下一个最佳选件。<br>有关更多信息，请参阅使用选件决策。<br>**注意**:此功能适用于 [!DNL Target] 还具有访问Offer decisioning和 [!DNL Target] 基于Experience Platform Web SDK的Adobe实施。 |

## at.js 版本 2.7.0（2021 年 10 月 28 日）

此版本包含以下增强功能：

* 添加了对 [Web 组件](https://developer.mozilla.org/en-US/docs/Web/Web_Components)的支持。在自定义元素以及自定义元素内部的元素上创建和测试个性化的体验及方案时，需要此版本的 at.js。此功能包括在 [!DNL Target Standard/Premium] 21.10.5 版本中。

## [!DNL Target Standard/Premium] 21.10.5（2021 年 10 月 28 日）

此维护版本包含以下增强功能：

| 功能 | 详细信息 |
| --- | --- |
| 可视化体验编辑器 (VEC) | 添加了对 [Web 组件](https://developer.mozilla.org/en-US/docs/Web/Web_Components)的支持。可以在自定义元素以及自定义元素内部的元素上创建和测试个性化的体验和方案。<br>有关更多信息，请参阅[可视化体验编辑器选项](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#custom)。 |

## [!DNL Target Standard/Premium] 21.10.4（2021 年 10 月 21 日）

此维护版本包含以下增强功能：

| 功能 | 详细信息 |
| --- | --- |
| 基于购物车的推荐 | 添加了新的算法系列，可根据访客购物车的内容提供推荐。<br>有关更多信息，请参阅[创建标准](/help/c-recommendations/c-algorithms/create-new-algorithm.md)中的“基于购物车”，以及[计划和实施推荐](/help/c-recommendations/plan-implement.md)中的“购物车添加/购物车查看/结账页面”和“排除访客购物车中已有的商品”。 |

## [!DNL Target Standard/Premium] 21.10.3（2021 年 10 月 19 日）

此维护版本包含以下增强功能、修复和更改：

* 修复了阻止客户在 [!DNL Analysis Workspace] 中通过单击 [!DNL Target] 活动报告中的[!UICONTROL 在 Analytics 中查看]按钮来打开 [!UICONTROL A4T] 面板的问题。（TGT-42099、TGT-42100）
* 修复了在使用[!UICONTROL 基于表单的体验编辑器]来编辑 [!UICONTROL A/B 测试]和[!UICONTROL 体验定位] (XT) 活动时，导致[!UICONTROL 编辑设计]按钮不显示的问题。(TGT-41980)
* 修复了在创建新的[!UICONTROL 推荐]活动时，导致在标准选择中不显示[!UICONTROL 兼容]复选框的问题。(TGT-42053)
* 修复了由于缺少 [!DNL Analytics] 权限而无法选择 [!DNL Analytics] 作为报表源 (A4T) 时显示的不正确的错误消息。(TGT-41954)
* 实施了多个辅助功能修复，以改进 [!DNL Target] UI 中的键盘导航功能。

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
