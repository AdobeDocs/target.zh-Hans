---
description: Release notes that provide information about features, enhancements, and fixes for the latest or upcoming Adobe Target releases.
keywords: 发行说明；发行；更新；未来发行；增强；新增功能；修复
seo-description: 发行说明，提供有关最新或即将发布的DNL Adobe Target版本的功能、增强和修复的信息。
seo-title: Adobe Target预发行说明
solution: Target
title: Target 发行说明（预发行版本）
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 285a09503ba6abaf2bfe19fc2b214c32ebd2de3a

---


# Target 发行说明（预发行版本）{#target-release-notes-prerelease}

下列发行说明将介绍 [!DNL Adobe Target] 最新版本或即将发布的版本的功能、增强功能、修复信息和已知问题。

**上次更新：2019 年 10 月 2 日**

>[!NOTE]
>
>下列发行说明包含预发布的信息。发布日期、功能及其他信息如有更改，恕不另行通知。要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。这些页面上的信息可能相同，也可能不同，具体取决于发行时间。
>
>括号中的问题编号供 [!DNL Adobe] 内部使用。

## 目标平台（待确定日期）

| 功能/增强 | 描述 |
| --- | --- |
| Node.js SDK版本1.0 | Target Node.js SDK允许您在服务器端部署Target。<br>此Node.js SDK可帮助您将Target轻松集成到其他Experience cloud解决方案中，如Adobe Experience Cloud Identity Service、Adobe Analytics和Adobe Audience Manager。<br>Node.js SDK在通过我们的交付API与Adobe Target集成时引入了最佳实践并消除了复杂性，使您的工程团队能够专注于业务逻辑。 下面是我们在最新版本中介绍的显着功能：<ul><li>支持预取和通知，允许您通过缓存优化性能。</li><li>Support for optimizing performance when you have a hybrid integration of Target on both your web pages and server-side. We are introducing a setting called  that will be populated by experiences retrieved via the server-side so that at.js 2.2 will no longer make an additional server call to retrieve the experiences. `serverState`This approach optimizes page load performance.</li><li> Support for retrieving VEC-created activities via the Node.js SDK, which is made possible by the new Delivery API.</li><li>Open sourced so your developers can contribute to the Node.js SDK.</li></ul> |
| Delivery API | An entirely new delivery API endpoint (/v1/delivery) will be available in production. Notable features are:<ul><li>一个端点，用于检索一个或多个mbox的体验。</li><li>Retrieve VEC-created activities via the API.</li><li>Support for an entirely new object called Views that is used for Single Page Applications (SPAs) and Mobile applications.</li></ul> |
| at.js版本2.2<br><br>andat.js版本1.8 | 这些版本的at.js提供：<ul><li>改进了在网页上同时使用Experience Cloud ID服务(ECID)v4.4和at.js 2.2或at.js 1.8时的性能。</li><li>以前，ECID曾发出两个阻止调用，之后at.js才能获取体验。 这已降低为单个呼叫，这显着提高了性能。</li></ul> 为了利用这些性能改进，请升级到at.js 2.2或at.js 1.8以及ECID库v4.4。 |


## Target Standard/Premium 19.10.1（2019 年 10 月 22 日） 

| 功能/增强 | 描述 |
| --- | --- |
| ![高级徽章](/help/assets/premium.png) ，基于用户的推荐 | 根据每个访客的浏览、查看和购买历史记录推荐项目。 这些项目通常称为“推荐给您”。<br>通过此标准，您可以向新访客和回头客提供个性化的内容和体验。 The list of recommendations is weighted towards the visitor's most-recent activity and is updated in-session and becomes more personalized as the visitor browses your site. |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
