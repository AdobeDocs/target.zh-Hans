---
keywords: 发行说明;新功能;版本;更新;更新;版本;增强;增强;修复;错误修复;更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 9489655d18170c581f2abf8502f01c7b7e0626b7
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 52%

---

# Target 发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的发行说明以及其他平台变更。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## [!DNL Target Standard/Premium] 22.5.1(错开释放；2022年5月11至13日)

此版本将按照以下分批次计划提供：

* **5月11日**:亚太地区
* **5月12日**:北美洲(NA)地区
* **5月13日**:欧洲、中东和非洲(EMEA)地区

此版本包含以下增强功能和修复：

* 修复了导致JavaScript错误并阻止某些客户访问特定活动详细信息的问题 [!UICONTROL Automated Personalization] (AP)活动。 (TGT-43526)
* 修复了导致某些客户无法向AP活动添加（或编辑）特定选件的问题。 (TGT-43503)
* 修复了 [!DNL Target] 显示以下错误消息的UI:“您的全局mbox可能不同步。 请尝试重新保存它。”此问题是UI问题，不会影响客户的实施。 (TGT-43475)
* 修复了在新建客户之前创建细化和受众时，导致一位客户无法编辑体验级别的活动细化和受众的问题 [!UICONTROL 受众] 已部署UI。 (TGT-43433)
* 修复了允许客户选择重复项的问题 [!DNL Adobe Audience Manager] (AAM)受众。 (TGT-43430)
* 修复了阻止客户在不同工作区中创建重复受众的问题。 (TGT-43423)
* 修复了阻止客户删除在 [!UICONTROL 基于表单的体验编辑器]. (TGT-43315)
* 修复了在单击图像选件并刷新UI后阻止客户访问代码选件的问题。 (TGT-43566)
* 确保 [!DNL Target] 创建使用 [!DNL Analytics for Target] (A4T)仅显示由 [!DNL Adobe Analytics]. (TGT-43294)
* 修复了在编辑、激活和停用配置文件脚本后，对配置文件脚本所做的编辑还原到原始未编辑脚本的问题。 配置文件脚本现在保持其编辑状态。 (TGT-43249)
* 修复了在尝试将受众移动到其他工作区时导致以下错误的问题：“我们无法完成您的请求。 如果问题仍然存在，请联系Adobe客户关怀团队。” (TGT-43212)
* 修复了在克隆单页应用程序(SPA)页面的自定义代码修改时导致错误的错误。 (TGT-43137)
* 修复了在复制体验并编辑促销活动后，导致原始促销活动受到影响的问题。 (TGT-41775)

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh_Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 文档更改、以往的发行说明和 Experience Cloud 发行说明

除了针对每个发行的说明外，以下资源还提供更多其他信息：

| 资源 | 详细信息 |
|--- |--- |
| 文档更改 | 查看这些发行说明中未包括的关于本指南的更新的详细信息。<br>有关更多信息，请参阅[文档更改](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)。 |
| 以前版本的发行说明 | 查看与以前版本的 Target Standard 和 Target Premium 中的新增功能和增强功能相关的信息。<br>有关更多信息，请参阅[以前版本的发行说明](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 发行说明 | 查看 Adobe Experience Cloud 解决方案的最新发行说明。<br>有关更多信息，请参阅 [Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans)。 |

## 预发行信息 {#section_5D588F0415A2435B851A4D0113ACA3A0}

您可以通过以下资源了解下一个 Target 版本即将包含的功能。

| 资源 | 详细信息 |
|--- |--- |
| Adobe 优先产品更新 | 若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：<br>[](https://www.adobe.com/cn/subscription/priority-product-update.html)https://www.adobe.com/cn/subscription/priority-product-update.html |
| 即将推出的发行说明 | 有关当月 Target 发行版本的信息（包括预发行信息），请参阅 [Target 发行说明 - 预发行](/help/main/r-release-notes/target-release-notes.md)页面。 |
