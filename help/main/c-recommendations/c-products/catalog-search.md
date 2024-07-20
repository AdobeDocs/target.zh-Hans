---
keywords: 目录搜索；目录；搜索；排除项；收藏集；过滤器
description: 了解如何使用Recommendations目录搜索来查找产品或内容、创建收藏集或排除项，以及从目录中删除项目等。
title: 如何使用Recommendations目录搜索？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="请参阅Target Premium中包含的内容。"
feature: Recommendations
exl-id: 925fea97-e2c5-4883-84e3-fd357a8ee8d9
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '993'
ht-degree: 22%

---

# 目录搜索

[!DNL Adobe Recommendations]中的[!UICONTROL Catalog Search]页面可帮助您在目录中查找产品或内容。 您可以在此页面上执行的最基本任务是搜索项目。 此外，您还可以更改环境、将搜索结果保存到收藏集或排除项、添加过滤器Facet以及修改表中的列、添加新的搜索Facet等。

目录指代您的整个产品集（实体）。您的目录可以包含许多收藏集，这是一种在逻辑存储桶中组织产品的方法。

## 访问目录搜索

要访问[!UICONTROL Catalog Search]页面，请单击&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL Catalog Search]**。

![目录搜索页面](/help/main/c-recommendations/c-products/assets/catalog-search.png)

## 搜索项目

您可以使用简单搜索或高级搜索来查找目录中的项目。

### 执行简单搜索

1. 在&#x200B;**[!UICONTROL Search Products]**&#x200B;字段中键入搜索词。

1. （可选）您可以通过从选项菜单中选择搜索选项来优化搜索，单击搜索字段中的向下箭头时，会显示该选项菜单。

   ![searchproductsmenu图像](assets/searchproductsmenu.png)

   搜索选项包括：

   * ALL — 使用OR逻辑搜索所有其他搜索标准所产生的结果。
   * 名称
   * 品牌
   * 类别
   * ID
   * 消息

1. 您现在可以滚动查看搜索结果中的项目以查看缩略图和其他产品信息。

   下图显示了使用“全部”选项的“单车”结果。

   ![自行车目录搜索](/help/main/c-recommendations/c-products/assets/bike-results.png)

   “产品”旁边显示的数字表示指定环境的可用产品总数中与搜索词相匹配的产品数量。

   请注意，您可以使用搜索自动完成功能。 在下图中，键入“bik”将返回包含单词“bike”的所有产品。

   ![搜索自动完成](/help/main/c-recommendations/c-products/assets/bike-results-2.png)

   >[!NOTE]
   >
   >对具有数字值的自定义属性执行目录搜索时，结果将该自定义属性视为字符串类型，而非数字值。
   >
   >目前，没有可让您更改属性类型的功能。 要作出改变，请[提出客户问题](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)，其中引用需要将类型从字符串变为数字的属性。

1. 您还可以使用过滤器查找所需的产品。 在以下示例中，通过展开[!UICONTROL Collections]方面并选择“自行车工具”，目录中的所有自行车工具都会显示。

   ![自行车工具](/help/main/c-recommendations/c-products/assets/bike-results-3.png)

1. 您可以通过输入搜索词（例如“chain”），在结果列表中进一步搜索。

   ![搜索链](/help/main/c-recommendations/c-products/assets/bike-results-4.png)

### 执行高级搜索 {#advanced-search}

您可以使用[!UICONTROL Advanced Search]进一步优化搜索结果，或将搜索结果保存为[收藏集](/help/main/c-recommendations/c-products/collections.md)或[排除项](/help/main/c-recommendations/c-products/exclusions.md)。

1. 单击&#x200B;**[!UICONTROL Advanced Search]**&#x200B;链接。

   ![高级搜索页面](/help/main/c-recommendations/c-products/assets/advances-search.png)

1. 使用下拉列表为搜索指定参数、运算符和值。

1. （可选）单击&#x200B;**[!UICONTROL Add Rule]**&#x200B;以添加其他搜索规则。

   每个额外的搜索规则都使用AND运算符进行连接。

1. 单击 **[!UICONTROL Search]**。

