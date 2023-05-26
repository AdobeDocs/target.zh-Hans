---
keywords: 包含规则；包含标准；推荐；促销活动；动态筛选；动态；实体属性匹配
description: 了解如何在Adobe中动态筛选 [!DNL Target] Recommendations，将潜在项目池与用户与之交互的特定项目进行比较。
title: 如何在Recommendations活动中按实体属性匹配进行筛选？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: aadd3132-d590-4dc9-b01b-bedf41bc7441
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 0%

---

# 实体属性匹配

动态筛选 [!DNL Adobe Target] [!DNL Recommendations] 将一组潜在的推荐项目与用户与之交互的特定项目进行比较。

>[!NOTE]
>
>此 [创建和使用包含规则的进程](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) 对于标准和促销，用例和示例是相似的。

例如，只推荐与当前项目品牌相匹配的项目，如下例所示：

如果品牌登陆页面上的mbox返回 `entity.brand=brandA`，则仅返回品牌A产品并显示在该页面上。 同样，在品牌B的品牌登陆页面上，仅返回品牌B产品。 对于此类型的动态包含规则，用户只需指定一个推荐规则即可返回所有品牌页面上的相关品牌结果，而无需指定收藏集或静态过滤器来匹配每个品牌名称。

请注意，您必须交付 `entity.brand` （位于这些登陆页面上的mbox中）才能使此功能正常工作。

## 实体属性匹配示例

[!UICONTROL 实体属性匹配] 仅用于推荐匹配的项目，例如：

* 用户当前正在查看的项目中的属性
* 用户最近查看的项目
* 用户最近购买的项目
* 用户最常查看的项目
* 存储在访客配置文件的自定义属性中的项目

### 根据品牌推荐项目

生成实体属性规则后，这些规则将筛选掉其属性与页面上传递的实体值不匹配的所有推荐。

以下示例显示与页面上显示的产品品牌相匹配的推荐：

当您访问具有品牌A产品的页面时，该页面会设置 `entity.brand` “BrandA”的参数。

![示例Target调用](/help/main/c-recommendations/c-algorithms/assets/example-target-call.png)

在页面上的推荐中，您将仅看到Brand A产品。

![品牌A推荐](/help/main/c-recommendations/c-algorithms/assets/brandA.png)

如果您随后查看Brand B产品页面， `entity.brand` 值将重置为“BrandB”，此时您将在Brand B产品页面上看到推荐的Brand B产品。

![品牌B推荐](/help/main/c-recommendations/c-algorithms/assets/brandB.png)

### 追加销售到更昂贵的产品

假设您是一家服装零售商，并且想要鼓励用户考虑价格更高、因此利润率更高的商品。 您可以使用“等于”和“介于”运算符来促销来自同一类别和同一品牌的更贵的商品。 例如，鞋类零售商可以促销更昂贵的跑鞋，以便向查看跑鞋的访客追加销售，如下面的示例所示：

![追加销售](/help/main/c-recommendations/c-algorithms/assets/upsell.png)

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

### 推广贴牌产品

您可以混合使用动态和静态筛选器来促销贴有私有标签的产品。 例如，一家办公室供应公司可以推广其自有品牌的碳粉盒，以便为看碳粉盒的访客带来更有利可图的销售，并推广其自有品牌的笔，以便为看笔的访客带来更有利可图的销售，如下面的示例所示：

![House品牌](/help/main/c-recommendations/c-algorithms/assets/housebrand.png)

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```
