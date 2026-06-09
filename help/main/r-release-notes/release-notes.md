---
keywords: 发行说明；新功能；版本；更新；更新；版本；增强；增强；修复；错误修复；更新；当前更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
TQID: https://experienceleague.adobe.com/-Unx6cVsw3wch2LJgPtvBYPe-10rdpiJ4v9F7tMSP08
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 391653c7a45a48c311c6a6cff358bd077f8c47b7
workflow-type: tm+mt
source-wordcount: 652
ht-degree: 41%

---

# [!DNL Target]发行说明（当前版本）

浏览[!DNL Adobe Target]中的最新功能、增强功能和修复。 这些发行说明还涵盖了[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js和其他平台组件（如果适用）的更新。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## [!DNL Target Standard/Premium] 26.6.1（2026年6月4日）

**活动**

+++查看详细信息

* [!UICONTROL 活动概述].**上的**&#x200B;不完整的活动URL 修复了[!UICONTROL 活动概述]未显示活动的完整URL的问题。 (TGT-54029)

* **活动报表中存在未本地化的日期格式。** 修复了从&#x200B;**[!UICONTROL 预设日期范围]**&#x200B;下拉列表中选择&#x200B;**最近X天**&#x200B;选项时，**[!UICONTROL 报表]**&#x200B;选项卡上未本地化日期格式的问题。 (TGT-51637)

* **无法在[!UICONTROL 位置].**&#x200B;保存具有某些GB18030字符的基于表单的活动 修复了当&#x200B;**[!UICONTROL 位置]**&#x200B;字段包含特定GB18030字符时无法保存基于表单的活动的问题。 (TGT-46980)

+++

**[!UICONTROL 受众]**

+++查看详细信息

* 创建简体中文和繁体中文受众流中的&#x200B;**未本地化的日历。** 修复了在创建受众流期间，**[!UICONTROL 时间范围]**&#x200B;属性的&#x200B;**[!UICONTROL 开始]**&#x200B;和&#x200B;**[!UICONTROL 结束]**&#x200B;字段中的日历未以简体中文(CHS)和繁体中文(CHT)区域设置进行本地化的问题。 (TGT-50619)

+++

**[!UICONTROL 可视化体验编辑器] (VEC)**

+++查看详细信息

* 更新后的活动生成器中的&#x200B;**未本地化的工具提示。** 修复了在更新的[!UICONTROL 可视化体验编辑器]活动生成器中&#x200B;**[!UICONTROL 细化]**&#x200B;和&#x200B;**[!UICONTROL 内容]**&#x200B;信息工具提示未本地化的本地化问题。 (TGT-53721)

* [!UICONTROL 体验受众].**中的**&#x200B;未本地化的[!UICONTROL 所有访客] 修复了左边栏中&#x200B;**[!UICONTROL 体验受众]**&#x200B;的&#x200B;**[!UICONTROL 所有访客]**&#x200B;字符串未在[!UICONTROL 可视化体验编辑器]中本地化的问题。 (TGT-50086)

+++

**[!UICONTROL 报表]**

+++查看详细信息

* [!UICONTROL 创建预设]窗口中的&#x200B;**未本地化的日期格式。** 修复了&#x200B;**[!UICONTROL 创建预设]**&#x200B;窗口的&#x200B;**[!UICONTROL 日期范围]**&#x200B;字段中的日期格式未本地化的问题。 (TGT-49239)

+++

**本地化**

+++查看详细信息

* 在多个区域显示&#x200B;**GB18030字符。** 修复了某些专用使用区域字符在&#x200B;**[!UICONTROL 受众]** UI、**[!UICONTROL 管理]** > **[!UICONTROL 属性]**、移动视区配置和Toast通知中错误显示为字母的问题。 （TGT-49622、TGT-49623、TGT-49624和TGT-49625）

+++

<!--
* **Blank page or CORS errors with Enhanced Experience Composer.** Fixed an issue where the [!UICONTROL Visual Experience Composer] could fail to load when Enhanced Experience Composer (EEC) was enabled. (TGT-54576)

**[!UICONTROL Visual Experience Composer] (VEC)**

+++See details

* **Click tracking for Experience B.** Fixed an issue where click tracking was not saved for **[!UICONTROL Experience B]** in the [!UICONTROL Visual Experience Composer]. (TGT-54843)

+++
-->

## 您需要了解的时间性更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

对于与[!DNL Adobe Target]和您的实施相关的时效性更新，[!DNL Adobe]通过[!UICONTROL Experience League]提供详细的发行说明和文档。 以下是一些与您的实施相关的关键功能亮点：

### [!DNL Target] UI版本切换弃用

有关详细信息，请参阅[[!DNL Target] UI更新常见问题解答](/help/main/c-intro/updated-ui-faq.md)。

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 文档更改、以往的发行说明和 Experience Cloud 发行说明

除了针对每个发行的说明外，以下资源还提供更多其他信息：

| 资源 | 详细信息 |
|--- |--- |
| [文档更改](/help/main/r-release-notes/doc-change.md) | 查看这些发行说明中未包括的关于本指南的更新的详细信息。 |
| [以前版本的发行说明](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 | 查看与以前版本的 Target Standard 和 Target Premium 中的新增功能和增强功能相关的信息。 |
| [Adobe Experience Cloud发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans){target=_blank} | 查看 Adobe Experience Cloud 解决方案的最新发行说明。 |

## 预发行信息 {#section_5D588F0415A2435B851A4D0113ACA3A0}

您可以通过以下资源了解下一个 Target 版本即将包含的功能。

| 资源 | 详细信息 |
|--- |--- |
| [Adobe 优先产品更新](https://www.adobe.com/cn/subscription/priority-product-update.html){target=_blank} | 提前收到有关 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案的即将发行产品增强功能的通知。 |
| [Target 发行说明 - 预发行版本](/help/main/r-release-notes/target-release-notes.md){target=_blank} | 有关当月的 Target 版本的信息，包括预发行信息。 |
