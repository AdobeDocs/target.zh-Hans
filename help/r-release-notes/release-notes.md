---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: 这些发行说明介绍了每个 Target Standard 和 Target Premium 版本的功能、增强功能、修复信息和已知问题。
title: 'Adobe Target 发行说明（当前版本） '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 9a74178fa337d0890ae3c4813e01ba0a12a44902
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 33%

---


# Target 发行说明（当前版本）{#target-release-notes-current}

这些发行说明介绍了每个 Target Standard 和 Target Premium 版本的功能、增强功能和修复信息。此外，还包含目标API、SDK、JavaScript库(at.js)的发行说明以及其他平台更改（如果适用）。

>[!NOTE]
>
>* **mbox.js弃用**: 2020年8月30日，Adobe目标将不再支持mbox.js库。 2020年8月30日之后，mbox.js发出的所有呼叫都将失败，并影响您的目标活动正在运行的页面。 我们建议所有客户在此日期之前迁移到at.js库的最新版本，以避免您的站点出现任何潜在问题。 For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). 请参 *阅Adobe目标技能生成器： 开发人员聊天，将Adobe目标的mbox.js迁移到下面的at* .js以获取信息。
   >
   >   
   尽管目前支持mbox.js，但自2017年7月起，我们便未对此库提供功能更新。 较新的at.js比mbox.js具有许多优势。 at.js可缩短Web实施的页面加载时间，提高安全性，并为单页应用程序提供更好的实施选项。
   >
   >   
   通过将所有客户转移到at.js，我们的工程师和支持人员将能够为您提供新功能并优惠您期望从Adobe获得的支持。
   >
   >
* **目标通知**: 有关即将进行的目标的信息，请参阅事件公告页，包括目标技能生成器会话、开发人员聊天、网络研讨会和目标咖啡休息会话。 有关详细信息，请参阅 [目标公告](/help/r-release-notes/target-announcements.md)。


括号中的问题编号供 [!DNL Adobe] 内部使用。

## 用户档案批处理状态API v2更改（2020年5月14日）

在5月20日发布后，用户档案批处理状态将仅返回行级故障数据（不返回成功数据）。 未通过的用户档案ID将由API继续返回。

以前和新的API响应如下：

`ProfileBatchStatus Api
http://<<edge>>/m2/<<client>>/profile/batchStatus?batchId=<batchid>`

**目前，我们将响应视为：**

```
<response>
 
    <batchId>samplebatch-1585929692655-59449976</batchId>
 
    <status>complete</status>
 
    <batchSize>164</batchSize>
 
    <profile>
 
        <id>1514187733806-729395</id>
 
        <status>success</status>
 
    </profile>
 
    <profile>
 
        <id>1573612762055-214017</id>
 
        <status>success</status>
 
    </profile>
 
    <profile>
 
        <id>some profile id</id>
 
        <status>failed</status>
 
    </profile>
 
</response>
```

**5月4日之后，答复将是：**

```
<response>
 
    <batchId>samplebatch-1585929692655-59449976</batchId>
 
    <status>complete</status>
 
    <batchSize>164</batchSize>
 
    <profile>
 
        <id>some profile id</id>
 
        <status>failed</status>
 
    </profile>
 
</response>
```

## Target Standard/Premium 20.4.1（2020 年 5 月 6 日）

此版本包含以下增强、修复和更改：

* 修复了对受众错误限定设备和浏览器类型的问题。 (TGT-36266)
* 修复了在963像素以下的屏幕上查看报告数据时无法显示的问题。 (TGT-36549)
* 修复了导致自动个性化报表无法正确呈现的问题。 (TGT-36619)
* 修复了允许在使用Analytics进行目标(A4t)的“自动分配”和“自动目标”活动中选择不兼容度量的问题。 (TGT-36646)
* 修复了导致可视体验书写器(VEC)中的某些选项无法正确显示的问题。 (TGT-36571)
* 修复了目标UI中的一个问题，该问题导致用户在单个体验中替换内容后，其他推荐优惠预览显示已编辑的内容。 （TGT-36053 和 TGT-36894）
* 修复了阻止某些用户从Recommendations目录删除项目的问题。 (TGT-36455)
* 修复了阻止用户在多页面活动中保存推荐条件的问题。 (TGT-36249)
* 修复了行为数据源单选按钮在连续第二次编辑条件时消失的问题。 (TGT-36796)
* 修复了导致Recommendations算法显示延长期间的“获取结果”的显示问题。 （TGT-36550 和 TGT-36551）
* 更新了许多本地化为各种语言的UI字符串。

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明-目标服务器端API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | 与Adobe目标的服务器端API相关的发行说明。 |
| [发行说明-目标Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | 与Adobe目标的Node.js SDK相关的发行说明。 |
| [发行说明-目标Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | 与Adobe目标的Java SDK相关的发行说明。 |
| [at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 有关各版本Adobe目标at.js JavaScript库中更改的详细信息。 |
| [mbox.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | 此页面显示对 mbox.js 的每个版本所做的更改。<br>请注意，mbox.js库不再在开发中。 所有客户都应该从 mbox.js 迁移到 at.js。 |

## 文档更改、以往的发行说明和 Experience Cloud 发行说明 {#section_1BC5F5208DA548E9B4344A0836E4B943}

除了针对每个发行的说明外，以下资源还提供更多其他信息：

| 资源 | 详细信息 |
|--- |--- |
| 文档更改 | 查看可能未包含在这些发行说明中的针对该指南的详细更新信息。<br>有关更多信息，请参阅[文档更改](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)。 |
| 以前版本的发行说明 | 查看与以前版本的 Target Standard 和 Target Premium 中的新增功能和增强功能相关的信息。<br>有关更多信息，请参阅[以前版本的发行说明](../r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 发行说明 | 查看 Adobe Experience Cloud 解决方案的最新发行说明。<br>有关详细信息，请参 [阅Experience Cloud发行说明](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)。 |

## 预发行信息 {#section_5D588F0415A2435B851A4D0113ACA3A0}

您可以通过以下资源了解下一个 Target 版本即将包含的功能。

| 资源 | 详细信息 |
|--- |--- |
| Adobe 优先产品更新列表 | 若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| 即将推出的发行说明 | 有关当月 Target 发行版本的信息（包括预发行信息），请参阅 [Target 发行说明 - 预发行](/help/r-release-notes/target-release-notes.md)页面。 |
