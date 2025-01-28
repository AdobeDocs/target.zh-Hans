---
keywords: 推荐；推荐活动；标准；算法；推荐键；自定义键；垂直行业；零售；eccommerce；商机生成；b2b；金融服务；媒体；发布
description: 了解如何在Adobe [!DNL Target] [!DNL Recommendations]中使用标准。
title: 如何在 [!DNL Target] Recommendations中使用标准？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
hide: true
hidefromtoc: true
exl-id: 7809984d-259d-4b99-93cd-3073e2fcf8bb
source-git-commit: b7c7e8d85f7f39024ed5e57177e5c9f628460e9c
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 5%

---

# [!UICONTROL Criteria]

[!DNL Adobe Target] [!DNL Recommendations]中的[!UICONTROL Criteria]是一些规则，可根据预先确定的一组访客行为来确定要推荐的产品或内容。 标准可以基于流行趋势、访客当前和过去的行为或类似产品和内容。 您可以添加多个标准，以便对多个推荐类型进行相互测试。

以下部分将详细解释有关标准键以及可用于每个键的推荐逻辑的信息。 单击链接可了解更多详细信息。

## 垂直行业 {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

在创建标准时，您可以根据推荐活动的目标选择垂直行业。

| 垂直行业 | 目标 |
|--- |--- |
| [!UICONTROL Retail/Ecommerce] | 转化促进完成购买 |
| [!UICONTROL Lead Generation/B2B/Financial Services] | 转化但不购买 |
| [!UICONTROL Media/Publishing] | 参与度 |

根据您选择的垂直行业，其他标准选项会发生变化。 您可以在&#x200B;**[!UICONTROL Administration]>[!UICONTROL Recommendations]**&#x200B;页面上设置默认垂直行业，也可以为每个标准指定垂直行业。

## 算法类型 {#section_885B3BB1B43048A88A8926F6B76FC482}

您选择的算法类型决定了可用的算法。

下表说明了各种算法类型及其随附的算法。

| 算法类型 | 使用时间 | 可用的算法 |
| --- | --- | --- |
| [!UICONTROL Cart-Based] | 根据用户的购物车内容提供推荐。 | <ul><li>[!UICONTROL People Who Viewed These, Also Viewed]</li><li>[!UICONTROL People Who Viewed These, Also Bought]</li><li>[!UICONTROL People Who Bought These, Also Bought]</li></ul>有关详细信息，请参阅&#x200B;*使推荐基于推荐键*&#x200B;中的[基于购物车的](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#cart-based)。 |
| [!UICONTROL Popularity-Based] | 根据项目在整个网站中的整体受欢迎程度或用户最喜爱或查看次数最多的类别、品牌、流派等中的项目受欢迎程度提供推荐。 | <ul><li>[!UICONTROL Most Viewed Across the Site]</li><li>[!UICONTROL Most Viewed by Category]</li><li>[!UICONTROL Most Viewed by Item Attribute]</li><li>[!UICONTROL Top Sellers Across the Site]</li><li>[!UICONTROL Top Sellers by Category]</li><li>[!UICONTROL Top Sellers by Item Attribute]</li><li>[!UICONTROL Top by Analytics Metric]</li></ul> |
| [!UICONTROL Item-Based] | 根据查找的用户当前正在查看或最近查看过的项目的相似项目提供推荐。 | <ul><li>[!UICONTROL People Who Viewed This, Viewed That]</li><li>[!UICONTROL People Who Viewed This, Bought That]</li><li>[!UICONTROL People Who Bought This, Bought That]</li><li>[!UICONTROL Items with Similar Attributes]</li></ul> |
| [!UICONTROL User-Based] | 根据用户的行为提供推荐。 | <ul><li>[!UICONTROL Recently Viewed Items]</li><li>[!UICONTROL Recommended for You]</li></ul> |
| [!UICONTROL Custom Criteria] | 根据您上传的自定义文件提出推荐。 | <ul><li>自定义算法</li></ul> |

有关每个算法的详细信息，请参阅[使推荐基于推荐键](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md)。

## 使用自定义推荐键 {#custom-key}

您还可以使推荐基于自定义配置文件属性的值。

>[!NOTE]
>
>可通过JavaScript、API或集成将自定义配置文件参数传递到[!DNL Target]。 有关自定义配置文件属性的详细信息，请参阅[访客配置文件](/help/main/c-target/c-visitor-profile/visitor-profile.md)。

例如，假设您要根据用户最近添加到队列中的影片显示推荐的影片。

1. 单击&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**。

1. 单击&#x200B;**[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**。

1. 在[基本信息部分](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info)中填写信息。

1. 在[推荐的算法](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#rec-algo)部分中，从&#x200B;**[!UICONTROL Algorithm Type]**&#x200B;列表中选择&#x200B;**[!UICONTROL Item Based]**。

1. 从&#x200B;**[!UICONTROL Algorithm]**&#x200B;列表中选择&#x200B;**[!UICONTROL People Who Viewed This, Viewed That]**。

1. 从&#x200B;**[!UICONTROL Recommendation Key]**&#x200B;列表中选择自定义配置文件属性（例如，[!UICONTROL Last Show Added to Watchlist]）。

## 查看标准信息 {#section_7162DE58E4594FD688A4D7FDB829FD8B}

您可以通过单击[!UICONTROL Name]列中的所需条件来查看条件详细信息。

通过&#x200B;**[!UICONTROL Attributes]**&#x200B;和详细信息部分，可查看有关所选标准的一般信息，包括其[!UICONTROL Name]、[!UICONTROL Description]、[!UICONTROL Industry Vertical]、[!UICONTROL Page Types]、[!UICONTROL Recommendation Key]、[!UICONTROL Recommendation Logic]、[!UICONTROL Algorithm ID]以及上次修改时间信息（日期和修改算法的人员）。

**[!UICONTROL Usage]**&#x200B;部分允许您查看引用所选标准的活动列表。

>[!NOTE]
>
>当前仅支持[!DNL Recommendations]活动的[!UICONTROL Algorithm Usage]功能。 包含[个推荐作为选件](/help/main/c-recommendations/recommendations-as-an-offer.md)的[!UICONTROL A/B Test]、[!UICONTROL Auto-Allocate]、[!UICONTROL Auto-Target]和[!UICONTROL Experience Targeting] (XT)活动当前不支持此功能。
