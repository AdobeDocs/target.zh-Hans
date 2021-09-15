---
keywords: 发行说明;新功能;版本;更新;更新;版本;增强;增强;修复;错误修复;更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么新功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 5a5b39db9b9b4ffd95573d643dcff52fe562c0c2
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 57%

---

# Target 发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 Target API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的发行说明以及其他平台变更。

>[!IMPORTANT]
>
>**mbox.js 生命周期结束**：从 2021 年 3 月 31 日起，[!DNL Adobe Target] 将不再支持 mbox.js 库。2021 年 3 月 31 日之后，所有从 mbox.js 进行的调用都将失败，并影响您通过提供默认内容而运行 [!DNL Target] 活动的页面。
>
>请迁移到新 [!DNL Adobe Experience Platform Web SDK] 或 at.js JavaScript 库的最新版本，以避免您的网站出现任何潜在问题。有关更多信息，请参阅[概述：为客户端 Web 实现 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## [!DNL Target Standard/Premium] 21.9.1（2021年9月14日）

此维护版本包含以下增强、修复和更改。

* 修复了由于某些Web浏览器中第三方Cookie的新安全策略，客户无法登录到[!UICONTROL 可视化体验编辑器](VEC)的问题。 在[对与可视化体验编辑器和增强型体验编辑器相关的问题进行故障诊断](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md)中，“使用Google Chrome版本80及更高版本时，在可视化体验编辑器(VEC)或增强型体验编辑器(EEC)中，“页面未加载”讨论了此问题。
* 修复了导致VEC中的选件名称显示选件的路径而不是选件的友好名称的问题。 (TGT-41300)
* 现在，A4T活动的体验名称会反映在[!DNL Analysis Workspace]中(TGT-38674)
* 修复了[!DNL Recommendations]中存在的一个问题，该问题会错误地将实体ID在复制活动中的促销活动中进行更改，以将其应用于原始活动。 (TGT-41482)
* 修复了VEC中[!DNL Recommendations]活动的[!UICONTROL 体验]页面上无法正确显示“编辑标准”按钮的问题。 (TGT-39512)
* 修复了复制活动并将其复制到测试工作区时无法同步活动的问题。 (TGT-40686)
* 修复了在VEC中使用“[!UICONTROL Insert After]”时，阻止修改具有[体验片段](/help/c-experiences/c-manage-content/aem-experience-fragments.md)的选择器的问题。 (TGT-41802)
* 修复了阻止将选件中的空JSON内容发送到后端的问题。 [!DNL Target] 现在会发送JSON对象，即使该对象为空也是如此。(TGT-41555)
* 修复了当客户在查看报表时单击“[!UICONTROL 在Analytics中查看]”时，导致旧版[!DNL Analytics]报表打开而不是[!DNL Analysis Workspace]的问题。 (TGT-41867)
* 为当客户尝试为[!UICONTROL Automated Personalization]活动选择[!DNL Analytics]作为报表源(A4T)时显示的UI消息添加了其他说明。 该消息指出，“[!DNL Target]是[!UICONTROL Automated Personalization]活动唯一支持的源。” (TGT-41954)
* 为当客户尝试使用“换行符”而不是逗号来分隔主机时的错误消息添加了额外说明。 (TGT-40671)
* 修复了导致某些活动的“[!UICONTROL 上次更新]”日期与西班牙和日语客户的英语UI不同（在查看西班牙语和日语版UI时）的问题。 (TGT-38980)

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
