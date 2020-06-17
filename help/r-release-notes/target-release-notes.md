---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: 发行说明，提供有关最新或即将发布的DNLAdobe Target版本的功能、增强和修复的信息。
title: Adobe Target预发行说明
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 44d9024cb9c1f6a1e28845f9545fed0d56fe176a
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 16%

---


# Target 发行说明（预发行版本）{#target-release-notes-prerelease}

本文包含预发行信息。 发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新时间：2020 年 6 月 17 日**

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


## Target Standard/Premium 20.5.1（2020 年 6 月 17 日） 

| 功能/增强 | 描述 |
| --- | --- |
| Analytics for Target (A4T) 支持 [!UICONTROL 自动分配] 活动 | [!UICONTROL 自动分配活动] 现在支持 [Analytics进行Target](/help/c-integrating-target-with-mac/a4t/a4t.md)。<br>此集成允许您使用自动 [!UICONTROL 分配] 、多重装备的强盗功能，在使用Adobe [!UICONTROL Analytics目标指标和／或Adobe] Analytics报告和分析功  能的同时，推动流量增长。<br>如果您已实 [施A4T](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) ，以与A/B测试和体验定位活动配合使用，您就可以了！<br>有关详细信息，请 [参阅AnalyticsTarget(A4T)支持在创建活动时自动分配活动](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa) ( *Auto-Allocate)*。 |
| [!UICONTROL 发布者] 角色 | 此新角色与当前“观察者”角 [!UICONTROL 色类似] (可以视图活动，但不能创建或编辑这些角色)。 但是，发 [!UICONTROL 布者] 角色具有激活活动的其他权限。<br>有关详细信息，请参阅： <ul><li>**Target Standard用户**: [在用户中指定角色](/help/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) 和 *权限*。</li><li>**Target高级版用户**: [第6步： 在“配置企业权限](/help/administrating-target/c-user-management/property-channel/properties-overview.md#section_8C425E43E5DD4111BBFC734A2B7ABC80) ”中 *指定角色和权限*。</li></ul> |
| 2020年6月25 [!DNL Analysis Workspace]<br>日支持A4T | [!UICONTROL 现在支持] (A4T)的Target分析 [!DNL Analysis Workspace]。 通 [!UICONTROL 过Analytics的Target(A4T)面板] ，您可以 [!DNL Adobe Target] 分析活动和体验 [!DNL Analysis Workspace]。<br>有关详细信息，请参 [阅Analytics](/help/c-integrating-target-with-mac/a4t/reporting.md) (A4T *报告)和* Analytics(A4T)面板中的“Reports in [A4T for Savige”(A4T)面板(](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/a4t-panel.html)**&#x200B;位于Analytics工具指南中)。 |

### 增强功能、修复和变更

* 修复了导致“访客”度量存储在活动的定义中而不是“UniqueVisitors”的问题。 (TGT-37098)
* 修复了UI中导 [!DNL Target] 致垂直滚动条在受众页面上无法正 [!UICONTROL 确工作] 的问题。 (TGT-36968)

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
