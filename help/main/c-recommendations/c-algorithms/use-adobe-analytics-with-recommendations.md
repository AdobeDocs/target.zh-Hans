---
keywords: 行为数据源；Analytics；推荐；标准；产品变量
description: 了解如何使用 [!DNL Adobe Analytics] 作为行为数据源，以使用来自的基于视图和/或基于购买的行为数据 [!DNL Analytics] 在 [!DNL Target Recommendations].
title: 如何使用 [!DNL Adobe Analytics] 替换为 [!DNL Target Recommendations]？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 2%

---

# 使用 [!DNL Adobe Analytics] 替换为 [!DNL Recommendations]

使用 [!DNL Adobe Analytics] 作为行为数据源，客户端可以从中使用基于视图和/或基于购买的行为数据 [!DNL Analytics] 在 [!DNL Adobe Target] [!DNL Recommendations] 活动。 此功能在以下情况下特别有用： [!DNL Target Recommendations] 设置是新的，并且 [!DNL Analytics] 有许多历史数据可供使用。

使用 [!DNL Analytics] 因为行为数据源可以充当有关用户行为的丰富信息源。 此信息可能包括来自仅与共享的第三方源或馈送的数据 [!DNL Analytics].

While [创建标准](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md) 在 [!DNL Recommendations]，您可以通过两个单选按钮选择要使用的数据源： [!UICONTROL mbox] 或 [!UICONTROL 分析]. 要创建标准，请单击 [!UICONTROL Recommendations] > [!UICONTROL 标准] > [!UICONTROL 创建标准] > [!UICONTROL 创建标准]. 有关更多信息，请参阅[创建标准](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md)。

![行为数据源按钮](assets/behavioral-data-source.png)

>[!NOTE]
>
>如果这两个按钮未显示在您的帐户中，请联系 [客户关怀](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

## Target中的Analytics数据用例

使用 [!DNL Analytics] 作为推荐的行为数据源，您还可以部署特定的用例，而无需使用所有 [!DNL Target] 实体参数。 虽然这要求具备某些先决条件，但要使此功能无缝工作，“产品变量”的可用性最为重要。 常规eVar和Prop不足以让此握手在两次握手之间自动发生 [!DNL Analytics] 和 [!DNL Target].

您可以使用 [!DNL Analytics] 作为行为数据源：

* 根据上个月其他用户从同一类别中购买的内容，在产品详细信息页面上向用户显示零售网站上的推荐，使用 [!DNL Analytics] 数据。
* 在媒体网站的主屏幕上显示特定类别中最受欢迎的内容（基于当前趋势） [!DNL Analytics] 数据。

## 中的实施 [!DNL Analytics]

以下部分可帮助您在 [!DNL Analytics] 侧面。

### 先决条件：在中设置产品变量 [!DNL Analytics]

在中实施产品变量 [!DNL Analytics] 具有所需的必要属性 [!DNL Target Recommendations].

A [!DNL Target Recommendations] 示例信息源格式用作指南，必须在其产品变量中定义所有属性。 之后，必须在中“映射”这些值 [!DNL Target] 相应的UI [!DNL Target] 实体值。

>[!NOTE]
>
>如果它是内容网站，则必须将相应的内容片段视为“产品”，并且必须将该内容的关联属性作为属性传递。 此类属性可以包括作者姓名、发布日期、内容标题、发布月份等。 类别级别的粒度或类别类型，应由业务根据用例要求确定。

有关如何设置产品变量的更多详细信息，请参阅 [产品](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html) 在 *实施Adobe Analytics* 指南。 该文档中的一些注释需要部署它的团队自行决定（例如：类别）。 始终建议咨询 [!DNL Adobe] ，然后再开始此活动。

### 注意事项

[!DNL Analytics] 数据通过每日馈送发送。 行为结果可能需要24小时才能反映在您网站上的推荐结果中。 与所有项目一样 [!DNL Recommendations] 标准设置，可以也应该测试此数据源。

为了快速决策要使用哪个数据源，如果用户每天生成很多有机数据，并且不需要太多依赖历史数据，则使用 [!DNL Target] mbox作为行为数据源非常适合。 如果最近生成的有机数据可用性较低，且您想要根据以下条件进行存放 [!DNL Analytics] 数据，然后使用 [!DNL Analytics] 因为行为数据源非常适合。

现在应该将这些变量映射到 [!DNL Target] 用于持续提供行为数据端。

## 在中实施 [!DNL Target]

1. In [!DNL Target]，单击 **[!UICONTROL Recommendations]**，然后单击 **[!UICONTROL 信息源]** 选项卡。

   ![信息源](/help/main/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. 单击 **[!UICONTROL 创建信息源]**.

1. 选择 **[!UICONTROL Analytics分类]**，然后指定报表包。

   ![Analytics分类选项](/help/main/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. 单击 **[!UICONTROL 下一个]** 以前进到 **[!UICONTROL 计划]** 设置，选择馈送的频段：

   * [!UICONTROL 每日]
   * [!UICONTROL 每周]
   * [!UICONTROL 每2周]
   * [!UICONTROL 从不]

   您还可以选择一天中信息源处理的时间。

1. 单击 **[!UICONTROL 下一个]** 以前进到  **[!UICONTROL 映射]** 设置，然后将字段列标题映射到相应的标题 [!UICONTROL Recommendations] 字段名称。

   ![映射部分](/help/main/c-recommendations/c-algorithms/assets/mapping.png)

1. 单击&#x200B;**[!UICONTROL 保存]**。

## 常见问题解答

在使用时请考虑以下常见问题 [!DNL Analytics] 替换为 [!DNL Target]：

### 是 `entity.id` 和 `entity.categoryId` 值需要在 [!DNL Target] mbox调用？

是，仍需要这两个值。 其余属性可以通过 [!DNL Analytics] 信息源，如本文档中所述。

### 我可以使用动态包含规则吗？例如，实体参数是否与配置文件属性匹配？ [!DNL Analytics] 馈送方式？

是的，你可以。 使用时，方法类似 [!DNL Target] 独立。 但是，在这种情况下，您必须注意时间因素。 应该与配置文件变量匹配的实体变量取决于可能在页面上稍后显示的数据层。
