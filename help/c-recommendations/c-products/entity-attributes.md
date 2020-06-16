---
keywords: entity;entity attributes;pass information to Recommendations;behavioral data;data counter;define relative URL;display inventory level;define price;define profit margin;custom attributes
description: 可使用实体属性，将产品或内容信息传递到 Recommendations。
title: 实体属性
uuid: 27672881-a79c-4271-9a61-defddb9a5249
translation-type: tm+mt
source-git-commit: 14e0c0bacb8ffb22f0156a1e2c15e4de7717ee39
workflow-type: tm+mt
source-wordcount: '1009'
ht-degree: 94%

---


# ![PREMIUM](/help/assets/premium.png) 实体属性{#entity-attributes}

可使用实体属性，将产品或内容信息传递到 Recommendations。

## 可用变量

下表说明了可用的变量。

### `entity.id`

仅支持单值。

此必填参数可识别产品。此字母数字 ID 必须在使用的所有 [!DNL Adobe Experience Cloud] 产品（包括 [!DNL Analytics]）中均相同，以便各个产品能够识别该项目并共享与其相关的数据。

`entity.id` 值不得包含斜杠、与号、问号、百分比符号、逗号或其他在 REST API 调用中传递时需要 URL 编码的标点字符。允许包含连字符和下划线。在 `entity.id` 值中包含无效标点符号会导致某些 [!DNL Recommendations] 功能失败。

示例: `'entity.id=67833'`

### `entity.name`

仅支持单值。

当推荐产品后，该产品名称将显示在网站上。

示例: `'entity.name=Giants& vs& Rockies& 5/12'`

### `entity.categoryId`

支持多值（逗号分隔列表）。

当前页面的类别。可以包括多个类别，如羊毛衫是第三级标题（例如女士、女士：毛衫、女士：毛衫：羊毛衫）。多个类别可使用逗号分隔。

`categoryId`限制为 250 个字符。

>[!NOTE]
>
>要按[!UICONTROL 类别]页面中的类别显示推荐，则只有一个 `categoryId` 可以被传递到用于显示该特定推荐的 mbox 中。`categoryId` 的值必须与“产品详细信息”页面上传递的 `entity.categoryId` 的值完全匹配。

示例：

* “产品详细信息”页面示例：womens, womens:sweaters, womens:sweaters:cardigans
* “类别”页面示例 - Sweaters：womens:sweaters
* “类别”页面示例 - Cardigans：womens:sweaters:cardigans

对于基于类别的推荐，可使用逗号分隔类别值。以逗号分隔的任意值都会变成类别。您也可以使用不同的分隔符（例如冒号 (:)）来分隔类别值中的子类别，从而定义子类别。

例如，在下面这段代码中，“Womens”类别被划分为若干子类别：

```
mboxCreate('mboxName', 'entity.id=343942-32', 'entity.categoryId= Womens, Womens:Outerwear, Womens:Outerwear:Jackets, Womens:Outerwear:Jackets:Parka, Womens:Outerwear:Jackets:Caban’, 'entity.thumbnailUrl=...', 'entity.message=...', );
```

对于 mbox 提交，会对键值使用最长的属性名称。如果属性名称长度相同，则使用最后一个属性。在上述示例中，类型键值为 Womens:Outerwear:Jackets:Caban。

### `entity.brand`

仅支持单值。

显示项目的品牌名称。

示例: `'entity.brand=brandxyz'`

### `entity.pageUrl`

仅支持单值。

为能购买该项目的页面定义相关的 URL。

示例: `'entity.pageUrl=baseball/giants-tix/giantsvrockies5.12.2000-67833'`

### `entity.thumbnailUrl`

仅支持单值。

将相关的 URL 定义到显示该项目的缩略图图像。

示例: `'entity.thumbnailUrl=baseball/giants-tix/giants-136px.gif'`

### `entity.message`

仅支持单值。

与推荐中显示的产品相关的消息，例如“打折”或“清仓”。消息通常比产品名称更详细。用于定义要在模板中随产品一起显示的附加信息。.

示例: `'entity.message=Family&nbsp;special'`

### `entity.inventory`

仅支持单值。必须为整数或长整型值。

显示项目的库存水平。

示例: `'entity.inventory=1'`

**空库存属性处理：**&#x200B;对于交付，如果您具有包含规则、收集规则或标准设置，其中 `entity.inventory` > 0 或 `entity.inventory` = 0，并且产品未设置库存，则 [!DNL Target] 会将此规则计算为 TRUE，并包括未设置库存的产品。这是默认完成的，以便未设置库存的产品会显示在推荐结果中。

同样，如果您具有全局排除规则，其中 `entity.inventory` = 0，并且产品未设置 `entity.inventory`，则 [!DNL Target] 会将此规则计算为 TRUE 并排除产品。

