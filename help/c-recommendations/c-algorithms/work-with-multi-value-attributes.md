---
description: 有关使用特殊多值运算符在Adobe Target Recommendations中使用多值字段的信息。
keywords: 多值；属性；推荐；多值；多值
seo-description: 有关使用特殊多值运算符在Adobe Target Recommendations中使用多值字段的信息。
seo-title: 在Adobe Target Recommendations中使用多值属性
solution: Target
title: 使用多值属性
title-outputclass: premium
topic: Premium
badge: premium
translation-type: tm+mt
source-git-commit: dafe9d58efac853190a83cbde1d93d1a3e52cc0b

---


# 使用多值属性

有时，您可能希望使用多值字段。 请仔细研究下面的示例：

* 您向用户提供影片。 一部电影有多个演员。
* 你卖音乐会的票。 给定用户有多个喜爱的栏。
* 你卖衣服。 T恤有多种尺寸。

要处理这些场景中的推荐，您可以将多值数据传递给并使 [!DNL Target Recommendations] 用特殊的多值运算符。

要识 [!DNL Recommendations] 别多值数据，应将其作为JSON数组发送，如下面的代码示例所示。

## 在JavaScript中传递多值mbox参数

```
 <!-- pass in the value of mbox parameter “favName” as JSON array -->
<script type="text/javascript">
   mboxCreate('myMbox','entity.id=<key>','favName=["a","b","c"]');
</script>
```

## 在CSV文件中传递多值实体属性

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

当根据上述格式将实体属性、配置文件属性或mbox参数提供为多值时， [!DNL Recommendations] 会自动推断字段是多值。

以下运算符可用于多值实体、配置文件和mbox属性：

* [!UICONTROL 包含在列表中]
* [!UICONTROL 列表中未包含]

## 在包含规则中使用多值属性

>[!NOTE]
>
>当将单值左侧与多值右侧进行比较时，当使用配置文件属性匹配或参数(mbox)属性匹配规则时，支持动态匹配到多值属性目前仅在标准中可用。 2020年初将提供对促销、实体属性匹配和包含规则左侧列表的支持。


### 示例：排除最近监视的项目

假定您希望防止推荐用户最近十部观看的电影中的任何电影。 首先，编写一个名为的配置 `user.lastWatchedMovies` 文件脚本，将最近十个查看的电影作为JSON数组进行跟踪。 然后，您可以使用以下包含规则排除项目：

```
`Profile Attribute Matching`
`id - is not contained in list - user.lastWatchedMovies`
```

包含规则的JSON API表示：

```
{
    "attribute": "id",
    "operation": "isNotContainedInList",
    "source": {
        "name": " user.lastWatchedMovies",
        "type": "PROFILE"
    }
} 
```

### 示例：推荐用户收藏夹中的项目

假设您希望仅在演奏乐队是用户最喜爱的乐队之一时向音乐会推荐票务。 首先，确保您有一个名为的配置文件变 `profile.favoriteBands` 量，其中包含用户最喜爱的栏。 然后，确保您的目录包含一个属 `entity.artistPerforming` 性，该属性包括演唱会中表演的艺术家。 然后，您可以使用以下包含规则：

```
`Profile Attribute Matching`
`artistPerforming - is contained in list - profile.favoriteBands`
```

包含规则的JSON API表示：

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

### 示例：API创建从用户收藏夹推荐项目的标准

使用多值筛选规则的条件（与所有条件一样）可以通过Adobe I/O API创建。 此处提供了用于创建条件的示例API调用， `id` 其中mbox参数列表中包含 `favorites` 实体属性：

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

这将与页面上的JavaScript配对，以传递收藏夹内容：

```
<!-- pass in the value of mbox parameter “favorites” as JSON array -->
<script type="text/javascript">
   mboxCreate('myMbox','entity.id=<key>','favorites=["a","b","c"]');
</script>
```
