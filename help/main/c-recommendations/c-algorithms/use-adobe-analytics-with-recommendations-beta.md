---
keywords: 行为数据源；Analytics；推荐；标准；产品变量
description: 了解如何将 [!DNL Adobe Analytics] 用作 [!DNL Target Recommendations]中的行为数据源。
title: 如何将 [!DNL Adobe Analytics] 与 [!DNL Target Recommendations]一起使用？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="请参阅Target Premium中包含的内容。"
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: 6d2a313b0e54aa5f6717eee850c79e4092309e7d
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 0%

---

# 将[!DNL Adobe Analytics]与[!DNL Recommendations]一起使用

将[!DNL Adobe Analytics]用作行为数据源可让客户端在[!DNL Adobe Target Recommendations]活动中使用[!DNL Analytics]中基于视图和基于购买的行为数据。 此功能在[!DNL Target Recommendations]设置是新的，且[!DNL Analytics]有许多历史数据可供使用的情况下特别有用。

将[!DNL Analytics]用作行为数据源可以充当有关用户行为的丰富信息源。 此信息可能包含来自仅与[!DNL Analytics]共享的第三方源或馈送的数据。

在[!DNL Recommendations]中[创建标准](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md)时，有两个单选按钮可让您选择要使用的数据源： [!UICONTROL mboxes]或[!UICONTROL Analytics]。 要创建标准，请单击[!UICONTROL Recommendations] > [!UICONTROL Criteria] > [!UICONTROL Create Criteria] > [!UICONTROL Create Criteria]。 有关详细信息，请参阅[创建标准](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md)。

>[!NOTE]
>
>如果这两个按钮未显示在您的帐户中，请联系[客户关怀](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

## [!DNL Target]中[!DNL Analytics]数据的用例

使用[!DNL Analytics]作为推荐的行为数据源还可让您部署特定的用例，而无需使用所有[!DNL Target]实体参数标记实体页面。 尽管这要求具备某些先决条件，但要使此功能无缝运行，“产品变量”的可用性是最重要的因素。 常规eVar和Prop不足以在[!DNL Analytics]和[!DNL Target]之间自动进行此握手。

您可以使用[!DNL Analytics]作为行为数据源来：

* 使用[!DNL Analytics]数据，根据上个月其他用户从同一类别中购买的内容，在产品详细信息页面上向用户显示零售网站上的推荐。
* 基于[!DNL Analytics]数据，在媒体网站的主屏幕上显示当前趋势特定类别中最受欢迎内容的内容。

## [!DNL Analytics]中的实现

以下部分可帮助您在[!DNL Analytics]端实施此功能。

### 先决条件：在[!DNL Analytics]中设置产品变量

使用[!DNL Target Recommendations]所需的必要特性在[!DNL Analytics]中实施产品变量。

[!DNL Target Recommendations]示例信息源格式用作指南，必须在其产品变量中定义所有属性。 之后，必须在[!DNL Target] UI中为相应的[!DNL Target]实体值“映射”这些值。

>[!NOTE]
>
>如果它是内容网站，则必须将相应的内容片段视为“产品”，并且必须将该内容的关联属性作为属性传递。 此类属性可以包括作者姓名、发布日期、内容标题、发布月份等。 类别级别的粒度或类别类型，应由业务根据用例需求来决定。

有关如何设置产品变量的更多详细信息，请参阅“*实施Adobe Analytics*”指南中的[产品](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html)。 该文档中的一些注释需要部署该文档的团队自行决定（例如：类别）。 在执行此活动之前，始终建议咨询[!DNL Adobe]。

### 注意事项

[!DNL Analytics]数据通过每日馈送发送。 行为结果可能需要24小时才能反映在您网站上的推荐结果中。 与所有[!DNL Recommendations]标准设置一样，可以也应该测试此数据源。

对于使用哪个数据源的快速决策，如果用户每天生成的有机数据很多，并且不需要太多依赖历史数据，则使用[!DNL Target] mbox作为行为数据源可能非常合适。 如果最近生成的有机数据可用性较低，则如果要基于[!DNL Analytics]数据进行存储，则使用[!DNL Analytics]作为行为数据源非常合适。

现在是在[!DNL Target]端映射这些变量以连续提供行为数据的时候了。

## 在[!DNL Target]中实施

1. 在[!DNL Target]中，单击&#x200B;**[!UICONTROL Recommendations]**，然后单击&#x200B;**[!UICONTROL Feeds]**&#x200B;选项卡。

1. 单击 **[!UICONTROL Create Feed]**。

1. 选择&#x200B;**[!UICONTROL Analytics Classifications]**，然后指定报表包。

1. 单击&#x200B;**[!UICONTROL Next]**&#x200B;以前进到&#x200B;**[!UICONTROL Schedule]**&#x200B;设置，为信息源选择频率段：

   * [!UICONTROL Daily]
   * [!UICONTROL Weekly]
   * [!UICONTROL Every 2 weeks]
   * [!UICONTROL Never]

   您还可以选择一天中信息源要处理的时间。

1. 单击&#x200B;**[!UICONTROL Next]**&#x200B;以前进到&#x200B;**[!UICONTROL Mapping]**&#x200B;设置，然后将字段列标题映射到相应的[!UICONTROL Recommendations]字段名称。

1. 单击 **[!UICONTROL Save]**。

## 常见问题解答

在将[!DNL Analytics]与[!DNL Target]结合使用时，请考虑以下常见问题解答：

### 是否需要在[!DNL Target] mbox调用中传递`entity.id`和`entity.categoryId`值？

是的，仍需要这两个值。 其余属性可以通过[!DNL Analytics]信息源进行传递，如本文档中所述。

### 我能否使用动态包含规则，例如实体参数是否与使用[!DNL Analytics]信息源方法的配置文件属性相匹配？

是的，你可以。 使用[!DNL Target]独立时的方法类似。 但是，在这种情况下，您必须注意时间因素。 应该与配置文件变量匹配的实体变量取决于数据层，该数据层可能会在页面上稍后出现。