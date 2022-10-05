---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解 Adobe Target 即将发布的版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 7f5b4265adbb0e98b7250f99b0268ba5b70dec7c
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 83%

---

# Target 发行说明（预发行版本）

本文包含预发行版本信息。发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新时间：2022 年 10 月 5 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target]标准版/高级版 22.10.1（交错发布：2022 年 10 月 10 日至 13 日）

此版本将按照以下交错发布计划发布：

* **10 月 10 日**：亚太 (APAC) 区域
* **10 月 11 日**：美洲区域
* **10 月 13 日**：欧洲、中东和非洲 (EMEA) 区域

此版本包含以下新功能、增强和修复：

| 功能 | 详细信息 |
| --- | --- |
| [!DNL Adobe Experience Manager] (AEM) 体验片段 | AEM 体验片段功能更新包括以下内容：<ul><li>在 [!UICONTROL Offers] 列表中添加了按类型（HTML 或 JSON）筛选 AEM 体验片段的功能。(TGT-43121)</li><li>修复了允许客户在使用 VEC 时插入不受支持的 JSON [!UICONTROL 体验片段]的问题。只有在使用[!UICONTROL 基于表单的体验]编写器时，才能插入 JSON 提供的内容。(TGT-43846)</li></ul>有关详细信息，请参阅 AEM [体验片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)。 |
| 适用于 Google Chrome 的新 [!UICONTROL Visual Experience Composer] 扩展程序 | Chrome Web Store 中提供了适用于 Chrome 的新 [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) 扩展程序。<br>从 2023 年 1 月开始，当前的 [!DNL Target] VEC Helper 扩展程序将停止在 Google Chrome 中运行，因为 Google 不允许使用 Manifest V2 的扩展程序。 下载新的扩展程序，从新的一年开始，继续在 [!DNL Target] 中以视觉方式创作您的网站。<br>以下链接显示了 Chrome 网络商店中的两个扩展：<ul><li>[新的扩展 ](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}</li><li>[旧的扩展 ](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak){target=_blank}</li></ul>有关更多信息，请参阅[可视化编辑帮助程序扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)。 |
| 文档更新 | 主要文档更新包括：<ul><li>新增和更新 [Adobe Target管理和报表API文档](https://developer.adobe.com/target/administer/admin-api/){target=_blank}包括对管理员和报表API端点的全面覆盖，包括属性、选件、主机、环境、客户端、受众、活动等。<br>请参阅 [[!DNL Adobe Target] [!UICONTROL 开发人员指南]](https://developer.adobe.com/target/){target=_blank}。</li><li>[A/Bn测试中的统计计算](/help/main/c-reports/statistical-methodology/statistical-calculations.md)<br>本文记录了A/Bn手动测试中使用的详细统计计算 [!DNL Adobe Target].<br>本文中的信息将 *Adobe Target A/B测试计算* 之前可在此网站上下载的pdf文件。</li></ul> |

* 修复了导致[!UICONTROL 受众细化]信息窗口中无法正确显示受众规则信息的问题。(TGT-43917)
* 提高了在加载的受众数接近[推荐的定位规则限制](/help/main/r-troubleshooting-target/target-limits.md#targeting-rules)时 [!DNL Target] 用户界面的性能。(TGT-43675)
* 修复了一个问题，在 VEC 中从[!UICONTROL 书写]模式切换到[!UICONTROL 浏览]模式后创建或编辑活动时，该问题导致无法在[!UICONTROL 体验]页面上的[!UICONTROL 修改]面板中正确显示某些组件。(TGT-43300)
* 修复了一个问题，该问题导致某些客户无法将使用[!UICONTROL 自动定位]的 [!UICONTROL A/B 测试] 活动存档。(TGT-40978)
* 添加了自动在单个报表组内的多个位置使用单个选件的功能。(TGT-40689)

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |


## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
