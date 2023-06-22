---
keywords: 发行说明;新功能;版本;更新;更新;版本;增强;增强;修复;错误修复;更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 3349b3a948186a18093adfc4580c5134e9ef7fc7
workflow-type: ht
source-wordcount: '671'
ht-degree: 100%

---

# [!DNL Target]发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的发行说明以及其他平台变更。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## [!DNL Target] Standard/Premium 23.5.2（2023 年 5 月 31 日）

此版本包含以下增强功能和修复：

* 修复了一个问题，该问题导致在生成配置文件 API 授权令牌时显示空白页。（TGT-45387 和 TGT-45423）
* 修复了如果图像名称包含 GB 18030 个字符，阻止在[!UICONTROL 创建设计]面板中显示该图像的问题。(TGT-44614)
* 修复了一个问题，在该问题中，体验中的文本/HTML 内有一些 GB 18030 符号字符转义不当。(TGT-44600)
* 修复了导致反映在分析过程中 [!UICONTROL Auto Personalization] 活动停滞的问题。(TGT-44820)
* 修正了如果活动名称包含方括号（[或]），则无法在[!UICONTROL 活动]页面上搜索活动的问题。(TGT-44777)
* 修复了一个问题，如果活动的目标包含特殊字符，则该问题阻碍该活动进行同步。(TGT-44982)
* 修复了一个问题，该问题导致对于某些客户的默认工作区，在 [!DNL Target] UI 中不显示任何活动。(TGT-45286)
* 更新了“不允许重复”标志的行为。更新了被排除的重复优惠标志，以便可重复优惠（如果优惠为默认内容优惠（对于 API v3、v4））并可重复选项（如果选项引用默认内容优惠且未定义模板）。(TNT-46617)
* 修复了一个问题，其中为 URL 添加了一个查询参数，该参数阻碍在[!UICONTROL 可视化体验编辑器] (VEC) 中加载页面。(TGT-44873)
* 纠正了整个 [!DNL Target] UI 中的多处本地化错误。

## 与[!DNL Target]共享 Real-Time CDP 配置文件属性 [!UICONTROL Real-Time CDP 配置文件属性]（2023 年 6 月 13 日）

此版本包含以下增强功能：

| 功能 | 详细信息 |
|--- |--- |
| 与 [!DNL Target] 共享的 Real-Time CDP 配置文件属性 | Real-Time CDP 配置文件属性可以共享给 [!DNL Target]，用于 HTML 选件和 JSON 选件。<P>有关更多信息，请参阅 [与  [!DNL Target]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#rtcdp-profile-attributes) 共享 Real-Time CDP 配置文件属性。 |

## [!DNL Target] Standard/Premium 23.5.1（2023 年 5 月 23-25 日）

将按以下交错的时间表发布此版本：

5 月 23 日：欧洲、中东和非洲 (EMEA) 地区
5 月 24 日：亚太 (APAC) 地区
5 月 25 日：美洲地区

此版本包含以下新增强功能和修复：

* 修复了阻止某些客户使用“大于”或“小于”运算符创建具有访客配置文件的受众的问题。(TGT-45271)
* 纠正了整个 [!DNL Target] UI 中的多处本地化错误。
* 为即将推出的新 UI 更新了多个位置的 Target UI（直到发布更新为止，这些更改都隐藏在功能标志的后面）。

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
