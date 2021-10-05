---
keywords: 发行说明;新功能;版本;更新;更新;版本;增强;增强;修复;错误修复;更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么新功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 5a5b39db9b9b4ffd95573d643dcff52fe562c0c2
workflow-type: ht
source-wordcount: '727'
ht-degree: 100%

---

# Target 发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 Target API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的发行说明以及其他平台变更。

>[!IMPORTANT]
>
>**mbox.js 生命周期结束**：从 2021 年 3 月 31 日起，[!DNL Adobe Target] 将不再支持 mbox.js 库。2021 年 3 月 31 日之后，所有从 mbox.js 进行的调用都将失败，并影响您通过提供默认内容而运行 [!DNL Target] 活动的页面。
>
>请迁移到新 [!DNL Adobe Experience Platform Web SDK] 或 at.js JavaScript 库的最新版本，以避免您的网站出现任何潜在问题。有关更多信息，请参阅[概述：为客户端 Web 实现 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## [!DNL Target Standard/Premium] 21.9.1（2021 年 9 月 14 日）

此维护版本包含以下增强功能、修复和更改。

* 修复了某些 Web 浏览器中针对第三方 Cookie 的新安全策略导致客户无法登录[!UICONTROL 可视体验编辑器] (VEC) 的问题。[排除与可视体验编辑器和增强体验编辑器相关的问题](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md)中的“使用 Google Chrome 80 和更高版本时，在可视体验编辑器 (VEC) 或增强体验编辑器 (EEC) 中不加载页面”中讨论了此问题。
* 修复了一个问题，该问题导致 VEC 中的选件名称显示选件路径而非选件的友好名称。(TGT-41300)
* A4T 活动的体验名称现在反映在 [!DNL Analysis Workspace] 中 (TGT-38674)
* 修复了 [!DNL Recommendations] 中的一个问题，该问题导致错误地将重复活动的促销中的实体 ID 更改应用于原始活动。(TGT-41482)
* 修复了一个问题，该问题导致“编辑标准”按钮无法在 VEC 中的 [!DNL Recommendations] 活动的[!UICONTROL 体验]页面上正常显示。(TGT-39512)
* 修复了一个问题，该问题导致在复制到测试工作区时无法同步活动。(TGT-40686)
* 修复了一个问题，该问题导致在 VEC 中使用[!UICONTROL 在此之后插入]时无法修改带[体验片段](/help/c-experiences/c-manage-content/aem-experience-fragments.md)的选择器。(TGT-41802)
* 修复了一个问题，该问题导致无法将选件中的空 JSON 内容发送到后端。[!DNL Target] 现在可发送 JSON 对象，即使该对象为空也是如此。(TGT-41555)
* 修复了一个问题，该问题导致当客户在查看报告时单击[!UICONTROL 在 Analytics 中查看]的情况下，打开旧 [!DNL Analytics] 报告而非 [!DNL Analysis Workspace]。(TGT-41867)
* 向客户尝试选择 [!DNL Analytics] 作为 [!UICONTROL Automated Personalization] 活动的报告源 (A4T) 时显示的 UI 消息中添加了附加说明。该消息指明“[!DNL Target] 是唯一受支持的 [!UICONTROL Automated Personalization] 活动的源。”(TGT-41954)
* 向客户尝试使用“换行符”而不是逗号分隔主机时显示的错误消息中添加了附加说明。(TGT-40671)
* 修复了一个问题，该问题导致一些活动的[!UICONTROL 上次更新日期]与西班牙客户和日本客户的英语 UI 中的不同（在查看西班牙语和日语版的 UI 时）。(TGT-38980)

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh_Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 文档更改、以往的发行说明和 Experience Cloud 发行说明

除了针对每个发行的说明外，以下资源还提供更多其他信息：

| 资源 | 详细信息 |
|--- |--- |
| 文档更改 | 查看这些发行说明中未包括的关于本指南的更新的详细信息。<br>有关更多信息，请参阅[文档更改](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)。 |
| 以前版本的发行说明 | 查看与以前版本的 Target Standard 和 Target Premium 中的新增功能和增强功能相关的信息。<br>有关更多信息，请参阅[以前版本的发行说明](/help/r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 发行说明 | 查看 Adobe Experience Cloud 解决方案的最新发行说明。<br>有关更多信息，请参阅 [Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans)。 |

## 预发行信息 {#section_5D588F0415A2435B851A4D0113ACA3A0}

您可以通过以下资源了解下一个 Target 版本即将包含的功能。

| 资源 | 详细信息 |
|--- |--- |
| Adobe 优先产品更新 | 若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：<br>[](https://www.adobe.com/cn/subscription/priority-product-update.html)https://www.adobe.com/cn/subscription/priority-product-update.html |
| 即将推出的发行说明 | 有关当月 Target 发行版本的信息（包括预发行信息），请参阅 [Target 发行说明 - 预发行](/help/r-release-notes/target-release-notes.md)页面。 |
