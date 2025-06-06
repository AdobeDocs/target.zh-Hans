---
keywords: 推荐键；推荐逻辑；当前类别；自定义属性；上次购买的项目；上次查看的项目；查看次数最多的项目；最喜爱的项目；热门程度；最近查看的项目；上次购买；上次查看次数最多；收藏；最近查看的项目
description: 了解如何使用基于键的推荐，这些键使用访客行为上下文在[!UICONTROL Recommendations]活动中显示相关结果。
title: 如何将[!UICONTROL Recommendation]基于[!UICONTROL Recommendation Key]？
feature: Recommendations
mini-toc-levels: 2
exl-id: 49764f18-88fb-41be-b2a0-e7ced9de742c
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '3463'
ht-degree: 27%

---

# 使推荐基于推荐键

基于算法的Recommendations使用访客行为上下文在[!DNL Adobe Target] [!DNL Recommendations]活动中显示相关结果。

每种算法类型提供了适合其类型的不同算法，如下表所示：

| 算法类型 | 何时使用/可用算法 |
| --- | --- |
| [!UICONTROL Cart-Based] | 根据用户的购物车内容提供推荐。<ul><li>[!UICONTROL People Who Viewed These, Also Viewed]</li><li>[!UICONTROL People Who Viewed These, Also Bought]</li><li>[!UICONTROL People Who Bought These, Also Bought]</li></ul> |
| [!UICONTROL Popularity-Based] | 根据项目在整个网站中的整体受欢迎程度或用户最喜爱或查看次数最多的类别、品牌、流派等中的项目受欢迎程度提供推荐。 <ul><li>[!UICONTROL Most Viewed Across the Site]</li><li>[!UICONTROL Most Viewed by Category]</li><li>[!UICONTROL Most Viewed by Item Attribute]</li><li>[!UICONTROL Top Sellers Across the Site]</li><li>[!UICONTROL Top Sellers by Category]</li><li>[!UICONTROL Top Sellers by Item Attribute]</li><li>[!UICONTROL Top by Analytics Metric]</li></ul> |
| [!UICONTROL Item-Based] | 根据查找的用户当前正在查看或最近查看过的项目的相似项目提供推荐。 <ul><li>[!UICONTROL People Who Viewed This, Viewed That]</li><li>[!UICONTROL People Who Viewed This, Bought That]</li><li>[!UICONTROL People Who Bought This, Bought That]</li><li>[!UICONTROL Items with Similar Attributes]</li></ul> |
| [!UICONTROL User-Based] | 根据用户的行为提供推荐。 <ul><li>[!UICONTROL Recently Viewed Items]</li><li>[!UICONTROL Recommended for You]</li></ul> |
| [!UICONTROL Custom Criteria] | 根据您上传的自定义文件提出推荐。 <ul><li>自定义算法</li></ul> |

每个标准都在其自身的选项卡中进行定义。流量会在不同的标准测试中均匀拆分。换句话说，如果您有两个标准，则流量会在这两个标准之间平均拆分。如果您有两个标准和两个设计，则流量会在四种组合之间平均拆分。您也可指定一定数量的网站访客（百分比），这部分访客将看到默认内容以进行对比。在这种情况下，指定百分比的访客将看到默认内容，其余内容将在您的标准和设计组合中拆分。

有关创建标准和定义其算法类型和算法的详细信息，请参阅[创建标准](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md)。

不同的推荐算法可以将其自身放置在不同类型的页面上。 有关每种算法类型及其可用算法的更多信息，请参阅以下部分。

## 基于购物车 {#cart-based}

[!UICONTROL Cart-Based]算法类型允许根据访客当前购物车的内容推荐项目。 推荐键是通过逗号分隔值的[mbox参数`cartIds`](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=zh-Hans){target=_blank}提供的。 仅考虑前 10 个值。

基于购物车的推荐逻辑类似于基于用户的算法“[!UICONTROL Recommended For You]”以及基于项目的算法“[!UICONTROL People Who Viewed These, Bought Those]”和“[!UICONTROL People Who Bought These, Bought Those]”。

