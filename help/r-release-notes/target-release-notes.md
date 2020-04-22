---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: 发行说明，提供有关最新或即将发布的DNL Adobe目标版本的功能、增强和修复的信息。
title: Adobe目标预发行说明
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 710b442dd7e2d906dafc5ec73748268681e08448

---


# Target 发行说明（预发行版本）{#target-release-notes-prerelease}

本文包含预发行信息。 发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新日期：2020 年 4 月 21 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。这些页面上的信息可能相同，具体取决于发布时间。 括号中的问题编号供 [!DNL Adobe] 内部使用。

>[!NOTE]
>
>* **mbox.js弃用**:2020年8月30日，Adobe目标将不再支持mbox.js库。 2020年8月30日之后，mbox.js发出的所有调用都将失败并影响您的目标活动正在运行的页面。 我们建议所有客户在此日期之前迁移到at.js库的最新版本，以避免您的站点出现任何潜在问题。 For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). 请参 *阅Adobe目标技能构建器：开发人员聊天、将Adobe目标的mbox.js迁移到以下at.js* ，以了解有关注册即将进行的开发人员聊天的有关此主题的信息。
   >
   >   
   尽管目前支持mbox.js，但自2017年7月以来，我们尚未对此库提供功能更新。 较新的at.js比mbox.js有许多优势。 除其他优势外，at.js还缩短了Web实施的页面加载时间，提高了安全性，并为单页应用程序提供了更好的实施选项。
   >
   >   
   通过将所有客户转移到at.js，我们的工程师和支持人员将能够为您提供新功能并优惠您期望从Adobe获得的支持。


## Adobe目标技能构建器：开发人员聊天，将Adobe目标的mbox.js迁移到at.js {#skill-builder}

请与Adobe目标产品经理David Son一起讨论将mbox.js迁移到at.js的好处。 聆听最新的at.js更新，了解其增强功能以及它们如何与科技领域的大趋势保持一致，以及一些实用提示，以确保在从mbox.js迁移到at.js时从目标中获得同等的价值。 Adobe目标开发人员不会想错过这个！

5月5日，星期二，上午8:00 - 9:00（太平洋夏令时）

[立即注册！](https://atskillbuilder-devchat.experienceleague.adobeevents.com/)

## Target Standard/Premium 20.4.1（2020 年 4 月 27 日） 

此版本包含以下增强、修复和更改：

* 修复了对受众的设备和浏览器类型进行错误限定的问题。 (TGT-36266)
* 修复了在宽度小于963像素的屏幕上查看报告数据时无法显示的问题。 (TGT-36549)
* 修复了导致自动个性化报表无法正确呈现的问题。 (TGT-36619)
* 修复了导致Visual Experience Composer(VEC)中的某些选项无法正确显示的问题。 (TGT-36571)
* 修复了目标UI中的一个问题，该问题导致用户在单个体验中替换内容后，其他Recommendations优惠预览显示已编辑的内容。 (TGT-36053)
* 修复了阻止某些用户从Recommendations目录删除项目的问题。 (TGT-36455)
* 修复了阻止用户在多页面活动中保存推荐条件的问题。 (TGT-36249)
* 修复了导致Recommendations算法在较长的时间段内显示“获取结果”的显示问题。 （TGT-36550 和 TGT-36551）

## 用户档案批处理状态API v2更改（2020年5月4日）

在5月4日的版本中，“用户档案批处理”状态将仅返回今后的行级失败数据（将不返回成功数据）。 未通过的用户档案ID将由API继续返回。

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

**5月4日以后，答复是：**

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

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
