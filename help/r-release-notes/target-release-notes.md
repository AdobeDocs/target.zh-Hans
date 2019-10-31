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
source-git-commit: 540367e4c49c712df98dc132bccf4f29b4d6f095

---


# Target 发行说明（预发行版本）{#target-release-notes-prerelease}

下列发行说明将介绍 [!DNL Adobe Target] 最新版本或即将发布的版本的功能、增强功能、修复信息和已知问题。

**上次更新：2019 年 10 月 31 日**

>[!NOTE]
>
>下列发行说明包含预发布的信息。发布日期、功能及其他信息如有更改，恕不另行通知。要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。这些页面上的信息可能相同，也可能不同，具体取决于发行时间。
>
>括号中的问题编号供 [!DNL Adobe] 内部使用。

## 目标平台（2019年10月31日）

| 功能 / 增强功能 | 描述 |
| --- | --- |
| Java SDK | Java [!DNL Target] SDK允许您部署 [!DNL Target] 服务器端。 此Java SDK可帮助您轻松 [!DNL Target] 地与其 [!DNL Adobe Experience Cloud] 他解决方案(如 [!DNL Adobe Experience Cloud Identity Service]、 [!DNL Adobe Analytics]和)集成 [!DNL Adobe Audience Manager]。<br>Java SDK在通过我们的交付API与集成时引入了最佳实践并消除了 [!DNL Target] 复杂性，这样您的工程团队就可以专注于业务逻辑。 下面是我们在最新版本中介绍的显着功能：<ul><li>支持预取和通知，允许您通过缓存优化性能。</li><li>支持在网页和服务器端混合集 [!DNL Target] 成时优化性能。 我们引入了一个名为的设置 `serverState` ，该设置由通过服务器端检索的体验填充，这样at.js 2.2将不再进行额外的服务器调用来检索体验。 此方法可优化页面加载性能。</li><li>支持通过Java SDK检索VEC创建的活动，新的交付API使这成为可能。</li><li>开放源码，这样您的开发人员就可以为 [Target Java SDK做出贡献](https://github.com/adobe/target-java-sdk)。</li></ul>有关详细信息，请参 [阅发行说明——目标Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md)。 |

## Target Standard/Premium 19.10.2（2019 年 10 月 31 日） 

| 功能 / 增强功能 | 描述 |
| --- | --- |
| ![高级徽章](/help/assets/premium.png) -使用多值属性 | 有时，您希望使用多值字段。 请仔细研究下面的示例：<ul><li>您向用户提供影片。 一部电影有多个演员。</li><li>你卖音乐会的票。 给定用户有多个喜爱的栏。</li><li>你卖衣服。 T恤有多种尺寸。</li></ul>要处理这些场景中的推荐，您可以将多值数据传递给Target Recommendations，并使用特殊的多值运算符。 |

## Target Standard/Premium 20.1.1

Target Standard/Premium 20.1.1版本将于2020年1月发布。 其确切日期、功能和增强功能将在此处公布。

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
