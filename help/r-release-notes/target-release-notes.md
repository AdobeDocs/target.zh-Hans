---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解 Adobe Target 即将发布的版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的版本中包括什么新功能？
feature: 发行说明
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 113e4627d491ea10192359c755dba29fc92e8e22
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 61%

---

# Target 发行说明（预发行版本）

本文包含预发行版本信息。发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新日期：2021 年 8 月 3 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

>[!IMPORTANT]
>
>**mbox.js 生命周期结束**：从 2021 年 3 月 31 日起，[!DNL Adobe Target] 将不再支持 mbox.js 库。2021 年 3 月 31 日之后，所有从 mbox.js 进行的调用都会失败，并影响您通过提供默认内容而运行 [!DNL Target] 活动的页面。
>
>请迁移到新 [!DNL Adobe Experience Platform Web SDK] 或 at.js JavaScript 库的最新版本，以避免您的网站出现任何潜在问题。有关详细信息，请参阅[概述：为客户端 Web 实现 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

## [!DNL Target Standard/Premium] 21.8.1（2021年8月4日）

此维护版本包含许多后端增强功能，包括以下面向客户的更改：

* 修复了导致在[!UICONTROL 基于表单的体验编辑器]中创建的[!UICONTROL 自动个性化]活动的报表引用报表中已删除的选件的问题。 此问题导致显示以下错误消息：“检索此报表的数据时遇到问题。 如果问题仍然存在，请联系Adobe客户关怀。” (TGT-41028)

## Target交付API（确定日期）

此版本包含以下增强功能：

* mbox参数限制已增加到100个参数。 以前的限制是50个参数。 (TNT-41717)
* `categoryId`的限制已增加到256个字符。 以前的限制为128个字符。
* 向交付API中添加了以下[!DNL Adobe Audience Manager](AAM)详细信息：

   * AAM UUID(Adobe Audience Manager独特用户ID)
   * dataPartnerId
   * dataPartnerUserId

   以前，交付API仅包含`dcsLocationHint`和`blob`。 (TNT-41644)

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