[!DNL Target]使用协作过滤技术确定访客购物车中每个项目的相似性，然后合并每个项目的这些行为相似性，以获取合并列表。

[!DNL Target]还使营销人员可以选择查看单个会话或多个会话中的访客行为：

* **[!UICONTROL Single Session]**：基于其他访客在单个会话中的操作。

  当产品根据使用情况、场合或事件强烈地“配合”在一起时，查看单个会话中的行为可能会有意义。 例如，一位访客正在购买打印机，可能还需要油墨和纸张。 或者，一位访客正在购买花生酱，可能还需要面包和果冻。

* **[!UICONTROL Across Sessions]**：基于其他访客在多个会话中所执行的操作。

  当感觉产品强烈地根据访客偏好或品味彼此相互“配合”时，查看多个会话中的行为可能会有意义。 例如，访客喜欢《星球大战》，可能还喜欢印第安纳·琼斯，即使访客不一定想在同一时间观看两部电影。 或者，访客喜欢棋类游戏“Codenames”，并且可能还喜欢棋类游戏“Avalon”，即使访客无法同时玩这两种游戏。

[!DNL Target]会根据每位访客当前购物车中的商品为其提供推荐，无论您查看的是单个会话中的访客行为还是多个会话中的访客行为。

以下算法可用于[!UICONTROL Cart-Based]算法类型：

### [!UICONTROL People Who Viewed This, Also Viewed]

推荐在查看了指定项目的同一会话中最常查看的项目。

此逻辑会返回查看此产品后用户查看的其他产品。 指定的产品未包含在结果集中。

此逻辑允许您通过推荐查看了某个项目的其他访客也查看过的项目来创建额外的转化机会。 例如，在您的网站上查看公路自行车的访客可能还会查看自行车头盔、自行车工具包、车锁等。 您可以使用此逻辑创建推荐，以推荐其他产品帮助您增加收入。

如果选择此算法，则可以选择以下Recommendations密钥：

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

### [!UICONTROL People Who Viewed This, Also Bought]

推荐在查看指定项目的同一会话中最常购买的项目。

此逻辑会返回查看此产品后用户购买的其他产品。 指定的产品未包含在结果集中。

利用此逻辑，您可以通过在产品页面上显示推荐来增加交叉销售机会，例如，该推荐会显示查看过所购买项目的其他访客所购买的项目。 例如，如果访客正在查看钓竿，推荐会显示其他访客购买的其他项目，例如鱼缸、拖把和钓鱼诱饵。 当访客浏览您的网站时，您会向访客提供额外的购买建议。

如果选择此算法，则可以选择以下Recommendations密钥：

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

### [!UICONTROL People Who Bought This, Also Bought]

推荐客户在购买指定项目的同时最常购买的其他项目。

此逻辑返回人们购买了这个产品后购买的其他产品。 指定的产品未包含在结果集中。

此逻辑允许您通过在购物车摘要页面上显示推荐（例如，显示其他购买者也购买的项目）来增加交叉销售机会。 例如，如果访客正在购买套装，推荐会显示其他访客与该套装一起购买的其他项目，例如领带、皮鞋和袖扣。 在访客审核其购买情况时，您向他们提供其他建议。

如果选择此算法，则可以选择以下Recommendations密钥：

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

## [!UICONTROL Popularity-Based]

[!UICONTROL Popularity-Based]算法类型允许您根据整个网站中项目的整体热门程度或用户最喜爱或查看次数最多的类别、品牌、流派等中的项目热门程度进行推荐。

以下算法可用于[!UICONTROL Popularity-Based]算法类型：

### [!UICONTROL Most Viewed Across the Site] {#most-viewed}

推荐由最常被查看的项目确定。 它由新近度/频率标准通过如下计算方式来决定：

* 首次查看产品得 10 分
* 接下来每次查看得 5 分
* 会话结束时将所有值除以 2

例如，在一次会话中查看冲浪板A然后查看冲浪板B会导致A：10，B：5。 会话结束时，您拥有A：5，B：2.5。如果在下一会话中查看相同的项目，则值将更改为A：15 B：7.5。

