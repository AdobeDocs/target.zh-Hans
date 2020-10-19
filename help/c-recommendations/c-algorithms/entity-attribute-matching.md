---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;entity attribute matching
description: 在Adobe TargetRecommendations动态过滤，方法是将潜在推荐项目池与用户已交互的特定项目进行比较。
title: Adobe TargetRecommendations动态包含规则中实体属性匹配的过滤
feature: criteria
translation-type: tm+mt
source-git-commit: b51c980d8e7db3ee574350a04f9056fe5b00a703
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 0%

---


# ![PREMIUM实体](/help/assets/premium.png) 属性匹配

Filter dynamically in [!DNL Adobe Target] [!DNL Recommendations] by comparing a pool of potential recommendations items to a specific item that the user has interacted with.

例如，仅建议与当前项目的品牌匹配的项目，如下例所示：

如果品牌登陆页上的mbox返 `entity.brand=Nike`回，则仅会返回Nike产品并显示在该页面上。 同样，在阿迪达斯的品牌登陆页中，只退回阿迪达斯产品。 对于这种类型的动态包含规则，用户只需指定一个推荐规则，该规则可在所有品牌页面中返回相关品牌结果，而无需指定集合或静态过滤器以匹配每个品牌名称。

## 实体属性匹配示例

[!UICONTROL 实体属性匹配] 允许您仅推荐匹配的项目，例如：

* 用户当前查看的项目中的属性
* 用户最近查看的项目
* 用户最近购买的物品
* 用户最常查看的项目
* 存储在访客用户档案中的自定义属性中的项

### 向上销售到更昂贵的产品

假设您是服装零售商，希望鼓励用户考虑价格更高、从而获利更多的商品。 您可以使用“等于”和“介于”运营商来宣传来自同一类别和同一品牌的更贵商品。 例如，鞋类零售商可以推广更昂贵的跑鞋，以向上销售看跑鞋的访客，如下面的代码示例所示：

```
Entity Attribute Matching
category - equals - current item's - category 
And 
Entity Attribute Matching
brand - equals - current item's - brand 
And 
Entity Attribute Matching
value - is between - 100% and 1000% of - current item's - value
```

### 推广专用标签产品

您可以混合使用动态和静态过滤器来推广专用标签产品。 例如，办公室供应公司可以推广公司家用品牌的碳粉盒，以便为查看碳粉的访客进行利润更高的销售，并推广公司家用品牌的钢笔，以便为看笔的访客进行利润更高的销售，如下面的代码示例所示：

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```
