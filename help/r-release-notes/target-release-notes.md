---
keywords: 发行说明；发行；更新；未来发行；增强；新增功能；修复；更新；预发行
description: 了解即将发布的Adobe Target版本（包括SDK、API和JavaScript库）中包含的新功能、增强和修复。
title: 即将发布的版本中包含哪些新增功能？
feature: 发行说明
translation-type: tm+mt
source-git-commit: 801a2717615a1f0ff2ce306cda59f68cc5c4a8f8
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 22%

---


# Target 发行说明（预发行版本）

本文包含预发行信息。 发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新日期：2021 年 1 月 3 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。这些页面上的信息可能相同，具体取决于发布时间。 括号中的问题编号供 [!DNL Adobe] 内部使用。

>[!IMPORTANT]
>
>**mbox.js终止使用**:2021年3月31日， [!DNL Adobe Target] 将不再支持mbox.js库。2021年3月31日之后，从mbox.js发出的所有调用将轻松失败，并会通过提供默认内容来影响运行[!DNL Target]活动的页面。
>
>Adobe建议所有客户在此日期之前迁移到新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript库的最新版本，以避免您的站点出现任何潜在问题。 有关详细信息，请参阅[概述：实现客户端web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)的目标。

## Target Standard/Premium 21.2.1（2021 年 3 月 9 日）

此维护版本包含以下增强功能、修复和更改。

括号中的问题编号供 [!DNL Adobe] 内部使用。

* 增加了允许的优惠大小(TGT-38304):

   | 类型 | 上一个限制 | 新限制 |
   | --- | --- | --- |
   | HTML | 256KB | 1024KB |
   | 来自目标UI的可视优惠 | 64KB | 每个体验1024 KB |
   | 通过API | 512KB | 1024KB |

* [!UICONTROL 自] 动目标 [!UICONTROL (AT)和] Automated Personalization(AP) [!UICONTROL 活动的] 个性化洞察报表现在每天生成。您可以选择一个报告，其中提供过去15、30和60天的[!UICONTROL 自动区段]或[!UICONTROL 重要属性]。 已删除45天和90天选项，以启用其他回顾窗口设置以每天运行。 (TGT-39472)
* 修复了当客户在活动的[!UICONTROL 目标和设置]页面上单击[!UICONTROL 编辑依赖关系]时，导致当前依赖关系不显示的问题。 (TGT-39340)
* 修复了刷新工作区[!UICONTROL 受众库]时的问题。 刷新之前，将显示当前选定工作区的受众。 刷新后，将显示[!UICONTROL 默认工作区]及其受众。 当前工作区及其受众现在在刷新后保留。 (TGT-38871)
* 修复了在复制[!UICONTROL Recommendations]活动并稍后通过更改原始活动的条件序列来编辑其时出现的问题。 原始活动中条件序列的更改也错误地应用于复制的活动。 (TGT-39155)
* 修复了导致[!UICONTROL Recommendations]排除显示的产品数不正确的问题。 (TGT-39599)

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
