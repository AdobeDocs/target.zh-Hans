---
keywords: 实体;实体属性;将信息传递到推荐;行为数据;数据计数器;定义相对 URL;显示库存水平;定义价格;定义利润率;自定义属性
description: 了解如何使用实体属性将产品或内容信息传递到 [!DNL Target] 推荐。
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
title: 如何使用实体属性？
feature: Recommendations
exl-id: 4ed5fad3-b8b6-4675-a741-9f85cf73fcf1
source-git-commit: b6697eee5925cb8fa3b2fa2e107af0c617d30f94
workflow-type: tm+mt
source-wordcount: '1078'
ht-degree: 48%

---

# 实体属性

使用实体属性将产品或内容信息传递到[!DNL Adobe Target Recommendations]。

实体是指您想推荐的项目。实体可以包括产品、内容（文章、幻灯片、图像、电影和电视节目）、工作列表、餐厅等。

[!DNL Recommendations]发送在算法中使用的`productId`或`productPurchasedId`（在代码中称为`entity.id`）。

请考虑以下事项：

* `entity.id`必须与发送至订单确认页面的`productPurchasedId`以及`productId`产品报表中使用的[!DNL Adobe Analytics]匹配。
* 您传递到[!DNL Recommendations]的实体属性值会在61天后过期。 Adobe建议您每月至少为目录中的每个项目向[!DNL Recommendations]传递一次每个实体属性的最新值。

大多数预定义参数仅接受单个值，且新值会覆盖旧值。 `categoryId` 参数可以接受以逗号分隔的，表示包含该产品的每个类别的值列表。新的 `categoryId` 值在实体更新期间不会覆盖现有值，而是会进行附加（250 个字符限制）。

通常，如果您使用的是at.js 1，则显示信息mbox类似于以下示例。*x*&#x200B;与`mboxCreate`。 所有实体参数属性都区分大小写。

>[!NOTE]
>
>如果您使用的是at.js 2.不再支持&#x200B;*x*、`mboxCreate`（如以下示例中所用）。 要使用at.js 2.[!DNL Recommendations]*x*，使用[targetPageParams](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/targetpageparams.html){target=_blank}。 有关示例，请参阅[计划和实施推荐](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank}。