1. （可选）单击&#x200B;**[!UICONTROL Save As]**，然后单击&#x200B;**[!UICONTROL Collection]**&#x200B;或&#x200B;**[!UICONTROL Exclusion]**。

   ![另存为选项](/help/main/c-recommendations/c-products/assets/save-as.png)

   有关详细信息，请参阅下面的[基于高级搜索创建收藏集或排除项](#save-as)。

## 查看项目的详细信息

您可以通过查看单个项目的详细信息来查看其详细信息，包括ID、名称、消息、类别等。

1. 单击搜索结果中的项目可查看其详细信息。

   ![产品详细信息](/help/main/c-recommendations/c-products/assets/bike-results-5.png)

## 从目录中删除项目

1. 单击搜索结果中的项目可查看其详细信息。

1. 单击 **[!UICONTROL Remove from Catalog]**。

1. 确认您要移除该项目。

从目录索引中删除有关该项的所有信息。 只有当该项目再次添加到数据馈送中时，它才会包含在您的目录中。 必须从信息源中单独删除已删除的项目。

## 刷新目录

上传第一个信息源时，将自动创建目录索引，并根据[指定的计划](/help/main/c-recommendations/c-products/feeds.md#steps)刷新。

通过信息源文件、API 或 mbox 更新接收更新时，目录将自动刷新。更新通常在一小时内完成。如果更新正在进行，则显示最近的更新开始时间。如果没有正在进行的更新，则显示最近的更新开始时间和结束时间。

## 基于高级搜索创建收藏集或排除项 {#save-as}

您可以在[!UICONTROL Catalog Search]页面([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search])上使用[!UICONTROL Advanced Search]创建[收藏集](/help/main/c-recommendations/c-products/collections.md)或[排除项](/help/main/c-recommendations/c-products/exclusions.md)。

1. 执行[高级搜索](#advanced-search)。

1. 单击&#x200B;**[!UICONTROL Save As]**，然后单击&#x200B;**[!UICONTROL Collection]**&#x200B;或&#x200B;**[!UICONTROL Exclusion]**。

   ![另存为选项](/help/main/c-recommendations/c-products/assets/save-as.png)

   >[!IMPORTANT]
   >
   >[!UICONTROL Advanced Search]功能不区分大小写；但是，在投放时返回的产品基于区分大小写的搜索。 这种不匹配可能会导致产生混淆。在使用[!UICONTROL Advanced Search]功能根据结果创建集合或排除项时，请确保考虑区分大小写。 例如，如果您搜索“Holiday”，初始搜索会列出包含“Holiday”和“holiday”的结果。如果您随后创建一个目录，以用于返回包含“holiday”的产品，则只会返回包含“holiday”的产品，而不会返回包含“Holiday”的产品。可以采用类似的方式处理排除项。

## 更改环境

[环境](/help/main/administrating-target/environments.md)允许您组织站点和生产前环境，以便轻松管理和分隔报表。

1. 单击环境链接。

   ![环境链接](/help/main/c-recommendations/c-products/assets/environment.png)

1. 选择所需的环境。

## 修改“目录搜索”页（过滤器和列）

您可以在当前会话的[!UICONTROL Catalog Search]页面上临时修改可用的筛选器和列。

### 修改筛选器

您可以将其他筛选器Facet添加到[!UICONTROL Catalog Search]页面。

1. 在&#x200B;**[!UICONTROL Filters]**&#x200B;面板中，单击&#x200B;**[!UICONTROL Modify]**。

   ![修改筛选器链接](/help/main/c-recommendations/c-products/assets/modify-filters.png)

1. 选择所需的搜索Facet（ID、名称、消息等），然后单击&#x200B;**[!UICONTROL Save]**。

   ![添加筛选器](/help/main/c-recommendations/c-products/assets/add-filters.png)

请记住，其他过滤器Facet仅在当前会话中可用。

### 修改列

您可以临时修改[!UICONTROL Catalog Search]页面上的活动列。

1. 单击&#x200B;**[!UICONTROL Columns]**&#x200B;链接。

   ![列选项](/help/main/c-recommendations/c-products/assets/columns.png)

1. （视情况而定）要重新排序活动列的顺序，请按所需顺序拖放&#x200B;**[!UICONTROL Active Columns]**&#x200B;部分中的列。

1. （视情况而定）根据需要将项目从&#x200B;**[!UICONTROL Active Columns]**&#x200B;拖放到&#x200B;**[!UICONTROL Inactive Columns]**（反之亦然）。

   您还可以单击要从活动区域移动到非活动区域的列旁边的删除图标( x )。

请记住，您所做的任何更改仅应用于当前会话。
