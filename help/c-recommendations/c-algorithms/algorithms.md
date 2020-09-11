---
keywords: recommendations;recommendations activity;criteria;algorithm;recommendation key;custom key;industry vertical;retail;eccommerce;lead generation;b2b;financial services;media;publishing
description: Adobe TargetRecommendations的标准是根据一组预定的访客行为确定推荐哪些产品的规则。
title: Adobe TargetRecommendations标准
feature: criteria
uuid: 738db164-174b-45b8-bb8a-778f6494f1d7
translation-type: tm+mt
source-git-commit: 55f0791bb68fc98e319fa70a647e5168ac72ae1e
workflow-type: tm+mt
source-wordcount: '1135'
ht-degree: 68%

---


# ![PREMIUM](/help/assets/premium.png) 标准 

标准即规则，可根据预先确定的一组访客行为来确定要推荐的产品。

标准可确定哪项操作将导致推荐哪个项目。您可以添加多个标准，以便对多个推荐类型进行相互测试。

## 垂直行业 {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

根据推荐活动的目标选择行业垂直。 根据您选择的垂直行业，

| 垂直行业 | 目标 |
|--- |--- |
| 零售/电子商务 | 转化促进完成购买 |
| 潜在客户拓展/B2B/金融服务 | 转化但不购买 |
| 媒体/出版 | 参与度 |

## Recommendation key {#section_885B3BB1B43048A88A8926F6B76FC482}

您选择的推荐键决定了标准类型。标准类型具有以下几种（在设置 [!DNL Recommendations] 活动时，这些标准类型会显示为相应的标准卡片）。

