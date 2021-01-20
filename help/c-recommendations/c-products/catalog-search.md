---
keywords: catalog search;catalog;search;exclusion;collection;filter
description: 了解如何使用Recommendations目录搜索找到产品或内容、创建集合或排除、从目录中删除项目等。
title: 如何使用Recommendations目录搜索
feature: Recommendations
translation-type: tm+mt
source-git-commit: 1d31bf9474f817827e9be9f515ae5d06fae0cb2a
workflow-type: tm+mt
source-wordcount: '1031'
ht-degree: 17%

---


# ![PREMIUMCatalog](/help/assets/premium.png) 搜索

[!DNL Adobe Recommendations]中的[!UICONTROL 目录搜索]页面可帮助您在目录中找到产品或内容。 在此页面上可以执行的最基本任务是搜索项目。 此外，您还可以更改环境、将搜索结果保存到集合或排除项、添加筛选彩块化、修改表中的列、添加新搜索彩块化等。

目录是指您的整个产品集（实体）。 您的目录可以包含许多集合，这是一种在逻辑桶中组织产品的方式。

## 访问目录搜索

要访问[!UICONTROL 目录搜索]页，请单击&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL 目录搜索]**。

![“目录搜索”页](/help/c-recommendations/c-products/assets/catalog-search.png)

## 搜索项目

您可以使用简单搜索或高级搜索在目录中查找项目。

### 执行简单搜索

1. 在&#x200B;**[!UICONTROL 搜索产品]**&#x200B;字段中键入搜索词。

1. （可选）您可以通过从选项菜单中选择搜索选项来细化搜索，当您单击搜索字段中的向下箭头时，会显示该选项。

   ![](assets/searchproductsmenu.png)

   搜索选项包括：

   * ALL -使用OR逻辑在所有其他搜索条件中搜索。
   * 名称
   * 品牌
   * 类别
   * ID
   * 消息

