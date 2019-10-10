---
description: 发行说明，提供有关最新或即将发布的Adobe target版本的功能、增强和修复的信息。
keywords: 发行说明；发行；更新；未来发行；增强；新增功能；修复
seo-description: 发行说明，提供有关最新或即将发布的DNL Adobe Target版本的功能、增强和修复的信息。
seo-title: Adobe Target预发行说明
solution: Target
title: Target 发行说明（预发行版本）
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: e11f8dfee9bcdfae530efc75b239f0d7af045005

---


# Target 发行说明（预发行版本）{#target-release-notes-prerelease}

下列发行说明将介绍 [!DNL Adobe Target] 最新版本或即将发布的版本的功能、增强功能、修复信息和已知问题。

**上次更新：2019 年 10 月 2 日**

>[!NOTE]
>
>下列发行说明包含预发布的信息。发布日期、功能及其他信息如有更改，恕不另行通知。要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。这些页面上的信息可能相同，也可能不同，具体取决于发行时间。
>
>括号中的问题编号供 [!DNL Adobe] 内部使用。

## 目标平台

| 功能/增强 | 描述 |
| --- | --- |
| Node.js SDK版本1.0<br>（2019年10月9日） | Target Node.js SDK允许您在服务器端部署Target。<br>此Node.js SDK可帮助您将Target轻松集成到其他Experience cloud解决方案中，如Adobe Experience Cloud Identity Service、Adobe Analytics和Adobe Audience Manager。<br>Node.js SDK在通过我们的交付API与Adobe Target集成时引入了最佳实践并消除了复杂性，使您的工程团队能够专注于业务逻辑。 下面是我们在最新版本中介绍的显着功能：<ul><li>支持预取和通知，允许您通过缓存优化性能。</li><li>支持在网页和服务器端同时集成Target时优化性能。 我们将引入一个名为的设置，该设置将由通过服务器端检索的体验填充，这样at.js 2.2将不再进行额外的服务器调用来检索体验。 `serverState` 此方法可优化页面加载性能。</li><li> 支持通过Node.js SDK检索VEC创建的活动，新的交付API使这成为可能。</li><li>开放源代码，以便开发人员能够为Node.js SDK做出贡献。</li></ul>有关详细信息，请 [参阅发行说明- Target Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md)。 |
| 交付API<br>（2019年10月9日） | 生产中将提供全新的交付API端点（/v1/交付）。 显着功能包括：<ul><li>一个端点，用于检索一个或多个mbox的体验。</li><li>通过API检索VEC创建的活动。</li><li>支持一个称为“视图”的全新对象，该对象用于单页应用程序(SPA)和移动应用程序。</li></ul>有关详细信息，请参 [阅发行说明——目标服务器端API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md)。 |
| at.js版本2.2<br><br>andat.js版本1.8<br>（2019年10月10日） | 这些版本的at.js提供：<ul><li>改进了在网页上同时使用Experience Cloud ID服务(ECID)v4.4和at.js 2.2或at.js 1.8时的性能。</li><li>以前，ECID曾发出两个阻止调用，之后at.js才能获取体验。 这已降低为单个呼叫，这显着提高了性能。</li></ul> 为了利用这些性能改进，升级到at.js 2.2或at.js 1.8以及ECID库v4.4.<br>at.js 2.2提供：<ul><li>**serverState**:at.js v2.2+中提供的设置，可用于在实施Target的混合集成时优化页面性能。 混合集成意味着您在客户端同时使用at.js v2.2+和服务器端的交付API或Target SDK来交付体验。 `serverState` 使at.js v2.2+能够直接应用从服务器端获取的内容中获取的体验，并作为所服务页面的一部分返回到客户端。<br>有关详细信息，请参阅targetGlobalSettings中的“serverState” [(serverState)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#server-state)。</li></ul> |


## Target Standard/Premium 19.10.1（2019 年 10 月 22 日） 

| 功能/增强 | 描述 |
| --- | --- |
| ![高级徽章](/help/assets/premium.png) ，基于用户的推荐 | 根据每个访客的浏览、查看和购买历史记录推荐项目。 这些项目通常称为“推荐给您”。<br>通过此标准，您可以向新访客和回头客提供个性化的内容和体验。 推荐列表会根据访客最近的活动进行加权，并会在会话中更新，并随着访客浏览您的网站而变得更加个性化。 |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
