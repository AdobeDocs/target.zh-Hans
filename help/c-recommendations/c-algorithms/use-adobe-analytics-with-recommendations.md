---
keywords: 行为数据源；分析；推荐；标准；产品变量
description: 了解如何使用Adobe Analytics作为行为数据源，从 [!DNL Target] Recommendations中的Analytics使用基于视图和/或基于购买的行为数据。
title: 如何将Adobe Analytics与 [!DNL Target] Recommendations一起使用？
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 1%

---

# 将Adobe Analytics与Recommendations结合使用

使用[!DNL Adobe Analytics]作为行为数据源使客户能够使用[!DNL Adobe Target]推荐活动中[!DNL Analytics]中基于视图和/或基于购买的行为数据。 在[!DNL Target Recommendations]设置是新设置且[!DNL Analytics]有大量历史数据可利用的情况下，此功能特别有用。

使用[!DNL Analytics]作为行为数据源可以充当有关用户行为的丰富信息源。 这可能包括来自仅与[!DNL Analytics]共享的第三方源或源的数据。

在Recommendations中[创建条件](/help/c-recommendations/c-algorithms/create-new-algorithm.md)时，有两个单选按钮可供您选择要使用的数据源：[!UICONTROL mboxes]或[!UICONTROL Analytics]。

![行为数据源按钮](/help/c-recommendations/c-algorithms/assets/behavioral-data-source.png)

>[!NOTE]
>
>如果帐户中未显示这两个按钮，请联系[客户关怀](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

## 分析数据在目标中的使用案例

使用[!DNL Analytics]作为推荐的行为数据源还提供部署特定用例的能力，而无需使用所有[!DNL Target]实体参数标记实体页面。 尽管这要求具备某些先决条件，但“产品变量”的可用性是该功能无缝工作的最重要因素。 常规eVar和Prop不足以使此握手在[!DNL Analytics]和[!DNL Target]之间自动发生。

可以使用[!DNL Analytics]作为行为数据源来：

* 根据上个月其他用户从同一类别购买的内容，使用Analytics数据，在零售网站上向PDP页面上的用户显示推荐。
* 根据[!DNL Analytics]数据，在媒体站点的主屏幕上显示有关当前趋势特定类别中最受欢迎内容的内容。

## 在Analytics中实施

以下几节将帮助您在[!DNL Analytics]端实现此功能。

### 先决条件：在Analytics中设置产品变量

您必须在[!DNL Analytics]中实现产品变量，并使用[!DNL Target Recommendations]所需的必要属性。

[!DNL Target Recommendations]示例源格式将作为指南，在此指南中，所有属性都需要在产品变量中定义。 以后，这些值必须在[!DNL Target] UI中为相应的[!DNL Target]实体值“mapped”。

>[!NOTE]
>
>如果内容站点，则相应的内容片段必须被视为有关该内容的“产品”和关联属性(例如：作者姓名、发布日期、内容标题、发布月等。) 必须作为属性传递。 类别级别或类别类型的粒度应由业务根据用例要求决定。

有关如何设置产品变量的详细信息，请参阅&#x200B;*Analytics实施指南*&#x200B;中的[products](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html)。 该文档中的一些注释需要部署团队的酌情处理(例如：类别)。 在执行此活动之前，始终建议与Adobe协商。

### 注意事项

[!DNL Analytics] 数据通过每日馈送发送。行为结果将在您网站上的推荐结果中反映，最长需要24小时。 与所有[!DNL Recommendations]条件设置一样，此数据源可以而且应该进行测试。

为了快速决策要使用哪个数据源，如果用户每天生成大量有机数据，而对历史数据的依赖性不大，那么使用[!DNL Target] mbox作为行为数据源就很合适。 如果最近生成的有机数据可用性较低，如果您希望存储[!DNL Analytics]数据，则使用[!DNL Analytics]作为行为数据源是一个不错的选择。

现在，是时候在[!DNL Target]端映射这些变量，以持续提供行为数据了。

## 在目标中实施

1. 在目标中，单击&#x200B;**[!UICONTROL Recommendations]**，然后单击&#x200B;**[!UICONTROL 源]**&#x200B;选项卡。

   ![信息源](/help/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. 单击&#x200B;**[!UICONTROL 创建源]**。

1. 选择&#x200B;**[!UICONTROL 分析分类]**，然后指定报表包。

   ![分析分类选项](/help/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. 单击&#x200B;**[!UICONTROL 映射]**，然后将字段列标题映射到相应的[!UICONTROL Recommendations]字段名称。

   ![映射节](/help/c-recommendations/c-algorithms/assets/mapping.png)

1. 单击&#x200B;**[!UICONTROL 保存]**。

## 常见问题解答

在将[!DNL Analytics]与[!DNL Target]一起使用时，请考虑以下常见问题：

### 在[!DNL Target] mbox调用中传递的`entity.id`和`entity.categoryId`值是否必需？

是，这两个值仍为必需。 其余属性可通过[!DNL Analytics]源传递，如本文档所述。

### 我是否可以使用动态包含规则（如实体参数）来使用[!DNL Analytics]源方法来匹配用户档案属性？

是的，你可以。 当使用[!DNL Target]独立时，此方法类似。 但在这种情况下，您必须注意时间因素。 应与用户档案变量匹配的实体变量取决于可能在页面稍后出现的数据层。