```javascript
<div class="mboxDefault"></div><script language="JavaScript1.2"> 
 
mboxCreate('productPage', 
 
'entity.id=67833', 
 
'entity.name=GIANTS VS ROCKIES 5/12', 
 
'entity.categoryId=BASEBALL, GIANTS, SF BAY AREA', 
 
'entity.pageUrl=/help/baseball/giants-tix/giantsvrockies5.12.2000-67833', 
 
'entity.venue=AT&T PARK', 
 
'entity.secondary=ROCKIES', 
 
'entity.thumbnailUrl=/help/baseball/giants-tix/giants-136px.gif', 
 
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

## 可用变量

下表说明了可用的变量。

### entity.id

仅支持单值。

此必填参数可识别产品。此字母数字 ID 必须在使用的所有 [!DNL Adobe Experience Cloud] 产品（包括 [!DNL Analytics]）中均相同，以便各个产品能够识别该项目并共享与其相关的数据。

`entity.id`值必须&#x200B;*不*&#x200B;包含空格、斜杠、&amp;符号、问号、百分比符号、逗号或其他在REST API调用中传递时需要URL编码的标点字符。 允许使用连字符和下划线。 在 `entity.id` 值中包含无效标点符号会导致某些 [!DNL Recommendations] 功能失败。

示例: `'entity.id=67833'`

### entity.name

仅支持单值。

当推荐产品后，该产品名称将显示在网站上。

示例: `'entity.name=Giants& vs& Rockies& 5/12'`

### entity.categoryId

支持多值（逗号分隔列表）。

当前页面的类别。entity.categoryID可以包含多个类别，例如羊毛衫子节（例如，`womens`、`womens:sweaters`、`womens:sweaters:cardigans`）。 多个类别必须以逗号分隔。

`categoryId`值限制为250个字符。

>[!NOTE]
>
>要基于[!UICONTROL Category]页面中的类别显示推荐，则只有一个`categoryId`可以传递到用于显示该特定推荐的mbox中。 `categoryId`的值必须与`entity.categoryId`页面上传递的[!UICONTROL Product Detail]的值完全匹配。

示例：

* 产品详细信息页面示例： `womens`，`womens:sweaters`，`womens:sweaters:cardigans`
* 示例类别页面毛衣： `womens:sweaters`
* 示例类别页面Cardigans： `womens:sweaters:cardigans`

对于基于类别的推荐，使用逗号分隔类别值。 以逗号分隔的任意值都会变成类别。您也可以使用不同的分隔符（例如冒号 (:)）来分隔类别值中的子类别，从而定义子类别。

例如，在以下代码中，妇女类别分为几个子类别：

```javascript
mboxCreate('mboxName', 'entity.id=343942-32', 'entity.categoryId= Womens, Womens:Outerwear, Womens:Outerwear:Jackets, Womens:Outerwear:Jackets:Parka, Womens:Outerwear:Jackets:Caban', 'entity.thumbnailUrl=...', 'entity.message=...', );
```

对于 mbox 提交，会对键值使用最长的属性名称。如果属性名称长度相同，则使用最后一个属性。在上述示例中，类别键值为`Womens:Outerwear:Jackets:Caban`。

### entity.brand

仅支持单值。

显示项目的品牌名称。

示例: `'entity.brand=brandxyz'`

### entity.pageUrl

仅支持单值。

为能购买该项目的页面定义相关的 URL。

示例: `'entity.pageUrl=baseball/giants-tix/giantsvrockies5.12.2000-67833'`

### entity.thumbnailUrl

仅支持单值。

将相关的 URL 定义到显示该项目的缩略图图像。

示例: `'entity.thumbnailUrl=baseball/giants-tix/giants-136px.gif'`

### entity.message

仅支持单值。

与推荐中显示的产品相关的消息，例如“打折”或“清仓”。消息通常比产品名称更详细。使用entity.message定义要在模板中与产品一起显示的附加信息。

示例: `'entity.message=Family&nbsp;special'`

### entity.inventory

仅支持单值。必须为整数或长整型值。

显示项目的库存水平。

示例: `'entity.inventory=1'`

**空库存属性处理：**&#x200B;对于交付，如果您具有包含规则、集合规则或标准设置，其中`entity.inventory` > 0或`entity.inventory` = 0，并且产品未设置库存，则[!DNL Target]会将此值计算为TRUE，并包含未设置库存的产品。 因此，未设置库存的产品将显示在推荐结果中。

同样，如果您具有全局排除规则，其中 `entity.inventory` = 0，并且产品未设置 `entity.inventory`，则 [!DNL Target] 会将此规则计算为 TRUE 并排除产品。

**已知问题：**&#x200B;产品搜索与未设置的库存值属性的交付不一致。 例如，对于具有`entity.inventory` = 0的规则，产品搜索不显示未设置库存值的产品。

### entity.value

仅支持单值。

定义项目的价格或价值。

示例: `'entity.value=15.99'`

entity.value仅支持十进制格式（例如，15.99）。 不支持逗号格式(15,99)。

### entity.margin

仅支持单值。

项目的利润率或其他价值。

示例: `'entity.margin=1.00'`

### 实体。*custom*

支持多值（JSON 数组）。

最多定义 100 个自定义变量，这些变量用于提供项目的其他信息。您可为每个自定义属性指定任意一个未使用过的属性名称。例如，您可以创建一个名为`entity.genre`的自定义属性来定义书籍或电影。 票务供应商可以为活动场地创建属性以用于辅助表演，例如体育活动中的客队或音乐会中的开场表演。

限制：

* 您无法将预定义实体属性的名称用于自定义实体属性。
* entity.environment 属性由系统保留，该属性不能用于自定义实体属性。尝试使用targetPageParams、信息源或API来传递entity.environment的操作将会被忽略。

示例：

`'entity.venue=AT&T&nbsp;Park'`

`'entity.secondary=Rockies'`

自定义实体属性支持多个值。有关字符和值限制，请参阅[自定义实体属性](/help/main/c-recommendations/c-products/custom-entity-attributes.md#limits)。

示例: `'entity.secondary=["band1",&nbsp;"band2"]'`

多值自定义实体属性需要使用有效的 JSON 数组。有关正确的语法信息，请参阅[自定义实体属性](/help/main/c-recommendations/c-products/custom-entity-attributes.md)。

### entity.event.detailsOnly

仅支持单值。

用于阻止 mbox 调用为算法递增行为数据计数器。

示例: `'entity.event.detailsOnly=true'`

在以下示例中，第一个mbox调用会更新目录和行为数据。 第二个mbox调用仅更新目录。

```javascript
mboxCreate('myMbox', 'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 'entity.inventory = 4' )
mboxCreate('myMbox',  'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 123', 'entity.inventory = 4' 'entity.event.detailsOnly=true' )
```

>[!MORELIKETHIS]
>
>* [自定义实体属性](/help/main/c-recommendations/c-products/custom-entity-attributes.md#concept_E5CF39BCAC8140309A73828706288322)
