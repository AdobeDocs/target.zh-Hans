---
keywords: 推荐;简介;简介;网络研讨会;演示
description: 了解Adobe [!DNL Target]中的“推荐”活动，这些活动根据以前的用户活动或其他算法自动显示可能让客户感兴趣的内容。
title: “推荐”活动是什么？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: bc4d9a46-ea21-4687-b8a0-7f2e1dc33ebf
TQID: 'https://experienceleague.adobe.com/6jmXI9CsdCnyyQrQXKzq5WF8OQPQSCbE2Zb8AnpUvks'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
source-git-commit: 4f38c80880eedd9b966cdb2f178f408bb529b60c
workflow-type: tm+mt
source-wordcount: '1633'
ht-degree: 9%
---
# 推荐简介 {#introduction-to-recommendations}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解[!DNL Adobe Target]中的[!DNL Recommendations]活动如何向访客显示相关产品或内容，以及如何规划和构建[!DNL Recommendations]实施和活动。

>[!ENDSHADEBOX]

此页面基于&#x200B;*Recommendations简介*&#x200B;网络研讨会。 [!DNL Recommendations]活动可根据先前的访问优化实时建议，从而自动显示客户可能感兴趣的产品或内容。 该页还介绍了如何在[!DNL Target] UI中构建[!DNL Recommendations]活动。

## 简介

客户越来越期待获得推荐，并将这些推荐作为探索其他可用选项的起点。 几乎每个人都购买了他们在推荐中首先看到的产品，无论是在商店中还是在数字财产上。

![显示通常随新手机一起购买的配件的推荐，包括充电器、手机壳和耳机。](/help/main/c-recommendations/assets/intro-1.png)

人们使用媒体和内容的方式越来越多地受到个性化推荐的驱动，Netflix、Spotify和YouTube等数字优先品牌通过推荐开始客户体验。 由于有更多的替代方案可用，因此关键是在交互时为客户确定最相关的内容。

营销人员可以使用 [!DNL Adobe Target] 在各种行业、客户类型和渠道中推动个性化体验。 下表列出了一些客户如何使用[!DNL Target]来提供个性化推荐的示例。