在常规页面（如主页或登陆页面以及站外广告）上使用此算法。

### [!UICONTROL Most Viewed by Category] {#most-viewed-category}

推荐由获得最多活动的类别决定，使用的方法与“查看次数最多的项目”相同，但是由类别接受评分，而非产品。

它由新近度/频率标准通过如下计算方式来决定：

* 首次查看类别得 10 分
* 接下来每次查看得 5 分

首次访问类别得 10 分。接下来每次访问同一类别得 5 分。每次访问中之前查看过的非当前类别将减 1 分。

例如，在一个会话中查看类别A然后查看类别B，结果为A：9，B：10。 如果您在下一个会话中查看相同的项目，则值将更改为 A：20，B：9。

在常规页面（如主页或登陆页面以及站外广告）上使用此算法。

如果您选择“按类别查看次数最多”算法，则可以选择以下Recommendations键值：

* [!UICONTROL Current Category]
* [!UICONTROL Favorite Category]

### [!UICONTROL Most Viewed by Item Attribute]

推荐与网站上查看次数最多的项目或媒体类似的项目或媒体。

通过此算法，您可以选择推荐所基于的项目属性，例如“名称”或“品牌”。

然后，选择访客配置文件中存储哪些配置文件属性进行匹配，例如“最喜爱的品牌”、“上一个添加到购物车的项目”或“查看次数最多的节目”。

### [!UICONTROL Top Sellers Across the Site] {#top-sellers}

显示整个网站中已完成最多的订单中包含的物料。 同一项目在一个订单中购买多件会被计为一次订购。

此算法允许您为网站上的最畅销商品创建推荐，以提高转化率和收入。 此逻辑尤其适用于首次访问网站的访客。

### [!UICONTROL Top Sellers by Category]

按类别显示已完成最多的订单中包含的物料。 同一项目在一个订单中购买多件会被计为一次订购。

通过此算法，您可以根据类别为网站上的最畅销商品创建推荐，以提高转化率和收入。 此逻辑尤其适用于首次访问网站的访客。

如果选择[!UICONTROL Most Viewed by Category]算法，则可以选择以下[!UICONTROL Recommendations Keys]：

* [!UICONTROL Current Category]
* [!UICONTROL Favorite Category]

### [!UICONTROL Top Sellers by Item Attribute]

推荐与网站上购买次数最多的项目或媒体类似的项目或媒体。

通过此算法，您可以选择推荐所基于的项目属性，例如“名称”或“品牌”。

然后，选择访客配置文件中存储哪些配置文件属性进行匹配，例如“最喜爱的品牌”、“上一个添加到购物车的项目”或“查看次数最多的节目”。

### [!UICONTROL Top by Analytics Metric]

显示“前x个”，其中&#x200B;*x*&#x200B;是任意[!DNL Analytics]量度。 使用来自mbox的行为数据时，您可以使用[!UICONTROL Top Sold]或[!UICONTROL Top Viewed] （x =“已出售”或x =“已查看”）。 如果您使用的是来自[!DNL Adobe Analytics]的行为数据，则可以使用x = &quot;购物车添加次数&quot;或一些其他[!DNL Analytics]量度。

## [!UICONTROL Item-Based]

[!UICONTROL Item-Based]推荐类型允许您根据用户当前正在查看或最近查看的项目的相似项目进行推荐。

以下算法可用于[!UICONTROL Item-Based]算法类型：

### [!UICONTROL People Who Viewed This, Viewed That] {#viewed-viewed}

推荐在查看了指定项目的同一会话中最常查看的项目。

此逻辑返回查看此产品后用户查看的其他产品；指定的产品不包含在结果集中。

此逻辑允许您通过推荐查看了某个项目的其他访客也查看过的项目来创建额外的转化机会。 例如，在您的网站上查看公路自行车的访客可能还会查看自行车头盔、自行车工具包、车锁等。 您可以使用此逻辑创建推荐，以推荐其他产品帮助您增加收入。

如果选择此算法，则可以选择以下[!UICONTROL Recommendations Keys]：

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

### [!UICONTROL People Who Viewed This, Bought That] {#viewed-bought}

