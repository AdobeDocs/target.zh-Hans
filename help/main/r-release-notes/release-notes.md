---
keywords: 发行说明；新功能；版本；更新；更新；版本；增强；增强；修复；错误修复；更新、当前更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 0f96fb2a74a0716542308037d183847c91b1dc04
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 52%

---

# [!DNL Target]发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的发行说明以及其他平台变更。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## [!DNL Target Standard/Premium] 25.5.1（2025年5月5日）

此版本包含以下修复和更新：

* 修复了无法在更新后的UI中为某些活动显示受众细化的问题。 (TGT-52057)
* 修复了阻止在活动中使用组合受众的问题。 (TGT-52346)
* 修复了阻止使用来自同一工作区的仅限该活动的受众，在非默认工作区中创建新活动的问题。 (TGE-52349)
* 修复了在创建和选择新受众后，导致仅限该活动的受众从更新后的UI中消失的问题。 (TGT=52091)
* 修复了阻止在活动中使用重复受众的问题。 （TGT-51200 和 TGT-52057）
* 修复了一个问题，该问题导致在更新后的UI中逆转受众细化和活动受众。 (TGT-52158)
* 修复了由于用户输入错误“此用户不允许使用非默认工作区”而阻止创建新活动的问题。 (TGT-52267)
* 修复了导致无法在默认工作区和非默认工作区的更新UI中显示选件的问题。 [!DNL Target]现在显示来自两个工作区的选件。 (TGT-52339)
* 修复了在编辑活动和更改修改的网站元素时，[!DNL Target]未警告客户的问题。 (TGT-52100)
* 修复了以下问题：编辑具有临时选件的选件时，会创建一个新选件而不是更新现有选件。 (TGT-52135)
* 修复了将选件移动到文件夹时导致无效有效负载错误的问题。 (TGT-52325)
* 修复了将选件移动到文件夹时导致用户输入错误的问题。 (TGT-52296)
* 为每个活动添加了`audienceMetadata`字段，并确保在编辑活动时已读取并更新该字段。 (TGT-51004)

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=zh-Hans){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

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
