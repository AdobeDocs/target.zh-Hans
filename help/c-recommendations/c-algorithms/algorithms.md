---
keywords: recommendations;recommendations activity;criteria;algorithm;recommendation key;custom key;industry vertical;retail;eccommerce;lead generation;b2b;financial services;media;publishing
description: Adobe Target的标准是根据一组预定的访客行为确定推荐哪些产品或内容的规则。
title: Adobe TargetRecommendations标准
feature: Recommendations
translation-type: tm+mt
source-git-commit: 7b86db4b45f93a3c6169caf81c2cd52236bb5a45
workflow-type: tm+mt
source-wordcount: '1059'
ht-degree: 53%

---


# ![PREMIUM](/help/assets/premium.png) 标准 

[!DNL Adobe Target]中的标准是根据一组预定的访客行为确定推荐哪些产品或内容的规则。 标准可基于流行趋势、访客的当前与过去行为，或相似的产品和内容。您可以添加多个标准，以便对多个推荐类型进行相互测试。

以下各节将进一步说明标准键和可用于每个键的推荐逻辑。 单击链接可获取更多详细信息。

## 垂直行业 {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

在创建标准时，您可以根据推荐活动的目标选择垂直行业。

| 垂直行业 | 目标 |
|--- |--- |
| 零售/电子商务 | 转化促进完成购买 |
| 潜在客户拓展/B2B/金融服务 | 转化但不购买 |
| 媒体/出版 | 参与度 |

其他条件选项会根据您选择的行业垂直而发生更改。 您可以在&#x200B;**[!UICONTROL Recommendations>设置]**&#x200B;页面上设置默认的行业垂直，也可以为每个条件指定行业垂直。

## 建议项{#section_885B3BB1B43048A88A8926F6B76FC482}

您选择的推荐键决定了标准类型。标准类型具有以下几种（在设置 [!DNL Recommendations] 活动时，这些标准类型会显示为相应的标准卡片）。

![“标准”页](/help/c-recommendations/c-algorithms/assets/criteria-page.png)

下表说明了各种标准类型及其附带的键。 单击链接可获取有关每个键的更多详细信息。

| 标准类型 | 键 |
|--- |--- |
| 当前页面活动 | 根据用户在当前页面上执行的操作来推荐项目。例如，查看了某个特定商品的访客可能希望查看同一类别的其他商品。<ul><li>[当前项目](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#current-item)</li><li>[当前类别 ](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#current-category)</li></ul> |
| 自定义 | 根据自定义属性推荐项目。<ul><li>[自定义属性](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#custom)</li></ul>如果要根据自定义属性来进行推荐，则必须选择自定义属性，然后再选择推荐类型。 |
| 过去的行为 | 根据访客过去对某个项目所做的回应来推荐项目。例如，以前购买过某个特定品牌的客户更有可能会购买属于该品牌的其他项目。<ul><li>[上次购买的项目](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#last-purchased)</li><li>[上次查看的项目](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#last-viewed)</li><li>[查看次数最多的项目](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#most-viewed-logic)</li><li>[最喜爱类别](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#favorite-category)</li></ul> |
| 人气 | 推荐最受欢迎的项目，例如相关类别中最热门的视频或网站上最常查看的产品。<ul><li>[热门程度](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#popularity)</li></ul> |
| [最近查看的项目](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#recently-viewed) | 推荐访客最近查看过的项目，例如访客上次访问您的网站时查看过的项目，或者目前趋势最为强劲的文章。 |

## 使用自定义推荐键{#custom-key}

您还可以根据自定义用户档案属性的值创建推荐。

>[!NOTE]
>
>自定义用户档案参数可以通过JavaScript、API或集成传递到目标。 有关自定义用户档案属性的详细信息，请参阅[访客用户档案](/help/c-target/c-visitor-profile/visitor-profile.md)。

例如，假定您要根据用户最近添加到队列的电影来显示推荐的电影。

1. 从[!UICONTROL 推荐键]下拉用户档案中选择您的自定义列表属性（例如，[!UICONTROL 添加到观察列表的上次显示]）。

1. 选择您的[!UICONTROL 推荐逻辑]（例如，[!UICONTROL 查看此内容的人员，查看该]）。

   ![“创建新条件”对话框](/help/c-recommendations/c-algorithms/assets/custom-key1.png)

如果您的自定义用户档案属性与单个实体ID不直接匹配，则有必要向[!DNL Recommendations]说明您希望如何与实体匹配。

例如，假定您要显示来自用户喜爱品牌的畅销商品。

1. 从[!UICONTROL 推荐键]下拉用户档案中选择您的自定义列表属性（例如，[!UICONTROL 收藏品牌]）。

1. 选择要与此键一起使用的[!UICONTROL 推荐逻辑]（例如，[!UICONTROL 热门卖家]）。

   此时会显示[!UICONTROL 按以下项的唯一值分组]选项。

1. 选择与您所选的键匹配的实体属性。在这种情况下，[!UICONTROL 收藏品牌]与`entity.brand`匹配。

   [!DNL Recommendations] 现在为每个品牌生成“最畅销商品”列表，并根据“最喜爱品牌”配置文件属性中存储的值向用户显示相应的“最畅销 [!UICONTROL 商] 品”列表。

   ![Top Sellers attribute](/help/c-recommendations/c-algorithms/assets/custom-key2.png)

## 标准／算法{#criteria-algorithms}

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

## 查看条件信息{#section_7162DE58E4594FD688A4D7FDB829FD8B}

您可以通过将鼠标悬停在标准卡片上并单击“信息”图标，在弹出卡片中查看标准详细信息，而无需打开该标准。

![“标准卡片”悬停信息](/help/c-recommendations/c-algorithms/assets/criteria_hover.png)

单击&#x200B;**[!UICONTROL 算法信息]**&#x200B;选项卡可查看有关所选标准的常规信息，包括其名称、描述、垂直行业、页面类型、推荐键、推荐逻辑和算法 ID。

![“算法信息”选项卡](/help/c-recommendations/c-algorithms/assets/criteria_info.png)

单击&#x200B;**[!UICONTROL 算法使用情况]**&#x200B;选项卡可查看引用所选标准的活动列表。卡列表处于活动状态、非活动状态和草稿活动。 单击“实时活动/非活动活动/拟定活动”下拉列表卡，视图引用该标准的整个活动列表。 您可以单击活动链接以打开活动进行编辑。

![“算法使用”选项卡](/help/c-recommendations/c-algorithms/assets/criteria_usage.png)

>[!NOTE]
>
>[!UICONTROL 算法使用]功能当前仅支持Recommendations活动。 A/B测试、自动分配、自动目标和体验定位(XT)活动当前不支持此功能，这些将[推荐作为优惠](/help/c-recommendations/recommendations-as-an-offer.md)。