推荐在查看了指定项目的同一会话中最常购买的项目。此标准会返回客户在查看指定项目后所购买的其他产品，返回的结果集中不包含指定的产品。

此逻辑返回查看此产品后用户购买的其他产品；指定的产品不包含在结果集中。

利用此逻辑，您可以通过在产品页面上显示推荐来增加交叉销售机会，例如，该推荐会显示查看过所购买项目的其他访客所购买的项目。 例如，如果访客正在查看钓竿，推荐会显示其他访客购买的其他项目，例如鱼缸、拖把和钓鱼诱饵。 当访客浏览您的网站时，您会向访客提供额外的购买建议。

如果选择此算法，则可以选择以下[!UICONTROL Recommendations Keys]：

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

### [!UICONTROL People Who Bought This, Bought That] {#bought-bought}

推荐客户在购买指定项目的同时最常购买的其他项目。

此逻辑返回人们购买了这个产品后购买的其他产品。 指定的产品未包含在结果集中。

此逻辑允许您通过在购物车摘要页面上显示推荐（例如，显示其他购买者也购买的项目）来增加交叉销售机会。 例如，如果访客正在购买套装，推荐会显示其他访客与该套装一起购买的其他项目，例如领带、皮鞋和袖扣。 在访客审核其购买情况时，您向他们提供其他建议。

如果选择此算法，则可以选择以下[!UICONTROL Recommendations Keys]：

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

### [!UICONTROL Items with Similar Attributes] {#similar-attributes}

根据当前页面活动或以往的访客行为来推荐类似的项目或媒体。

如果选择[!UICONTROL Items with Similar Attributes]或[!UICONTROL Media with Similar Attributes]，则可以选择设置内容相似度规则。

使用内容相似度生成推荐对于新项目特别有效，这些新项目不太可能在使用[!UICONTROL People Who Viewed This]、[!UICONTROL Viewed That]和基于过去行为的其他逻辑的推荐中显示。 您还可以使用内容相似度为没有过去购买数据或其他历史数据的新访客生成有用的推荐。

如果选择此算法，则可以选择以下[!UICONTROL Recommendations Keys]：

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

