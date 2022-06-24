---
keywords: 发行说明;新功能;版本;更新;更新;版本;增强;增强;修复;错误修复;更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 91%

---

# Target 发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的发行说明以及其他平台变更。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## [!DNL Target Standard/Premium] 22.6.1（2022 年 6 月 7 日至 9 日，交错发行）

此版本将按照以下交错发布计划发布：

* **6 月 7 日**：亚太 (APAC) 地区
* **6 月 8 日**：美洲地区
* **6 月 9 日**：欧洲、中东和非洲 (EMEA) 地区

此版本包含以下增强功能和修复：

* 对新的[!UICONTROL 受众]页面进行了增强，以防止过去存储受众的旧数据库与直接从后端检索信息的新架构之间出现不一致的状态。(TGT-43552)
* 修复了由于 Target UI 创建“空”容器而导致某些客户无法保存合并受众的问题。 (TGT-43588)

## Target 平台版本（2022 年 5 月 25 日）

此版本包含以下增强功能和修复：

* 添加了 [用户代理客户端提示](https://developer.adobe.com/target/implement/client-side/atjs/user-agent-and-client-hints/)支持{target=_blank}。
* 修复了一个问题，在[!UICONTROL 体验定位] (XT) 活动中呈现[!UICONTROL 优惠决策]时，该问题间歇性地导致超时。(TNT-44611)

## at.js 版本 2.9.0（2022 年 5 月 27 日）

* 添加了 [用户代理客户端提示](https://developer.adobe.com/target/implement/client-side/atjs/user-agent-and-client-hints/)支持{target=_blank}。
* 修复了同一页面上的多个 mbox 请求具有不同印象 ID 的错误。

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=cn) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js版本详细信息](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 文档更改、以往的发行说明和 Experience Cloud 发行说明

除了针对每个发行的说明外，以下资源还提供更多其他信息：

| 资源 | 详细信息 |
|--- |--- |
| 文档更改 | 查看这些发行说明中未包括的关于本指南的更新的详细信息。<br>有关更多信息，请参阅[文档更改](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)。 |
| 以前版本的发行说明 | 查看与以前版本的 Target Standard 和 Target Premium 中的新增功能和增强功能相关的信息。<br>有关更多信息，请参阅[以前版本的发行说明](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 发行说明 | 查看 Adobe Experience Cloud 解决方案的最新发行说明。<br>有关更多信息，请参阅 [Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)。 |

## 预发行信息 {#section_5D588F0415A2435B851A4D0113ACA3A0}

您可以通过以下资源了解下一个 Target 版本即将包含的功能。

| 资源 | 详细信息 |
|--- |--- |
| Adobe 优先产品更新 | 若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：<br>[](https://www.adobe.com/cn/subscription/priority-product-update.html)https://www.adobe.com/cn/subscription/priority-product-update.html |
| 即将推出的发行说明 | 有关当月 Target 发行版本的信息（包括预发行信息），请参阅 [Target 发行说明 — 预发行](/help/main/r-release-notes/target-release-notes.md)页面。 |
