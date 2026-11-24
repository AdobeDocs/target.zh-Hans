---
keywords: 多值；属性；推荐；多值；多值；多值
description: 了解如何使用特殊的多值运算符在[!DNL Target Recommendations]中使用多值字段。
title: 使用多值属性
feature: Recommendations
exl-id: 82018a9a-0983-458c-9387-3602dab4409b
TQID: 'https://experienceleague.adobe.com/FrjVxvYfGh2o-qomXRbVh6WS6f65Mja41gBMhejEPlE'
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
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '502'
ht-degree: 2%
---
# 使用多值属性 {#multi-value-attributes}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何将多值数据发送到[!DNL Adobe Target Recommendations]，以及如何在多值运算符的包含规则中使用它。

>[!ENDSHADEBOX]

多值字段会保存同一项目或访客的多个值。 例如：

* 提供给用户的电影：给定的电影有多个演员。
* 演唱会门票已售：给定用户有多个最喜爱的乐队。
* 已售服装：衬衫有多种尺寸。

若要处理这些方案中的推荐，可以将多值数据传递给[!DNL Target Recommendations]并与特殊的多值运算符一起使用。

## 发送多值数据 {#send}

要允许[!DNL Recommendations]识别多值数据，应将其作为JSON数组发送。

有关JavaScript (`targetPageParams`)中的多值参数，请参阅&#x200B;*自定义实体属性*&#x200B;中的[实现多值属性](/help/main/c-recommendations/c-products/custom-entity-attributes.md#section_80FEFE49E8AF415D99B739AA3CBA2A14)。

在CSV文件中，多值实体属性在属性的单元格中作为JSON数组发送，如下例所示。

+++ 具有多值属性的示例CSV文件

```
## RECSRecommendations Upload File,,,,,,,,,,,,,,,,,,,
## RECS''## RECS'' indicates a Recommendations pre-process header. Please do not remove these lines.,,,,,,,,,,,,,,,,,,,
## RECS,,,,,,,,,,,,,,,,,,,
## RECSUse this file to upload product display information to Recommendations. Each product has its own row. Each line must contain 19 values and if not all are filled a space should be left.,,,,,,,,,,,,,,,,,,,
## RECSThe last 100 columns (entity.custom1 - entity.custom100) are custom. The name 'customN' can be replaced with a custom name such as 'onSale' or 'brand'.,,,,,,,,,,,,,,,,,,,
## RECSIf the products already exist in Recommendations then changes uploaded here will override the data in Recommendations. Any new attributes entered here will be added to the product''s entry in Recommendations.,,,,,,,,,,,,,,,,,,,
## RECSentity.id ,entity.name,entity. categoryId ,entity. message ,entity.thumbnailUrl ,entity.value ,entity.pageUrl ,entity.inventory ,entity.margin ,entity.custom1 ,entity.custom2 ,entity.custom3 ,entity.custom4,entity.custom5,entity.custom6,entity.custom7,entity.custom8,entity.custom9,entity.custom10,
1,Sample Product 1,category1,Save 10%,http://sample.store/products/images/product1_th.jpg,325,http://sample.store/products/product_detail.jsp?productId=1,1000,48,a,"[ ""v1"", ""v2"" ]",, , , , , , , ,
2,Sample Product 2,category1,Save 10%,http://sample.store/products/images/product2_th.jpg,369,http://sample.store/products/product_detail.jsp?productId=2,1000,52,a,"[ ""v1"", ""v2"" ]",, , , , , , , ,
3,Sample Product 3,category1,Save 10%,http://sample.store/products/images/product3_th.jpg,479,http://sample.store/products/product_detail.jsp?productId=3,1000,78,a,"[ ""v1"", ""v2"" ]",,,,,,,,,
4,Sample Product 4,category1,Save 10%,http://sample.store/products/images/product4_th.jpg,409,http://sample.store/products/product_detail.jsp?productId=4,1000,66,a,"[ ""v1"", ""v2"" ]",,,,,,,,,
5,Sample Product 5,category1,Save 10%,http://sample.store/products/images/product5_th.jpg,325,http://sample.store/products/product_detail.jsp?productId=5,1000,45,a,"[ ""v1"", ""v2"" ]",,,,,,,,, 
```

+++

当实体属性、配置文件属性或mbox参数以此格式提供为多值时，[!DNL Recommendations]会自动推断字段是多值。

## 在包含规则中使用多值属性 {#multi-value-inclusion-rules}

以下运算符可用于多值实体、配置文件和mbox属性：

* **[!UICONTROL 包含在列表]**&#x200B;中
* **[!UICONTROL 不包含在列表]**&#x200B;中

>[!NOTE]
>
>目前，仅在使用配置文件属性匹配或参数(mbox)属性匹配规则（将左侧的单个值与右侧的多个值进行比较）的标准中，才支持与多值属性的动态匹配。 促销、实体属性匹配或包含规则左侧的列表当前不支持多值属性。

### 示例：排除最近观看的项目

要阻止推荐用户最近观看的10部电影中的任何电影，请首先编写名为`user.lastWatchedMovies`的配置文件脚本，以JSON数组形式跟踪最近观看的10部电影。 然后，可以使用以下包含规则排除这些项目：

```
Profile Attribute Matching
id - is not contained in list - user.lastWatchedMovies
```

包含规则的JSON API表示形式：

```
{
    "attribute": "id",
    "operation": "isNotContainedInList",
    "source": {
        "name": "user.lastWatchedMovies",
        "type": "PROFILE"
    }
} 
```

### 示例：推荐用户收藏夹中的项目

若要仅在乐队演奏是用户最喜爱的乐队之一时才推荐音乐会门票，需要以下两项：名为`profile.favoriteBands`的配置文件变量，其中包含用户最喜爱的乐队；以及目录中的属性`entity.artistPerforming`，其中包含音乐会中演奏的歌手。 随后可以使用以下包含规则：

```
Profile Attribute Matching
artistPerforming - is contained in list - profile.favoriteBands
```

包含规则的JSON API表示形式：

```
{
    "attribute": "artistPerforming",
    "operation": "isContainedInList",
    "source": {
        "name": "profile.favoriteBands",
        "type": "PROFILE"
    }
}
```

### 示例：API创建从用户的收藏夹中推荐项目的标准

使用多值筛选规则的条件可以通过[!DNL Adobe Target] API创建，例如所有条件。 以下示例API调用创建了一个条件，其中mbox参数列表`favorites`中包含实体属性`id`：

```
curl -X POST \
  https://<serverhost>/api/recs/<client>/criteria/item \
  -H 'Accept: application/vnd.adobe.target.v1+json' \
  -H 'Accept-Encoding: gzip, deflate' \
  -H 'Cache-Control: no-cache' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: <from API client>' \
  -H 'X-Target-user-email: <email address>' \
  -H 'cache-control: no-cache' \
  -d '{
    "name": "viewed criteria",
    "criteriaTitle": "test title",
    "type": "VIEWED_CF",
    "key": "CURRENT",
    "daysCount": "TWO_WEEKS",
    "aggregation": "NONE",
    "backupDisabled": false,
    "partialDesignAllowed": true,
    "configuration": {
        "inclusionRules": [
            {
                "attribute": "id",
                "operation": "isContainedInList",
                "source": {
                    "name": "mbox.favorites",
                    "type": "MBOX"
                }
            }
        ]
    }
}'
```

此调用与传入收藏夹内容的页面上的JavaScript配对：

```
<!-- pass in the value of mbox parameter "favorites" as JSON array -->
<script type="text/javascript">
   mboxCreate('myMbox','entity.id=<key>','favorites=["a","b","c"]');
</script>
```
