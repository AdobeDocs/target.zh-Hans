---
keywords: 行为数据源；Analytics；推荐；标准；产品变量
description: 了解如何在[!DNL Target Recommendations]中使用[!DNL Adobe Analytics]作为行为数据源。
title: 将 Adobe Analytics 与推荐配合使用
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
TQID: 'https://experienceleague.adobe.com/2ryixOT-YoKjDlMbqs8g2DJElNVmlCUFhbdZzpfSnNs'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
source-git-commit: 374d176c5c40826d958a8b87d220422466433690
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 1%
---
# 将[!DNL Adobe Analytics]与[!DNL Recommendations]一起使用 {#use-analytics-with-recommendations}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何将[!DNL Adobe Analytics]用作[!DNL Adobe Target Recommendations]活动中的行为数据源。

>[!ENDSHADEBOX]

将[!DNL Adobe Analytics]用作行为数据源可允许[!DNL Adobe Target Recommendations]活动使用[!DNL Analytics]中基于视图和基于购买的行为数据。 当[!DNL Target Recommendations]设置是新的，并且[!DNL Analytics]有许多历史数据可供使用时，这将很有用。 数据可能还包括仅与[!DNL Analytics]共享的来自第三方源或馈送的信息。

在[!DNL Recommendations]中[创建标准](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#data-source)时，使用&#x200B;**[!UICONTROL 行为数据Source]**&#x200B;选项选择数据源： **[!UICONTROL Adobe Target]**&#x200B;或&#x200B;**[!UICONTROL Analytics]**。

>[!NOTE]
>
>如果这两个选项未显示在帐户中，请联系[客户关怀团队](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

## [!DNL Target]中[!DNL Analytics]数据的用例 {#use-cases}

将[!DNL Analytics]用作行为数据源还允许部署特定用例，而无需使用所有[!DNL Target]实体参数标记实体页面。 这需要满足某些先决条件，而“产品变量”的可用性是最重要的先决条件。 常规eVar和Prop不足以让[!DNL Analytics]和[!DNL Target]自动交换此数据。

[!DNL Analytics]可用作行为数据源，用于：

* 使用[!DNL Analytics]数据，根据上个月其他用户从同一类别中购买的内容，在产品详细信息页面上向用户显示零售网站上的推荐。
* 基于[!DNL Analytics]数据，在媒体网站的主屏幕上显示当前趋势特定类别中最受欢迎内容的内容。

## [!DNL Analytics]中的实现

### 先决条件：在[!DNL Analytics]中设置产品变量 {#prerequisites}

使用[!DNL Target Recommendations]所需的属性在[!DNL Analytics]中实施产品变量。 [!DNL Target Recommendations]示例信息源格式将指导必须在产品变量中定义哪些属性。 这些值必须稍后在[!DNL Target] UI中“映射”到相应的[!DNL Target]实体值。

>[!NOTE]
>
>如果它是内容网站，则必须将相应的内容片段视为“产品”，并且必须将该内容的关联属性作为属性传递。 此类属性可以包括作者姓名、发布日期、内容标题、发布月份等。 业务部门应根据用例的要求决定类别级别的粒度，或类别类型。

有关如何设置产品变量的更多详细信息，请参阅“*实施Adobe Analytics*”指南中的[产品](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html?lang=zh-Hans)。 该文档中的一些说明，例如有关类别的说明，需要部署该文档的团队做出判断。 建议先咨询[!DNL Adobe]再进行此活动。

### 注意事项 {#considerations}

[!DNL Analytics]数据通过每日馈送发送。 行为结果可能需要24小时才能反映在网站上的推荐结果中。 与所有[!DNL Recommendations]标准设置一样，应测试此数据源。

要选择数据源，请执行以下操作：

* 当用户每天生成大量有机数据并且几乎不需要依赖历史数据时，[!DNL Target] mbox非常适合。
* 当最近生成的有机数据较少且将使用[!DNL Analytics]数据时，[!DNL Analytics]非常适合。

仍必须在[!DNL Target] mbox调用中传递`entity.id`和`entity.categoryId`值。 其他属性可以通过[!DNL Analytics]馈送传递，如本页所述。

动态包含规则（例如将实体参数与配置文件属性进行匹配）可以与[!DNL Analytics]信息源方法一起使用。 此方法与使用[!DNL Target]独立方法类似，但必须考虑时间：应该匹配配置文件变量的实体变量取决于数据层，该数据层可能稍后出现在页面上。

## 在[!DNL Target]中实施 {#implement-target}

产品变量在[!DNL Target]中映射，以提供连续的行为数据供给。

1. 在[!DNL Target]中，单击&#x200B;**[!UICONTROL 推荐]**，然后单击&#x200B;**[!UICONTROL 信息源]**&#x200B;选项卡。

1. 单击&#x200B;**[!UICONTROL 创建信息源]**。

   ![突出显示“创建馈送”按钮的“馈送”页面](../assets/feeds_1.png)

1. Select **[!UICONTROL Analytics分类]**，然后指定报表包。

1. 单击&#x200B;**[!UICONTROL 下一步]**&#x200B;以前进到&#x200B;**[!UICONTROL 计划]**&#x200B;设置，然后为信息源选择一个频率： **[!UICONTROL 每日]**、**[!UICONTROL 每周]**、**[!UICONTROL 每两周]**&#x200B;或&#x200B;**[!UICONTROL 从不]**。 也可以选择每天处理馈送的时间。

   ![使用“频率”选项“每日”、“每周”、“每两周”和“从不”以及“时间”字段安排“创建信息源”对话框中的步骤](../assets/feeds_3.png)

1. 单击&#x200B;**[!UICONTROL 下一步]**&#x200B;前进到&#x200B;**[!UICONTROL 映射]**&#x200B;设置，然后将字段列标题映射到适当的&#x200B;**[!UICONTROL 推荐]**&#x200B;字段名称。

1. 单击&#x200B;**[!UICONTROL 保存]**。

有关创建馈送的详细信息，请参阅[创建馈送](/help/main/c-recommendations/c-products/feeds.md#steps)。
