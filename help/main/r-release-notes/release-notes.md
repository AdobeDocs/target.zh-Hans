---
keywords: 发行说明；新功能；版本；更新；更新；版本；增强；增强；修复；错误修复；更新、当前更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 911950b341d8221145eeacfa288926b0a1be434e
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 43%

---

# [!DNL Target]发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的发行说明以及其他平台变更。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## [!DNL Target Standard/Premium] 25.3.5（2025年3月11日）

此版本包含以下修复和更新：

* 修复了更新的[!UICONTROL Visual Experience Composer] (VEC)中的问题，该问题导致痕迹导航不始终显示在编辑器底部，从而难以准确地选择元素。 (TGT-51844)
* 解决了阻止用户更改[!UICONTROL Modifications]面板中选件的问题。 (TGT-51800)
* 解决了在体验和受众的左侧面板（包括在[!UICONTROL ClickTrack]模式下）中错误显示操作的问题。 (TGT-51895)
* 解决了[!UICONTROL ClickTrack]选择器未应用于正确受众页面的问题。 (TGT-51871)

## [!DNL Target Standard/Premium] 25.3.4（2025年3月7日）

此版本包含以下修复和更新：

* 解决了仅活动受众在[!UICONTROL Audiences]面板中不可见，导致无法编辑或重用的问题。 (TGT-51860)
* 修复了阻止[!DNL Target Standard]客户使用[!UICONTROL Analytics for Target] (A4T)报表创建活动的问题。 (TGT-51854)
* 修复了在批量创建和编辑操作期间从有效负载中排除本地ID计数器的问题。 (TGT-51867)

## [!DNL Target Standard/Premium] 25.3.2（2025年3月6日）

此版本包含以下修复和更新：

* 修复了复制仅包含活动受众的活动时无法创建新活动，从而错误地使用原始活动的受众的问题。 (TGT-51855)
* 修复了阻止编辑具有仅限该活动的受众的[!UICONTROL Experience Targeting] (XT)活动的问题。 (TGT-51846)
* 修复了[!UICONTROL Visual Experience Composer] (VEC)在首次编辑时无法正确将修改应用于体验的问题。 (TGT-51843)
* 修复了单击VEC中的某些元素时触发“ID”错误的问题。 (TGT-51814)
* 在活动创建期间更新了VEC中的错误处理。 (TGT-51759)
* 修复了在保存活动时，[!UICONTROL Modifications]面板中缺少视图导致“无效用户输入”错误的问题。 (TGT-51827)
* 修复了阻止创建推荐标准的问题。 (TGT-51834)
* 在重定向到其他URL之前添加了确认消息。 (TGT-51703)
* 修复了选件和文件夹中的GraphQL集成测试问题。 (TGT-51839)

## [!DNL Target Standard/Premium] 25.3.1（2025年3月3日）

此版本包含以下修复和更新：

* 组合受众可以包括子组，每个子组包含多个受众。 此版本修复了导致子组受众无法在[!UICONTROL Rules]对话框中显示的问题。 (TGT-51813)
* 解决了在打开旧版活动时，某些体验受众被替换为[!UICONTROL All Visitors]的问题。 (TGT-51812)
* 解决了阻止编辑仅具有活动受众的活动的问题。 (TGT-51807)
* 解决了阻止在更新的[!DNL Target] UI中编辑页面标题修改的问题。 (TGT-51797)
* 解决了在复制体验、删除其他体验然后尝试保存活动时发生的空错误。 (TGT-51796)
* 解决了在创建活动的[!UICONTROL Targeting]步骤期间，受众信息面板中无法显示受众排除规则的问题。 (TGT-51579)
* 更新了韩语本地化的错误消息。 （TGT-51701 和 TGT-51699）

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

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
