---
keywords: 发行说明;新功能;版本;更新;更新;版本;增强;增强;修复;错误修复;更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: e130c68c838e799228956c598c583038a2f68ecf
workflow-type: ht
source-wordcount: '494'
ht-degree: 100%

---

# [!DNL Target]发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的发行说明以及其他平台变更。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## [!DNL Adobe Target] 计划的边缘基础设施升级 {#edge}

计划的边缘基础设施升级需要将额外的 IP 或域列入允许列表。检查边缘部署 41-48 的 NAT 和 IP/域并将其列入允许列表。基础设施升级将于 2023 年 8 月 9 日开始。


有关更多信息，请参阅《Adobe Target 开发人员指南》**&#x200B;中的[将 Target 边缘节点列入允许列表](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html?lang=zh-Hans){target=_blank}。

## [!DNL Target] Standard/Premium 23.8.1（2023 年 8 月 9 日）

此版本包含以下增强和修复：

* 修复了一个问题，该问题有时导致活动无法正确同步，如[!UICONTROL 活动]列表页面上的[!UICONTROL 状态]栏中所示。（TGT-46010 和 TGT-44831）
* 修复了一个问题，该问题有时导致无法在使用 [!UICONTROL Analytics for Target] (A4T) 作为报告源的活动的[!UICONTROL 报告]页面上显示“[!UICONTROL 在 Analytics 中查看]”链接。(TGT-45808)
* 调整了表格中值的显示方式，改为显示百分比，而非带小数的数字。例如，8% 而非 .08。(TGT-45548)
* 修复了一个问题，该问题导致客户无法使用键盘焦点在[!UICONTROL 体验定位] (XT) 活动的[!UICONTROL 目标和设置]页面中移至下一个元素。(TGT-44526)
* 修复了一个问题，该问题导致在创建活动时打开“[!UICONTROL 添加受众]”对话框后键盘失去焦点。(TGT-44525)

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
