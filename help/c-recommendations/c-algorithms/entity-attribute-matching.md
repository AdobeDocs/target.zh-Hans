---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;entity attribute matching
description: 在Adobe TargetRecommendations动态过滤，方法是将潜在推荐项目池与用户已交互的特定项目进行比较。
title: Adobe TargetRecommendations动态包含规则中实体属性匹配的过滤
feature: criteria
translation-type: tm+mt
source-git-commit: c814215476ef6e40f4f175fe3f9dbb2c26b966eb
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 0%

---


# ![PREMIUM实体](/help/assets/premium.png) 属性匹配

Filter dynamically in [!DNL Adobe Target] [!DNL Recommendations] by comparing a pool of potential recommendations items to a specific item that the user has interacted with.

>[!NOTE]
>
>The [process for creating and using inclusion rules](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) for criteria and promotions is similar, as are the use cases and examples.

例如，仅建议与当前项目的品牌匹配的项目，如下例所示：

如果品牌登陆页上的mbox返 `entity.brand=Nike`回，则仅会返回Nike产品并显示在该页面上。 同样，在阿迪达斯的品牌登陆页中，只退回阿迪达斯产品。 使用这种类型的动态包含规则，用户只需指定一个推荐规则，该规则可在所有品牌页面中返回相关品牌结果，而不必指定集合或静态过滤器以匹配每个品牌名称。

请注意，您必须在mbox `entity.brand` 中提供这些登陆页，才能使其正常工作。

## 实体属性匹配示例

[!UICONTROL 实体属性匹配] 允许您仅推荐匹配的项目，例如：

* 用户当前查看的项目中的属性
* 用户最近查看的项目
* 用户最近购买的物品
* 用户最常查看的项目
* 存储在访客用户档案中的自定义属性中的项

### 根据品牌推荐项目

构建实体属性规则后，它们将过滤掉所有具有与页面上传递的实体值不匹配的属性的建议。

以下示例显示了页面上显示的与产品品牌匹配的推荐：

当您访问包含Nike产品的页面时，该页面会将参数的值 `entity.brand` 设置为“Nike”。

![示例目标调用](/help/c-recommendations/c-algorithms/assets/example-target-call.png)

在页面上的推荐中，您将仅看到Nike产品。

![耐克推荐](/help/c-recommendations/c-algorithms/assets/nike.png)

视图Adidas产品页面时，价 `entity.brand` 值将重置为“Adidas”,Adidas产品页面将推荐Adidas产品。

![Adidas推荐](/help/c-recommendations/c-algorithms/assets/adidas.png)

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
