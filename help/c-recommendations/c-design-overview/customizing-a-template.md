---
keywords: custom design;velocity;decimal;comma;customize design
description: 在Adobe TargetRecommendations，使用开放源码Velocity设计语言自定义推荐设计。
title: 使用 Velocity 自定义设计
feature: designs
uuid: 80701a15-c5eb-4089-a92e-117eda11faa2
translation-type: tm+mt
source-git-commit: afbec50cb0ec4e689bfaa77296ffda91bc6de3a5
workflow-type: tm+mt
source-wordcount: '1014'
ht-degree: 61%

---


# ![PREMIUM](/help/assets/premium.png) 使用 Velocity 自定义设计{#customize-a-design-using-velocity}

Use the open-source Velocity design language to customize recommendation designs in [!DNL Adobe Target Recommendations].

## Velocity 概述 {#section_C431ACA940BC4210954C7AEFF6D03EA5}

有关 Velocity 的信息可在 [](https://velocity.apache.org)https://velocity.apache.org 中找到。

所有 Velocity 逻辑、语法等内容均可用于推荐设计。这表示您可以使用 Velocity 而非 JavaScript 来创建 *for* 循环、*if* 语句和其他代码。

任何在 `productPage` mbox 中或通过 CSV 上传方式发送到 [!DNL Recommendations] 的变量均可在设计中显示。这些值引用了下列语法：

```
$entityN.variable
```

变量名称必须遵循 Velocity 简写表示法，即以 *$* 字符开头，后跟 Velocity 模板语言 (VTL) 标识符。VTL 标识符必须以字母字符（a-z 或 A-Z）开头。

Velocity 变量名称只能使用以下类型的字符：

* 字母（a-z、A-Z）
* 数字 (0-9)
* 连字符 ( - )
* 下划线 ( _ )

以下变量可用作 Velocity 数组。因此，可通过索引对这些变量进行迭代或引用。

* `entities`
* `entityN.categoriesList`

例如：

```
#foreach ($category in $entity1.categoriesList) 
<br/>$category 
#end
```

或

```
#if ($entities[0].categoriesList.size() >= 3 ) 
$entities[0].categoriesList[2] 
#end
```

有关 Velocity 变量的详细信息，请参阅 [https://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html#variables](https://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html#variables)。

如果您在设计中使用配置文件脚本，脚本名称前的 $ 符号必须使用 \ 进行转义。例如，`\${user.script_name}`。

>[!NOTE]
>
>设计中可引用的最大图元数（硬编码或通过循环）为99。 模板脚本最长可包含 65,000 个字符。

例如，如果您想要在设计中显示类似于下面的内容：

![](assets/velocity_example.png)

您可使用以下代码：

```
<table style="border:1px solid #CCCCCC;"> 
<tr> 
<td colspan="3" style="font-size: 130%; border-bottom:1px solid  
#CCCCCC;"> You May Also Like... </td> 
</tr> 
<tr> 
<td style="border-right:1px solid #CCCCCC;"> 
<div class="search_content_inner" style="border-bottom:0px;"> 
<div class="search_title"><a href="$entity1.pageUrl"  
style="color: rgb(112, 161, 0); font-weight: bold;"> 
$entity1.id</a></div> 
By $entity1.message <a href="?x14=brand;q14=$entity1.message"> 
(More)</a><br/> 
sku: $entity1.prodId<br/> Price: $$entity1.value 
<br/><br/> 
</div> 
</td> 
<td style="border-right:1px solid #CCCCCC; padding-left:10px;"> 
<div class="search_content_inner" style="border-bottom:0px;">  
<div class="search_title"><a href="$entity2.pageUrl"  
style="color: rgb(112, 161, 0); font-weight: bold;"> 
$entity2.id</a></div> 
By $entity2.message <a href="?x14=brand;q14=$entity2.message"> 
(More)</a><br/> 
sku: $entity2.prodId<br/> 
Price: $$entity2.value 
<br/><br/> 
</div> 
</td> 
<td style="padding-left:10px;"> 
<div class="search_content_inner" style="border-bottom:0px;"> 
<div class="search_title"><a href="$entity3.pageUrl"  
style="color: rgb(112, 161, 0); font-weight: bold;"> 
$entity3.id</a></div> 
By $entity3.message <a href="?x14=brand;q14=$entity3.message"> 
(More)</a><br/> 
sku: $entity3.prodId<br/> Price: $$entity3.value 
<br/><br/> 
</div> 
</td> 
</tr>  
</table>
```

>[!NOTE]
>
>如果要在指示变量名称的标记完成之前在变量的值之后添加文本，则可以使用形式记号来圈住变量的名称。 例如：`${entity1.thumbnailUrl}.gif`。

您还可以在设计中将 `algorithm.name` 和 `algorithm.dayCount` 用作变量，以便使用一个设计来测试多个标准，并在该设计中动态显示标准名称。这样可指示访客查看了“最畅销商品”或属于“查看了这个项目，但购买了那个项目的人”。您甚至还可以使用这些变量来显示 `dayCount`（标准中使用的数据所对应的天数，例如“过去 2 天的最畅销商品”，等等）。

## 在Velocity模板中使用数字

默认情况下，Velocity模板将所有实体属性视为字符串值。 您可能希望将实体属性视为数字值，以执行数学运算或将其与另一个数值进行比较。 要将实体属性视为数字值，请执行以下步骤：

1. 声明一个伪变量，并将其初始化为任意整数或多次值。
1. 确保要使用的实体属性不为空(目标Recommendations的模板分析器验证并保存模板时需要)。
1. 将实体属性传递 `parseInt` 到 `parseDouble` 您在步骤1中创建的虚拟变量上的或方法，将字符串转换为整数或多次值。
1. 对新数值执行数学运算或比较。

### 示例：计算折扣价格

假定您希望将项目的显示价格降低0.99美元以应用折扣。 您可以采用以下方法来实现此效果：

```
#set( $Double = 0.1 )

#if( $entity1.get('priceBeforeDiscount') != '' )
    #set( $discountedPrice = $Double.parseDouble($entity1.get('priceBeforeDiscount')) - 0.99 )
    Item price: $$discountedPrice
#else
    Item price unavailable
#end
```

### 示例：根据项目的等级选择要显示的星数

假定您希望根据项目的数值平均客户评级显示适当数量的星星。 您可以采用以下方法来实现此效果：

```
#set( $Double = 0.1 )

#if( $entity1.get('rating') != '' )
    #set( $rating = $Double.parseDouble($entity1.get('rating')) )
    #if( $rating >= 4.5 )
        <img src="5_stars.jpg">
    #elseif( $rating >= 3.5 )
        <img src="4_stars.jpg">
    #elseif( $rating >= 2.5 )
        <img src="3_stars.jpg">
    #elseif( $rating >= 1.5 )
        <img src="2_stars.jpg">
    #else
        <img src="1_star.jpg">
    #end
#else
    <img src="no_rating_default.jpg">
#end
```

### 示例：根据项目长度（以分钟为单位）计算时间（以小时和分钟为单位）

假定您以分钟为单位存储电影的长度，但希望以小时和分钟为单位显示电影的长度。 您可以采用以下方法来实现此效果：

```
#if( $entity1.get('length_minutes') )
#set( $Integer = 1 )
#set( $nbr = $Integer.parseInt($entity1.get('length_minutes')) )
#set( $hrs = $nbr / 60)
#set( $mins = $nbr % 60)
#end
```

## 使用推荐的产品显示关键项 {#section_7F8D8C0CCCB0403FB9904B32D9E5EDDE}

您可以对设计进行修改，以便同时显示关键项目和其他推荐产品。例如，您可能想要在推荐产品旁边显示当前项目，以供访客参考。

要实现这一点，需在设计中创建一个列，并使该列使用您的推荐所基于的 `$key` 属性，而不是 `$entity` 属性。例如，您的关键项目列的代码可能与以下内容类似：

```
<div class="at-table-column"> 
   <a href="$key.pageURL"> 
      <img src=$key.thumbnailUrl" class="at-thumbnail"/> 
      <br/><h3>$key.name</h3> 
      <br/><p class="at-light">$key.message</p> 
      <br/><p class="at-light">$key.value</p> 
   </a> 
</div>
```

最终生成的设计如下所示，其中有一列显示了关键项目。

![](assets/rec_key.png)

创建 [!DNL Recommendations] 活动时，如果关键项目是从访客的配置文件中获取的（例如“上次购买的项目”），则 [!DNL Target] 会在[!UICONTROL 可视化体验编辑器] (VEC) 中显示一个随机产品。这是因为在您设计活动时配置文件不可用。访客查看页面时，他们将看到预期的关键项目。

## 在字符串值中执行替换 {#section_01F8C993C79F42978ED00E39956FA8CA}

您可以修改设计以替换字符串中的值。 例如，将美国使用的小数点分隔符替换为欧洲和其他国家／地区使用的逗号分隔符。

以下代码显示了条件销售定价示例中的一行内容：

```
<span class="price">$entity1.value.replace(".", ",") €</span><br>
```

以下代码显示了完整的条件销售价格示例：

```
<div class="price"> 
    #if($entity1.hasSalesprice==true) 
    <span class="old">Statt <s>$entity1.salesprice.replace(".", ",") €</s></span><br> 
    <span style="font-size: 10px; float: left;">jetzt nur</span> $entity1.value.replace(".", ",") €<br> #else 
    <span class="price">$entity1.value.replace(".", ",") €</span><br> #end 
    <span style="font-weight:normal; font-size:10px;"> 
                                        $entity1.vatclassDisplay 
                                        <br/> 
                                        $entity1.delivery 
                                        <br> 
                                    </span>
```

## 自定义模板大小并检查空值 {#default}

下面的模板使用 Velocity 脚本控制实体显示的动态大小，从而可容纳一对多结果，这样当 [!DNL Recommendations] 未返回足够的匹配实体时，便无需创建空的 HTML 元素。此脚本非常适用于备份推荐没有意义且已启用“[!UICONTROL 部分模板渲染]”的情景。

以下 HTML 代码段将替换 4x2 默认设计中的现有 HTML 部分（为简便起见，此处不包括 CSS）：

* 如果存在第五个实体，脚本将插入一个闭合 div，并使用 `<div class="at-table-row">` 另起一个新行。
* 在 4x2 设计中，显示的结果最多为 8 个，但可以通过修改 `$count <=8` 对该值进行自定义，以适应较小或较大的列表。
* 请注意，该逻辑无法将实体均衡地分布在多个行上。例如，如果有五个或六个实体要显示，则不会动态地变为顶行显示三个，底行显示两个（或顶行显示三个，底行显示三个）。顶行将显示四个项目后，才会另起一行。

```
<div class="at-table">
  <div class="at-table-row">
    #set($count=1) 
    #foreach($e in $entities)  
        #if($e.id != "" && $count < $entities.size() && $count <=8) 
            #if($count==5) 
                </div>
                <div class="at-table-row">
            #end
            <div class="at-table-column">
                <a href="$e.pageUrl"><img src="$e.thumbnailUrl" class="at-thumbnail" />
                    <br/>
                    <h3>$e.name</h3>
                    <br/>
                    <p class="at-light">$e.message</p>
                    <br/>
                    <p class="at-light">$$e.value</p>
                </a>
            </div>
            #set($count = $count + 1) 
        #end 
    #end
  </div>
</div>
```
