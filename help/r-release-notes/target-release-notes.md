---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: 发行说明，提供有关最新或即将发布的DNLAdobe Target版本的功能、增强和修复的信息。
title: Adobe Target预发行说明
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 058828bbf3f13704d9e941563b7dab5259be6809
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 19%

---


# Target 发行说明（预发行版本）{#target-release-notes-prerelease}

本文包含预发行信息。 发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新时间：2020 年 6 月 23 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。这些页面上的信息可能相同，具体取决于发布时间。 括号中的问题编号供 [!DNL Adobe] 内部使用。

>[!NOTE]
>
>* **mbox.js弃用**: 2020年8月30日，Adobe Target将不再支持mbox.js库。 2020年8月30日之后，mbox.js发出的所有呼叫都将失败，并影响您的Target活动正在运行的页面。 我们建议所有客户在此日期之前迁移到at.js库的最新版本，以避免您的站点出现任何潜在问题。 有关详细信息，请 [参阅At.js工作方式](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) 和 [Adobe Target技能生成器： 开发人员聊天，将Adobe Target的mbox.js迁移到at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。
   >
   >   
   尽管目前支持mbox.js，但自2017年7月起，我们便未对此库提供功能更新。 较新的at.js比mbox.js具有许多优势。 at.js可缩短Web实施的页面加载时间，提高安全性，并为单页应用程序提供更好的实施选项。
   >
   >   
   通过将所有客户转移到at.js，我们的工程师和支持人员将能够为您提供新功能并优惠您期望从Adobe获得的支持。
   >
   >
* **Target通知**: 有关即将进行的Target的信息，请参阅事件公告页，包括Target技能生成器会话、开发人员聊天、网络研讨会和Target咖啡休息会话。 有关详细信息，请参阅 [Target公告](/help/r-release-notes/target-announcements.md)。


## Target Standard/高级版20.6.1（2020年7月，确切日期待定）

此版本包括以下增强功能：

### AnalyticsTarget(A4T)支持自动 [!UICONTROL Target] 活动

[!UICONTROL 自动Target] 活动现在支 [持AnalyticsTarget](/help/c-integrating-target-with-mac/a4t/a4t.md)。

此集成使用高级机器学习从多个高性能营销人员定义的体验中进行选择，从而个性化内容并推动转化。 自动定位根据每位访客的个人客户配置文件和具有相似配置文件的先前访客的行为，向每位访客提供量身定制的体验。

如果您已实 [施A4T](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) 以用于A/B测试活动，您已经可以了！

### [!UICONTROL 管理] 部分UI刷新

我们已更新“管 [!UICONTROL 理] ”部分(以 [!UICONTROL 前称为Admin])及其页面，使您的工作流更简单、高效。

亮点包括：

* **[!UICONTROL “视觉体验书写器]”页&#x200B;**: 通过此新页面(**[!UICONTROL “管理&#x200B;]**”**[!UICONTROL >“可视体验书写器&#x200B;]**”)，您可以：

   * 配置VEC的常规设置(指定默认URL，启用增 [!UICONTROL 强体验书写器]，加载混合内容，并在活动流图中生成体验快照)
   * 配置移动视区
   * 配置CSS选择器

* **[!UICONTROL 报告]页&#x200B;**: 通过此新页面(**[!UICONTROL “管理&#x200B;]**”>“**[!UICONTROL 报告&#x200B;]**”[!DNL Target])，您可以配置一般设置，以在应用于[!DNL Target]整个帐户的报告中使用。

   可用设置包括：

   * 用 [!DNL Adobe Experience Cloud] 于报告的解决方案
   * 用于报告的时区
   * 用于报告的货币
   * 要从报告中排除的IP地址
   * 是否显示报告收入的估计增长
   * 是否启用细粒度优先级

* 以前的 [!UICONTROL 主机] (Hosts)页面已拆分为两个新页面：

   * [!UICONTROL 主机]
   * [!UICONTROL 环境]

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
