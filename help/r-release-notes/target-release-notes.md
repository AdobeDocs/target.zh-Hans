---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解 Adobe Target 即将发布的版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的版本中包括什么新功能？
feature: 发行说明
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 3be6ad187b99472ccd3019e6998eba4953e2f5b5
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 51%

---

# Target 发行说明（预发行版本）

本文包含预发行版本信息。发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新日期：2021 年 5 月 24 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

>[!IMPORTANT]
>
>**mbox.js 生命周期结束**：从 2021 年 3 月 31 日起，[!DNL Adobe Target] 将不再支持 mbox.js 库。2021 年 3 月 31 日之后，所有从 mbox.js 进行的调用都会失败，并影响您通过提供默认内容而运行 [!DNL Target] 活动的页面。
>
>请迁移到新 [!DNL Adobe Experience Platform Web SDK] 或 at.js JavaScript 库的最新版本，以避免您的网站出现任何潜在问题。有关详细信息，请参阅[概述：为客户端 Web 实现 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

## ![Adobe Experience Platform Web SDK](/help/assets/platform.png) [!DNL Adobe Experience Platform Web SDK] 版本2.5.0（2021年6月1日）

此版本的[!DNL Platform Web SDK]支持以下功能：

| 功能 | 详细信息 |
| --- | --- |
| 对[!UICONTROL Analytics for Target](A4T)的重定向支持 | 现在，使用A4T时，Platform Web SDK支持[!DNL Target]重定向。 [!DNL Adobe Target]中的重定向选件会导致浏览器重定向到新页面。 |
| 响应令牌 | Platform Web SDK现在支持[!DNL Target]响应令牌。 响应令牌允许您自动将特定于[!DNL Adobe Target]的信息输出到品牌的网页。 此信息可以包括有关活动、选件、体验、用户配置文件、地理信息等的详细信息。 这些详细信息可提供额外的响应数据，以便与内部或第三方系统共享或用于调试。 |

## [!DNL Target Standard/Premium] 21.5.1（2021年6月8日）

随着发行日期的临近，将会添加内容。

## [!DNL Target Standard/Premium] 21.5.2（确定日期）

此版本包含以下新增功能和增强功能。括号中的问题编号供 [!DNL Adobe] 内部使用。

| 功能 | 详细信息 |
| --- | --- |
| ![Premium](/help/assets/premium.png) [!DNL Recommendations] | 以下增强功能适用于[!DNL Recommendations]流行算法：<ul><li>当[!DNL Target]是行为数据源时，为所有常用（查看次数最多/最畅销的）算法都提供一个新的六小时“回顾窗口”（数据范围）选项。 （当[!DNL Adobe Analytics]是行为数据源时，此回顾窗口为&#x200B;*不*。）</li><li>选择后，以下算法大约每三小时运行一次（而不是每12小时运行一次）。<ul><li>查看次数最多</li><li>购买次数最多</li><li>按类别查看次数最多</li><li>按类别购买次数最多</li><li>按自定义属性查看次数最多的项目（使用groupBy功能）</li><li>按自定义属性购买的最多产品（使用groupBy功能）</li></ul></ul>(TOP-1086) |

此版本包含以下修复。

* 随着发行日期的临近，将会添加内容。

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
