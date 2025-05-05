---
keywords: 包含规则；包含标准；推荐；促销活动；动态筛选；动态；实体属性匹配
description: 了解如何通过将潜在项目池与用户与之交互的特定项目进行比较，在 [!DNL Target Recommendations] 中动态筛选。
title: 如何在Recommendations活动中按实体属性匹配进行筛选？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: aadd3132-d590-4dc9-b01b-bedf41bc7441
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 0%

---

# 实体属性匹配

通过比较潜在的推荐项池与用户与之交互的特定项，在[!DNL Adobe Target Recommendations]中动态筛选。

>[!NOTE]
>
>为标准和促销活动创建和使用包含规则[&#128279;](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)的过程与用例和示例类似。

例如，只推荐与当前项目品牌相匹配的项目，如以下示例所示：

如果品牌登陆页面上的mbox返回`entity.brand=brandA`，则仅返回品牌A产品并显示在该页面上。 同样，在品牌B的品牌登陆页面上，仅返回品牌B产品。 对于这种类型的动态包含规则，用户只需指定一个推荐规则即可返回所有品牌页面上的相关品牌结果，而无需指定收藏集或静态过滤器来匹配每个品牌名称。

请注意，您必须在这些登陆页面的mbox中交付`entity.brand`，此流程才能正常工作。

## 实体属性匹配示例

[!UICONTROL Entity Attribute Matching]允许您仅推荐匹配的项目，例如：

* 用户当前正在查看的项目中的属性
* 用户最近查看的项目
* 用户最近购买的项目
* 用户最常查看的项目
* 在访客配置文件的自定义属性中存储的项目

### 根据品牌推荐项目

生成实体属性规则后，这些规则将筛选掉其属性与页面上传递的实体值不匹配的所有推荐。

以下示例显示与页面上显示的产品品牌相匹配的推荐：

当您访问具有品牌A产品的页面时，该页面会将`entity.brand`参数的值设置为“品牌A”。

![示例Target调用](/help/main/c-recommendations/c-algorithms/assets/example-target-call.png)

在页面上的推荐中，您将仅看到品牌A产品。

![品牌A推荐](/help/main/c-recommendations/c-algorithms/assets/brandA.png)

如果您随后查看品牌B产品页面，则`entity.brand`值将重置为“品牌B”，并且您将会在品牌B产品页面上看到推荐的品牌B产品。

![品牌B推荐](/help/main/c-recommendations/c-algorithms/assets/brandB.png)

### 追加销售到更昂贵的产品

假设您是一家服装零售商，并且希望鼓励用户考虑定价较高，因此利润率较高的商品。 您可以使用“等于”和“介于”运算符来促销来自同一类别和同一品牌的更贵的商品。 例如，鞋类零售商可以促销更昂贵的跑鞋，以便向查看跑鞋的访客追加销售，如下面的示例所示：

![追加销售](/help/main/c-recommendations/c-algorithms/assets/upsell-new.png)

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

您可以混合使用动态和静态筛选器来促销专用标签产品。 例如，一家办公室供应公司可以推广公司自有品牌的碳粉盒，以便让看碳粉的访客获得更有利可图的销售，还可以推广公司自有品牌的笔，让看笔的访客获得更有利可图的销售，如以下示例所示：

![家庭品牌](/help/main/c-recommendations/c-algorithms/assets/housebrand-new.png)
)

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```