1. 您现在可以滚动浏览搜索结果中的项目，查看视图缩略图和其他产品信息。

   下图显示了使用“全部”选项“自行车”的结果。

   ![Catalog Search for bike](/help/c-recommendations/c-products/assets/bike-results.png)

   “产品”旁边显示的数字表示指定环境的可用产品总数中与搜索词相匹配的产品数量。

   请注意，您可以使用搜索自动完成功能。 在下图中，键入“bik”将返回包含“bike”一词的所有产品。

   ![搜索自动完成](/help/c-recommendations/c-products/assets/bike-results-2.png)

   >[!NOTE]
   >
   >当您使用数字值对自定义属性执行目录搜索时，结果会将自定义属性视为字符串类型而不是数字值。
   >
   >目前，没有可用的功能允许您更改属性的类型。 要进行更改，请[打开一个引用需要类型从字符串更改为数字的属性的客户问题](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

1. 您还可以使用过滤器来查找所需的产品。 在以下示例中，通过展开[!UICONTROL 集合]彩块并选择“自行车工具”，目录中显示的所有自行车工具。

   ![自行车工具](/help/c-recommendations/c-products/assets/bike-results-3.png)

1. 您可以通过输入搜索词（例如“链”）在结果列表中进一步搜索。

   ![搜索链](/help/c-recommendations/c-products/assets/bike-results-4.png)

### 执行高级搜索{#advanced-search}

您可以使用[!UICONTROL 高级搜索]进一步优化搜索结果或将搜索结果另存为[集合](/help/c-recommendations/c-products/collections.md)或[排除](/help/c-recommendations/c-products/exclusions.md)。

1. 单击&#x200B;**[!UICONTROL 高级搜索]**&#x200B;链接。

   ![高级搜索页](/help/c-recommendations/c-products/assets/advances-search.png)

1. 使用下拉列表指定搜索的参数、运算符和值。

1. （可选）单击&#x200B;**[!UICONTROL 添加规则]**&#x200B;以添加其他搜索规则。

   每个附加搜索规则都与AND运算符相连。

1.  单击&#x200B;**[!UICONTROL 搜索]**。

1. （可选）单击“另存为&#x200B;]**”，然后单击“集合”**[!UICONTROL “集合”]**或“排除”**[!UICONTROL 。****

   ![另存为选项](/help/c-recommendations/c-products/assets/save-as.png)

   有关详细信息，请参阅下面的[根据高级搜索创建集合或排除。](#save-as)

## 视图项的详细信息

您可以通过查看单个项目的详细信息来视图其详细信息，包括ID、名称、消息、类别等。

1. 单击搜索结果中的项以视图其详细信息。

   ![产品详细信息](/help/c-recommendations/c-products/assets/bike-results-5.png)

## 从目录中删除项目

1. 单击搜索结果中的项以视图其详细信息。

1. 单击&#x200B;**[!UICONTROL 从目录]**&#x200B;中删除。

1. 确认要删除项目。

有关该项目的所有信息都将从目录索引中删除。 只有在数据源中再次添加该项目时，该项目才会包含在您的目录中。 已删除的项目必须从源中单独删除。

## 刷新目录

上传第一个源时，将自动创建目录的索引，并根据[指定的计划](/help/c-recommendations/c-products/feeds.md#steps)刷新。

通过信息源文件、API 或 mbox 更新接收更新时，目录将自动刷新。更新通常在一小时内完成。如果更新正在进行，则显示最近的更新开始时间。如果没有正在进行的更新，则显示最近的更新开始时间和结束时间。

## 基于高级搜索创建收藏集或排除项 {#save-as}

您可以使用“目录搜索”页面上的“高级搜索”（[](/help/c-recommendations/c-products/collections.md)[](/help/c-recommendations/c-products/exclusions.md)推荐[!UICONTROL  > ]目录搜索[!UICONTROL  > ]高级搜索[!UICONTROL ）来创建]收藏集[!UICONTROL 或]排除项。

1. 执行[高级搜索](#advanced-search)。

1. 单击&#x200B;**[!UICONTROL 另存为]**，然后单击&#x200B;**[!UICONTROL 集合]**&#x200B;或&#x200B;**[!UICONTROL 排除]**。

   ![另存为选项](/help/c-recommendations/c-products/assets/save-as.png)

   >[!IMPORTANT]
   >
   >[!UICONTROL 高级搜索]功能不区分大小写；但是，在投放时返回的产品基于区分大小写的搜索。 这种不匹配可能会导致产生混淆。使用[!UICONTROL 高级搜索]功能根据结果创建集合或排除时，请确保考虑区分大小写。 例如，如果您搜索“Holiday”，初始搜索会列出包含“Holiday”和“holiday”的结果。如果您随后创建一个目录，以用于返回包含“holiday”的产品，则只会返回包含“holiday”的产品，而不会返回包含“Holiday”的产品。可以采用类似的方式处理排除项。

## 更改环境

[环](/help/administrating-target/environments.md) 境允许您组织站点和预制作环境，以便轻松管理和分离报告。

1. 单击环境链接。

   ![环境链接](/help/c-recommendations/c-products/assets/environment.png)

1. 选择所需环境。

## 修改“目录搜索”页(过滤器和列)

您可以临时修改当前会话的[!UICONTROL 目录搜索]页面上的可用过滤器和列。

### 修改过滤器

您可以向[!UICONTROL 目录搜索]页面添加其他筛选器彩块化。

1. 在&#x200B;**[!UICONTROL 过滤器]**&#x200B;面板中，单击&#x200B;**[!UICONTROL 修改]**。

   ![修改过滤器链接](/help/c-recommendations/c-products/assets/modify-filters.png)

1. 选择所需的搜索彩块化（ID、名称、消息等），然后单击&#x200B;**[!UICONTROL 保存]**。

   ![添加过滤器](/help/c-recommendations/c-products/assets/add-filters.png)

请记住，附加的筛选器彩块化仅在当前会话中可用。

### 修改列

您可以临时修改[!UICONTROL 目录搜索]页面上的活动列。

1. 单击&#x200B;**[!UICONTROL 列]**&#x200B;链接。

   ![列选项](/help/c-recommendations/c-products/assets/columns.png)

1. （视情况而定）要重新排序活动列的顺序，请按所需顺序拖放&#x200B;**[!UICONTROL 活动列]**&#x200B;部分中的列。

1. （视情况而定）根据需要将项目从&#x200B;**[!UICONTROL 活动列]**&#x200B;拖放到&#x200B;**[!UICONTROL 非活动列]**（反之亦然）。

   还可以单击要从活动部分移动到非活动部分的列旁边的删除图标(x)。

请记住，您所做的任何更改只适用于当前会话。