有关详细信息，请参阅[内容相似度](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#similarity)。

## [!UICONTROL User-Based]

[!UICONTROL User-Based]算法类型允许您根据用户行为提供推荐。

以下算法可用于[!UICONTROL User-Based]算法类型：

### [!UICONTROL Recently Viewed Items] {#recently-viewed}

使用访客的历史记录（跨会话）根据设计中的版块数量显示访客最近查看过的 *x* 个项目。

[!UICONTROL Recently Viewed Items]算法返回特定于给定[环境](/help/main/administrating-target/hosts.md)的结果。 如果两个网站属于不同的环境，并且访客在两个网站之间切换访问，则每个网站仅显示相应网站的最近查看的项目。如果两个网站位于同一环境中，并且访客在两个网站之间切换访问，则访客会看到两个网站的最近查看的相同项目。

>[!NOTE]
>
>您无法将[!UICONTROL Recently Viewed Items]条件用于备份推荐。

可以筛选[!UICONTROL Recently Viewed Items]或[!UICONTROL Recently Viewed Media]，以便仅显示具有特定属性的项目。

* [!UICONTROL Recently Viewed]标准可配置，与推荐中的其他标准类似。
* 您可以使用与任何其他条件相同的方式使用[收藏集](/help/main/c-recommendations/c-products/collections.md)、[排除项](/help/main/c-recommendations/c-products/exclusions.md)和[包含项](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)（包括用于价格和库存的特殊规则）。

可能的用例包括，具有多个企业的跨国公司可能有一个跨多个数字资产的访客查看项目。 在这种情况下，您可以限制最近查看的项目，以便仅显示之前查看的相应财产中的项目。这样可防止最近查看过的项目显示在其他数字资产的网站上。

在常规页面（如主页或登陆页面以及站外广告）上使用此算法。

>[!NOTE]
>
>[!UICONTROL Recently Viewed Items]尊重排除全局设置和活动的选定收藏集设置。 如果某个项目被全局排除项排除在外，或者未包含在选定的收藏集中，则不会显示该项目。 因此，在使用[!UICONTROL Recently Viewed Items]标准时，通常应使用“所有收藏集”设置。

### [!UICONTROL Recommended for You] {#recommended-for-you}

根据每位访客的浏览、查看和购买历史记录推荐商品。

通过此算法，您可以为新访客和回访访客提供个性化内容和体验。 推荐列表根据访客最近的活动进行加权，在会话中更新，并随着用户浏览您的网站而更加个性化。

查看次数和购买次数均用于确定推荐的项目。 指定的推荐键（例如，[!UICONTROL Current Item]）用于应用您选择的任何包含规则过滤器。

例如，您可以：

* 排除不符合特定标准的项目（产品缺货、30天前发布的文章、评级R的电影等）。
* 将必备件限制为单个类别或当前类别。

如果选择此算法，则可以选择以下筛选键：

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

## 自定义标准 {#custom}

[!UICONTROL Custom Criteria]算法类型允许您根据上传的自定义文件提供推荐。

推荐由使用 user.*x* 或 profile.*x* 属性存储在访客配置文件中的项目确定。

如果选择该选项，轮廓属性中必须存在 `entity.id` 值。

如果要根据自定义属性来进行推荐，则必须选择自定义属性，然后再选择推荐类型。

您可以基于自己的自定义标准输出进行实时筛选。例如，您可以将推荐项目限制为访客最喜欢的类别或品牌。这样，您便能够将离线计算与实时筛选结合使用。

此功能意味着您可以使用[!DNL Target]来基于离线计算的推荐或管理的自定义列表添加个性化。 这样做可以将数据科学和研究与 Adobe 行之有效的众多功能（包括交付、运行时筛选、A/B 测试、定位、报表、集成，等等）结合起来。

在[!UICONTROL Custom Criteria]上添加包含规则后，这会将原本为静态的推荐转变为基于访客兴趣的动态推荐。

* 与推荐中的其他标准一样，自定义标准也可配置。
* 您可以使用与任何其他条件相同的方式使用[收藏集](/help/main/c-recommendations/c-products/collections.md)、[排除项](/help/main/c-recommendations/c-products/exclusions.md)和[包含项](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)（包括用于价格和库存的特殊规则）。

用例可能包括：

* 您想要推荐管理的自定义列表中的影片，但“仅”当访客尚未观看这些影片时才进行推荐。
* 您要运行离线算法并使用结果来支持推荐，但必须确保从不推荐缺货项目。
* 您想要只包含属于访客最喜爱类别的项目。

## 推荐键 {#keys}

[!UICONTROL Recommendation Key]下拉列表中提供了以下推荐键：

### [!UICONTROL Current Item] {#current-item}

推荐由访客当前正在查看的项目决定。

推荐会向对指定项目感兴趣的访客显示可能令其感兴趣的其他项目。

如果选择该选项，`entity.id` 值必须作为显示 mbox 中的参数传递。

可以与以下算法一起使用：

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

使用以下位置在您的网站上使用[!UICONTROL Current Item]推荐键：

* 单项目页面，例如产品页面。
* 请勿在空的搜索结果页面上使用。

### [!UICONTROL Last Purchased Item] {#last-purchased}

推荐由每位唯一访客最近购买的项目决定。这是自动捕获的，因此页面上不得传递任何值。

可以与以下算法一起使用：

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

使用以下位置在您的网站上使用[!UICONTROL Last Purchased Item]推荐键：

* 主页，“我的帐户”页面，站外广告。
* 请勿在产品页面或与购买相关的页面上使用。

#### 自定义推荐键

您可以使推荐基于自定义轮廓属性的值。例如，假设您要根据访客最近添加到队列中的影片显示推荐的影片。

1. 从&#x200B;**[!UICONTROL Recommendation Key]**&#x200B;下拉列表中选择自定义配置文件属性（例如，“[!UICONTROL Last Show Added to Watchlist]”）。
1. 然后选择您的&#x200B;**[!UICONTROL Recommendation Logic]**（例如“[!UICONTROL People Who Viewed This, Viewed That]”）。

如果自定义轮廓属性与单个实体 ID 不直接匹配，则需要向 [!DNL Recommendations] 说明您希望如何与实体进行匹配。例如，假设您要显示访客最喜爱的品牌中的最畅销商品项目。

1. 从&#x200B;**[!UICONTROL Recommendation Key]**&#x200B;下拉列表中选择自定义配置文件属性（例如，“最喜爱的品牌”）。

1. 然后选择要与此键一起使用的&#x200B;**[!UICONTROL Recommendation Logic]**（例如，“[!UICONTROL Top Sellers]”）。

   将显示[!UICONTROL Group By Unique Value Of]选项。

1. 选择与您所选的键匹配的实体属性。 在这种情况下，“[!UICONTROL Favorite Brand]”与`entity.brand`匹配。

   [!DNL Recommendations]现在为每个品牌生成“[!UICONTROL Top Sellers]”列表，并根据访客的[!UICONTROL Favorite Brand]配置文件属性中存储的值向访客显示相应的“[!UICONTROL Top Sellers]”列表。

### [!UICONTROL Last Viewed Item] {#last-viewed}

推荐由每位唯一访客最近查看的项目决定。这是自动捕获的，因此页面上不得传递任何值。

可以与以下算法一起使用：

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

使用以下位置在您的网站上使用[!UICONTROL Last Viewed Item]推荐键：

* 主页，“我的帐户”页面，站外广告。
* 请勿在产品页面或与购买相关的页面上使用。

### [!UICONTROL Most Viewed Item] {#most-viewed-logic}

显示网站上查看次数最多的项目或媒体。

此逻辑允许您根据网站上查看次数最多的项目显示推荐，以提高其他项目的转化率。 例如，媒体网站可在其主页上显示其查看次数最多的视频的推荐，以鼓励访客观看其他视频。

此推荐键可与以下算法一起使用：

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

### [!UICONTROL Current Category] {#current-category}

推荐由访客当前正在查看的产品类别决定。

推荐会显示指定产品类别中的项目。

如果选择该选项，`entity.categoryId` 值必须作为显示 mbox 的参数传递。

此推荐键可与以下算法一起使用：

* [!UICONTROL Top Sellers]
* [!UICONTROL Most Viewed]

使用以下位置在您的网站上使用[!UICONTROL Current Category]推荐键：

* 单类别页面。
* 请勿在空的搜索结果页面上使用。

### [!UICONTROL Favorite Category] {#favorite-category}

推荐由访客最喜爱的产品类别决定。

推荐会显示指定产品类别中的项目。

如果选择该选项，`entity.categoryId` 值必须作为显示 mbox 的参数传递。

此推荐键可与以下算法一起使用：

* [!UICONTROL Top Sellers]
* [!UICONTROL Most Viewed]

使用以下位置在您的网站上使用[!UICONTROL Current Category]推荐键：

* 单类别页面。
* 请勿在空的搜索结果页面上使用。

### [!UICONTROL Site Affinity] {#site-affinity}

根据项目间关系的确定性来推荐项目。您可以配置此标准，以确定需要多少数据，才能使用[!UICONTROL Inclusion Rules]滑块显示推荐。 例如，如果您选择“非常强”，则会推荐具有最强匹配确定性的产品。

例如，如果您设置了非常强的亲和度，且您的设计包含 5 个项目，其中有 3 个项目达到了联系阈值强度，则另外 2 个未达到最低强度要求的项目不会在推荐中显示，且会被替换为您定义的备用项目。具有最强亲和度的项目会最先显示。

例如，在线零售商可以在后续访问中推荐访客在过去会话期间感兴趣的项目。 捕获每个访客会话的活动，以根据回访间隔和频率模型计算亲和度。 当此访客返回您的网站时，将使用网站亲和度根据您网站上以往的操作显示推荐。

有些客户具有多种产品收藏集和多种网站行为，对于他们而言，设置较弱的网站亲和度可能会获得更好的结果。

此逻辑可以与以下推荐键一起使用：

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]
