---
keywords: 发行说明;新功能;版本;更新;更新;版本;增强;增强;修复;错误修复;更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 4395caa7e40717c59067eaedff5e53776768eda9
workflow-type: ht
source-wordcount: '573'
ht-degree: 100%

---

# [!DNL Target]发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的发行说明以及其他平台变更。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## 从浏览器受众属性中弃用 iPad 和 iPhone（2024 年 4 月 30 日）

| 弃用 | 详细信息 |
|--- |--- |
| 即将从在创建受众时所使用的[浏览器属性](/help/main/c-target/c-audiences/c-target-rules/browser.md)中弃用 [!DNL iPad] 和 [!DNL iPhone]<p>弃用日期：<P>2024 年 4 月 30 日 | [!DNL Adobe Target] 可让您[定位多个类别属性中的任一属性](/help/main/c-target/c-audiences/c-target-rules/target-rules.md)，包括在访问您的页面时使用特定的[浏览器或浏览器选项](/help/main/c-target/c-audiences/c-target-rules/browser.md)的用户。<P><B>从 2024 年 4 月 30 日开始，在为受众创建类别时，将从可用的[!UICONTROL 浏览器]类型下拉列表中删除 iPad 和 iPhone。</b><P>使用 [!DNL Target] UI 创建的内置受众（例如“浏览器：iPad”和“浏览器：iPhone”）将自动移至新的受众定义。<p>有关必须手动更改的替代设置的示例，请参阅[从浏览器受众属性中弃用 iPad 和 iPhone（2024 年 4 月 30 日）](/help/main/c-target/c-audiences/c-target-rules/browser.md#deprecation)。 |

## [!DNL Target] Standard/Premium 24.1.1（2024 年 1 月 22 日、23 日和 25 日）

此版本计划在接下来的几天发布：

* **1 月 22 日**：欧洲、中东和非洲 (EMEA) 地区
* **1 月 23 日**：亚太 (APAC) 地区
* **1 月 25 日**：美洲区域

此版本包含以下增强和修复：

* 具有收入目标量度的 [!UICONTROL Analytics for Target] (A4T) 活动未将“收入”显示为列名称，并且未在报告中以 ($) 格式显示收入量度。这是一个已经解决的外观问题。(TGT-46995)
* 修复了一个问题，该问题导致报告日期间隔不起作用。(TGT-47396)
* 修复了一个问题，该问题导致在客户使用[!UICONTROL 更多操作]图标激活或停用某项活动后在[!UICONTROL 所有活动]页面上显示的状态有误。(TGT-47367)
* 修复了一个问题，该问题导致无法为单个客户显示[!UICONTROL 重要属性]报告。(TGT-47272)
* 修复了一个问题，该问题导致在单个客户尝试启用“需要身份验证”时显示“负载无效”消息。(TGT-47195)
* 更新了 [!DNL Target] UI 中的大量本地化字符串。

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
