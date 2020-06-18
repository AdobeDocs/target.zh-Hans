---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: 这些发行说明介绍了每个 Target Standard 和 Target Premium 版本的功能、增强功能、修复信息和已知问题。
title: 'Adobe Target 发行说明（当前版本） '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: b25108284abbc44320fdceddd8ca155e2b800b3c
workflow-type: tm+mt
source-wordcount: '1038'
ht-degree: 28%

---


# Target 发行说明（当前版本）{#target-release-notes-current}

这些发行说明介绍了每个 Target Standard 和 Target Premium 版本的功能、增强功能和修复信息。此外，还包含TargetAPI、SDK、JavaScript库(at.js)的发行说明以及其他平台更改（如果适用）。

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


括号中的问题编号供 [!DNL Adobe] 内部使用。

## Target Standard/Premium 20.5.1（2020 年 6 月 17 日） 

| 功能/增强 | 描述 |
| --- | --- |
| Analytics for Target (A4T) 支持 [!UICONTROL 自动分配] 活动 | [!UICONTROL 自动分配活动] 现在支持 [Analytics进行Target](/help/c-integrating-target-with-mac/a4t/a4t.md)。<br>此集成允许您使用自动 [!UICONTROL 分配] 、多重装备的强盗功能，在使用Adobe [!UICONTROL Analytics目标指标和／或Adobe] Analytics报告和分析功  能的同时，推动流量增长。<br>如果您已实 [施A4T](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) ，以与A/B测试和体验定位活动配合使用，您就可以了！<br>有关详细信息，请 [参阅AnalyticsTarget(A4T)支持在创建活动时自动分配活动](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa) ( *Auto-Allocate)*。 |
| 自动Target和自动个性化活动流量分配的响应令牌 | 已 [经向自](/help/administrating-target/response-tokens.md) 动Target和自动个性化  活动添加了两个响应令牌，以便确定访客是因被分配到“控制”还是“目标”流量而获得特定体验。<ul><li>`experience.trafficAllocationId` 如果访客从“控制”流量中获得体验，则返回0；如果访客从“目标”流量分配中获得体验，则返回1。</li><li>`experience.trafficAllocationType` 分别返回“控制”和“目标”。</li></ul>有关控制与目标流量的更多信息，请参 [阅选择自动个性化或自动Target活动的控件](/help/c-activities/t-automated-personalization/experience-as-control.md)。 |
| [!UICONTROL 发布者] 角色 | 此新角色与当前“观察者”角 [!UICONTROL 色类似] (可以视图活动，但不能创建或编辑这些角色)。 但是，发 [!UICONTROL 布者] 角色具有激活活动的其他权限。<br>有关详细信息，请参阅： <ul><li>**Target Standard用户**: [在用户中指定角色](/help/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) 和 *权限*。</li><li>**Target高级版用户**: [第6步： 在“配置企业权限](/help/administrating-target/c-user-management/property-channel/properties-overview.md#section_8C425E43E5DD4111BBFC734A2B7ABC80) ”中 *指定角色和权限*。</li></ul> |
| 2020年6月25 [!DNL Analysis Workspace]<br>日支持A4T | [!UICONTROL 现在支持] (A4T)的Target分析 [!DNL Analysis Workspace]。 通 [!UICONTROL 过Analytics的Target(A4T)面板] ，您可以 [!DNL Adobe Target] 分析活动和体验 [!DNL Analysis Workspace]。<br>有关详细信息，请参 [阅Analytics](/help/c-integrating-target-with-mac/a4t/reporting.md) (A4T *报告)和* Analytics(A4T)面板中的“Reports in [A4T for Savige”(A4T)面板(](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/a4t-panel.html)**&#x200B;位于Analytics工具指南中)。 |

### 增强功能、修复和变更

* 修复了导致“访客”度量存储在活动的定义中而不是“UniqueVisitors”的问题。 (TGT-37098)
* 修复了UI中导 [!DNL Target] 致垂直滚动条在受众页面上无法正 [!UICONTROL 确工作] 的问题。 (TGT-36968)

## at.js 1.8.2和at.js 2.3.1版本（2020年6月15日）

at.js库中已进行以 [!DNL Target] 下改进和修复：

| 功能/增强 | 描述 |
| --- | --- |
| at.js 1.8.2 | 此版本的at.js是维护版本，包括以下修复：<ul><li>修复了在使用CNAME和边缘覆盖(at.js 1)时的问题。*x可能* 会错误地创建服务器域，这会导致请 [!DNL Target] 求失败。 (TNT-35064)</li></ul>For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md). |
| at.js 2.3.1 | 此版本的 at.js 是一个维护版本，它包括以下增强功能和修复：<ul><li>通过targetGlobalSettings `deviceIdLifetime` 使设置可 [覆盖](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)。 (TNT-36349)</li><li>修复了在使用CNAME和边缘覆盖时，at.js 2的问题。*x可能* 会错误地创建服务器域，这会导致请 [!DNL Target] 求失败。 (TNT-35065)</li><li>修复了使用扩展 [!DNL Target] v2和扩 [!DNL Launch] 展时延 [!DNL Adobe Analytics] 迟呼叫的 [!DNL Launch] 问 [!DNL Target][!DNL Analytics]`sendBeacon` 题。 (TNT-36407,TNT-35990,TNT-36000)</li></ul>For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md). |

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明-Target服务器端API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | 与Adobe Target的服务器端API相关的发行说明。 |
| [发行说明-TargetNode.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | 与Adobe Target的Node.js SDK相关的发行说明。 |
| [发行说明-TargetJava SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | 与Adobe Target的Java SDK相关的发行说明。 |
| [at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 有关Adobe Targetat.js JavaScript库各版本中更改的详细信息。 |
| [mbox.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | 此页面显示对 mbox.js 的每个版本所做的更改。<br>请注意，mbox.js库不再在开发中。 所有客户都应该从 mbox.js 迁移到 at.js。 |

## 文档更改、以往的发行说明和 Experience Cloud 发行说明 {#section_1BC5F5208DA548E9B4344A0836E4B943}

除了针对每个发行的说明外，以下资源还提供更多其他信息：

| 资源 | 详细信息 |
|--- |--- |
| 文档更改 | 查看可能未包含在这些发行说明中的针对该指南的详细更新信息。<br>有关更多信息，请参阅[文档更改](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)。 |
| 以前版本的发行说明 | 查看与以前版本的 Target Standard 和 Target Premium 中的新增功能和增强功能相关的信息。<br>有关更多信息，请参阅[以前版本的发行说明](../r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 发行说明 | 查看 Adobe Experience Cloud 解决方案的最新发行说明。<br>有关详细信息，请参阅 [Experience Cloud发行说明](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)。 |

## 预发行信息 {#section_5D588F0415A2435B851A4D0113ACA3A0}

您可以通过以下资源了解下一个 Target 版本即将包含的功能。

| 资源 | 详细信息 |
|--- |--- |
| Adobe 优先产品更新列表 | 若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| 即将推出的发行说明 | 有关当月 Target 发行版本的信息（包括预发行信息），请参阅 [Target 发行说明 - 预发行](/help/r-release-notes/target-release-notes.md)页面。 |
