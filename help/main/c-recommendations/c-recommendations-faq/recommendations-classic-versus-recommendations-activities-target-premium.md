---
keywords: 推荐;推荐算法;推荐活动;经典版推荐
description: 查看信息以帮助您了解旧版Recommendations Classic与Recommendations activities in [!DNL Target] Premium之间的区别。
title: Recommendations Classic与[!DNL Target] Premium中的推荐之间有何区别？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: 07548155-9548-4870-b886-6cb4ff37a0bd
TQID: 'https://experienceleague.adobe.com/EoTkyY0kOwRKT52WIwOuTCoUziIJOnNtTo6llsTNpsM'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 19%
---
# Recommendations Classic与[!DNL Target] Premium中的“推荐”活动 {#classic-versus-activities}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解[!DNL Recommendations Classic]与[!DNL Target Premium]中的[!DNL Recommendations]活动有何不同，以便在这两种活动之间进行选择。

>[!ENDSHADEBOX]

>[!NOTE]
>
>[!DNL Recommendations] 活动作为 [!DNL Target Premium] 解决方案的一部分提供。 如果没有 [!DNL Target Premium] 许可证，它们将无法在 [!DNL Target Standard] 中使用。

在 [!DNL Recommendations] Classic 产品中，显示推荐的方法是先在页面上创建一个数据收藏集 mbox，然后在页面上的某个特定位置添加一个显示 mbox。 [!DNL Target Premium]中的[!DNL Recommendations]活动将收集访客信息并在页面上的任意位置创建推荐，而不对推荐产品或内容的每个位置都使用mbox。 页面标题中的JavaScript引用可在页面上的任意位置启用推荐。 此引用将键（如`entity.id`和`entity.categoryId`键）传递到全局[!DNL Target] mbox。

[!DNL Recommendations Classic] 在 [!DNL Experience Cloud] UI 中显示为其自身的卡片。 [!DNL Recommendations] 活动可在 [!DNL Target Premium] 工作流中找到。

[!DNL Recommendations Classic] 用户可以继续在 [!DNL Target Recommendations] 中使用他们的 [!DNL Recommendations] mbox。 通过保留mbox并在标头中使用JavaScript代码为页面上的其他元素激活[!DNL Recommendations]功能，还可以组合Classic方法和[!DNL Target]方法。 但是，为获得完整的[!DNL Target]功能，[!DNL Recommendations Classic]用户可能希望删除旧的mbox并仅依赖[!DNL Target Recommendations]。

[!DNL Target]中的[!DNL Recommendations]活动在以下主要方面优于[!DNL Recommendations Classic]。

## 产品建议形式的推荐 {#recs-as-offer}

推荐可包含在[!UICONTROL A/B测试]（包括[!UICONTROL 自动分配]和[!UICONTROL 自动定位]）和[!UICONTROL 体验定位] (XT)活动中。 此功能与其他功能一起，还支持在同一活动内测试和定位推荐和非推荐内容。 有关更多信息，请参阅[将推荐作为产品建议](/help/main/c-recommendations/recommendations-as-an-offer.md)。

## 标准 {#criteria-comparison}

[!DNL Target Recommendations]包含一个标准库，该库具有预打包的规则和配置集。 在[!DNL Recommendations Classic]中，通过填写表单并从一长串规则中进行选择，手动构建每个推荐。 创建[!DNL Recommendations]活动时，会选择预配置的标准集。 仍可以创建自定义推荐，但标准库包含许多最常见的配置，这些配置是预先构建的，用于简化流程并使用人们能够理解的语言。 预封装标准可以按原样使用，也可以复制和编辑以符合特定需求。

![幻灯片显示标准卡片“追加销售”，该卡片使用用户理解的语言、规则和逻辑以及标记为](assets/overview_criteria.png)的配置

预先配置的标准按垂直行业、页面类型和实施进行排序。 例如，可以在产品页面上找到适用于零售业的标准，以显示属于特定类别（由`entity.categoryID`参数定义）的产品。

有关使用和创建标准的更多信息，请参阅[标准](/help/main/c-recommendations/c-algorithms/algorithms.md)。

## 工作流 {#workflow-comparison}

[!DNL Recommendations]工作流已得到简化。 可视化工作流并非是复杂的表单，而是指导您完成以下步骤：

1. 选择标准。
1. Select预配置的[设计](/help/main/c-recommendations/c-design-overview/create-design.md#create-design)。
1. 预览生成的推荐。

## 可视化预览 {#visual-preview}

可以在设置推荐后预览推荐，并进行任何必要的更改，而无需在页面上创建推荐，然后对其进行测试。 可从 [!DNL Target] 中进行预览。

## 定位 {#targeting-comparison}

[!DNL Recommendations Classic]有六个定位选项。 [!DNL Recommendations]活动使用全部[!DNL Target]个定位选项。 使用[!DNL Target]或其他[!DNL Adobe Experience Cloud]受众（如[!DNL Audience Manager]和[!DNL Analytics]）定义受众。 然后选择看到每个设计的活动参加者所占的百分比，以及看到控制的参加者所占的百分比。

![包含“所有访客”受众、追加销售条件、三个设计（每个设计具有30%的流量）以及“无推荐”控制组的流程图](assets/overview_targeting.png)

## 报表 {#reporting-comparison}

在[!DNL Target]中，[!DNL Recommendations]提供了改进的报表，这些报表利用[!DNL Target]和[!DNL Experience Cloud]的功能。 这些报表不只显示[!DNL Recommendations]提供的提升度（与没有这些提升度的结果相比），而是显示有关[!DNL Recommendations]活动的完整信息。

