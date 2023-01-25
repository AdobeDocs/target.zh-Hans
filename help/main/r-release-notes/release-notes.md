---
keywords: 发行说明;新功能;版本;更新;更新;版本;增强;增强;修复;错误修复;更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 50703e9709d515cbee18569fedb6139e9bf18ccd
workflow-type: tm+mt
source-wordcount: '756'
ht-degree: 91%

---

# [!DNL Target]发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的发行说明以及其他平台变更。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## [!DNL Target] Standard/Premium 22.13.3（2023 年 1 月 25 日至 26 日）

此版本将按照以下交错发布计划发布：

* **1月25日**:欧洲、中东和非洲(EMEA)地区
* **1月25日**:亚太地区
* **1月26日**:美洲地区

此版本包含以下新功能、增强和修复：

| 功能 | 详细信息 |
| --- | --- |
| [JSON选件](/help/main/c-experiences/c-manage-content/create-json-offer.md) 在Automated Personalization支持(AP) | 使用基于表单的体验编辑器在 [!UICONTROL Automated Personalization] (AP) 活动中添加了对 JSON 选件的支持。(TGT-41460) |
| 推荐 | 中的友好名称 [!UICONTROL Analytics for Target] A4T报表现已可用。 [!DNL Target] 以前仅列出体验 ID。此增强使 [!DNL Adobe Analytics] 和 [!DNL Target] 之间的报表保持一致，并帮助客户简化在 A4T 中构建报表。(TGT-41853) |
| [AEM 体验片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) | 添加了区分 [!DNL Adobe Experience Manager] 片段(AEM XF)类型 [!DNL Target]. 而不是“体验片段”选项， [!DNL Target] 现在，您可以按“HTMLXF”和“JSON XF”进行过滤和搜索。 (TGT-44132) |

* 修复了在 [!UICONTROL A/B 测试]和 [!UICONTROL Experience Targeting] (XT) 活动中导致“500 错误”的问题，并包含建议。当 [!DNL Target] 无法从 [!DNL Target] UI 和 [!DNL Recommendations] 后端正确删除不再使用的条件对象时，会导致此问题。(TGT-44383)
* 从 [!UICONTROL Offer Level] 报告中为 [!UICONTROL Automated Personalization] 活动显示的优惠名称中删除了位置。此更改使报告更具可读性。(TGT-44294)
* 从 [!DNL Target] UI 中的 AP 和[!UICONTROL 自动目标][!UICONTROL 个性化洞察]和[!UICONTROL 重要属性]报告中删除了 45 天和 90 天日历选项。由于使用模式和为了提高性能，已弃用这些日期范围。UI 已更新，以反映当前允许的范围：15 天、30 天和 60 天。(TGT-39357)
* 禁用了在活动上线后更改[!UICONTROL 目标和设置]页面上的[!UICONTROL 与优化目标相同]设置的功能。(TGT-43923)
* 修复了从 [!DNL Target Standard] 升级到 [!DNL Target Premium] 时导致 [!DNL Target] 后端默认工作区出现问题的情况。（TGT-44081 和 TGT-44306）
* 更改了[!UICONTROL 实施]页面（[!UICONTROL 管理]>[!UICONTROL 实施]）上“设备上决策的实现方法”的链接，使其指向说明如何为所有受支持的 SDK（Node.js、Java、.NET 和 Python）使用设备上决策的页面。有关更多信息，请参阅 [Target SDK 快速入门](https://developer.adobe.com/target/implement/server-side/sdk-guides/getting-started/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}。
* 修复了使用 [!DNL Scene7] 和 [!DNL Target] 时导致文件上传问题的情况。
* 通过使用内部可用性审计的结果，增强了 [!DNL Target] UI 对残障人士提供的可访问性。这些增强的辅助功能包括访问以前无法通过键盘访问的功能、替代文本增强功能、缩放 UI 部分以提高可用性的能力、改进键盘焦点等等。(TGT-42759)
* 对整个 [!DNL Target] UI 进行了各种本地化修复。

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
