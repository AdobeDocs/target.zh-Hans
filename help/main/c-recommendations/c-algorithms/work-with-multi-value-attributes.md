---
keywords: 多值；属性；推荐；多值；多值；多值
description: 了解如何使用特殊的多值运算符在 [!DNL Target Recommendations] 中使用多值字段。
title: 我能否在Recommendations中使用多值属性？
feature: Recommendations
exl-id: 82018a9a-0983-458c-9387-3602dab4409b
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 9%

---

# 使用多值属性

有时，您可能需要使用多值字段。 请仔细研究下面的示例：

* 您向用户提供电影。给定的电影有多个演员。
* 您出售音乐会门票。给定的用户有多个喜欢的乐队。
* 您出售服装。某款衬衫有多种尺寸可供选择。

若要处理这些方案中的推荐，可将多值数据传递给[!DNL Target Recommendations]并使用特殊的多值运算符。

为了允许[!DNL Recommendations]识别多值数据，应将其作为JSON数组发送，如以下代码示例所示。

## 在JavaScript中传递多值参数

```
function targetPageParams() { 
  return { 
    'entity.id':                   '123', 
    'entity.categoryId':            '["A", "A:B", "A:B:C", "A:B:C:D"]',        
    'entity.MultiValueAttribute':   '["X", "Y", "Z"]', 
    'entity.event.detailsOnly':     'true', 
    'excludedIds":                  '[123, 3232, 2323, 4344]', 
    'orderId":                      '123456', 
    'orderTotal":                   '195.32', 
    'productPurchaseId":            '[001,002,003]' 
  }; 
}
```

有关详细信息，请参阅&#x200B;*自定义实体属性*&#x200B;中的[实现多值属性](/help/main/c-recommendations/c-products/custom-entity-attributes.md#section_80FEFE49E8AF415D99B739AA3CBA2A14)。

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

根据上述格式以多值形式提供实体属性、配置文件属性或mbox参数时，[!DNL Recommendations]会自动推断字段是多值。

以下运算符可用于多值实体、配置文件和mbox属性：

* [!UICONTROL is contained in list]
* [!UICONTROL is not contained in list]

## 在包含规则中使用多值属性

>[!NOTE]
>
>目前，仅当使用配置文件属性匹配或参数(mbox)属性匹配规则（将左侧的单个值与右侧的多个值进行比较）时，才会在标准中支持与多值属性的动态匹配。 促销、实体属性匹配或包含规则左侧的列表当前不支持多值属性。

### 示例：排除最近观看的项目

假设您要阻止推荐用户最近十次观看的电影中的任何电影。 首先，编写名为`user.lastWatchedMovies`的配置文件脚本，以JSON数组形式跟踪最近查看过的10部电影。 然后，您可以使用以下包含规则排除这些项目：

```
`Profile Attribute Matching`
`id - is not contained in list - user.lastWatchedMovies`
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

假设您只想向演唱会推荐门票（如果正在播放的乐队是用户最喜爱的乐队之一）。 首先，确保您有一个名为`profile.favoriteBands`的配置文件变量，该变量包含用户最喜爱的乐队。 然后，请确保您的目录包含属性`entity.artistPerforming`，该属性包含音乐会中表演的艺人。 然后，您可以使用以下包含规则：

```
`Profile Attribute Matching`
`artistPerforming - is contained in list - profile.favoriteBands`
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

使用多值过滤规则的标准（如所有标准）可以通过[!DNL Adobe Target] API创建。 此处提供了用于创建条件的示例API调用，其中mbox参数列表`favorites`中包含实体属性`id`：

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

此操作将与页面上的JavaScript配对，以传入收藏夹内容：

```
<!-- pass in the value of mbox parameter "favorites" as JSON array -->
<script type="text/javascript">
   mboxCreate('myMbox','entity.id=<key>','favorites=["a","b","c"]');
</script>
```
