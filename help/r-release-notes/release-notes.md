---
keywords: 发行说明；新增功能；发行；更新；更新；发行；增强；修复；错误修复；更新
description: 了解 Adobe Target 当前版本包含的新增功能、增强功能和修复，包括 SDK、API 和 JavaScript 库。
title: 当前版本中包含哪些新增功能？
feature: 发行说明
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
translation-type: tm+mt
source-git-commit: 60c3dfe28f3618113d4d03da538e4d0e4ac2feb8
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 36%

---

# Target 发行说明（当前版本）

这些发行说明提供了有关每个[!DNL Adobe Target Standard]和[!DNL Target Premium]版本的功能、增强和修复的信息。 此外，还包含目标 API、SDK、JavaScript库(at.js)的发行说明和其他平台更改（如果适用）。

>[!IMPORTANT]
>
>**mbox.js终止使用**:自2021年3月31日起， [!DNL Adobe Target] 不再支持mbox.js库。2021年3月31日之后，从mbox.js发出的所有调用将轻松失败，并会通过提供默认内容来影响运行[!DNL Target]活动的页面。
>
>在此日期之前迁移到新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript库的最新版本，以避免站点出现任何潜在问题。 有关详细信息，请参阅[概述：实现客户端web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)的目标。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## at.js 2.4.1（2021年3月23日）

此版本的 at.js 是一个维护版本，它包括以下增强功能和修复：

* 修复了mbox请求中包含`targetPageParams`的问题。 `targetPageParams` 应仅包含在 `pageLoad` 请求中。(TNT-40247)
* 修复了[!DNL Adobe Experience Platform Launch]扩展中的文档和窗口全局对象的问题，方法是将Platform launch全局对象依赖关系替换为对它们的直接引用。 (TNT-37124)

## Recommendations源处理服务器的IP地址更改（2021年3月16日）

[!DNL Target Recommendations]源处理服务器IP地址已于2021年3月16日更新。 有关详细信息，请参阅Recommendations源处理服务器](/help/c-recommendations/c-recommendations-faq/ip-addresses-marketing-cloud.md)使用的[ IP地址。

## Target Standard/Premium 21.2.1（2021 年 3 月 9 日）

此维护版本包含以下增强功能、修复和更改。

括号中的问题编号供 [!DNL Adobe] 内部使用。

* 增加了允许的优惠大小(TGT-38304):

   | 类型 | 上一个限制 | 新限制 |
   | --- | --- | --- |
   | HTML | 256KB | 1024KB |
   | 来自目标UI的可视优惠 | 64KB | 每个体验1024 KB |
   | 通过API | 512KB | 1024KB |

* [!UICONTROL 现] 在每天都 [!UICONTROL 会为自动目标] (AT)和 [!UICONTROL Automated Personalization] (AP)活动制作个性化见解报表。您可以选择一个报告，其中提供过去15、30和60天的[!UICONTROL 自动区段]或[!UICONTROL 重要属性]。 已删除45天和90天选项，以启用其他回顾窗口设置以每天运行。 (TGT-39472)
* 修复了当客户在活动的[!UICONTROL 目标和设置]页面上单击[!UICONTROL 编辑依赖关系]时，导致当前依赖关系不显示的问题。 (TGT-39340)
* 修复了刷新工作区[!UICONTROL 受众库]时的问题。 刷新之前，将显示当前选定工作区的受众。 刷新后，将显示[!UICONTROL 默认工作区]及其受众。 当前工作区及其受众现在在刷新后保留。 (TGT-38871)
* 修复了在复制[!UICONTROL Recommendations]活动并稍后通过更改原始活动的条件序列来编辑其时出现的问题。 原始活动中条件序列的更改也错误地应用于复制的活动。 (TGT-39155)
* 修复了导致[!UICONTROL Recommendations]排除显示的产品数不正确的问题。 (TGT-39599)

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 文档更改、以往的发行说明和 Experience Cloud 发行说明

除了针对每个发行的说明外，以下资源还提供更多其他信息：

| 资源 | 详细信息 |
|--- |--- |
| 文档更改 | 视图本指南中未包含的更新的详细信息。<br>有关更多信息，请参阅[文档更改](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)。 |
| 以前版本的发行说明 | 查看与以前版本的 Target Standard 和 Target Premium 中的新增功能和增强功能相关的信息。<br>有关更多信息，请参阅[以前版本的发行说明](/help/r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 发行说明 | 查看 Adobe Experience Cloud 解决方案的最新发行说明。<br>有关详细信息，请参阅 [Experience Cloud发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)。 |

## 预发行信息 {#section_5D588F0415A2435B851A4D0113ACA3A0}

您可以通过以下资源了解下一个 Target 版本即将包含的功能。

| 资源 | 详细信息 |
|--- |--- |
| Adobe优先级产品更新 | 若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| 即将推出的发行说明 | 有关当月 Target 发行版本的信息（包括预发行信息），请参阅 [Target 发行说明 - 预发行](/help/r-release-notes/target-release-notes.md)页面。 |
