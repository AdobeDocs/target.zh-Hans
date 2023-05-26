---
keywords: 多值；属性；推荐；多值；多值
description: 了解如何在Adobe中使用多值字段 [!DNL Target] Recommendations使用特殊的多值运算符，例如，推荐具有多个演员的影片时。
title: 我能否在Recommendations中使用多值属性？
feature: Recommendations
exl-id: 82018a9a-0983-458c-9387-3602dab4409b
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 8%

---

# 使用多值属性

有时，您可能希望使用多值字段。 请仔细研究下面的示例：

* 您向用户提供电影。给定的电影有多个演员。
* 您出售音乐会门票。给定的用户有多个喜欢的乐队。
* 您出售服装。某款衬衫有多种尺寸可供选择。

要处理这些场景中的推荐，可将多值数据传递到 [!DNL Target Recommendations] 并使用特殊的多值运算符。

允许 [!DNL Recommendations] 要识别多值数据，应以JSON数组的形式发送它，如以下代码示例所示。

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

有关更多信息，请参阅 [实施多值属性](/help/main/c-recommendations/c-products/custom-entity-attributes.md#section_80FEFE49E8AF415D99B739AA3CBA2A14) 在 *自定义实体属性*.

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

当按照上述格式以多值形式提供实体属性、配置文件属性或mbox参数时， [!DNL Recommendations] 自动推断字段为多值。

以下运算符可用于多值实体、配置文件和mbox属性：

* [!UICONTROL 包含在列表中]
* [!UICONTROL 不包含在列表中]

## 在包含规则中使用多值属性

>[!NOTE]
>
>当前，仅当使用配置文件属性匹配或参数(mbox)属性匹配规则比较左侧的单个值和多值右侧时，才支持与多值属性的动态匹配。 促销、实体属性匹配或包含规则左侧的列表当前不支持多值属性。

### 示例：排除最近观看的项目

假定您想要阻止推荐用户最近十次观看的电影中的任何电影。 首先，编写一个名为的配置文件脚本 `user.lastWatchedMovies` 以JSON数组形式跟踪最近查看的十部电影。 然后，您可以使用以下包含规则排除这些项目：

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

假设您只想在演唱会中推荐门票（如果正在播放的乐队是用户最喜爱的乐队之一）。 首先，确保您有一个名为的配置文件变量 `profile.favoriteBands` 包含用户最喜爱的乐队。 然后，确保您的目录中包含属性 `entity.artistPerforming` 包括演唱会里的艺人。 然后，您可以使用以下包含规则：

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

### 示例：API创建推荐用户收藏夹中项目的标准

使用多值过滤规则的标准（与所有标准一样）可以通过Adobe I/OAPI创建。 创建标准（其中实体属性）的示例API调用 `id` 包含在mbox参数列表中 `favorites` 此处提供：

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
<!-- pass in the value of mbox parameter “favorites” as JSON array -->
<script type="text/javascript">
   mboxCreate('myMbox','entity.id=<key>','favorites=["a","b","c"]');
</script>
```
