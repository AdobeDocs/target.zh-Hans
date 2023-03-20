---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解 Adobe Target 即将发布的版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 04d4cf13e0054a767e9bf08770cdace1e130067f
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 49%

---

# Target 发行说明（预发行版本）

本文包含预发行版本信息。发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新日期：2023 年 3 月 20 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target] Standard/Premium 23.3.1（2023年3月28日至30日）

将按以下交错的时间表发布此版本：

* **3 月 28 日**：欧洲、中东和非洲 (EMEA) 地区
* **3 月 29 日**：亚太 (APAC) 地区
* **3 月 30 日**：美洲地区

此版本包含以下新功能、增强和修复：

| 功能 | 详细信息 |
|--- |--- |
| 用于无头个性化和实验的AEM内容片段 | 使用 [!DNL Adobe Experience Manager] (AEM) [!UICONTROL 内容片段] in [!DNL Target] 活动。 将AEM的易用性和强大功能与 [!DNL Target] 以大规模测试和个性化体验。 |
| 为[!UICONTROL 自动分配]和[!UICONTROL 自动定位]优化了 A4T 指标 | 通过 [!DNL Target]，可在使用 [!UICONTROL A4T] 进行[!UICONTROL 自动分配]和[!UICONTROL 自动定位]活动时，根据二项式事件或连续事件选择指标。<P>请注意，在支持的指标中发生了以下变化：<ul><li>[!DNL Target] 保留现有活动以前的行为直至 2023 年 9 月 9 日。在此日期之后，将不再继续执行使用不支持的指标的活动，以强制现有活动采用新行为。</li></ul> |
| 使用 [!UICONTROL Analytics for Target (A4T)] 进行的[!UICONTROL 自动分配] | 更新了教程：<ul><li>[在  [!DNL Analysis Workspace]  中为[!UICONTROL 自动分配]活动设置 A4T 报表](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank}</li></ul> |
| 使用 [!UICONTROL Analytics for Target (A4T)] 进行的[!UICONTROL 自动定位] | 更新了教程：<ul><li>[在  [!DNL Analysis Workspace]  中为[!UICONTROL 自动定位]活动设置 A4T 报表](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html){target=_blank}</li></ul> |

* 增强了受众和活动同步，以便在 [!DNL Adobe Experience Platform] 和 [!DNL Adobe Audience Manager] 在 [!DNL Target] UI更快。 (TGT-44568)
* 进行了相应更改，以允许用户删除 [!UICONTROL 默认URL] 在 [!UICONTROL 管理] > [!UICONTROL 可视化体验编辑器] > [!UICONTROL 默认URL]. 此更改允许客户将默认URL更改回空字符串，此前在初始配置后无法执行此更改。 (TGT-44577)
* 删除了阻止客户编辑或删除现成受众（具有保留名称的受众）的限制。 (TGT-44655)
* 已禁用[!UICONTROL 完成]“ ”选项，此选项在 [!DNL Target] 创建时的UI [合并受众](/help/main/c-target/combining-multiple-audiences.md). (TGT-44079)
* 修复了 [!UICONTROL 语言] 链接 [!UICONTROL 受众] 页面，以便它正确链接到“[!UICONTROL 帐户通信首选项]”页面。 (TGT-43562)
* 解决了有时阻止客户创建 [!UICONTROL A/B测试] 活动 [!UICONTROL Adobe Analytics] 选项 [!UICONTROL 管理] > [!UICONTROL 报表] > [!UICONTROL 报表Experience Cloud解决方案]. (TGT-44844)
* 修复了阻止客户查看 [!UICONTROL 多变量测试] 活动，其中包含许多体验 [!UICONTROL 可视化体验编辑器] (VEC)。 的 [DOM路径](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) 有时，VEC底部的显示屏会阻止客户查看上一个体验。 (TGT-44578)
* 修复了在VEC中的浏览URL无法反映在需要授权或调用重定向的常规浏览器会话中可见的当前页面的问题。 (TGT-44350)
* 修复了阻止客户更改 [!UICONTROL 筛选不兼容的标准] 设置 [!UICONTROL Recommendations] > [!UICONTROL 设置]. (TGT-44398)
* 修复了导致POST请求新建的问题 [!DNL Recommendations] 使用 [!UICONTROL Analytics分类] 报表包的名称中带有圆点。 (TGT-44598)
* 更新了 [!DNL Target] UI指向新 [Visual Editing Helper扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). (TGT-44459)
* 增强了安全性，以防止在 [!DNL Recommendations] 信息源。 (TGT-43769)
* 修复了阻止客户在 [!DNL Recommendations] 图像名称包含时的设计 [GB18030字符](https://en.wikipedia.org/wiki/GB_18030){target=_blank}. (TGT-44614)
* 修复了导致 [GB18030字符](https://en.wikipedia.org/wiki/GB_18030){target=_blank} 在 [!UICONTROL 修改] 编辑时显示面板 [!UICONTROL 文本/HTML] 活动 [!UICONTROL 体验] 页面。
* 对整个 [!DNL Target] UI 进行了各种本地化修复。


## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |


## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
