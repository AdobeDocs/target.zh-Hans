---
keywords: 发行说明;新功能;版本;更新;更新;版本;增强;增强;修复;错误修复;更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 98%

---

# [!DNL Target]发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的发行说明以及其他平台变更。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## [!DNL Target] Standard/Premium 23.3.1（2023 年 3 月 28-30 日）

将按以下交错的时间表发布此版本：

* **3 月 28 日**：欧洲、中东和非洲 (EMEA) 地区
* **3 月 29 日**：亚太 (APAC) 地区
* **3 月 30 日**：美洲地区

此版本包含以下新功能、增强和修复：

| 功能 | 详细信息 |
|--- |--- |
| 为[!UICONTROL 自动分配]和[!UICONTROL 自动定位]优化了 A4T 指标<p>（发布日期：2023 年 3 月 30 日） | 通过 [!DNL Target]，可在使用 [!UICONTROL A4T] 进行[!UICONTROL 自动分配]和[!UICONTROL 自动定位]活动时，根据二项式事件或连续事件选择指标。<P>请注意，在支持的指标中发生了以下变化：<ul><li>[!DNL Target] 保留现有活动以前的行为直至 2023 年 9 月 9 日。在此日期之后，将不再继续执行使用不支持的指标的活动，以强制现有活动采用新行为。</li></ul>有关更多信息，请参阅[[!UICONTROL 自动分配]和[!UICONTROL 自动定位]活动支持 A4T](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#supported) 中的“支持的目标量度”。<br>以下教程已随此功能一并更新：<ul><li>[在  [!DNL Analysis Workspace]  中为[!UICONTROL 自动分配]活动设置 A4T 报表](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank}</li><li>[在  [!DNL Analysis Workspace]  中为[!UICONTROL 自动定位]活动设置 A4T 报表](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html){target=_blank}</li></ul> |

* 增强了受众和活动同步，以便在 [!DNL Adobe Experience Platform] 和 [!DNL Adobe Audience Manager] 中创建的项目可更快地在 [!DNL Target] UI 中可用。(TGT-44568)
* 增强了 UI，可让用户在[!UICONTROL 管理] > [!UICONTROL 视觉体验编辑器] > [!UICONTROL 默认 URL] 下删除 [!UICONTROL 默认 URL]。此更改允许客户将默认 URL 更改回空字符串，这在以前的初始配置后是不可能实现的。(TGT-44577)
* 删除了阻止客户编辑或删除开箱即用的受众（具有保留名称的受众）的限制。(TGT-44655)
* 禁用了在创建[组合受众](/help/main/c-target/combining-multiple-audiences.md)时，加载微调器在 [!DNL Target] UI 中可见时的[!UICONTROL “完成”]选项。(TGT-44079)
* 修复了[!UICONTROL 受众]页面底部的[!UICONTROL 语言]链接，使其正确链接到“[!UICONTROL 帐户通讯偏好]”页面。(TGT-43562)
* 解决了有时阻止客户在[!UICONTROL 管理]>[!UICONTROL 报告]>[!UICONTROL 报告体验云解决方案]下选择 [!UICONTROL Adobe Analytics] 选项后创建 [!UICONTROL A/B 测试]活动的问题。(TGT-44844)
* 修复了使客户无法查看[!UICONTROL 多元测试]活动中的最后一次体验，该活动具有[!UICONTROL 视觉体验编辑器]（VEC）中提供的许多体验。VEC 底部的 [DOM 路径](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path)有时会阻止客户看到上次体验。(TGT-44578)
* 修复了导致 VEC 中的浏览 URL 无法反映在正常浏览器会话中可见的当前页面（如果页面需要授权或调用重定向）的问题。(TGT-44350)
* 修复了阻止客户更改[!UICONTROL 建议]>[!UICONTROL 设置]中的[!UICONTROL 过滤器不兼容标准]设置的问题。(TGT-44398)
* 修复了在名称中带有点的报表包中使用 [!UICONTROL Analytics Classifications] 时导致创建 [!DNL Recommendations] 源的 POST 请求失败的问题。(TGT-44598)
* 更新了 [!DNL Target] UI 中的链接以指向新的 [Visual Editing Helper 扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)。(TGT-44459)
* 增强安全性以防止 [!DNL Recommendations] 提要中的服务器端请求伪造 (SSRF) 尝试。(TGT-43769)
* 在整个 [!DNL Target] UI 中作出了多项本地化修复。

## at.js 版本 2.10.2（2023 年 3 月 7 日）

* 修复了导致 `trackEvent` 函数始终返回错误的问题。

有关所有 at.js 版本的信息，请参阅 [at.js 版本详细信息](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} in the [Adobe Target Developer Guide](https://experienceleague.corp.adobe.com/docs/target-dev/developer/overview.html){target=_blank}。

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
