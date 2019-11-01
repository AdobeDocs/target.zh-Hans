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
source-git-commit: 5f05f218e5fdea26827b86cb7fbea05ac6349014

---


# Target 发行说明（当前版本）{#target-release-notes-current}

这些发行说明介绍了每个 Target Standard 和 Target Premium 版本的功能、增强功能和修复信息。此外，还包含Target API、SDK、JavaScript库(at.js)的发行说明以及其他平台更改（如果适用）。

括号中的问题编号供 [!DNL Adobe] 内部使用。

## 目标平台（2019年10月31日）

| 功能/增强 | 描述 |
| --- | --- |
| Java SDK | Java [!DNL Target] SDK允许您部署 [!DNL Target] 服务器端。 此Java SDK可帮助您轻松 [!DNL Target] 地与其 [!DNL Adobe Experience Cloud] 他解决方案(如 [!DNL Adobe Experience Cloud Identity Service]、 [!DNL Adobe Analytics]和)集成 [!DNL Adobe Audience Manager]。<br>Java SDK在通过我们的交付API与集成时引入了最佳实践并消除了 [!DNL Target] 复杂性，这样您的工程团队就可以专注于业务逻辑。 下面是我们在最新版本中介绍的显着功能：<ul><li>支持预取和通知，允许您通过缓存优化性能。</li><li>支持在网页和服务器端混合集 [!DNL Target] 成时优化性能。 我们引入了一个名为的设置 `serverState` ，该设置由通过服务器端检索的体验填充，这样at.js 2.2将不再进行额外的服务器调用来检索体验。 此方法可优化页面加载性能。</li><li>支持通过Java SDK检索VEC创建的活动，新的交付API使这成为可能。</li><li>开放源码，这样您的开发人员就可以为 [Target Java SDK做出贡献](https://github.com/adobe/target-java-sdk)。</li></ul>有关详细信息，请参 [阅发行说明——目标Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md)。<br>通过Adobe Tech Blog了解有关Target Java SDK的更多信息- [使用新的Target Java SDK进行服务器端优化](https://medium.com/adobetech/server-side-optimization-with-the-new-target-java-sdk-421dc418a3f2)。 |

## Target Standard/Premium 19.10.2（2019 年 10 月 31 日） 

| 功能/增强 | 描述 |
| --- | --- |
| ![高级徽章](/help/assets/premium.png) “多值”属性 | 有时，您希望使用多值字段。 请仔细研究下面的示例：<ul><li>您向用户提供影片。 一部电影有多个演员。</li><li>你卖音乐会的票。 给定用户有多个喜爱的栏。</li><li>你卖衣服。 T恤有多种尺寸。</li></ul>要处理这些场景中的推荐，您可以将多值数据传递给Target Recommendations，并使用特殊的多值运算符。<br>有关详细信息，请 [参阅使用多值属性](/help/c-recommendations/c-algorithms/work-with-multi-value-attributes.md)。 |

## Target Standard/Premium 19.10.1（2019 年 10 月 22 日） 

| 功能/增强 | 描述 |
| --- | --- |
| ![高级徽章](/help/assets/premium.png) ，基于用户的推荐<br>（2019年10月24日） | 根据每个访客的浏览、查看和购买历史记录推荐项目。 这些项目通常称为“推荐给您”。<br>通过此标准，您可以向新访客和回头客提供个性化的内容和体验。 推荐列表会根据访客最近的活动进行加权，并会在会话中更新，并随着访客浏览您的网站而变得更加个性化。<br>有关详细信息，请参阅标准／算法中的“基于用 [户的推荐”](/help/c-recommendations/c-algorithms/algorithms.md#criteria-algorithms)。 |

### Adobe Experience cloud导航

* 登录到时，您 [!DNL Adobe Experience Cloud]将转到新的标题导航。 它看起来与上一个导航非常相似，顶部有黑条，但它提供了以下改进：

   * 更轻松地在 [!DNL Identity Management System] (IMS)组织之间切换或切换到其他解决方案。
   * 改进的用户帮助：搜索结果包括产品文档中的结 [!DNL Target] 果、社区论坛和更多视频内容，让您能够更轻松地访问更多内容，从而帮助您发挥最大作用 [!DNL Target]。 我们还在“帮助”菜单中添加了反馈机 [!UICONTROL 制] ，使报告问题或分享您的想法更加容易。

   * 改进了Net Promoter Score(NPS)反馈功能，因此调查模式不会干扰您的工作流。
   * 改进了登录流程。 以前，所 [!DNL Target] 有客户在单击标题中的图标后都登 [!DNL Target] 录到Target登录页面。 然后，此页允许客户继续执行 [!DNL Target Standard/Premium]、 [!DNL Search&Promote]或 [!DNL Recommendations Classic]，如下所示：

      ![登陆页面](/help/r-release-notes/assets/landing.png)

      我们为所有客户取消了此登录页面。 现在，您始终可以通过单击新标题导 [!UICONTROL 航栏中的图标，直][!DNL Target] 接转到“活动列表”页面。

      如果您使 [!DNL Recommendations Classic]用，您可以直接转到解决方案，也可以从在“推荐”选项卡上创建的简短链 [!UICONTROL 接] ，如下所示：

      ![Recs Classic深层链接](/help/r-release-notes/assets/recs-classic.png)

      如果您使 [!DNL Search&Promote]用，则需要直接转到 [Search&amp;Promote URL](https://center.atomz.com/center/?ims=1) (https://center.atomz.com/center/?ims=1)。 从内部到达 [!DNL Search&Promote] 的路径已 [!DNL Adobe Target] 完全删除。

   * 标题 [!DNL Target] 的“通知”下拉框 [!UICONTROL 中] ，当前不提供通知。
   >[!NOTE]
   >
   >这些功能不会同时推出，也不会一起推出给所有客户。 我们将在未来几周推出这些功能，从 [!DNL Target Standard/Premium] 19.10.1（2019年10月22日）版本开始。
   >
   >作为新导航栏转出的一部分，您还会注意到一些URL更改。 所有以前已添加书签的链接将继续有效，但我们建议您为新链接加入书签以加快打开速度。

## at.js版本2.2和1.8（2019年10月10日）

| 功能/增强 | 描述 |
| --- | --- |
| at.js版本2.2<br><br>andat.js版本1.8 | 这些版本的at.js提供：<ul><li>改进了在网页上同时使用Experience Cloud ID服务(ECID)v4.4和at.js 2.2或at.js 1.8时的性能。</li><li>以前，ECID曾发出两个阻止调用，之后at.js才能获取体验。 这已降低为单个呼叫，这显着提高了性能。</li></ul> 为了利用这些性能改进，升级到at.js 2.2或at.js 1.8以及ECID库v4.4.<br>at.js 2.2提供：<ul><li>**serverState**:at.js v2.2+中提供的设置，可用于在实施Target的混合集成时优化页面性能。 混合集成意味着您在客户端同时使用at.js v2.2+和服务器端的交付API或Target SDK来交付体验。 `serverState` 使at.js v2.2+能够直接应用从服务器端获取的内容中获取的体验，并作为所服务页面的一部分返回到客户端。<br>有关详细信息，请参阅targetGlobalSettings中的“serverState” [(serverState)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#server-state)。</li></ul> |

## 目标平台（2019年10月9日）

| 功能/增强 | 描述 |
| --- | --- |
| Node.js SDK版本1.0 | Target Node.js SDK允许您在服务器端部署Target。<br>此Node.js SDK可帮助您将Target轻松集成到其他Experience cloud解决方案中，如Adobe Experience Cloud Identity Service、Adobe Analytics和Adobe Audience Manager。<br>Node.js SDK在通过我们的交付API与Adobe Target集成时引入了最佳实践并消除了复杂性，使您的工程团队能够专注于业务逻辑。 下面是我们在最新版本中介绍的显着功能：<ul><li>支持预取和通知，允许您通过缓存优化性能。</li><li>支持在网页和服务器端同时集成Target时优化性能。 我们将引入一个名为的设置，该设置将由通过服务器端检索的体验填充，这样at.js 2.2将不再进行额外的服务器调用来检索体验。 `serverState` 此方法可优化页面加载性能。</li><li> 支持通过Node.js SDK检索VEC创建的活动，新的交付API使这成为可能。</li><li>开放源代码，以便开发人员能够为Node.js SDK做出贡献。</li></ul><br>有关详细信息，请 [参阅发行说明- Target Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md)。<br>通过Adobe Tech Blog —— 开放式搜索新的Adobe Target Node.js SDK，进一步了 [解Target Node.js SDK](https://medium.com/adobetech/open-sourcing-the-new-adobe-target-node-js-sdk-b6feafd828bc)。 |
| 交付API | 生产中提供了全新的交付API端点（/v1/交付）。 显着功能包括：<ul><li>一个端点，用于检索一个或多个mbox的体验。</li><li>通过API检索VEC创建的活动。</li><li>支持一个称为“视图”的全新对象，该对象用于单页应用程序(SPA)和移动应用程序。</li></ul><br>有关详细信息，请参 [阅发行说明——目标服务器端API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md)。 |

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明——目标服务器端API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | 与Adobe Target的服务器端API相关的发行说明。 |
| [发行说明——目标Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | 与Adobe Target的Node.js SDK相关的发行说明。 |
| [发行说明——目标Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | 与Adobe Target的Java SDK相关的发行说明。 |
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
