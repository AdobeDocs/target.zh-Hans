---
keywords: 发行说明;新功能;版本;更新;更新;版本;增强;增强;修复;错误修复;更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 5566393192b131b837fece1bb2a6781e2f953190
workflow-type: ht
source-wordcount: '1055'
ht-degree: 100%

---

# [!DNL Target]发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的发行说明以及其他平台变更。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## 模型 API 版本（2022 年 11 月 23 日）

新的 [!DNL Adobe Target] 模型 API（也称为阻止列表 API）可让用户查看和管理机器学习模型中用于 [!UICONTROL Automated Personalization] (AP) 和[!UICONTROL 自动定位] (AT) 活动的功能的列表。

有关详细信息，请参阅 *Adobe Target 开发人员指南* 中的[模型 API 概述](https://developer.adobe.com/target/before-administer/models-api/){target=_blank}。

## [!DNL Target] Standard/Premium 22.10.3（交错发布：2022 年 10 月 25 日至 27 日）

此版本将按照以下交错发布计划发布：

* **10 月 25 日**：欧洲、中东和非洲 (EMEA) 地区
* **10 月 26 日**：亚太 (APAC) 地区
* **10 月 27 日**：美洲地区

此版本包含以下新功能、增强和修复：

| 功能 | 详细信息 |
| --- | --- |
| 为[!UICONTROL 自动分配]和[!UICONTROL 自动定位]<br>优化了 A4T 指标（可供某些客户进行测试。将在未来版本中提供给所有客户。） | 请注意以下更改：<ul><li>在 [!UICONTROL Auto-Allocate] 和 [!UICONTROL Auto-Target] 活动的 [!UICONTROL Analytics for Target] A4T 报表中添加了对非二分和最大化指标的支持</li><li>保留现有活动的行为直至 2023 年 2 月。在此日期之后，将停止活动以强制现有活动迁移到新行为</li><li>从 2023 年 2 月 20 日开始，将不再支持 [!DNL Target] 活动中的 `averagetimespentonsite`、`bouncerate` 和 `entries` 指标。</li></ul> |

* 在 [!DNL Target] UI 中添加了工具提示以帮助客户更高效地在受众生成器中导航并了解如何使用可能不熟悉的功能。(TGT-44139)
* 添加了阻止客户编辑被 [!DNL Target] 禁用的活动（因为它使用不支持的指标）的功能。UI 中的一条消息指示客户重复该活动，然后更新转化指标。

   在此版本中，将为新活动弃用 [!DNL Target] 活动中的 `averagetimespentonsite`、`bouncerate` 和 `entries` 指标。现有活动可继续使用这些量度直至 2023 年 5 月。

* 在 [!DNL Target] UI 中添加了工具提示，帮助客户在创建或编辑使用 A4T 的[!UICONTROL 自动定位]活动时选择优化标准。

## [!DNL Target]Standard/Premium 22.10.1（交错发布：2022 年 10 月 10 日至 13 日）

此版本将按照以下交错发布计划发布：

* **10 月 10 日**：亚太 (APAC) 区域
* **10 月 12 日**：美洲区域
* **10 月 13 日**：欧洲、中东和非洲 (EMEA) 区域

此版本包含以下新功能、增强和修复：

| 功能 | 详细信息 |
| --- | --- |
| [!DNL Adobe Experience Manager] (AEM) 体验片段 | AEM 体验片段功能更新包括以下内容：<ul><li>在 [!UICONTROL Offers] 列表中添加了按类型（HTML 或 JSON）筛选 AEM 体验片段的功能。(TGT-43121)</li><li>修复了允许客户在使用 VEC 时插入不受支持的 JSON [!UICONTROL 体验片段]的问题。只有在使用[!UICONTROL 基于表单的体验]编写器时，才能插入 JSON 提供的内容。(TGT-43846)</li></ul>有关详细信息，请参阅 AEM [体验片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)。 |
| 适用于 Google Chrome 的新 [!UICONTROL Visual Experience Composer] 扩展程序 | Chrome Web Store 中提供了适用于 Chrome 的新 [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) 扩展程序。<br>从 2023 年 1 月开始，当前的 [!DNL Target] VEC Helper 扩展程序将停止在 Google Chrome 中运行，因为 Google 不允许使用 Manifest V2 的扩展程序。 下载新的扩展程序，从新的一年开始，继续在 [!DNL Target] 中以视觉方式创作您的网站。<br>以下链接显示了 Chrome 网络商店中的两个扩展：<ul><li>[新的扩展 ](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}</li><li>[旧的扩展 ](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak){target=_blank}</li></ul>有关更多信息，请参阅[可视化编辑帮助程序扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)。 |
| 文档更新 | 主要文档更新如下所示：<ul><li>新的和更新的[Adobe Target 管理和报告 API 文档](https://developer.adobe.com/target/administer/admin-api/){target=_blank} 全面涵盖了管理和报告 API 端点，包括属性、优惠、主机、环境、客户端、受众、活动等。<br>在[[!DNL Adobe Target] [!UICONTROL 开发人员指南]](https://developer.adobe.com/target/){target=_blank}中查看此内容和其他开发人员内容。</li><li>[A/Bn 测试中的统计计算](/help/main/c-reports/statistical-methodology/statistical-calculations.md)<br>本文记录了在手动 A/Bn 测试中使用的详细统计计算 [!DNL Adobe Target]。<br>本文中的信息取代了&#x200B;*用于 A/B 测试的 Adobe Target 计算* pdf 文件，以前可在此站点上下载。</li></ul> |

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
