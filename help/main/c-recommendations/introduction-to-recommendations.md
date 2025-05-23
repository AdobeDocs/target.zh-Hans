---
keywords: 推荐;简介;简介;网络研讨会;演示
description: 了解 Adobe [!DNL Target] 中的“推荐”活动，这些活动根据以前的用户活动或其他算法自动显示可能让客户感兴趣的内容。
title: “推荐”活动是什么？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: bc4d9a46-ea21-4687-b8a0-7f2e1dc33ebf
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '2086'
ht-degree: 90%

---

# “推荐”简介

本文中的文本来自““推荐”简介”**&#x200B;网络研讨会，您可以在下面查看全文。

**““推荐”简介”网络研讨会包括对如何利用 [!DNL Adobe Target Recommendations] 价值的深入探讨。了解此 [!DNL Target] 活动如何通过基于先前的访问优化实时建议来自动显示客户可能感兴趣的产品或内容。此外，深入了解 [!DNL Target] UI，获取有关如何构建 [!DNL Recommendations] 活动的分步概述。

## 简介

我们都了解我们在零售业中看到的推荐类型。越来越多的客户期待获得这类推荐，并将它们用作探索其他可用选项的切入点。如果考虑您自己的购物行为，这些类型的推荐效果非常好。几乎我们中的每个人都购买了我们在推荐中首先看到的某个产品，无论是在商店中还是在数字财产网站上。

下图显示了一个推荐，该推荐显示了通常随新手机一起购买的配件，包括充电器、手机壳和耳机。

![显示其他人随新手机一起购买的配件的推荐。](/help/main/c-recommendations/assets/intro-1.png)

但我们并不总是在考虑数字化优先品牌如何提高客户期望的标准。 我们使用媒体和内容的方式也越来越多地受到个性化推荐的驱动。请想想您打开 Netflix、Spetify 或 YouTube 时看到的第一个内容。这些品牌就是通过推荐来开始客户体验。在一个比以往任何时候都有更多可用替代内容的世界中，您必须在客户进行交互时为其确定最相关的内容，这一点至关重要。

![显示数字优先品牌的推荐](/help/main/c-recommendations/assets/intro-2.png)

营销人员可以使用 [!DNL Adobe Target] 在各种行业、客户类型和渠道中推动个性化体验。

[!DNL Adobe Target] 可以随时随地提供个性化内容。

![显示 Target 如何在不同场景中提供相应推荐的插图](/help/main/c-recommendations/assets/intro-3.png)

