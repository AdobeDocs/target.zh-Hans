---
keywords: 包含规则；包含标准；推荐；促销活动；动态筛选；动态；实体属性匹配
description: 了解如何在Adobe中动态筛选 [!DNL Target] Recommendations ，方法是将潜在项目池与用户交互的特定项目进行比较。
title: 如何在Recommendations活动中按实体属性匹配进行过滤？
feature: Recommendations
exl-id: aadd3132-d590-4dc9-b01b-bedf41bc7441
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 0%

---

# ![PREMIUM](/help/main/assets/premium.png) 实体属性匹配

动态筛选 [!DNL Adobe Target] [!DNL Recommendations] 通过将潜在推荐项目池与用户交互的特定项目进行比较。

>[!NOTE]
>
>的 [创建和使用包含规则的过程](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) 与用例和示例一样，标准和促销活动的用例和示例也类似。

例如，如以下示例所示，只推荐与当前项目品牌匹配的项目：

如果品牌登录页面上的mbox返回 `entity.brand=brandA`，则仅会返回并显示该页面上的品牌A产品。 同样，在品牌B的品牌登录页面上，仅返回品牌B产品。 使用此类型的动态包含规则时，用户只需指定一个推荐规则即可在所有品牌页面中返回相关品牌结果，而无需指定收藏集或静态筛选器来匹配每个品牌名称。

请注意，您必须将 `entity.brand` 的mbox中，以使其正常工作。

## 实体属性匹配示例

[!UICONTROL 实体属性匹配] 允许您仅推荐与之匹配的项目，例如：

* 用户当前正在查看的项目中的属性
* 用户最近查看的项目
* 用户最近购买的项目
* 用户最常查看的项目
* 存储在访客配置文件的自定义属性中的项目

### 根据品牌推荐项目

构建实体属性规则后，它们将筛选出所有具有与页面上传递的实体值不匹配属性的推荐。

以下示例显示与页面上显示的产品品牌匹配的推荐：

当您访问的页面具有品牌A产品，该页面会将 `entity.brand` 参数添加到“BrandA”。

![Target调用示例](/help/main/c-recommendations/c-algorithms/assets/example-target-call.png)

在页面的“推荐”中，您将仅看到品牌A产品。

![品牌A推荐](/help/main/c-recommendations/c-algorithms/assets/brandA.png)

如果您随后查看Brand B产品页面，则 `entity.brand` 值将重置为“BrandB”，并且您将看到在Brand B产品页面上推荐的B品牌产品。

![品牌B推荐](/help/main/c-recommendations/c-algorithms/assets/brandB.png)

### 向上销售更贵的产品

假设您是一家服装零售商，希望鼓励用户考虑价格更高、从而获利更丰厚的项目。 您可以使用“等于”和“介于”运算符来促销来自同一类别和同一品牌的更贵的商品。 例如，鞋类零售商可以促销更贵的跑鞋，以向上销售查看跑鞋的访客，如以下示例所示：

![向上销售](/help/main/c-recommendations/c-algorithms/assets/upsell.png)

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

### 推广私有标签产品

您可以混合使用动态和静态筛选器来促销专用标签产品。 例如，办公室供应公司可以推广公司家用品牌的碳粉盒，以便为查看碳粉盒的访客进行更有利可图的销售，并推广公司家用品牌的笔，以便为查看笔的访客进行更有利可图的销售，如下例所示：

![House Brand](/help/main/c-recommendations/c-algorithms/assets/housebrand.png)

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```