| 用例 | 示例 |
|---|---|
| 发布 | Web发布者使用[!DNL Target Recommendations]向网站访客推荐文章并提高参与度。 |
| 视频教程 | [!DNL Adobe Creative Cloud]使用[!DNL Target]向Photoshop应用程序中的Photoshop用户推荐视频教程。 |
| 游戏 | 游戏公司使用[!DNL Target]向其控制台上的用户推荐游戏和内容。 |
| B2B销售 | 企业对企业的公司使用[!DNL Target]向B2B潜在用户推荐视频、白皮书和博客文章、提供下载，并向现有客户提供帮助。 |
| 旅行 | 一家德国旅游预订公司使用[!DNL Target]向旅客推荐酒店等产品。 有关详细信息，请参阅[Adobe Summit会话](https://2017.summit.adobe.com/na/sessions/summit-online/online-2017/#17608){target=_blank}。 |
| 零售 | 一家领先的B2B retailer使用[!DNL Target]在浏览器及其移动设备应用程序中推荐顶级类别和产品以吸引访客。 |

## 绝佳建议的要素

出色的推荐具有相关性和个性化。 三个元素驱动了相关性和个性化：

* **营销人员控件**&#x200B;以驱动推荐项目的相关性。 营销人员知道推荐模型应考虑其产品或内容的哪些属性。 例如，在视频网站上，用户可能对同一导演的电影感兴趣，但可能对同一工作室的电影不感兴趣。 [!DNL Target]提供控件以使用此域知识增强算法。
* **复杂的模型**，用于了解数百万个目录项和交互事件。 [!DNL Target]拥有经过十多年经验积累的机器学习功能，每年处理数十亿条推荐。
* **用户上下文**&#x200B;以确保推荐及时且相关。 例如，推荐不得包含某个用户刚刚观看的视频或刚刚添加到购物车的衬衫。 [!DNL Target]用户配置文件可用于推荐，以确保个性化。

## 实现 [!DNL Target] 推荐

从定义以下各点的策略开始：

* **要推荐的项目**：产品、视频或内容。
* **推荐的位置**：渠道（Web、移动设备、店内、网亭等）、客户历程的部分以及包含推荐的网站页面。
* **成功测量**：如何确定推荐是否成功，例如，通过将没有推荐的体验与具有推荐的体验进行比较，或者通过比较两种不同类型的推荐。 某些量度（例如对客户存留期值的影响）很难直接衡量，因此通常更容易使用更具体的量度，例如每次访问带来的收入、平均订单值或点击次数。 在某些情况下，目标是最小化某个量度，例如支持调用的数量。

定义策略后，[!DNL Target Recommendations]的实现涉及三个广泛的步骤：

![显示推荐实施三个步骤的插图：向Target传递您的内容或产品信息、捕获用户行为以及使用正确的上下文获取推荐。](assets/intro-6.png)

### 向[!DNL Target]讲授您的内容或产品

当您开始使用[!DNL Recommendations]时，您会传递有关每个要推荐项目的信息。

![显示如何向Target传递内容或产品信息的插图：CSV或Google信息源格式的信息源、带有Target的数据层、API以及Analytics集成。](assets/intro-7.png)

最简单且最常用的方法是：每天或每周从产品信息管理系统或内容管理系统发送CSV文件。 其他选项包括：使用[!DNL Adobe Target] JavaScript库从页面传递数据层上的信息，使用API直接从源系统传递信息，或者使用[!DNL Adobe Analytics]集成（如果您已将目录数据传递到[!DNL Analytics]）。 您可以同时使用多个选项，例如，每天通过CSV文件传递大多数数据，并通过API更频繁地传递库存更新。 IT部门通常会参与此步骤的设置。

无论您选择哪种方法，都可以在三个类别中包含有关每个项目的元数据：

* **要向收到推荐的用户显示的数据。** 例如，电影的名称和缩略图图像 URL。
* **对应用营销和促销控件有用的数据。** 例如，电影的评级，这样您就不会推荐评级为 NC-17 的电影。
* **用于确定项目与其他项目相似度的数据。** 例如，电影的流派或者电影中的演员。

### 捕获用户行为

![显示如何捕获用户行为的插图：查看次数和点击次数导致购买、转化、下载、订阅和播放，已使用Target、Analytics或API进行跟踪。](assets/intro-9.png)

添加标记或使用现有[!DNL Analytics]实施，以便[!DNL Target]了解您的用户查看和购买的项目。 如果购买与上下文无关，请跟踪不同类型的转化事件，例如，下载PDF、完成调查、订阅新闻稿或观看视频。

如果您已经使用[!DNL Target]在网站上运行A/B测试活动，则可能已经完成此步骤。 如果您已使用[!DNL Adobe Analytics]报告网站访问和转化行为，则可以使用[!DNL Analytics]作为行为数据源。 否则，最简单的选项是使用标签管理器（如[[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-using-adobe-launch.html){target=_blank}中的标签）设置此项。 也可以通过实时API将离线或应用程序内的交互发送到[!DNL Target]。

### 使用正确的上下文信息获取推荐

![显示如何使用正确的上下文信息获取推荐的插图：查看的当前产品、当前产品类别、用户喜爱的类别、用户喜爱的品牌和用户忠诚度级别都传递到Target。](assets/intro-10.png)

除了聚合用户行为之外，[!DNL Target]还需要显示推荐的特定上下文，其中包括有关页面的信息和来自用户配置文件的信息。 [!DNL Target]使用此信息来筛选项目并改进推荐的个性化。

## 构建第一个“推荐”活动

[!DNL Recommendations]活动结合了受众、标准和设计。 [!DNL Target]包括14个内置受众、42个内置标准和10个内置设计模板。 您可以自定义每个项目或添加您自己的项目。

![显示构成良好推荐活动各个部分的插图：受众（谁应该看到这些推荐）、标准（应该推荐哪些项目）和设计（如何显示推荐项目）。](assets/intro-11.png)

[!DNL Target]使用条件卡的概念，就像个性化的方法一样。 选择或创建正确的标准对于实现预期的个性化结果很重要。 标准卡片的工作方式与funnel类似，可将您从整个目录带到最终的一组推荐。

![标准funnel的插图：目录内容、静态筛选器（集合和排除项）、算法（推荐键和逻辑）、在线业务规则（动态筛选和属性权重）以及最终推荐，位于示例标准卡片旁边。](assets/intro-14.png)

以下部分介绍了此funnel的各个部分及其在[!DNL Target]中的工作方式。

### 静态筛选器（收藏集和排除项）

静态筛选器是与您不希望频繁更改的目录属性相关的广泛适用的规则，因此您可以在多个推荐中使用它们。

![静态筛选条件的插图。 内容：包含所有电影并从推荐中排除评级为NC-17的电影。 产品：包含美国提供的所有产品，并从区域私有标签中排除产品。](assets/intro-16.png)

### 算法（推荐键和推荐逻辑）

下一步是选择作为推荐基础的推荐键和逻辑。 推荐键是您要“查找”以选择推荐的内容。

![算法步骤的插图。 推荐键：当前查看的项目、当前查看的类别、上次购买的项目或自定义属性。 推荐逻辑：具有相似属性的项目、类别中查看次数最多的项目、购买此项目的客户也购买了这些项目，或自定义算法。](assets/intro-17.png)

[!DNL Target]包含算法组合。

![算法组合插图：基于热门程度（查看次数最多，最畅销商品）、基于内容（内容相似度）、基于项目的协同筛选（已查看/已查看、已查看/已购买、已购买/已购买，其中已购买可以是任何转化）、个性化(最近查看、网站亲和度、配置文件增强的协作。 正在筛选)，并自带（自定义算法）。](assets/intro-15.png)

### 在线业务规则

最后一步是应用在线业务规则，这些规则会根据访客对数字资产所做的操作，通过领域知识和当前上下文来增强算法。

![联机业务规则的插图。 内容：排除以前观看过的电影，从同一导演那里放映电影，并提升采用相同流派的电影。 产品：排除缺货产品，显示价格在5美元到500美元之间的项目，并提升来自同一品牌的项目。](/help/main/c-recommendations/assets/intro-18.png)
