---
keywords: 发行说明;新功能;版本;更新;更新;版本;增强;增强;修复;错误修复;更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 17bb53ef1f48b4c5f9f6c5caccf1fe8aa3e17286
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 89%

---

# [!DNL Target]发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的发行说明以及其他平台变更。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## [!DNL Adobe Target] Edge计划的基础架构升级 {#edge}

计划的边缘基础架构升级要求将其他IP或域列入允许列表。 查看并允许列出边缘部署的NAT和IP/域41-48。 基础设施升级从2023年8月9日开始。
&quot;

有关更多信息，请参阅 [允许列表Target边缘节点](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html?lang=zh-Hans){target=_blank} 在 *Adobe Target开发人员指南*.

## [!DNL Target] Standard/Premium 23.7.1（7 月 24-26 日）

将按以下交错的时间表发布此版本：

* **7 月 24 日**：欧洲、中东和非洲 (EMEA) 地区
* **7 月 25 日**：亚太 (APAC) 地区
* **7 月 26 日**：美洲地区

此版本包含以下增强功能和修复：

* 改进了在[使用 DOM 路径](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path)在 [!UICONTROL Visual Experience Composer] (VEC) 中导航元素时的搜索功能，以便包含影子 DOM 元素。(TGT-45262)
* 修复了阻止[更改叠加](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md)设置正常工作的问题。(TGT-45202)
* 修复了一些客户在收到以下错误消息后无法下载活动报告的问题：“用户无权访问报告”。（TGT-45724 和 TGT-45747）

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 文档更改、以往的发行说明和 Experience Cloud 发行说明

除了针对每个发行的说明外，以下资源还提供更多其他信息：

| 资源 | 详细信息 |
|--- |--- |
| [文档更改](/help/main/r-release-notes/doc-change.md) | 查看这些发行说明中未包括的关于本指南的更新的详细信息。 |
| [以前版本的发行说明](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 | 查看与以前版本的 Target Standard 和 Target Premium 中的新增功能和增强功能相关的信息。 |
| [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans){target=_blank} | 查看 Adobe Experience Cloud 解决方案的最新发行说明。 |

## 预发行信息 {#section_5D588F0415A2435B851A4D0113ACA3A0}

您可以通过以下资源了解下一个 Target 版本即将包含的功能。

| 资源 | 详细信息 |
|--- |--- |
| [Adobe 优先产品更新](https://www.adobe.com/cn/subscription/priority-product-update.html){target=_blank} | 提前收到有关 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案的即将发行产品增强功能的通知。 |
| [Target 发行说明 - 预发行版本](/help/main/r-release-notes/target-release-notes.md){target=_blank} | 有关当月的 Target 版本的信息，包括预发行信息。 |
