---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解 Adobe Target 即将发布的版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: c5445903e7bbab210d0e72200c54ab07975c21c5
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 79%

---

# Target 发行说明（预发行版本）

本文包含预发行版本信息。发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新时间：2022 年 10 月 4 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target]标准版/高级版 22.10.1（交错发布：2022 年 10 月 5 日至 7 日）

此版本将按照以下交错发布计划发布：

* **10 月 5 日**：亚太 (APAC) 区域
* **10 月 6 日**：美洲区域
* **10 月 7 日**：欧洲、中东和非洲 (EMEA) 区域

此版本包含以下新功能、增强和修复：

| 功能 | 详细信息 |
| --- | --- |
| [!DNL Adobe Experience Manager] (AEM)体验片段 | 对AEM体验片段功能的更新包括：<ul><li>在 [!UICONTROL 选件] 列表。 (TGT-43121)</li><li>修复了允许客户插入JSON的问题 [!UICONTROL 体验片段] 选件，但不支持此功能。 JSON选件仅在使用 [!UICONTROL 基于表单的体验] 编辑器。 (TGT-43846)</li></ul>有关更多信息，请参阅AEM [体验片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md). |
| 适用于 Google Chrome 的新 [!UICONTROL Visual Experience Composer] 扩展程序 | Chrome Web Store 中提供了适用于 Chrome 的新 [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) 扩展程序。<br>从 2023 年 1 月开始，当前的 [!DNL Target] VEC Helper 扩展程序将停止在 Google Chrome 中运行，因为 Google 不允许使用 Manifest V2 的扩展程序。 下载新的扩展程序，从新的一年开始，继续在 [!DNL Target] 中以视觉方式创作您的网站。<br>以下链接显示了Chrome Web Store中的两个扩展：<ul><li>[新扩展](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}</li><li>[旧扩展](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak){target=_blank}</li></ul>有关更多信息，请参阅 [Visual Editing Helper扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). |
| 为[!UICONTROL 自动分配]和[!UICONTROL 自动定位]<br>优化了 A4T 指标（具体发布日期待定。） | 请注意以下更改：<ul><li>在[!UICONTROL 自动分配]和[!UICONTROL 自动定位]活动的[!UICONTROL 定位分析] A4T 报表中添加了对二进制和最大化指标的支持</li><li>保留现有活动的行为直至 2023 年 2 月 20 日。在此日期之后，将停止活动以强制现有活动迁移到新行为</li><li>从 2023 年 2 月 20 日开始，将不再支持 [!DNL Target] 活动中的 `averagetimespentonsite`、`bouncerate` 和 `entries` 指标。</li></ul> |

* 修复了导致[!UICONTROL 受众细化]信息窗口中无法正确显示受众规则信息的问题。(TGT-43917)
* 提高了在加载的受众数接近[推荐的定位规则限制](/help/main/r-troubleshooting-target/target-limits.md#targeting-rules)时 [!DNL Target] 用户界面的性能。(TGT-43675)
* 修复了一个问题，在 VEC 中从[!UICONTROL 书写]模式切换到[!UICONTROL 浏览]模式后创建或编辑活动时，该问题导致无法在[!UICONTROL 体验]页面上的[!UICONTROL 修改]面板中正确显示某些组件。(TGT-43300)
* 修复了一个问题，该问题导致某些客户无法将使用[!UICONTROL 自动定位]的 [!UICONTROL A/B 测试] 活动存档。(TGT-40978)
* 添加了自动在单个报表组内的多个位置使用单个选件的功能。(TGT-40689)

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
