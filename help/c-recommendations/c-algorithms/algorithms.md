---
keywords: 推荐；推荐活动；标准；算法；推荐键；自定义键；垂直行业；零售；电子商务；商机拓展；b2b；金融服务；媒体；发布
description: 了解如何在Adobe [!DNL Target] [!DNL Recommendations]中使用标准。
title: 如何在 [!DNL Target] Recommendations中使用标准？
feature: Recommendations
exl-id: a6e4c857-f991-4293-9d33-8d7c2ca5dade
source-git-commit: 7a52f7c046fb00672ef1b13704308be39f89c7ad
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 24%

---

# ![PREMIUM](/help/assets/premium.png) 标准 

[!DNL Adobe Target] [!DNL Recommendations]中的标准是规则，可根据预先确定的一组访客行为来确定要推荐的产品或内容。 标准可基于流行趋势、访客的当前与过去行为，或相似的产品和内容。您可以添加多个标准，以便对多个推荐类型进行相互测试。

以下部分将进一步说明标准键以及可用于每个键的推荐逻辑。 单击链接以了解更多详细信息。

## 垂直行业 {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

在创建标准时，您可以根据推荐活动的目标选择垂直行业。

| 垂直行业 | 目标 |
|--- |--- |
| 零售/电子商务 | 转化促进完成购买 |
| 潜在客户拓展/B2B/金融服务 | 转化但不购买 |
| 媒体/出版 | 参与度 |

其他标准选项会根据您选择的垂直行业而发生更改。 您可以在&#x200B;**[!UICONTROL Recommendations >设置]**&#x200B;页面上设置默认垂直行业，也可以为每个标准指定垂直行业。

## 算法类型 {#section_885B3BB1B43048A88A8926F6B76FC482}

您选择的算法类型确定可用的算法。 算法类型有多种，在设置[!DNL Recommendations]活动时，这些算法类型会显示为标准卡片。

![标准页面](assets/criteria-page.png)

下表说明了各种算法类型及其随附的算法。

| 算法类型 | 何时使用 | 可用算法 |
| --- | --- | --- |
| [!UICONTROL 基于热门程度] | 根据网站上某个项目的整体受欢迎程度或用户最喜爱或最常查看的类别、品牌、流派等项目的受欢迎程度，提出推荐。 | <ul><li>整个网站查看次数最多</li><li>按类别查看次数最多</li><li>按项目属性查看次数最多</li><li>网站最畅销商品</li><li>按类别划分的最畅销商品</li><li>按物料属性列出的最畅销商品</li><li>按Analytics量度排名最前</li></ul> |
| [!UICONTROL 基于项目] | 根据查找与用户当前正在查看或最近已查看的项目类似的项目来提供推荐。 | <ul><li>查看了这个项目，也查看了那个项目的人</li><li>查看了这个项目，但购买了那个项目的人</li><li>购买了这个项目，也购买了那个项目的人</li><li>具有相似属性的项目</li></ul> |
| [!UICONTROL 基于用户] | 根据用户的行为进行推荐。 | <ul><li>最近查看的项目</li><li>为您推荐</li></ul> |
| 基于购物车 | （即将推出）根据用户的购物车内容进行推荐。 | <ul><li>查看了这些项目，也查看了这些项目的人</li><li>查看了这些项目，购买了这些项目的人</li><li>购买了这些，也购买了那些的人</li></ul> |
| [!UICONTROL 自定义标准] | 根据您上传的自定义文件进行推荐。 | <ul><li>自定义算法</li></ul> |

有关每个算法的更多信息，请参阅[使推荐基于推荐键](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md)。

## 使用自定义推荐键 {#custom-key}

您还可以根据自定义配置文件属性的值来推荐。

>[!NOTE]
>
>自定义配置文件参数可以通过JavaScript、API或集成传递到[!DNL Target]。 有关自定义配置文件属性的更多信息，请参阅[访客配置文件](/help/c-target/c-visitor-profile/visitor-profile.md)。

例如，假定您要根据用户最近添加到队列的影片显示推荐的影片。

1. 单击&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL 标准]**。

1. 单击&#x200B;**[!UICONTROL 创建标准]** > **[!UICONTROL 创建标准]**。

1. 填写[基本信息部分](/help/c-recommendations/c-algorithms/create-new-algorithm.md#info)中的信息。

1. 在[推荐的算法](/help/c-recommendations/c-algorithms/create-new-algorithm.md#rec-algo)部分中，从&#x200B;**[!UICONTROL 算法类型]**&#x200B;列表中选择&#x200B;**[!UICONTROL 基于项目]**。

1. 从&#x200B;**[!UICONTROL 算法]**&#x200B;列表中选择&#x200B;**[!UICONTROL 查看了此项，并查看了该]**&#x200B;的人员。

1. 从&#x200B;**[!UICONTROL 推荐键]**&#x200B;列表中选择自定义配置文件属性（例如，[!UICONTROL 最近添加到观看列表的节目]）。

   ![“创建新标准”对话框](assets/custom-key1.png)

## 查看标准信息 {#section_7162DE58E4594FD688A4D7FDB829FD8B}

您可以通过将鼠标悬停在标准卡片上并单击“信息”图标，在弹出卡片中查看标准详细信息，而无需打开该标准。

![“标准卡片”悬停信息](/help/c-recommendations/c-algorithms/assets/criteria_hover.png)

单击&#x200B;**[!UICONTROL 算法信息]**&#x200B;选项卡可查看有关所选标准的常规信息，包括其名称、描述、垂直行业、页面类型、推荐键、推荐逻辑和算法 ID。

![“算法信息”选项卡](/help/c-recommendations/c-algorithms/assets/criteria_info.png)

单击&#x200B;**[!UICONTROL 算法使用情况]**&#x200B;选项卡可查看引用所选标准的活动列表。卡片中列出了活动、不活动和草稿活动。 单击实时活动/不活动活动/草稿活动下拉列表，以查看引用该标准的活动的整个列表。 您可以单击活动链接以打开活动进行编辑。

![“算法使用情况”选项卡](/help/c-recommendations/c-algorithms/assets/criteria_usage.png)

>[!NOTE]
>
>[!UICONTROL 算法使用]功能当前仅支持Recommendations活动。 当前，A/B测试、自动分配、自动定位和体验定位(XT)活动不支持此功能，这些活动包含[推荐作为选件](/help/c-recommendations/recommendations-as-an-offer.md)。
