---
keywords: 行为数据源；分析；推荐；标准；产品变量
description: 了解如何使用Adobe Analytics作为行为数据源，从Recommendations目标的Analytics中使用基于视图和／或基于购买的行为数据。
title: 我如何将Adobe Analytics与目标·Recommendations结合使用？
feature: Recommendations
translation-type: tm+mt
source-git-commit: 87877502d25fe8da830f70126820d1ca825ebc9d
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 0%

---


# Adobe Analytics与Recommendations

使用[!DNL Adobe Analytics]作为行为数据源，客户可以使用[!DNL Adobe Target]推荐活动中[!DNL Analytics]的基于视图和／或基于购买的行为数据。 此功能在[!DNL Target Recommendations]设置是新的并且[!DNL Analytics]有大量历史数据可利用的情况下尤其有用。

使用[!DNL Analytics]作为行为数据源可以充当有关用户行为的丰富信息源。 这可能包括来自仅与[!DNL Analytics]共享的第三方源或源的数据。

在Recommendations创建条件[时，有两个单选按钮可供您选择要使用的数据源：[!UICONTROL mboxes]或[!UICONTROL Analytics]。](/help/c-recommendations/c-algorithms/create-new-algorithm.md)

![行为数据源按钮](/help/c-recommendations/c-algorithms/assets/behavioral-data-source.png)

>[!NOTE]
>
>如果帐户中未显示这两个按钮，请联系[客户服务中心](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

## 目标中分析数据的使用案例

使用[!DNL Analytics]作为推荐的行为数据源还能够部署特定用例，而无需使用所有[!DNL Target]实体参数标记实体页面。 尽管这要求具备某些先决条件，但“产品变量”的可用性是该功能无缝工作的最重要因素。 常规eVar和Prop不足以使此握手在[!DNL Analytics]和[!DNL Target]之间自动发生。

可以使用[!DNL Analytics]作为行为数据源来：

* 使用Analytics数据，根据上个月其他用户从同一类别购买的内容，在零售网站上向PDP页面上的用户显示推荐。
* 根据[!DNL Analytics]数据，在媒体站点的主屏幕上显示当前趋势特定类别中最受欢迎的内容。

## 在Analytics中实施

以下各节将帮助您在[!DNL Analytics]端实现此功能。

### 先决条件：在Analytics中设置产品变量

必须在[!DNL Analytics]中实现产品变量，并使用[!DNL Target Recommendations]所需的必要属性。

[!DNL Target Recommendations]示例源格式将作为指南，在此指南中需要在产品变量中定义所有属性。 以后，这些值必须在[!DNL Target] UI中为相应的[!DNL Target]实体值“映射”。

>[!NOTE]
>
>如果它是内容站点，则相应的内容片段必须被视为有关该内容的“产品”和关联属性(例如：作者姓名、发布日期、内容标题、发布月份等。) 必须作为属性进行传递。 类别级别或类别类型的粒度应由业务根据用例要求确定。

有关如何设置产品变量的详细信息，请参阅&#x200B;*Analytics Implementation Guide*&#x200B;中的[products](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html)。 该文档中的一些注释需要部署团队的酌情决定(例如：类别)。 在执行此活动之前，始终建议与Adobe协商。

### 注意事项

[!DNL Analytics] 数据通过每日源发送。行为结果将在24小时内反映在网站上的推荐结果中。 与所有[!DNL Recommendations]条件设置一样，此数据源可以而且应该进行测试。

为了快速决策要使用哪个数据源，如果用户每天生成的有机数据很多，对历史数据的依赖性不大，那么使用[!DNL Target] mbox作为行为数据源是很合适的。 如果最近生成的有机数据可用性较低，如果要存储在[!DNL Analytics]数据上，则使用[!DNL Analytics]作为行为数据源是非常合适的。

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

### 在[!DNL Target] mbox调用中是否需要传递`entity.id`和`entity.categoryId`值？

是，这两个值仍是必需的。 其余属性可通过[!DNL Analytics]源进行传递，如本文档所述。

### 我是否可以使用动态包含规则（如实体参数）来使用[!DNL Analytics]供给方法匹配用户档案属性？

是的，你可以。 当使用[!DNL Target]独立时，该方法类似。 但是，在这种情况下，您必须注意时间因素。 与用户档案变量匹配的实体变量取决于稍后可能在页面上显示的数据层。

