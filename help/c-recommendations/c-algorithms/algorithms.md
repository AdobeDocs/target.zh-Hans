---
description: 标准即规则，可根据预先确定的一组访客行为来确定要推荐的产品。
keywords: 推荐;推荐活动;标准;算法
seo-description: Adobe Target 中的标准即规则，可根据预先确定的一组访客行为来确定要推荐的产品。
seo-title: 标准
solution: Target
title: 标准
title-outputclass: premium
topic: Premium
uuid: 738db164-174b-45b8-bb8a-778f6494f1d7
badge: premium
translation-type: tm+mt
source-git-commit: c50623d8068cda63667be8f2fff25c7694f41279

---


# ![PREMIUM](/help/assets/premium.png) 标准 {#criteria}

标准即规则，可根据预先确定的一组访客行为来确定要推荐的产品。

标准可确定哪项操作将导致推荐哪个项目。您可以添加多个标准，以便对多个推荐类型进行相互测试。

## 垂直行业 {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

您可以根据“推荐”活动的目标来选择垂直行业：

| 垂直行业 | 目标 |
|--- |--- |
| 零售/电子商务 | 转化促进完成购买 |
| 潜在客户拓展/B2B/金融服务 | 转化但不购买 |
| 媒体/出版 | 参与度 |

## Recommendation key {#section_885B3BB1B43048A88A8926F6B76FC482}

您选择的推荐键决定了标准类型。标准类型具有以下几种（在设置 [!DNL Recommendations] 活动时，这些标准类型会显示为相应的标准卡片）。

| 标准类型 | 键 |
|--- |--- |
| 当前页面活动 | 根据用户在当前页面上执行的操作来推荐项目。例如，查看了某个特定商品的访客可能希望查看同一类别的其他商品。<ul><li>当前项目</li><li>当前类别 </li></ul> |
| 自定义 | 根据自定义属性推荐项目。<ul><li>自定义属性</li></ul>如果要根据自定义属性来进行推荐，则必须选择自定义属性，然后再选择推荐类型。<br>您可以基于自己的自定义标准输出进行实时筛选。例如，您可以将推荐项目限制为访客最喜欢的类别或品牌。这样，您便能够将离线计算与实时筛选结合使用。<br>这项功能意味着您可以使用 Target 来基于离线计算的推荐或管理的自定义列表添加个性化。这样做可以将数据科学和研究与 Adobe 行之有效的众多功能（包括交付、运行时筛选、A/B 测试、定位、报表、集成，等等）结合起来。<br>通过在自定义标准中添加包含规则，您可以将原本为静态的推荐转变为基于访客兴趣的动态推荐。<ul><li>与推荐中的其他标准一样，自定义标准也可配置。</li><li>您可以使用[收藏集](/help/c-recommendations/c-products/collections.md)、[排除项](/help/c-recommendations/c-products/exclusions.md)和[包含项](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)（包括针对价格和库存的特殊规则），其使用方法与任何其他标准相同。</li></ul>用例可能包括：<ul><li>您想要推荐管理的自定义列表中的影片，但“仅”当访客尚未观看这些影片时才进行推荐。</li><li>您想要运行离线算法，并使用得出的结果来进行推荐，但是您需要确保绝不推荐缺货的项目。</li><li>您想要只包含属于访客最喜爱类别的项目。</li></ul> |
| 过去的行为 | 根据访客过去对某个项目所做的回应来推荐项目。例如，以前购买过某个特定品牌的客户更有可能会购买属于该品牌的其他项目。<ul><li>上次购买的项目</li><li>上次查看的项目</li><li>查看次数最多的项目</li><li>最喜爱类别</li></ul> |
| 人气 | 推荐最受欢迎的项目，例如相关类别中最热门的视频或网站上最常查看的产品。<ul><li>人气</li></ul> |
| 最近查看的项目 | 推荐访客最近查看过的项目，例如访客上次访问您的网站时所查看的项目，或访客当前最倾向于查看的商品。<br>“最近查看的项目”算法会返回特定于某个[环境](/help/administrating-target/hosts.md)中的访客活动。如果两个网站属于不同的环境，并且访客在两个网站之间切换访问，则算法将仅返回相应网站的最近查看的项目。<br>此标准类型不受收藏集限制。<ul><li>最近查看的项目</li></ul>**注意：**&#x200B;您无法在备用推荐中使用“最近查看的项目”标准。<br>可以筛选最近查看的项目/媒体，以便仅显示具有特定属性的项目。<ul><li>与推荐中的其他标准一样，“最近查看的项目”标准也可配置。</li><li>您可以使用[收藏集](/help/c-recommendations/c-products/collections.md)、[排除项](/help/c-recommendations/c-products/exclusions.md)和[包含项](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)（包括针对价格和库存的特殊规则），其使用方法与任何其他标准相同。</li></ul>用例可能包括：<ul><li>一家开展多种业务的跨国公司可能会让访客在多个数字财产中查看项目。在这种情况下，您可以限制最近查看的项目，以便仅显示之前查看的相应财产中的项目。执行此操作可防止最近查看的项目在其他数字财产网站上显示。</li></ul> |

