---
keywords: 发行说明；版本；更新；未来版本；增强；新功能；修复；更新；预发行；抢先体验
description: 了解即将发布的 [!DNL Adobe Target]版本中包括的新功能、增强功能和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 2812132c2720f54fa7bee2b0a5e16623362fdc33
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 34%

---

# [!DNL Target] 发行说明（预发行版本）

本文包含即将发布的 [!DNL Adobe Target] 版本的预发行信息，包括 SDK、API 和 JavaScript 库。

**上次更新日期：2025年7月10日**

>[!NOTE]
>
>* 发布日期、功能及其他信息如有更改，恕不另行通知。
>
>* 要查看有关当前版本的信息，请参阅[Target发行说明](release-notes.md)。
>
>* 括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target Standard/Premium] 25.7.3（2025年7月24日）

由于最近发现的问题（主要与复杂的客户自定义相关），此版本包含以下修复和更新：

**活动**

+++查看详细信息
* 修复了Builder类中的`buildViews`方法不正确地将`viewMaxLocalId`设置为视图总计数而不是分配的最高值`viewLocalId`的问题。 (TGT-53207)

+++

**Form-Based Experience Composer（基于表单的体验编辑器）**

+++查看详细信息
* 修复了在创建或编辑[!UICONTROL Form-Based Experience Composer] (AP)活动时，在&#x200B;**[!UICONTROL Manage Content]**&#x200B;中单击![图标（ ](/help/main/assets/icons/Experience.svg)管理内容图标[!UICONTROL Automated Personalization]）后导致编辑器崩溃的问题。 (TGT-53047)

+++

**推荐**

+++查看详细信息
* 修复了一个问题，该问题导致[!UICONTROL Catalog Search]在滚动到列表底部时无法加载其他结果，从而恢复与旧版UI一致的行为。 (TGT-53088)
* 修复了在更新的[!UICONTROL Number of Products] UI中[!UICONTROL Collections]页面中缺少[!DNL Target]列的问题。 列现在可正确显示，并恢复预期的功能。 (TGT-53168)
* 修复了[!UICONTROL Collection]规则未根据规则正确过滤的问题。 (TGT-53254)
* 修复了阻止从[!UICONTROL Criteria Details]对话框中删除项目的问题。 (TGT-53245)
* 修复了导致无法打开或无法与无名称的产品交互的问题。 选择返回未命名结果的环境时，出现此问题，导致无法访问产品详细信息。 (TGT-53007)
* 修复了在选择某些产品时导致[!UICONTROL Catalog Search]页面崩溃并显示空白屏幕的问题。 (TGT-53087)

+++

**可视化体验编辑器 (VEC)**

+++查看详细信息

* 修复了VEC中的一个问题：将修改应用于视图会导致重复并触发“用户输入无效”错误。 (TGT-52886)
* 修复了在VEC中配置图像选件时，[!UICONTROL Undo]和[!UICONTROL Insert Before]选项的[!UICONTROL Insert After]功能存在的问题。

  以前，在图像选件上撤消[!UICONTROL Insert Before]或[!UICONTROL Insert After]操作会导致不一致的行为或无法正确还原修改，尤其是在旧版[!DNL Target] UI中创建的活动中。 此问题已得到解决，以确保撤消操作现在能够可靠地用于这些修改。 (TGT-52809)

+++

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明： Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
