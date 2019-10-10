---
description: 这些发行说明提供了每个 Target Standard 和 Target Premium 版本的功能、增强、修复问题和已知问题等信息。
keywords: 发行说明；新增功能；发行；更新；更新；发行；增强；修复；错误修复
seo-description: 这些发行说明介绍了每个 Target Standard 和 Target Premium 版本的功能、增强功能、修复信息和已知问题。
seo-title: 'Adobe Target 发行说明（当前版本） '
solution: Target
title: Target 发行说明（当前版本）
topic: 推荐
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: e11f8dfee9bcdfae530efc75b239f0d7af045005

---


# Target 发行说明（当前版本）{#target-release-notes-current}

这些发行说明介绍了每个 Target Standard 和 Target Premium 版本的功能、增强功能和修复信息。此外，还包含Target API、SDK、JavaScript库(at.js)的发行说明以及其他平台更改（如果适用）。

## at.js版本2.2和1.8（2019年10月10日）

| 功能/增强 | 描述 |
| --- | --- |
| at.js版本2.2<br><br>andat.js版本1.8 | 这些版本的at.js提供：<ul><li>改进了在网页上同时使用Experience Cloud ID服务(ECID)v4.4和at.js 2.2或at.js 1.8时的性能。</li><li>以前，ECID曾发出两个阻止调用，之后at.js才能获取体验。 这已降低为单个呼叫，这显着提高了性能。</li></ul> 为了利用这些性能改进，升级到at.js 2.2或at.js 1.8以及ECID库v4.4.<br>at.js 2.2提供：<ul><li>**serverState**:at.js v2.2+中提供的设置，可用于在实施Target的混合集成时优化页面性能。 混合集成意味着您在客户端同时使用at.js v2.2+和服务器端的交付API或Target SDK来交付体验。 `serverState` 使at.js v2.2+能够直接应用从服务器端获取的内容中获取的体验，并作为所服务页面的一部分返回到客户端。<br>有关详细信息，请参阅targetGlobalSettings中的“serverState” [(serverState)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#server-state)。</li></ul> |

## 目标平台（2019年10月9日）

| 功能/增强 | 描述 |
| --- | --- |
| Node.js SDK版本1.0 | Target Node.js SDK允许您在服务器端部署Target。<br>此Node.js SDK可帮助您将Target轻松集成到其他Experience cloud解决方案中，如Adobe Experience Cloud Identity Service、Adobe Analytics和Adobe Audience Manager。<br>Node.js SDK在通过我们的交付API与Adobe Target集成时引入了最佳实践并消除了复杂性，使您的工程团队能够专注于业务逻辑。 下面是我们在最新版本中介绍的显着功能：<ul><li>支持预取和通知，允许您通过缓存优化性能。</li><li>支持在网页和服务器端同时集成Target时优化性能。 我们将引入一个名为的设置，该设置将由通过服务器端检索的体验填充，这样at.js 2.2将不再进行额外的服务器调用来检索体验。 `serverState` 此方法可优化页面加载性能。</li><li> 支持通过Node.js SDK检索VEC创建的活动，新的交付API使这成为可能。</li><li>开放源代码，以便开发人员能够为Node.js SDK做出贡献。</li></ul><br>有关详细信息，请 [参阅发行说明- Target Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md)。 |
| 交付API | 生产中提供了全新的交付API端点（/v1/交付）。 显着功能包括：<ul><li>一个端点，用于检索一个或多个mbox的体验。</li><li>通过API检索VEC创建的活动。</li><li>支持一个称为“视图”的全新对象，该对象用于单页应用程序(SPA)和移动应用程序。</li></ul><br>有关详细信息，请参 [阅发行说明——目标服务器端API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md)。 |

## Target Standard/Premium 19.9.2（2019 年 9 月 30 日）

此维护版本包括以下增强功能：

* 多个安全修复，包括对可视化体验编辑器 (VEC) 中富文本编辑器 (RTE) 的安全更新。(TGT-35383)
* 现在，除DIV外，A/B测试和体验定位活动中还可以将推荐选件添加到DIV以外的元素（例如P、UL、H1）。 (TGT-34333)
* 活动通知（目标UI中的铃铛图标）不再可用。 通知的新外观即将推出。

## Target Standard/Premium 19.9.1（2019 年 9 月 10 日）

| 功能/增强 | 描述 |
| --- | --- |
| ![高级徽章](/help/assets/premium.png) Enterprise权限 | 在Target 2019年9月版本中，企业权限为客户提供了以下访问控制：<UL><li>您可以选择可将集成应用到的工作空间.</li><li>您可以对 Adobe I/O 集成应用以下角色：审批者、编辑者或观察者。</li></ul>有关分步说明和更多信息，请参阅[授予 Adobe I/O 集成访问工作区的权限并分配角色](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md)。 |

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明——目标服务器端API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | 与Adobe Target的服务器端API相关的发行说明。 |
| [发行说明——目标Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | 与Adobe Target的Node.js SDK相关的发行说明。 |
| [at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 有关Adobe Target at.js javaScript库各版本中更改的详细信息。 |
| [mbox.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | 此页面显示对 mbox.js 的每个版本所做的更改。<br>请注意，mbox.js库不再在开发中。 所有客户都应该从 mbox.js 迁移到 at.js。 |

## 文档更改、以往的发行说明和 Experience Cloud 发行说明 {#section_1BC5F5208DA548E9B4344A0836E4B943}

除了针对每个发行的说明外，以下资源还提供更多其他信息：

| 资源 | 详细信息 |
|--- |--- |
| 文档更改 | 查看可能未包含在这些发行说明中的针对该指南的详细更新信息。<br>有关更多信息，请参阅[文档更改](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)。 |
| 以前版本的发行说明 | 查看与以前版本的 Target Standard 和 Target Premium 中的新增功能和增强功能相关的信息。<br>有关更多信息，请参阅[以前版本的发行说明](../r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 发行说明 | 查看 Adobe Experience Cloud 解决方案的最新发行说明。<br>有关详细信息，请参 [阅Experience cloud发行说明](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)。 |

## 预发行信息 {#section_5D588F0415A2435B851A4D0113ACA3A0}

您可以通过以下资源了解下一个 Target 版本即将包含的功能。

| 资源 | 详细信息 |
|--- |--- |
| Adobe 优先产品更新列表 | 若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| 即将推出的发行说明 | 有关当月 Target 发行版本的信息（包括预发行信息），请参阅 [Target 发行说明 - 预发行](/help/r-release-notes/target-release-notes.md)页面。 |
