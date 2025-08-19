---
keywords: 发行说明；版本；更新；未来版本；增强；新功能；修复；更新；预发行；抢先体验
description: 了解即将发布的 [!DNL Target]版本中包括的新功能、增强功能和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 3b80ca92a445bbdab6202a28c03130d24920dfd0
workflow-type: tm+mt
source-wordcount: '893'
ht-degree: 16%

---

# [!DNL Target] 发行说明（预发行版本）

本文包含即将发布的 [!DNL Adobe Target] 版本的预发行信息，包括 SDK、API 和 JavaScript 库。

**上次更新日期：2025年8月19日**

>[!NOTE]
>
>* 发布日期、功能及其他信息如有更改，恕不另行通知。本文中的信息会经常更新，尤其是在发布版本之前。
>
>* 要查看有关当前版本的信息，请参阅[Target发行说明](release-notes.md)。
>
>* 括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target Standard/Premium] 25.8.3（2025年8月21日）

此版本包含以下更新和修复：

**优惠决策**

+++查看详细信息
* **修复了阻止客户在更新的UI中编辑决策优惠和选择特定页面元素的问题**：在更新的活动创建流程中，客户无法在可视化体验编辑器(VEC)中编辑现有决策优惠或选择特定页面元素。 决策优惠显示为HTML优惠不正确，编辑期间所做的更改未保存。 此外，某些区域URL（如日本站点）无法在VEC中正确加载，阻止活动创建和更新。 (TGT-53425)
* **修复了在保存之后[!UICONTROL Offer Decision]选择器无法修改和意外更改的问题**：在更新的活动创建过程中，客户无法按预期修改[!UICONTROL Offer Decision]选择器。 尝试更改选择器失败，选择器在保存后恢复到不正确的值。 这会导致决策选件从可视化体验编辑器(VEC)中消失，阻止进一步编辑。 (TGT-53433)
* **修复了保存[!UICONTROL Offer Decisions]后**&#x200B;从活动中消失的问题：在活动创建过程中添加的[!UICONTROL Offer Decisions]在保存并重新打开活动后未保留。 在编辑动态内容并使用特定选择器和属性插入[!UICONTROL Offer Decisions]时，出现此问题。 (TGT-53434)

+++

**推荐**

+++查看详细信息
* **修复了Recs UI中的自定义标准CSV下载返回404错误的问题**：修复了客户无法在活动创建过程中下载自定义标准CSV的问题。 (TGT-51966)
* **修复了[!UICONTROL Catalog Search]**&#x200B;中图像加载不一致的问题：修复了[!UICONTROL &#x200B; Catalog Search]中的缩略图和图像在活动创建过程中加载不一致的问题。 除非“缩略图URL”列可见，并且某些产品图像在导航或搜索操作后已加载部分或完全未加载，否则图像无法显示。 (TGT-52778)
* **修复了在复制的体验中编辑推荐会影响原始体验的问题**：客户报告在复制的体验中修改推荐无意中更改了原始体验。 具体而言，在活动创建过程中复制体验B并编辑其设计或标准后，相同的更改会反映在原始体验B中，尽管它们是单独的实体。 (TGT-53369)
* **修复了对重复体验的更改无意中影响活动中原始体验的问题：**&#x200B;客户报告说，在活动中复制体验并分配新受众时，对复制体验的设计或标准所做的任何更改也会反映在原始体验中。 即使没有直接对原始版本进行任何编辑，也会发生这种情况，从而影响在同一活动中创建独立变体的能力。 (TGT-53361)
* **修复了[!UICONTROL Recommendation Catalog]间歇性地无法显示完整产品属性数据的问题**：在更新的[!DNL Recommendations] UI中，客户遇到以下问题：即使数据存在于馈送中，某些产品属性（如消息）仍无法一致地显示在目录搜索结果中。 此问题要求客户手动重新配置列可见性以检索缺少的值。 (TGT-52769)
+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++查看详细信息
* **修复了活动创建过程中阻止升级到AP活动中的[!UICONTROL Targeting]步骤的问题**：修复了活动创建过程中客户无法继续到[!UICONTROL Targeting] (AP)活动中的[!UICONTROL Automated Personalization]步骤的问题（除非添加了两个位置）。 此行为与以前的体验不同，在以前的体验中，具有多个选件的单个位置便已足够。 该要求已得到纠正，允许客户继续将单个位置设置作为其AP工作流的一部分。 (TGT-53426)
* **修复了新活动创建进程未为透明图像设置fmt=png-alpha参数的问题**：在更新的UI中，在活动创建进程中插入的图像默认不再包含`fmt=png-alpha`参数，从而导致透明度丢失。 此行为与以前的UI不同，后者自动将参数附加到图像URL，并保留透明背景。 (TGT-52615)

+++

**[!UICONTROL Workspaces]**

+++查看详细信息
* **修复了以下问题：在活动创建过程中选择**&#x200B;时，受限于单个工作区的客户可以查看来自其他工作区的活动[!UICONTROL All Workspaces]：受限于一个工作区的客户意外地可以查看所有工作区的活动。 此可见性可能会对其他工作区中的实时活动造成意外更改，从而可能影响网站性能。 (TGT-53101)
* **修复了以下问题：客户在没有访问权限的情况下可以从[!UICONTROL Default Workspace]查看活动：**&#x200B;只有暂存工作区访问权限的客户能够通过活动创建流程从[!UICONTROL Default Workspace]查看活动。 尽管后端配置和访问权限正确，但仍会发生这种情况。 (TGT-53297)

+++

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明： Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