**已知问题：**&#x200B;产品搜索与未设置库存值属性的交付不一致。例如，对于设置为 `entity.inventory` = 0 的规则，产品搜索将不显示未设置库存值的产品。

### `entity.value`

仅支持单值。

定义项目的价格或价值。

示例: `'entity.value=15.99'`

### `entity.margin`

仅支持单值。

项目的利润率或其他价值。

示例: `'entity.margin=1.00'`

### `entity.<custom>`

支持多值（JSON 数组）。

最多定义 100 个自定义变量，这些变量用于提供项目的其他信息。您可为每个自定义属性指定任意一个未使用过的属性名称。例如，您可以创建一个名为 `entity.genre` 的自定义属性，用来定义一本书籍或一部电影。或者，票务供应商可以为活动场地创建属性以用于辅助表演，例如体育赛事中的客队或音乐会上的开场表演。

限制：

* 您无法将预定义实体属性的名称用于自定义实体属性。
* entity.environment 属性由系统保留，该属性不能用于自定义实体属性。尝试使用 targetPageParams、信息源或 API 来传递 entity.environment 的操作将会被忽略。

示例：

`'entity.venue=AT&T&nbsp;Park'`

`'entity.secondary=Rockies'`

自定义实体属性支持多个值。有关字符和值限制，请参阅[自定义实体属性](/help/c-recommendations/c-products/custom-entity-attributes.md#limits)。

示例: `'entity.secondary=["band1",&nbsp;"band2"]'`

>[!NOTE]
>
>多值自定义实体属性需要使用有效的 JSON 数组。有关正确的语法信息，请参阅“自定义实体属性”。

### `entity.event.detailsOnly`

仅支持单值。

用于阻止 mbox 调用为算法递增行为数据计数器。

示例: `'entity.event.detailsOnly=true'`

在下面的示例中，第一个 mbox 调用将更新目录和行为数据。第二个 mbox 调用将仅更新目录。

```
mboxCreate('myMbox', 'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 'entity.inventory = 4' )
mboxCreate('myMbox',  'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 123', 'entity.inventory = 4' 'entity.event.detailsOnly=true' )
```

## 使用实体属性

>[!NOTE]
>
>提供的实体属性值会在 61 天后过期。这意味着对于目录中的每个项目，应确保每月至少向 Target 推荐传递一次每个实体属性的最新值。

推荐会发送在算法中使用的 `productId` 或 `productPurchasedId`（在代码中称为 `entity.id`）。

>[!NOTE]
>
>`entity.id` 必须与发送至订单确认页面的 `productPurchasedId` 以及 Adobe Analytics 产品报表中使用的 `productId` 相匹配。

大多数预定义的参数仅接受单个值，且新值会覆盖旧值。`categoryId` 参数可以接受以逗号分隔的，表示包含该产品的每个类别的值列表。新的 `categoryId` 值在实体更新期间不会覆盖现有值，而是会进行附加（250 个字符限制）。

通常，如果您使用at.js 1，则显示信息mbox可能与以下示例类似。*x* with `mboxCreate`.

>[!NOTE]
>
>如果您使用at.js 2。*x*, `mboxCreate` （如以下示例中所示）不再受支持。 使用at.js 2将产品或内容信息传递给Recommendations。*x*，使 [用targetPageParams](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md)。 有关此示例，请参阅计 [划和实施建议](/help/c-recommendations/plan-implement.md)。

>[!NOTE]
>
>所有实体参数属性都区分大小写。

```
<div class="mboxDefault"></div><script language="JavaScript1.2"> 
 
mboxCreate('productPage', 
 
'entity.id=67833', 
 
'entity.name=GIANTS VS ROCKIES 5/12', 
 
'entity.categoryId=BASEBALL, GIANTS, SF BAY AREA', 
 
'entity.pageUrl=../baseball/giants-tix/giantsvrockies5.12.2000-67833', 
 
'entity.venue=AT&T PARK', 
 
'entity.secondary=ROCKIES', 
 
'entity.thumbnailUrl=../baseball/giants-tix/giants-136px.gif', 
 
'entity.message=FAMILY SPECIAL', 
 
'entity.value=15.99', 
 
'entity.inventory=1' 
 
); 
 
</script>
```

>[!NOTE]
>
>`pageUrl` 和 `thumbnailUrl` 首选使用相对 URL，而非绝对 URL，因为“推荐”会接收从您网站上的所有环境发送的数据。使用相对 URL 可避免硬编码链接指向临时服务器或开发服务器。

如果 mbox 在产品页面上，您可以同时包含产品 ID 和类别 ID，然后由所选择的算法决定显示哪个 ID。产品 ID 用于亲和算法，类别 ID 用于分类算法。

## 相关主题：

* [自定义实体属性](../../c-recommendations/c-products/custom-entity-attributes.md#concept_E5CF39BCAC8140309A73828706288322)
