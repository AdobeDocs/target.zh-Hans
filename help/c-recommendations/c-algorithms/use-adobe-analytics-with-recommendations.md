---
keywords: 行为数据源；分析；推荐；标准；产品变量
description: 了解如何使用Adobe Analytics作为行为数据源，从Recommendations目标的Analytics中使用基于视图和／或基于购买的行为数据。
title: 我如何将Adobe Analytics与目标·Recommendations结合使用？
feature: Recommendations
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '1035'
ht-degree: 3%

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

### 部署步骤

假定所有先决条件都已到位，[!DNL Adobe Target Recommendations]团队必须执行以下任务:

>[!IMPORTANT]
>
>以下步骤仅供说明。 [!DNL Recommendations]团队的成员当前必须执行这些步骤。 [有关详细信息，请联系 Customer Care。](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)

1. 在[!DNL Target]中，单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 实施]**&#x200B;以获取您的[!DNL Target]客户端代码。

   ![客户端代码](/help/c-recommendations/c-algorithms/assets/client-code.png)

1. 获取您的[!DNL Analytics]报表包。

   使用[!DNL Analytics]生产站点报告套件。 这是跟踪已部署[!DNL Recommendations]的站点的报表包。

1. 在[!DNL Analytics]中，单击&#x200B;**[!UICONTROL 管理员]** > **[!UICONTROL 数据源]**。

   ![“设置”>“数据源”](/help/c-recommendations/c-algorithms/assets/data-feed.png)

1. 单击&#x200B;**[!UICONTROL 添加]**&#x200B;以创建新源。

   ![添加源](/help/c-recommendations/c-algorithms/assets/add-feed.png)

1. 填写信息源：

   * **名称**:Recs Prod Feed
   * **报表包**:您的预定报告套件
   * **电子邮件**:为管理员用户指定任何适当的地址
   * **源间隔**:选择所需的间隔
   * **延迟处理**:没有延迟。
   * **开始和结束日期**:连续供给

   ![信息源部分](/help/c-recommendations/c-algorithms/assets/feed-information.png)

1. 填写&#x200B;**[!UICONTROL Destination]**&#x200B;部分的详细信息：

   >[!NOTE]
   > 
   >执行此步骤前，请咨询[!DNL Adobe Analytics]团队。

   * **类型**:FTP
   * **Host**: `xxx.yyy.com`
   * **路径**:您的 [!DNL Target] 客户代码
   * **用户名**:指定您的用户名
   * **密码**:指定密码

   屏幕截图仅供参考。 您的部署将具有不同的凭据。 执行此步骤时，请咨询[!DNL Adobe Analytics]团队或客户关怀。

   ![目标部分](/help/c-recommendations/c-algorithms/assets/destination.png)

1. 填写&#x200B;**[!UICONTROL 数据列]**&#x200B;定义：

   * **压缩格式**:Gzip
   * **打包类型**:单个文件
   * **清单：完** 成文件

      ![压缩格式、打包类型和清单设置](/help/c-recommendations/c-algorithms/assets/compression.png)

   * **包含的列**:

      >[!IMPORTANT]
      >
      >必须按此处说明的相同顺序添加列。 按以下顺序选择列，然后单击每列的&#x200B;**[!UICONTROL 添加]**。

      * hit_time_gmt
      * visid_high
      * visid_low
      * event_list
      * product_list
      * visit_num

1. 单击&#x200B;**[!UICONTROL 保存]**。

   ![数据列定义部分](/help/c-recommendations/c-algorithms/assets/data-column-definitions.png)

这样，在[!DNL Analytics]端的设置就完成了。 现在，是时候在[!DNL Target]端映射这些变量，以持续提供行为数据了。

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

