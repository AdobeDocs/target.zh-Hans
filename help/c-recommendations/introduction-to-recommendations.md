---
description: Introduction to Target Recommendations activities that automatically display products or content that might interest your customers based on previous user activity or other algorithms. “推荐”有助于将客户导向到他们可能还不知道的相关项目。
keywords: Recommendations;intro;introduction;webinar;demo
seo-description: Adobe Target Recommendations活动简介，这些活动可根据先前的用户活动或其他算法自动显示可能吸引客户的产品或内容。 “推荐”有助于将客户导向到他们可能还不知道的相关项目。
seo-title: Introduction to Recommendations activities in Adobe Target
solution: Target
title: Introduction to Recommendations
title-outputclass: premium
topic: Premium
badge: premium
translation-type: tm+mt
source-git-commit: 516433edd366fad5950c99d748aa7f6f718dd5fd

---


# ![PREMIUM Introduction to Recommendations](/help/assets/premium.png)

The text in this article comes from the Introduction to Recommendations webinar, which you can view in its entirety below.**

**“Recommendations 简介”网络研讨会包括对如何利用 [!DNL Adobe Target Recommendations] 价值的深入探讨。了解此 [!DNL Target] 活动如何通过基于先前的访问优化实时建议来自动显示客户可能感兴趣的产品或内容。此外，深入了解 [!DNL Target] UI，获取有关如何构建 [!DNL Recommendations] 活动的分步概述。

## 简介

我们都知道零售业中的推荐类型。 越来越多的客户期望得到这类推荐，并将其作为探索其他可用选项的起点。 If you think about your own shopping behavior, these kind of recommendations work really well. 几乎我们中的每个人都买了一款我们在推荐中首先看到的产品，不管是在商店里还是数字地产上。

下图显示了一个建议，该建议显示通常使用新电话购买的附件，包括充电站、机箱和耳机。

![推荐其他人用新手机购买的配件。](/help/c-recommendations/assets/intro-1.png)

但我们并不总是在考虑数字优先品牌如何提升客户期望。 我们消费媒体和内容的方式越来越受到个性化推荐的驱动。 想想你打开Netflix、Spotify或YouTube时看到的第一件事。 这些品牌通过推荐开始客户体验。 在可用替代内容比以往更多的世界中，在互动时为客户确定最相关的内容至关重要。

![展示数字优先品牌的推荐](/help/c-recommendations/assets/intro-2.png)

营销人 [!DNL Adobe Target] 员使用它来推动跨各种行业、客户类型和渠道的个性化体验。

[!DNL Adobe Target] 随处提供个性化内容。

![说明Target如何在各个位置提供推荐的图示](/help/c-recommendations/assets/intro-3.png)