## Using a custom recommendations key {#custom-key}

您还可以根据自定义配置文件属性的值来推荐。

>[!NOTE]
>
>可以通过JavaScript、API或集成将自定义配置文件参数传递到Target。 有关自定义配置文件属性的详细信息，请参 [阅访客配置文件](/help/c-target/c-visitor-profile/visitor-profile.md)。)

例如，假定您希望根据用户最近添加到其队列的电影显示推荐的电影。

Select your custom profile attribute from the [!UICONTROL Recommendation Key] drop-down list (for example, [!UICONTROL Last Show Added to Watchlist]).

Then select your [!UICONTROL Recommendation Logic] (for example, [!UICONTROL People Who Viewed This, Viewed That]).

![“创建新条件”对话框](/help/c-recommendations/c-algorithms/assets/custom-key1.png)

If your custom profile attribute does not directly match to a single entity ID, it is necessary to explain to [!DNL Recommendations] how you want the match to an entity to occur.

例如，假设您希望显示来自用户喜爱品牌的畅销商品。

Select your custom profile attribute from the [!UICONTROL Recommendation Key] drop-down list (for example, [!UICONTROL Favorite Brand].

Then select the [!UICONTROL Recommendation Logic] you want to use with this key (for example, [!UICONTROL Top Sellers]).

此时会显示[!UICONTROL 按以下项的唯一值分组]选项。选择与您所选的键匹配的实体属性。In this case [!UICONTROL Favorite Brand] matches to `entity.brand`.

[!DNL Recommendations] 现在为每个品牌生成一个“最畅销商品”列表，并根据“最喜爱的品牌”配置文件属性中存储的值向用户显示相应的“最畅销商品  ”列表。

![“最畅销商品”属性](/help/c-recommendations/c-algorithms/assets/custom-key2.png)

## 标准/算法 {#criteria-algorithms}

[!DNL Target Recommendations] 会使用复杂的算法来确定访客操作在何种情况下才符合活动中设置的标准。推荐键决定了可用的推荐逻辑选项。

| 标准 | 描述 |
|--- |--- |
| 具有相似属性的项目/媒体 | 根据当前页面活动或以往的访客行为来推荐类似的项目或媒体。<br>**注意：**&#x200B;如果您选择了具有相似属性的项目/媒体，则可以选择设置内容相似度规则。 |
| 查看了这个项目，也查看了那个项目的人 | 推荐在查看了指定项目的同一会话中最常查看的项目。 |
| 查看了这个项目，但购买了那个项目的人 | 推荐在查看了指定项目的同一会话中最常购买的项目。此标准会返回客户在查看指定项目后所购买的其他产品，返回的结果集中不包含指定的产品。 |
| 购买了这个项目，也购买了那个项目的人 | 推荐客户在购买指定项目的同时最常购买的其他项目。 |
| 网站亲和度 | 根据项目间关系的确定性来推荐项目。您可以配置此标准，以确定需要多少数据，才能使用“包含规则”滑块显示推荐。例如，如果您选择“非常强”，则会推荐具有最强匹配确定性的产品。<br>例如，如果您设置了非常强的亲和度，且您的设计包含 5 个项目，其中有 3 个项目达到了联系阈值强度，则另外 2 个未达到最低强度要求的项目不会在推荐中显示，且会被替换为您定义的备用项目。具有最强亲和度的项目会最先显示。<br>有些客户具有多种产品收藏集和多种网站行为，对于他们而言，设置较弱的网站亲和度可能会获得更好的结果。 |
| 最畅销商品 | 大多数已完成的订单中都包含的项目。同一项目在一个订单中购买多件会被计为一次订购。 |
| 查看次数最多 | 最常查看的项目或媒体。 |
| 最近查看的项目/媒体 | 访客最近查看过的项目。使用此标准时，您应该更新 Target 设计，以便处理因先前查看的项目不足而显示空白推荐的情况。 |
| 基于用户的推荐 | 根据每个访客的浏览、查看和购买历史记录推荐项目。 这些项目通常称为“推荐给您”。<br>通过此标准，您可以向新访客和回头客提供个性化的内容和体验。 推荐列表会根据访客的最新活动进行加权，并会在会话中更新，并随着用户浏览您的网站而变得更加个性化。<br>视图和购买均用于确定推荐的项目。 指定的推荐密钥（例如，当前项目）用于应用您选择的任何包含规则筛选器。 例如，您可以：<ul><li>排除不符合特定标准的项目（产品无库存、30天前发布的文章、评级为R的电影等）</li><li>将包含的项目限制为单个类别或当前类别</li></ul> |

>[!NOTE] {class="- topic/note "}
>
>如果您在推荐运行时更改其标准，则会丢失报表数据。

您还可以使用有关访客的其他已知信息来增强您的推荐。

所有为期一天的标准每天运行两次。所有为期一周或更长时间的标准每天运行一次。“网站亲和度”标准每天运行一次。备用标准每天运行两次。

## 查看标准信息 {#section_7162DE58E4594FD688A4D7FDB829FD8B}

您可以通过将鼠标悬停在标准卡片上并单击“信息”图标，在弹出卡片中查看标准详细信息，而无需打开该标准。

![“标准卡片”悬停信息](/help/c-recommendations/c-algorithms/assets/criteria_hover.png)

单击&#x200B;**[!UICONTROL 算法信息]**&#x200B;选项卡可查看有关所选标准的常规信息，包括其名称、描述、垂直行业、页面类型、推荐键、推荐逻辑和算法 ID。

![“算法信息”选项卡](/help/c-recommendations/c-algorithms/assets/criteria_info.png)

单击&#x200B;**[!UICONTROL 算法使用情况]选项卡可查看引用所选标准的活动列表。**&#x200B;该卡片列出了活跃和不活跃的活动。单击“实时活动”或“不活跃的活动”下拉列表可查看引用该标准的整个活动列表。您可以单击活动链接以打开活动进行编辑。

![“标准使用情况”选项卡](/help/c-recommendations/c-algorithms/assets/criteria_usage.png)

## 确定已准备好显示标准结果的时间 {#section_03F328C07F234692B6D996DF745584B3}

在活动图中，“标准”卡片现在会指示已准备好显示结果的时间。通过了解是否已准备好显示结果，有助于您确定活动是否已准备好激活，以使其成为实时活动。通过了解是否已准备好显示结果，还有助于您了解标准是否存在任何问题。

>[!NOTE]
>
>有关加载时间的讨论，请参阅[创建标准](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE)中的“预期标准处理时间”。

下图显示了“推荐”活动的“概述”页面上的活动图。您还可以在活动创建工作流中查看该活动图，其中包含步骤 2 中的标准状态结果。

![“概述”页面上的标准状态](/help/c-recommendations/c-algorithms/assets/criteria_status.png)

状态结果包括以下内容：“结果就绪”、“结果未就绪”和“信息源失败”，如下图所示：

![](assets/criteria_status_multi.png)

