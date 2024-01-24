---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解即将发布的 [!DNL Adobe Target]版本中包括的新功能、增强功能和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 99152f66217f66174e8b6a5a7319f11b22c74b8e
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 95%

---

# [!DNL Target] 发行说明（预发行版本）

本文包含即将发布的 [!DNL Adobe Target] 版本的预发行信息，包括 SDK、API 和 JavaScript 库。

**上次更新日期： 2024年1月22日**

>[!NOTE]
>
>发布日期、功能及其他信息如有更改，恕不另行通知。
>
>要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## 从浏览器受众属性中弃用 iPad 和 iPhone（2024 年 4 月 30 日）

| 弃用 | 详细信息 |
|--- |--- |
| 即将从在创建受众时所使用的[浏览器属性](/help/main/c-target/c-audiences/c-target-rules/browser.md)中弃用 [!DNL iPad] 和 [!DNL iPhone]<p>弃用日期：<P>2024 年 4 月 30 日 | [!DNL Adobe Target] 可让您[定位多个类别属性中的任一属性](/help/main/c-target/c-audiences/c-target-rules/target-rules.md)，包括在访问您的页面时使用特定的[浏览器或浏览器选项](/help/main/c-target/c-audiences/c-target-rules/browser.md)的用户。<P><B>从 2024 年 4 月 30 日开始，在为受众创建类别时，将从可用的[!UICONTROL 浏览器]类型下拉列表中删除 iPad 和 iPhone。</b><P>如果您有受众使用[!UICONTROL 浏览器]属性将 iPad 或 iPhone 作为目标，则您必须在 2024 年 4 月 30 日之前更改这些设置以确保这些受众继续发挥预期的作用。<p>有关替代设置的示例，请参阅 [从“浏览器”受众属性弃用iPad和iPhone （2024年4月30日）](/help/main/c-target/c-audiences/c-target-rules/browser.md#deprecation). |

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

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
