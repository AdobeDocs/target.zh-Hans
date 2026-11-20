---
keywords: 产品;收藏集
description: 了解Adobe [!DNL Target]推荐中的实体。 实体是指您要使用[!DNL Target]推荐的项目，例如文章、电影或产品。
title: 如何使用实体？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: ffe23eea-b914-4c86-ad54-c63c1cc1c0d7
TQID: 'https://experienceleague.adobe.com/zfISb59XJ5qrD1-FA0syglPPswIL8cA0N0pBpY4tgIE'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 5ed511322cc9f04c349471f8ad84a17526d4925f
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 1%
---
# 实体入门 {#get-started-entities}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解[!DNL Adobe Target Recommendations]中的实体以及在何处管理这些实体。

>[!ENDSHADEBOX]

实体是[!DNL Recommendations]可以推荐的项目。 实体可以是产品、内容（例如文章、幻灯片、图像、电影或电视节目）、工作列表、餐厅等。

[!DNL Recommendations]根据您设置的条件显示收藏集中的项目。

## 实体如何实现推荐

可以通过多种方式将有关您的实体的信息传递到[!DNL Recommendations]，包括：

* 使用mbox或`targetPageParams`从您的页面发送的[实体属性](/help/main/c-recommendations/c-products/entity-attributes.md)。
* 带有可以使用CSV文件、[!DNL Google Product Search]源格式或[!DNL Adobe Analytics]产品分类的[源](/help/main/c-recommendations/c-products/feeds.md)。
* 使用投放API。

如果[!DNL Target]同时从信息源和mbox中收集某个项目的数据，则使用最新数据。

上传的实体和实体属性值会在61天后过期。 至少每60天再次发送每个项目一次。 否则，[!DNL Target]会认为该项不再相关，并将其从目录中删除。

## 管理您的实体

使用以下页面可处理您的实体：

* [实体属性](/help/main/c-recommendations/c-products/entity-attributes.md)和[自定义实体属性](/help/main/c-recommendations/c-products/custom-entity-attributes.md)：定义传递给[!DNL Recommendations]的产品或内容信息。
* [信息源](/help/main/c-recommendations/c-products/feeds.md)：将实体或内容信息获取到您的推荐中。
* [目录搜索](/help/main/c-recommendations/c-products/catalog-search.md)：在您的目录中查找项目。
* [收藏集](/help/main/c-recommendations/c-products/collections.md)：设置您的收藏集。 创建[!DNL Recommendations]活动时，将为每个体验选择一个集合。
* [排除项](/help/main/c-recommendations/c-products/exclusions.md)：阻止某些项目显示在推荐中。 排除项适用于帐户中的所有活动。
