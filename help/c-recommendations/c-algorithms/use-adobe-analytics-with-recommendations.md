---
keywords: behavioral data source;analytics;recommendations;criteria;product variables
description: 使用Adobe Analytics作为行为数据源，客户可以使用Adobe RecommendationsAnalytics提供的基于视图和／或基于购买的行为数据。
title: 将Adobe Analytics与目标·Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: abe28722199c74c8b57dbfd0ca893dbf2e862cad
workflow-type: tm+mt
source-wordcount: '875'
ht-degree: 2%

---


# Adobe Analytics与Recommendations

使 [!DNL Adobe Analytics] 用作为行为数据源使客户能够使用推荐活动中基于视图和／或基于购买的 [!DNL Analytics] 行为 [!DNL Adobe Target] 数据。 此功能在设置为新的并且有 [!DNL Target Recommendations] 大量历史数据 [!DNL Analytics] 可利用的情况下尤其有用。

使 [!DNL Analytics] 用作为行为数据源可以充当有关用户行为的丰富信息源。 这可能包括来自仅与共享的第三方源或源的数据 [!DNL Analytics]。

在 [Recommendations](/help/c-recommendations/c-algorithms/create-new-algorithm.md) ，创建条件时，有两个单选按钮可供您选择要使用的数据源： [!UICONTROL mbox] 或 [!UICONTROL Analytics]。

![行为数据源按钮](/help/c-recommendations/c-algorithms/assets/behavioral-data-source.png)

>[!NOTE]
>
>如果您的帐户中未显示这两个按钮，请联系客 [户关怀](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

## 用例

使 [!DNL Analytics] 用作为推荐的行为数据源还能够部署特定用例，而无需使用所有实体参数标记实体 [!DNL Target] 页面。 尽管这要求具备某些先决条件，但“产品变量”的可用性是该功能无缝工作的最重要因素。 常规eVar和Prop不足以使此握手在和之间自动 [!DNL Analytics] 发生 [!DNL Target]。

您可以 [!DNL Analytics] 用作行为数据源：

* 使用Analytics数据，根据上个月其他用户从同一类别购买的内容，在零售网站上向PDP页面上的用户显示推荐。
* 根据数据，在媒体站点的主屏幕上显示当前趋势特定类别中最受欢迎的内容 [!DNL Analytics] 。

## 在Analytics中实施

以下几节将帮助您在侧面实现此 [!DNL Analytics] 功能。

### 先决条件：Analytics中的产品变量

您必须在中实施产 [!DNL Analytics] 品变量，并使用必需的属性 [!DNL Target Recommendations]。

示 [!DNL Target Recommendations] 例源格式将作为指南，在该指南中需要在产品变量中定义所有属性。 以后，这些值必须在UI中“映 [!DNL Target] 射”相应的实 [!DNL Target] 体值。

>[!NOTE]
>
>如果它是内容站点，则相应的内容片段必须被视为有关该内容的“产品”和关联属性(例如：作者姓名、发布日期、内容标题、发布月份等。) 必须作为属性进行传递。 类别级别或类别类型的粒度应由业务根据用例要求确定。

有关如何设置产品变量的更多详细信息，请参 [阅](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/products.html) 《Analytics实施 *指南》中的产品*。 该文档中的一些注释需要部署团队的酌情决定(例如：类别)。 在执行此活动之前，始终建议与Adobe协商。

### 注意事项

[!DNL Analytics] 数据通过每日源发送。 行为结果将在24小时内反映在网站上的推荐结果中。 与所有条 [!DNL Recommendations] 件设置一样，此数据源可以而且应该进行测试。

为了快速决策要使用哪个数据源，如果用户每天生成的有机数据很多，对历史数据的依赖性不大，那么使用mbox作为行为数据源是很合适的。 [!DNL Target] 如果最近生成的有机数据可用性较低，如果您想要存储 [!DNL Analytics] 数据，则 [!DNL Analytics] 使用行为数据源是一个不错的选择。

### 部署步骤

假定所有先决条件均已到位，请执行以下任务:

1. 在中 [!DNL Target]，单击 **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** (管理>实 [!DNL Target] 施)以获取您的客户端代码。

   ![客户端代码](/help/c-recommendations/c-algorithms/assets/client-code.png)

1. 获取您 [!DNL Analytics] 的报表包。

   使用您 [!DNL Analytics] 的生产站点报告套件。 这是跟踪您已部署的站点的报表 [!DNL Recommendations] 包。

1. 在中， [!DNL Analytics]单击“管 **[!UICONTROL 理]** ”> **[!UICONTROL “数据源]**”。

   ![“设置”>“数据源”](/help/c-recommendations/c-algorithms/assets/data-feed.png)

1. Click **[!UICONTROL Add]** to create a new feed.

   ![添加源](/help/c-recommendations/c-algorithms/assets/add-feed.png)

1. 填写信息源：

   * **名称**:Recs Prod Feed
   * **报表包**:您的预定报告套件
   * **电子邮件**:为管理员用户指定任何适当的地址
   * **源间隔**:选择所需的间隔
   * **延迟处理**:没有延迟。
   * **开始和结束日期**:连续供给

   ![信息源部分](/help/c-recommendations/c-algorithms/assets/feed-information.png)

1. Fill in the details in the **[!UICONTROL Destination]** section:

   >[!NOTE]
   > 
   >执行此步 [!DNL Adobe Analytics] 骤前，请咨询团队。

   * **类型**:FTP
   * **主持人**:xxx.yyy.com
   * **路径**:您的目标客户端代码
   * **用户名**:xxyy
   * **密码**:xxxxxxxxx

   屏幕截图仅供参考。 您的部署将具有不同的凭据。 执行此步 [!DNL Adobe Analytics] 骤时，请咨询团队或客户关怀。

   ![目标部分](/help/c-recommendations/c-algorithms/assets/destination.png)

1. 填写“数 **[!UICONTROL 据列]** ”定义：

   * **压缩格式**:Gzip
   * **打包类型**: 单个文件
   * **清单：** 完成文件

      ![压缩格式、打包类型和清单设置](/help/c-recommendations/c-algorithms/assets/compression.png)

   * **包含的列**:

      >[!IMPORTANT]
      >
      >必须按此处说明的相同顺序添加列。 按照以下顺序选择列，然后单 **[!UICONTROL 击]** “添加”。

      * hit_time_gmt
      * visid_high
      * visid_low
      * event_list
      * product_list
      * visit_num

1. 单击&#x200B;**[!UICONTROL 保存]**。

   ![数据列定义部分](/help/c-recommendations/c-algorithms/assets/data-column-definitions.png)

这样，侧面的设置 [!DNL Analytics] 就完成了。 现在，是时候将这些变量并 [!DNL Target] 排，以持续提供行为数据了。

## 在目标中实施

1. 在目标中，单 **[!UICONTROL 击]**“Recommendations”，然 **[!UICONTROL 后单击]** “源”。

   ![信息源](/help/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. 单击 **[!UICONTROL 创建源]**。

1. 选择 **[!UICONTROL 分析分类]**，然后指定报表包。

   ![分析分类选项](/help/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. 单击 **[!UICONTROL “映射]**”，然后将字段列标题映射到相应的 [!UICONTROL Recommendations] 字段名称。

   ![映射节](/help/c-recommendations/c-algorithms/assets/mapping.png)

1. 单击&#x200B;**[!UICONTROL 保存]**。