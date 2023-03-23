---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解 Adobe Target 即将发布的版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 7b8390042a0e15df6c05d176b2f525ddd83c9608
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 100%

---

# Target 发行说明（预发行版本）

本文包含预发行版本信息。发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新日期：2023 年 3 月 20 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target] Standard/Premium 23.3.1（2023 年 3 月 28-30 日）

将按以下交错的时间表发布此版本：

* **3 月 28 日**：欧洲、中东和非洲 (EMEA) 地区
* **3 月 29 日**：亚太 (APAC) 地区
* **3 月 30 日**：美洲地区

此版本包含以下新功能、增强和修复：

| 功能 | 详细信息 |
|--- |--- |
| 用于无头个性化和实验的 AEM 内容片段 | 在 [!DNL Target] 活动中使用 [!DNL Adobe Experience Manager] (AEM) [!UICONTROL 内容片段]。将简单易用的 AEM 与 [!DNL Target] 中强大的人工智能 (AI) 和机器学习 (ML) 功能结合使用，从而测试和个性化大量体验。 |
| 为[!UICONTROL 自动分配]和[!UICONTROL 自动定位]优化了 A4T 指标 | 通过 [!DNL Target]，可在使用 [!UICONTROL A4T] 进行[!UICONTROL 自动分配]和[!UICONTROL 自动定位]活动时，根据二项式事件或连续事件选择指标。<P>请注意，在支持的指标中发生了以下变化：<ul><li>[!DNL Target] 保留现有活动以前的行为直至 2023 年 9 月 9 日。在此日期之后，将不再继续执行使用不支持的指标的活动，以强制现有活动采用新行为。</li></ul> |
| 使用 [!UICONTROL Analytics for Target (A4T)] 进行的[!UICONTROL 自动分配] | 更新的教程：<ul><li>[在  [!DNL Analysis Workspace]  中为[!UICONTROL 自动分配]活动设置 A4T 报表](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank}</li></ul> |
| 使用 [!UICONTROL Analytics for Target (A4T)] 进行的[!UICONTROL 自动定位] | 更新的教程：<ul><li>[在  [!DNL Analysis Workspace]  中为[!UICONTROL 自动定位]活动设置 A4T 报表](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html){target=_blank}</li></ul> |

* 增强了受众和活动同步，以便在 [!DNL Adobe Experience Platform] 和 [!DNL Adobe Audience Manager] 中创建的项目可更快地在 [!DNL Target] UI 中可用。(TGT-44568)
* 进行更改以允许用户在[!UICONTROL 管理] > [!UICONTROL 视觉体验编辑器] > [!UICONTROL 默认 URL] 中删除 [!UICONTROL 默认 URL]。此更改允许客户将默认 URL 更改回空字符串，这在以前的初始配置后是不可能实现的。(TGT-44577)
* 删除了阻止客户编辑或删除开箱即用的受众（具有保留名称的受众）的限制。(TGT-44655)
* 禁用了在创建[组合受众](/help/main/c-target/combining-multiple-audiences.md)时，加载微调器在 [!DNL Target] UI 中可见时的[!UICONTROL “完成”]选项。(TGT-44079)
* 修复了[!UICONTROL 受众]页面底部的[!UICONTROL 语言]链接，使其正确链接到“[!UICONTROL 帐户通讯偏好]”页面。(TGT-43562)
* 解决了有时阻止客户在[!UICONTROL 管理]>[!UICONTROL 报告]>[!UICONTROL 报告体验云解决方案]下选择 [!UICONTROL Adobe Analytics] 选项后创建 [!UICONTROL A/B 测试]活动的问题。(TGT-44844)
* 修复了使客户无法查看[!UICONTROL 多元测试]活动中的最后一次体验，该活动具有[!UICONTROL 视觉体验编辑器]（VEC）中提供的许多体验。VEC 底部的 [DOM 路径](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path)有时会阻止客户看到上次体验。(TGT-44578)
* 修复了导致 VEC 中的浏览 URL 无法反映在正常浏览器会话中可见的当前页面（如果页面需要授权或调用重定向）的问题。(TGT-44350)
* 修复了阻止客户更改[!UICONTROL 建议]>[!UICONTROL 设置]中的[!UICONTROL 过滤器不兼容标准]设置的问题。(TGT-44398)
* 修复了在名称中带有点的报表包中使用 [!UICONTROL Analytics Classifications] 时导致创建新 [!DNL Recommendations] 源的 POST 请求失败的问题。(TGT-44598)
* 更新了 [!DNL Target] UI 中的链接以指向新的 [Visual Editing Helper 扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)。(TGT-44459)
* 增强安全性以防止 [!DNL Recommendations] 提要中的服务器端请求伪造 (SSRF) 尝试。(TGT-43769)
* 修复了如果图像名称包含 [GB18030 字符](https://en.wikipedia.org/wiki/GB_18030){target=_blank} 时客户无法查看 [!DNL Recommendations] 设计中的预览图像的问题。(TGT-44614)
* 修复了在活动的[!UICONTROL 体验]页面上编辑[!UICONTROL 文本/HTML]时，导致[!UICONTROL 修改]面板中的一些 [GB18030字符](https://en.wikipedia.org/wiki/GB_18030){target=_blank}被转义的问题。(TGT-44600)
* 对整个 [!DNL Target] UI 进行了各种本地化修复。


## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |


## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
