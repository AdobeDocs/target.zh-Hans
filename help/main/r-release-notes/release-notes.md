---
keywords: 发行说明；新功能；版本；更新；更新；版本；增强；增强；修复；错误修复；更新、当前更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: c6799d43ee2f5ebe568f7199ae4ec1deaa164c06
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 52%

---

# [!DNL Target]发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的发行说明以及其他平台变更。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## [!DNL Target Standard/Premium] 25.4.1（2025年4月2日）

此版本包含以下修复和更新：

* 修复了导致体验受众从活动中消失的问题。 (TGT-52003)
* 修复了在投放期间导致出现意外元素的问题。 (TGT-52011)
* 修复了阻止客户在Ove[!UICONTROL r]视图页面的定位图形中以及活动编辑期间查看受众的问题。 (TGT-52050)
* 修复了一个问题，该问题阻止客户在[!UICONTROL Experience Targeting] (XT)活动中按优先级重新排序体验。 (TGT-52054)
* 修复了在撤消文本样式更改时导致呈现不正确的问题。 (TGT-51876)
* 修复了在修改重定向选件时，[!DNL Target]还会删除与该选件关联的所有[!UICONTROL ClickTrack]选择器的问题。 (TGT-51936)
* 修复了在取消[!UICONTROL ClickTrack]时导致[!DNL Target]错误保存选择器的问题。 (TGT-51937)
* 修复了在未进行任何更改的情况下打开和关闭[!UICONTROL Goals & Settings]页面上的mbox选取器后触发无效名称错误的问题。 (TGT-51983)
* 修复了阻止编辑在旧版[!DNL Target] UI中创建的临时优惠的问题。 (TGT-51984)
* 修复了阻止编辑具有包含自定义代码的临时选件的活动的问题。 (TGT-51995)
* 修复了在编辑组合受众定义时导致排除规则显示为包含规则的问题。 (TGT-51999)
* 修复了在体验编辑期间阻止自定义代码正确显示的问题。 (TGT-52005)
* 修复了[!UICONTROL Insert Before]选项无法用于在导航栏之前插入内容的问题。 (TGT-52031)
* 修复了导致无法在报告中正确突出显示默认体验的问题。 (TGT-51716)
* 修复了在创建活动时触发`default message [Invalid optionLocalIds: xx]]`消息的问题。 (TGT-52038)

## at.js版本2.11.8（2025年3月31日）

* 解决了字符串后缀验证中CodeQL识别的漏洞，以防止在调整大小和移动操作期间出现边缘情况。 (TNT-51516)

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
