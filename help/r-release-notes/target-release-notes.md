---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: 发行说明，提供有关最新或即将发布的DNLAdobe Target版本的功能、增强和修复的信息。
title: Adobe Target预发行说明
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 7f23f80a0528ea2e6de78a5491c87ca72862813d
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 16%

---


# Target 发行说明（预发行版本）{#target-release-notes-prerelease}

本文包含预发行信息。 发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新日期：2020 年 7 月 13 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。这些页面上的信息可能相同，具体取决于发布时间。 括号中的问题编号供 [!DNL Adobe] 内部使用。

>[!NOTE]
>
>* **mbox.js弃用**: 2020年8月30日，Adobe Target将不再支持mbox.js库。 2020年8月30日之后，mbox.js发出的所有调用将正常失败，并会通过提供默认内容影响目标活动运行的页面。 我们建议所有客户在此日期之前迁移到at.js库的最新版本，以避免您的站点出现任何潜在问题。 有关详细信息，请 [参阅At.js工作方式](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) 和 [Adobe Target技能生成器： 开发人员聊天，将Adobe Target的mbox.js迁移到at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。
   >
   >   
   尽管目前支持mbox.js，但自2017年7月起，我们便未对此库提供功能更新。 较新的at.js比mbox.js具有许多优势。 at.js可缩短Web实施的页面加载时间，提高安全性，并为单页应用程序提供更好的实施选项。
   >
   >   
   通过将所有客户转移到at.js，我们的工程师和支持人员将能够为您提供新功能并优惠您期望从Adobe获得的支持。
   >
   >
* **目标通知**: 有关即将进行的目标的信息，请参阅事件公告页，包括目标技能生成器会话、开发人员聊天、网络研讨会和目标咖啡休息会话。 有关详细信息，请参阅 [目标公告](/help/r-release-notes/target-announcements.md)。


## Target Standard/Premium 20.7.1（2020 年 7 月 21 日） 

此版本包括以下增强功能：

### [!UICONTROL 管理] 部分UI刷新

我们正在逐步重写整个 [!DNL Target] UI，使用新的技术堆栈，以便能够优惠改进的性能、减少发布新功能时所需的维护时间以及改善整个产品的用户体验。 刷新的第一个部分是 [!UICONTROL Setup] （设置）部分，它已更名为 [!UICONTROL Administration]（管理）

作为此刷新的一部分，您将能够使用“管理”部分中的页面轻松执行 [!UICONTROL 许多] 操作，如：

* 从“实施”选项卡(“管理”>“ [!UICONTROL 实施] ”)下&#x200B;**[!UICONTROL 载最新]** 的at.js **[!UICONTROL 文件]**。
* 自定义您的at.js设置，并可轻松查看更改(“**[!UICONTROL 管理]** ”> **[!UICONTROL “实]**&#x200B;施”)。
* 修改增强的报告设置，如默认货币和时区、要从报告中排除的IP等。 (**[!UICONTROL 管理]** > **[!UICONTROL 报告]**)
* 出于隐私原因模糊处理访客IP **[!UICONTROL 地址]** (“管 **[!UICONTROL 理”]**>“实施”)
* 在AdobeAdmin Console（“管理”>“用户”）中管理每个工作区的用户及其角色的现&#x200B;**[!UICONTROL 有视图]** ，之 **[!UICONTROL 前再进]**&#x200B;行列表。
* 搜索并过滤“管理”部分中 [!UICONTROL 的所有] 表。

### 增强功能、修复和变更

此版本包含以下增强、修复和更改：

* 修复了在刷新后无法保留站点首选项的问题。 (TGT-37239)
* 修复了“在后插 [!UICONTROL 入”] >“图 [!UICONTROL 像”无法正常使用] 可缩放矢量图形(SVG)图像的问题。 (TGT-37242)
* 修复了具有“发布者”角 [!UICONTROL 色的用户] ，该问题导致无法删除草稿活动。 (TGT-37358)
* 修复了在选择“我的所有工作区”时阻止 [!UICONTROL 用户编辑活动] 的问题。 (TGT-37276)

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