* **发布**:Web发布者可 [!DNL Target Recommendations] 使用向网站访问者推荐文章并推动提高参与度。
* **视频教程**:用 [!DNL Adobe Creative Cloud] 于向 [!DNL Target] Photoshop应用程序中的Photoshop用户推荐视频教程。
* **游戏**:游戏公司使 [!DNL Target] 用在其控制台上向用户推荐游戏和内容。
* **B2B销售**:企业 [对企业公司使用Target向B2B潜在客户推荐视频、白皮书和博客文章；提供下载；并为现有客户提供帮助](https://theblog.adobe.com/testing-shifts-high-gear-intel)。

* **旅行**:一 [家德国旅游书店使用Target向旅客推荐酒店等](https://2017.summit.adobe.com/na/sessions/summit-online/online-2017/#17608)。

* **零售**:一 [家领先的B2B零售商使用Target推荐顶级类别和产品，以便在浏览器和移动应用程序中为访客提供回访](https://theblog.adobe.com/optimization-personalization-b2b-powerhouse-grainger/)。

这些只是客户使用Target提供个性化推荐的几种方式。

哪些因素可以提供出色的推荐？

![说明了可提供出色建议的三个元素](/help/c-recommendations/assets/intro-4.png)

重大建议应该是相关的和个性化的。 这意味着您需要三件事来推动相关性和个性化：

* **营销人员控制** ，以帮助提高推荐项目的相关性。 作为营销人员，您将宝贵的上下文带到表格中，并了解哪些产品或内容属性与推荐模型相关。 如果您运行的是视频站点，您知道用户可能对观看来自同一导演的电影感兴趣，但可能不关心观看由同一工作室制作的电影。 [!DNL Target] 使您能借助控件增强此领域知识的算法。
* **Sophisticated models to make sense of millions of items in your catalog and interaction events.**[!DNL Target] 拥有在十年的经验中构建的复杂机器学习功能，并且我们每年处理数十亿的建议。
* **User context to ensure that recommendations are timely and relevant to your users.** You don’t want to recommend the video that someone just watched or the shirt that someone just added to their cart. Target’s rich user profile can be used in recommendations to ensure personalization.

## Implement Target Recommendations

从战略开始。

![说明推荐策略](/help/c-recommendations/assets/intro-5.png)

* **您要推荐哪些项目？** 首先，考虑您要推荐哪些项目。 这可能是产品、视频或内容。
* **要在何处显示推荐？** 接下来，考虑您要推荐的位置。 广泛而言，哪些渠道（Web、移动、店内、自助终端等）。 客户旅程的哪些部分将包含推荐？ 您网站上的哪些页面将包含推荐？
* **您如何确定推荐是否成功？** 假设您有没有推荐的体验和有推荐的体验，或者您有两种不同类型的推荐。 您如何确定哪种体验对您的客户来说更好？ 某些指标可能比其他指标更难衡量。 例如，推荐对客户终身价值的影响通常很难直接得到。 因此，通常更容易得到抽象度较低、更具体的指标，例如每次访问的收入、平均订单值或点击次数。 在某些情况下，您可能希望最小化一个度量，例如，支持调用的数量。

制定战略后，您准备开始实施 [!DNL Target Recommendations]。

创建建议实施涉及三个广泛的步骤：

![说明创建推荐实施步骤的插图](/help/c-recommendations/assets/intro-6.png)

1. 教授 [!DNL Target] 您的情境或产品。
1. 捕获用户行为。
1. 获取具有正确上下文的推荐。

### 教授 [!DNL Target] 您的情境或产品

开始时，您 [!DNL Recommendations]会传递有关要推荐的每个项目的信息。 [!DNL Target] 提供了多个集成选项以创建您的目录。

![说明如何向Target教授上下文或产品的插图](/help/c-recommendations/assets/intro-7.png)

最简单、最常用的方法是从产品信息管理系统或内容管理系统每天或每周发送CSV文件。 但是，您也可以使用 [!DNL Adobe Target] Javascript库在页面上传递数据层上的信息，利用我们的API直接从源系统传递信息，或者如果您已经将目录数据传递到，则使用我们的 [!DNL Adobe Analytics] 集成 [!DNL Analytics]。

有时，您可能希望同时使用多个选项，例如，每天通过CSV文件传递大多数数据，并通过API更频繁地传递库存更新。

您的IT部门通常会参与帮助设置此步骤。

Whichever method you choose, you should include metadata about each item in three categories:

![Illustration showing metadata information for your catalog](/help/c-recommendations/assets/intro-8.png)

* 要显示给接收推荐的用户的数据。 例如，电影的名称和缩略图图像URL。
* Data that is useful for applying marketing and merchandising controls. 例如，电影的等级，以便不推荐NC-17电影。
* 用于确定项目与其他项目的相似性的数据。 例如，电影的类型或电影中的演员。

### 捕获用户行为

接下来，您应添加标记或利用现有实施 [!DNL Analytics] 来跟踪驱动算法的转化事件（如查看和购买） [!DNL Target] 。

![说明如何捕获用户行为的插图](/help/c-recommendations/assets/intro-9.png)

您需要确保了 [!DNL Target] 解用户正在查看和购买的物品。 如果购买与上下文无关，您可能希望跟踪其他类型的转换事件，例如，下载PDF、完成调查、订阅新闻稿、观看视频等。

如果您已经在您的 [!DNL Target] 站点上使用运行A/B测试活动，则可能已完成此步骤。 或者，如果您已经使用 [!DNL Adobe Analytics] 报告网站访问和转化行为，则可以将其用作 [!DNL Analytics] 行为数据源。 否则，使用标记管理器(如 [Adobe Launch)进行设置最简单](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)。 还可以通过实时API将离线或应用程序内交 [!DNL Target] 互发送到。

### 获取具有正确上下文的推荐

在交互时传递有关用户和上下文的信息以返回相 [!DNL Target] 关的个性化推荐。

![说明如何使用正确的上下文获取推荐的插图](/help/c-recommendations/assets/intro-10.png)

除了用户行为汇总外，您还需要传递显 [!DNL Target] 示推荐的特定上下文。 这包括有关页面的信息和来自用户配置文件的信息。 [!DNL Target] 使用这些信息来提供个性化的推荐。 例如，在零售网站上，您希望了解访客当前查看的产品和产品类别。 您还希望了解有关该用户的信息（喜爱的品牌、喜爱的产品类别、忠诚度等级等）。 此信息非常重要，因此可 [!DNL Target] 以过滤项目并改进推荐的个性化。

## 构建您的第一个Recommendations活动

什么是活 [!DNL Recommendations] 动？

![显示可进行良好推荐活动的部分的插图](/help/c-recommendations/assets/intro-11.png)

活 [!DNL Recommendations] 动由以下组件组成：

* **受众**:哪些人应该看到这些建议？
* **标准**:应推荐哪些项目？
* **设计**:如何显示建议的项目？

![说明构成推荐活动的因素：受众、标准和设计](/help/c-recommendations/assets/intro-12.png)

开箱即用，包 [!DNL Target] 括14个内置受众、42个内置标准和10个内置设计模板。 您可以自定义这些项目中的每一项或添加您自己的项目。 我们之前曾举办过 [有关在中构建受众的网络研讨会](https://landing.adobe.com/acs/2018/na/adobe-target/registration.html)[!DNL Target]。 本节重点介绍定义标准，该标准定义将推荐哪些项目。

Target使用标准卡的概念。 标准卡就像个性化的菜谱。

![标准卡插图](/help/c-recommendations/assets/intro-13.png)

选择或创建正确的标准以达到您期望的个性化效果非常重要。 标准就像一个漏斗，它将您从整个目录带到最终的推荐集。

![漏斗插图](/help/c-recommendations/assets/intro-14.png)

以下各节介绍了此漏斗的各个部分及其工作方式 [!DNL Target]:

### 静态过滤器（集合和排除）

静态过滤器是与目录属性相关且您不希望经常更改的广泛适用规则。

![集合和排除的图示](/help/c-recommendations/assets/intro-16.png)

例如，在内容上下文中，您可能希望在推荐中包含所有电影，但不包括NC-17等级的电影。 在零售环境中，您可能在世界不同地区拥有多个品牌，但您只想推荐在美国可用的产品。 您可能还希望从区域专用标签中排除产品。

这些都是大致适用的目录属性，您可能希望在多个推荐中使用这些属性，但您不希望它们经常更改。

### 算法（推荐密钥和逻辑）

下一步是选择推荐密钥和逻辑。 这是您决定推荐的依据。

![算法插图](/help/c-recommendations/assets/intro-17.png)

您首先需要选择推荐密钥。 推荐密钥是您“查找”的推荐内容。 这是您推荐的依据。

您的建议基于：

* 访客当前查看的项目
* 访客当前查看的类别
* 访客上次购买或添加到购物车的物品
* 与访客或项目相关的自定义属性

然后，您根据这些键选择所需的推荐逻辑：

* 具有相似属性的项目
* 特定类别中查看次数最多的项目
* 购买此物品的客户也购买了这些物品
* 自定义属性

开箱即用，包 [!DNL Target] 括一系列算法。

![算法组合插图](/help/c-recommendations/assets/intro-15.png)

* **基于人气的算法包括** “查看次数最多”和“最畅销商品”。
* **基于内容的算法包括** “内容相似性”。
* **基于项目的协作过滤算法** ，包括“已查看／已查看”、“已查看／已购买”和“已购买／已购买”。 请注意，“购买”可以是任何转换。
* **个性化算法** ，包括“最近查看”、“站点亲和力”和增强了档案的协作过滤。
* **自带算法** ，让您使用自己的自定义算法。

### 在线业务规则

最后一步是应用在线业务规则。 您可以根据访客对您的数字资产的操作，为算法提供域知识和当前上下文。

![在线业务规则说明](/help/c-recommendations/assets/intro-18.png)

例如，在内容上下文中，您可能希望排除访客之前观看的影片、推荐同一导演的影片或提升同一流派的影片。 在零售环境中，您可能希望排除缺货产品、显示价格范围在5到500美元之间的物品或提升同一品牌的物品。

## Demo

完成上述推荐漏斗中说明的任务后，您将保留最终推荐。 要在内部观看产品内演示， [!DNL Target]请于21:00开始在 ** Adobe Target Basics网络研讨会（链接到以下内容）中进行演示。

## Adobe Target 基础知识网络研讨会：Recommendations 简介{#intro-to-recs}

[推荐介绍](https://forums.adobe.com/external-link.jspa?url=https%3A%2F%2Fadobecustomersuccess.adobeconnect.com%2Fp8gt31drhs3e%2F%3FOWASP_CSRFTOKEN%3D4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)