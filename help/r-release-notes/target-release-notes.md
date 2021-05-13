---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解 Adobe Target 即将发布的版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的版本中包括什么新功能？
feature: 发行说明
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: f5047484b7cb113698b9b09f699d4e6a293b0b59
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 36%

---

# Target 发行说明（预发行版本）

本文包含预发行版本信息。发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新日期：2021 年 5 月 12 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。这些页面上的信息可能相同，具体取决于发布时间。 括号中的问题编号供 [!DNL Adobe] 内部使用。

>[!IMPORTANT]
>
>**mbox.js终止使用**:自2021年3月31日起， [!DNL Adobe Target] 不再支持mbox.js库。2021年3月31日之后，从mbox.js发出的所有调用都会正常失败，并会通过提供默认内容影响运行[!DNL Target]活动的页面。
>
>要避免站点出现任何潜在问题，请迁移到新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript库的最新版本。 有关详细信息，请参阅[概述：为客户端 Web 实现 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

## [!DNL Adobe Experience Platform Web SDK] （2021年5月17日）

此版本的[!DNL Platform Web SDK]包含对[!DNL Target]重定向的[!UICONTROL 目标](A4T)的分析支持。

## [!DNL Target Standard/Premium] 21.5.1（2021年5月25日）

随着发布日期的临近，将添加内容。

## [!DNL Target Standard/Premium] 21.5.2（确定日期）

此版本包含以下新增功能和增强功能。 括号中的问题编号供 [!DNL Adobe] 内部使用。

| 功能 | 详细信息 |
| --- | --- |
| ![Premium](/help/assets/premium.png) [!DNL Recommendations] | 以下增强功能适用于[!DNL Recommendations]流行度算法：<ul><li>当[!DNL Target]是行为数据源时，将为所有流行（最常查看/最热门的卖家）算法提供一个新的六小时“回顾窗口”（数据范围）选项。 （当[!DNL Adobe Analytics]是行为数据源时，此回顾窗口&#x200B;*不*&#x200B;可用。）</li><li>选择后，以下算法大约每三小时运行一次（而不是每12小时运行一次）。<ul><li>查看次数最多</li><li>购买量最高</li><li>最受类别</li><li>按类别购买最多</li><li>自定义属性查看次数最多（使用groupBy功能）</li><li>按自定义属性购买最多的产品（使用groupBy功能）</li></ul></ul>(TOP-1086) |

此版本包含以下修复。

* 将随着发行日期的临近而添加。

## at.js版本2.5.0（待确定日期）

此版本的at.js包含以下增强和更改：

* [对at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) 的设备上决策支持
* [预览](/help/c-activities/c-activity-qa/activity-qa.md) 链接支持Automated Personalization活动

此版本还删除了对Microsoft Internet Explorer 10及更高版本的支持。

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