| 标准类型 | 键 |
|--- |--- |
| 当前页面活动 | 根据用户在当前页面上执行的操作来推荐项目。例如，查看了某个特定商品的访客可能希望查看同一类别的其他商品。<ul><li>[当前项目](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#current-item)</li><li>[当前类别 ](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#current-category)</li></ul> |
| 自定义 | 根据自定义属性推荐项目。<ul><li>[自定义属性](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#custom)</li></ul>如果要根据自定义属性来进行推荐，则必须选择自定义属性，然后再选择推荐类型。 |
| 过去的行为 | 根据访客过去对某个项目所做的回应来推荐项目。例如，以前购买过某个特定品牌的客户更有可能会购买属于该品牌的其他项目。<ul><li>[上次购买的项目](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#last-purchased)</li><li>[上次查看的项目](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#last-viewed)</li><li>[查看次数最多的项目](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#most-viewed-logic)</li><li>[最喜爱类别](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#favorite-category)</li></ul> |
| 人气 | 推荐最受欢迎的项目，例如相关类别中最热门的视频或网站上最常查看的产品。<ul><li>[热门程度](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#popularity)</li></ul> |
| 最近查看的项目 | 推荐访客最近查看过的项目，例如访客上次访问您的网站时所查看的项目，或访客当前最倾向于查看的商品。<br>“最近查看的项目”算法会返回特定于某个[环境](/help/administrating-target/hosts.md)中的访客活动。如果两个网站属于不同的环境，并且访客在两个网站之间切换访问，则算法将仅返回相应网站的最近查看的项目。<br>此标准类型不受收藏集限制。<ul><li>[最近查看的项目](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#recently-viewed)</li></ul>**注意：**&#x200B;您无法在备用推荐中使用“最近查看的项目”标准。<br>可以筛选最近查看的项目/媒体，以便仅显示具有特定属性的项目。<ul><li>与推荐中的其他标准一样，“最近查看的项目”标准也可配置。</li><li>您可以使用[收藏集](/help/c-recommendations/c-products/collections.md)、[排除项](/help/c-recommendations/c-products/exclusions.md)和[包含项](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)（包括针对价格和库存的特殊规则），其使用方法与任何其他标准相同。</li></ul>用例可能包括：<ul><li>一家开展多种业务的跨国公司可能会让访客在多个数字财产中查看项目。在这种情况下，您可以限制最近查看的项目，以便仅显示之前查看的相应财产中的项目。执行此操作可防止最近查看的项目在其他数字财产网站上显示。</li></ul> |

## 使用自定义推荐密钥 {#custom-key}

您还可以根据自定义用户档案属性的值创建推荐。

>[!NOTE]
>
>自定义用户档案参数可以通过JavaScript、API或集成传递到目标。 有关自定义用户档案属性的详细信息，请参阅 [访客用户档案](/help/c-target/c-visitor-profile/visitor-profile.md)。

例如，假定您要根据用户最近添加到队列的电影来显示推荐的电影。

1. Select your custom profile attribute from the [!UICONTROL Recommendation Key] drop-down list (for example, [!UICONTROL Last Show Added to Watchlist]).

1. Select your [!UICONTROL Recommendation Logic] (for example, [!UICONTROL People Who Viewed This, Viewed That]).

   ![“创建新条件”对话框](/help/c-recommendations/c-algorithms/assets/custom-key1.png)

If your custom profile attribute does not directly match to a single entity ID, it is necessary to explain to [!DNL Recommendations] how you want the match to an entity to occur.

例如，假定您要显示来自用户喜爱品牌的畅销商品。

1. Select your custom profile attribute from the [!UICONTROL Recommendation Key] drop-down list (for example, [!UICONTROL Favorite Brand]).

1. Select the [!UICONTROL Recommendation Logic] you want to use with this key (for example, [!UICONTROL Top Sellers]).

   此时会显示[!UICONTROL 按以下项的唯一值分组]选项。

1. 选择与您所选的键匹配的实体属性。In this case [!UICONTROL Favorite Brand] matches to `entity.brand`.

   [!DNL Recommendations] 现在为每个品牌生成一个“最畅销者”列表，并根据“最喜爱品牌”列表属性中存储的值向用户显示相应的“最 [!UICONTROL 畅销] ”用户档案。

   ![Top Sellers attribute](/help/c-recommendations/c-algorithms/assets/custom-key2.png)

## Criteria/algorithms {#criteria-algorithms}

[!DNL Target Recommendations] 会使用复杂的算法来确定访客操作在何种情况下才符合活动中设置的标准。推荐键决定了可用的推荐逻辑选项。

| 标准 | 描述 |
|--- |--- |
| [具有相似属性的项目/媒体](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#similar-attributes) | 根据当前页面活动或以往的访客行为来推荐类似的项目或媒体。 |
| [查看了这个项目，也查看了那个项目的人](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#viewed-viewed) | 推荐在查看了指定项目的同一会话中最常查看的项目。 |
| [查看了这个项目，但购买了那个项目的人](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#viewed-bought) | 推荐在查看了指定项目的同一会话中最常购买的项目。 |
| [购买了这个项目，也购买了那个项目的人](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#bought-bought) | 推荐客户在购买指定项目的同时最常购买的其他项目。 |
| [网站亲和度](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#site-affinity) | 根据项目间关系的确定性来推荐项目。 |
| [最畅销商品](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#top-sellers) | 大多数已完成的订单中都包含的项目。同一项目在一个订单中购买多件会被计为一次订购。 |
| [查看次数最多](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#most-viewed) | 最常查看的项目或媒体。 |
| [基于用户的Recommendations](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#user-based) | 根据每个访客的浏览、查看和购买历史记录推荐项目。 这些项目通常称为“推荐给您”。 |

>[!NOTE]
>
>如果您在推荐运行时更改其标准，则会丢失报表数据。

您还可以使用有关访客的其他已知信息来增强您的推荐。

所有为期一天的标准每天运行两次。所有为期一周或更长时间的标准每天运行一次。“网站亲和度”标准每天运行一次。备用标准每天运行两次。

## Viewing criteria information {#section_7162DE58E4594FD688A4D7FDB829FD8B}

您可以通过将鼠标悬停在标准卡片上并单击“信息”图标，在弹出卡片中查看标准详细信息，而无需打开该标准。

![“标准卡片”悬停信息](/help/c-recommendations/c-algorithms/assets/criteria_hover.png)

单击&#x200B;**[!UICONTROL 算法信息]**&#x200B;选项卡可查看有关所选标准的常规信息，包括其名称、描述、垂直行业、页面类型、推荐键、推荐逻辑和算法 ID。

![“算法信息”选项卡](/help/c-recommendations/c-algorithms/assets/criteria_info.png)

单击&#x200B;**[!UICONTROL 算法使用情况]**&#x200B;选项卡可查看引用所选标准的活动列表。卡列表处于活动状态、非活动状态和草稿活动。 单击“实时活动/非活动活动/拟定活动”下拉列表卡，视图引用该标准的整个活动列表。 您可以单击活动链接以打开活动进行编辑。

![“算法使用”选项卡](/help/c-recommendations/c-algorithms/assets/criteria_usage.png)

>[!NOTE]
>
>目前 [!UICONTROL 仅Recommendations活动] 支持算法使用功能。 A/B测试、自动分配、自动目标和体验定位(XT)活动当前不支持此功能，这些包含 [作为优惠的建议](/help/c-recommendations/recommendations-as-an-offer.md)。