* **发布**：Web 发布者使用 [!DNL Target Recommendations] 向网站访客推荐文章并提高参与度。
* **视频教程**：[!DNL Adobe Creative Cloud] 使用 [!DNL Target] 向 Photoshop 应用程序中的 Photoshop 用户推荐视频教程。
* **游戏**：游戏公司使用 [!DNL Target] 向其控制台上的用户推荐游戏和内容。
* **B2B 销售**：[企业对企业的公司使用 Target 向 B2B 潜在用户推荐视频、白皮书和博客文章；提供下载；并向现有客户提供帮助](https://theblog.adobe.com/testing-shifts-high-gear-intel)。

* **旅游**：[一家德国旅游预订商使用 Target 向旅行者推荐酒店等产品](https://2017.summit.adobe.com/na/sessions/summit-online/online-2017/#17608)。

* **零售业**：[一家行业领先的 BB 零售商使用 Target 在浏览器及移动应用程序中推荐顶级类别和产品，以吸引访客](https://theblog.adobe.com/optimization-personalization-b2b-powerhouse-grainger/)2。

这些只是客户使用 Target 提供个性化推荐的几种方式。

怎样才能提出出色的推荐？

![显示构成出色推荐的三个元素的插图](/help/main/c-recommendations/assets/intro-4.png)

出色的推荐应具有相关性和个性化。这意味着您需要以下三个元素来提高相关性和个性化：

* **营销人员控件**，可帮助驱动所推荐项目的相关性。作为营销人员，您可以为表格提供有价值的上下文信息，而且您知道产品或内容的哪些属性与要考虑的推荐模型相关。如果您正在运营一个视频网站，您知道用户可能有兴趣观看同一导演拍摄的电影，但可能并不关心由同一工作室制作的电影。 [!DNL Target] 可为您提供允许您使用此域知识来增强算法的控件。
* **完善的模型**，可帮助了解您目录中的数百万个项目和各种交互活动。[!DNL Target] 拥有经过十多年经验积累的先进的机器学习功能，我们每年都会处理数十亿条推荐。
* **用户上下文**，可确保推荐及时并且与用户相关。您不希望推荐某个用户刚刚观看过的视频，或者某个用户刚刚添加到购物车的衬衫。 Target的丰富用户配置文件可用于推荐，以确保个性化。

## 实现 [!DNL Target] 推荐

从策略开始。

![显示推荐策略的插图](/help/main/c-recommendations/assets/intro-5.png)

* **您想要推荐哪些项目？**&#x200B;首先考虑要推荐的项目。这个项目可以是产品、视频或内容。
* **您想在何处显示推荐？**&#x200B;接下来，请思考您希望在何处提出推荐。概括地讲，就是哪些渠道（Web、移动设备、店内、网亭等）。客户历程的哪些部分将包含推荐？您网站上的哪些页面将包含推荐？
* **您将如何确定推荐是否成功？**&#x200B;假定您拥有一个不包含推荐的体验，一个包含推荐的体验，或者您拥有两个包含不同类型推荐的体验。如何确定哪种体验更适合您的客户？有些量度可能比其他量度更难衡量。例如，推荐对客户存留期值的影响通常很难直接获得。因此，我们通常容易获得一个不太抽象、更具体的量度，例如每次访问带来的收入、平均订单值或者点击次数。在某些情况下，您可能希望最小化某个量度，例如支持调用的数量。

制定策略后，就可以开始实施 [!DNL Target Recommendations]。

制定推荐实施涉及到三个主要步骤：

![显示制定推荐实施步骤的插图](/help/main/c-recommendations/assets/intro-6.png)

1. 向 [!DNL Target] 传递上下文或产品信息。
1. 捕获用户行为。
1. 使用正确的上下文信息获取推荐。

### 向 [!DNL Target] 传递上下文或产品信息

开始使用 [!DNL Recommendations] 时，您会传递有关每个要推荐项目的信息。[!DNL Target] 提供了多个可创建目录的集成选项。

![显示如何向 Target 传递上下文或产品信息的插图](/help/main/c-recommendations/assets/intro-7.png)

最简单、最常用的方法就是每日或每周从产品信息管理系统或内容管理系统发送 CSV 文件。但您也可以使用 [!DNL Adobe Target] Javascript 库从页面传递数据层上的信息，利用我们的 API 直接从您的源系统传递信息，或者使用我们的 [!DNL Adobe Analytics] 集成（如果您已经将目录数据传递到 [!DNL Analytics]）。

有时候，您可能希望同时使用多个选项，例如，每天通过 CSV 文件传递大部分数据，并通过 API 更频繁地传递库存更新。

您的 IT 部门通常会参与帮助设置此步骤。

无论选择哪种方法，您都应将有关每个项目的元数据包括在三个类别中：

![显示目录元数据信息的插图](/help/main/c-recommendations/assets/intro-8.png)

* 要向收到推荐的用户显示的数据。例如，电影的名称和缩略图图像 URL。
* 用于应用营销和销售控制的数据。例如，电影的评级，这样您就不会推荐评级为 NC-17 的电影。
* 用于确定项目与其他项目相似度的数据。例如，电影的流派或者电影中的演员。

### 捕获用户行为

接下来，您应该添加标签或利用现有的 [!DNL Analytics] 实施来跟踪可驱动 [!DNL Target] 算法的转化事件（例如查看次数或购买项目）。

![显示如何捕获用户行为的插图](/help/main/c-recommendations/assets/intro-9.png)

您需要确保 [!DNL Target] 了解用户正在查看和购买的项目。如果购买与上下文无关，则可能需要跟踪不同类型的转化事件，例如，下载PDF、完成调查、订阅新闻稿、观看视频等。

如果您已经使用 [!DNL Target] 在网站上运行 A/B 测试活动，则可能已经完成了此步骤。或者，如果您已经使用 [!DNL Adobe Analytics] 来报告网站访问情况和转化行为，则可以使用 [!DNL Analytics] 作为行为数据源。如果没有，最简单的做法是使用标签管理器（如[[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-using-adobe-launch.html?lang=zh-Hans){target=_blank}中的标签）进行此设置。 也可以通过实时API将离线或应用程序内的交互发送到[!DNL Target]。

### 使用正确的上下文信息获取推荐

在交互时将有关用户和上下文的信息传递给 [!DNL Target]，以返回相关的个性化推荐。

![显示如何使用正确的上下文信息获取推荐的插图](/help/main/c-recommendations/assets/intro-10.png)

除了聚合用户行为之外，您还需要将显示推荐的特定上下文传递给 [!DNL Target]。这包括有关页面的信息和来自用户配置文件的信息。[!DNL Target] 将使用此信息来进行个性化推荐。例如，在零售网站上，您想了解访客当前正在查看的产品和产品类别。同时还想了解有关该用户的信息（最喜爱的品牌、最喜爱的产品类别、忠诚度等级等等）。这个信息非常重要，借助此信息，[!DNL Target] 可以筛选项目并改进推荐的个性化。

## 构建第一个“推荐”活动

什么是 [!DNL Recommendations] 活动？

![显示构成良好推荐活动各个部分的插图](/help/main/c-recommendations/assets/intro-11.png)

[!DNL Recommendations] 活动由以下部分组成：

* **受众**：谁应该看到这些推荐？
* **标准**：应该推荐哪些项目？
* **设计**：应该如何显示推荐的项目？

![显示构成推荐活动各个部分（受众、标准和设计）的插图](/help/main/c-recommendations/assets/intro-12.png)

[!DNL Target] 开箱即用地包括 14 个内置受众、42 个内置标准和 10 个内置设计模板。您可以自定义每个项目或添加自己的项目。我们以前举办过有关在[!DNL Target]中构建受众[&#128279;](https://landing.adobe.com/acs/2018/na/adobe-target/registration.html)的网络研讨会。 本节侧重于定义标准，这些标准可定义将推荐哪些项目。

Target 使用标准卡片的概念。标准卡片就像个性化的配方。

![标准卡片插图](/help/main/c-recommendations/assets/intro-13.png)

选择或创建恰当的标准，以实现您所期望的个性化效果，这一点很重要。标准就像一个漏斗，可对整个目录进行筛选直至剩下最终的一组推荐。

![漏斗插图](/help/main/c-recommendations/assets/intro-14.png)

以下章节介绍了此漏斗的各个部分及其在 [!DNL Target] 中的工作方式：

### 静态筛选器（收藏集和排除项）

静态筛选器是与您不希望频繁更改的目录属性相关的广泛适用的规则。

![收藏集和排除项插图](/help/main/c-recommendations/assets/intro-16.png)

例如，在内容上下文中，您可能希望在推荐中包含所有电影，但不包括评级为 NC-17 的电影。在零售上下文中，您可能在全球不同地区创建了多个品牌，但您只想推荐在美国提供的产品。你可能还想从区域自有品牌排除一些产品。

所有这些都是广泛适用的目录属性，您可能希望在多个推荐中使用这些属性，并且不希望频繁对其进行更改。

### 算法（推荐键和推荐逻辑）

下一步是选择推荐键和推荐逻辑。您可以在此确定推荐的依据。

![算法插图](/help/main/c-recommendations/assets/intro-17.png)

首先需要选择的就是推荐键。推荐键是您要“查找”以选择推荐的内容。这就是您推荐的依据。

推荐可以基于：

* 访客当前正在查看的项目
* 访客当前正在查看的类别
* 访客上次购买或添加到购物车的项目
* 与访客或项目相关的自定义属性

然后，根据这些键选择所需的推荐逻辑：

* 具有相似属性的项目
* 特定类别中查看次数最多的项目
* 购买了这个项目，也购买了这些项目的客户
* 自定义属性

[!DNL Target] 开箱即用地包括一个算法组合。

![算法组合插图](/help/main/c-recommendations/assets/intro-15.png)

* **基于热门程度的算法**&#x200B;包括“查看次数最多”和“最畅销商品”。
* **基于内容的算法**&#x200B;包括“内容相似度”。
* **基于项目的协同筛选算法**&#x200B;包括“已查看/已查看”、“已查看/已购买”和“已购买/已购买”。请注意，“已购买”可以是任意转化。
* **个性化算法**&#x200B;包括“最近查看”、“网站亲和度”和配置文件增强的协同筛选。
* **自带算法**&#x200B;可让您使用自己的自定义算法。

### 在线业务规则

最后一步是应用在线业务规则。在这里，您可以根据访客对数字财产所做的操作，使用域知识和当前上下文信息来增强算法。

![在线业务规则插图](/help/main/c-recommendations/assets/intro-18.png)

例如，在内容上下文中，您可能希望排除访客之前观看过的电影、推荐同一导演拍摄的电影，或者增加同一流派的电影。在零售上下中，您可能希望排除缺货产品，显示价格在 5 美元到 500 美元之间的项目，或者增加来自同一品牌的项目。

## Demo

完成上述推荐漏斗中所述的任务后，您将获得最终的推荐。要在 [!DNL Target] 中观看产品内演示，该演示在 *Adobe Target 基础知识网络研讨会*&#x200B;中的 21:00 分钟处开始，其链接如下。

## Adobe [!DNL Target] 基础知识网络研讨会：“推荐”简介 {#intro-to-recs}

[“推荐”简介](https://adobecustomersuccess.adobeconnect.com/p8gt31drhs3e/?OWASP_CSRFTOKEN=4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)
