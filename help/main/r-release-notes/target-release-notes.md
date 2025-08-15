---
keywords: 发行说明；版本；更新；未来版本；增强；新功能；修复；更新；预发行；抢先体验
description: 了解即将发布的 [!DNL Target]版本中包括的新功能、增强功能和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 1f8fa78c2b88e179f021128a8fd3dac177dfa3dd
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 37%

---

# [!DNL Target] 发行说明（预发行版本）

本文包含即将发布的 [!DNL Adobe Target] 版本的预发行信息，包括 SDK、API 和 JavaScript 库。

**上次更新日期：2025年8月15日**

>[!NOTE]
>
>* 发布日期、功能及其他信息如有更改，恕不另行通知。本文中的信息会经常更新，尤其是在发布版本之前。
>
>* 要查看有关当前版本的信息，请参阅[Target发行说明](release-notes.md)。
>
>* 括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target Standard/Premium] 25.8.3（2025年8月21日）

此版本包含以下更新和修复：

**推荐**

+++查看详细信息
* **修复了Recs UI中的自定义标准CSV下载返回404错误的问题**：修复了客户无法在活动创建过程中下载自定义标准CSV的问题。
* **修复了[!UICONTROL Catalog Search]**&#x200B;中图像加载不一致的问题：修复了[!UICONTROL &#x200B; Catalog Search]中的缩略图和图像在活动创建过程中加载不一致的问题。 除非“缩略图URL”列可见，并且某些产品图像在导航或搜索操作后已加载部分或完全未加载，否则图像无法显示。 (TGT-52778)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++查看详细信息
* **修复了活动创建过程中阻止升级到AP活动中的[!UICONTROL Targeting]步骤的问题**：修复了活动创建过程中客户无法继续到[!UICONTROL Targeting] (AP)活动中的[!UICONTROL Automated Personalization]步骤的问题（除非添加了两个位置）。 此行为与以前的体验不同，在以前的体验中，具有多个选件的单个位置便已足够。 该要求已得到纠正，允许客户继续将单个位置设置作为其AP工作流的一部分。 (TGT-53426)

+++

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明： Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
