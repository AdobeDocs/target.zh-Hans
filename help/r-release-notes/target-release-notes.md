---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解 Adobe Target 即将发布的版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的版本中包括什么新功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 3fb58864e265653b48e851c8dff404589bb867a6
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 51%

---

# Target 发行说明（预发行版本）

本文包含预发行版本信息。发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新时间：2021 年 10 月 25 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

>[!IMPORTANT]
>
>**mbox.js 生命周期结束**：从 2021 年 3 月 31 日起，[!DNL Adobe Target] 将不再支持 mbox.js 库。2021 年 3 月 31 日之后，所有从 mbox.js 进行的调用都会失败，并影响您通过提供默认内容而运行 [!DNL Target] 活动的页面。
>
>请迁移到新 [!DNL Adobe Experience Platform Web SDK] 或 at.js JavaScript 库的最新版本，以避免您的网站出现任何潜在问题。有关更多信息，请参阅[概述：为客户端 Web 实现 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

## [!DNL Target Standard/Premium] 21.10.5（2021年10月28日）

此维护版本包含以下增强功能：

| 功能 | 详细信息 |
| --- | --- |
| 可视化体验编辑器 (VEC) | 添加了 [Web组件](https://developer.mozilla.org/en-US/docs/Web/Web_Components). 可以在自定义元素和自定义元素内的元素上创建和测试个性化体验和选件。<br>此版本将与at.js版本2.7.0的发行版本一致。 |

## [!DNL Target Standard/Premium] 21.10.4（2021年10月21日）

此维护版本包含以下增强功能：

| 功能 | 详细信息 |
| --- | --- |
| 基于购物车的Recommendations | 添加了一系列新的算法，用于根据访客购物车的内容提供推荐。<br>有关更多信息，请参阅 [创建标准](/help/c-recommendations/c-algorithms/create-new-algorithm.md) 和“购物车加货/购物车查看/结账页面”以及“排除访客购物车中已有的项目”(位于 [规划和实施Recommendations](/help/c-recommendations/plan-implement.md). |

## [!DNL Target Standard/Premium] 21.10.3（2021年10月19日）

此维护版本包含以下增强、修复和更改：

* 修复了阻止客户打开 [!UICONTROL A4T] 面板 [!DNL Analysis Workspace] 单击 [!UICONTROL 在Analytics中查看] 按钮 [!DNL Target] 活动报表。 (TGT-42099、TGT-42100)
* 修复了导致 [!UICONTROL 编辑设计] 按钮，在编辑时不显示 [!UICONTROL A/B测试] 和 [!UICONTROL 体验定位] (XT)活动 [!UICONTROL 基于表单的体验编辑器]. (TGT-41980)
* 修复了阻止 [!UICONTROL 兼容] 复选框，以在创建新 [!UICONTROL Recommendations] 活动。 (TGT-42053)
* 修复了在无法选择 [!DNL Analytics] 作为报表源(A4T)，因为 [!DNL Analytics] 权限。 (TGT-41954)
* 实施了多项辅助功能修复，以改进 [!DNL Target] UI。

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
