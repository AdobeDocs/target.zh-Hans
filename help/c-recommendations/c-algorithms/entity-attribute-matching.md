---
keywords: 包含规则；包含条件；推荐；促销；动态过滤；动态；实体属性匹配
description: 了解如何通过将潜在项目池与用户与之交互的特定项目进行比较，在Adobe [!DNL Target] Recommendations中动态筛选。
title: 如何在Recommendations活动中按实体属性匹配进行筛选？
feature: Recommendations
exl-id: aadd3132-d590-4dc9-b01b-bedf41bc7441
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---

# ![PREMIUMEntity属](/help/assets/premium.png) 性匹配

通过将潜在推荐项的池与用户与之交互的特定项进行比较，在[!DNL Adobe Target] [!DNL Recommendations]中动态过滤。

>[!NOTE]
>
>标准和促销的[创建和使用包含规则](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)的过程与使用案例和示例类似。

例如，仅建议与当前项目的品牌匹配的项目，如下例所示：

如果品牌登陆页上的mbox返回`entity.brand=brandA`，则仅返回品牌A产品并在该页面上显示。 同样，在品牌B的品牌登陆页中，只返回品牌B产品。 使用这种类型的动态包含规则，用户只需指定一个推荐规则，该规则可在所有品牌页面中返回相关品牌结果，而无需指定集合或静态过滤器以匹配每个品牌名称。

请注意，您必须在mbox中的这些登陆页上传送`entity.brand`，才能使此操作正常工作。

## 实体属性匹配示例

[!UICONTROL 实体属] 性匹配允许您仅推荐匹配的项目，例如：

* 用户当前查看的项目中的属性
* 用户最近查看的项目
* 用户最近购买的物品
* 用户最常查看的项目
* 存储在访客用户档案中的自定义属性中的项

### 根据品牌推荐项目

构建实体属性规则后，它们将过滤掉所有具有与页面上传递的实体值不匹配的属性的建议。

以下示例显示了页面上显示的与产品品牌匹配的推荐：

当您访问具有品牌A产品的页面时，该页面会将`entity.brand`参数的值设置为“品牌A”。

![示例目标调用](/help/c-recommendations/c-algorithms/assets/example-target-call.png)

在页面的推荐中，您将仅看到品牌A产品。

![品牌A推荐](/help/c-recommendations/c-algorithms/assets/brandA.png)

如果您随后视图了品牌B产品页面，`entity.brand`值将重置为“品牌B”，您将看到在品牌B产品页面上推荐的品牌B产品。

![品牌B推荐](/help/c-recommendations/c-algorithms/assets/brandB.png)

### 向上销售到更昂贵的产品

假设您是一家服装零售商，希望鼓励用户考虑价格更高、因而利润更高的产品。 您可以使用“等于”和“介于”运算符来宣传来自同一类别和同一品牌的更昂贵物品。 例如，鞋类零售商可以推广更贵的跑鞋，以便向上销售看跑鞋的访客，如下例所示：

![向上销售](/help/c-recommendations/c-algorithms/assets/upsell.png)

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

您可以混合动态和静态过滤器来推广专用标签产品。 例如，办公室供应公司可以推广公司家庭品牌的碳粉盒，以便为看着碳粉的访客进行利润更高的销售，并推广公司家庭品牌的钢笔，以推动看笔的访客进行利润更高的销售，如以下示例所示：

![House Brand](/help/c-recommendations/c-algorithms/assets/housebrand.png)

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```
