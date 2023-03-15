---
keywords: 目录搜索；目录；搜索；排除项；收藏集；筛选器
description: 了解如何使用Recommendations目录搜索来查找产品或内容、创建收藏集或排除项、从目录中删除项目，等等。
title: 如何使用Recommendations目录搜索？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 925fea97-e2c5-4883-84e3-fd357a8ee8d9
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 23%

---

# 目录搜索

的 [!UICONTROL 目录搜索] 页面 [!DNL Adobe Recommendations] 可帮助您在目录中查找产品或内容。 在此页面上可以执行的最基本任务是搜索项目。 此外，您还可以更改环境、将搜索结果保存到收藏集或排除项、添加过滤器彩块化、修改表中的列、添加新的搜索彩块化等。

目录指代您的整个产品集（实体）。您的目录可以包含许多收藏集，这是一种在逻辑存储段中组织产品的方法。

## 访问目录搜索

访问 [!UICONTROL 目录搜索] 页面，单击 **[!UICONTROL Recommendations]** > **[!UICONTROL 目录搜索]**.

![“目录搜索”页面](/help/main/c-recommendations/c-products/assets/catalog-search.png)

## 搜索项目

您可以使用简单搜索或高级搜索在目录中查找项目。

### 执行简单搜索

1. 在 **[!UICONTROL 搜索产品]** 字段。

1. （可选）您可以优化搜索，方法是在单击搜索字段中的向下箭头时，从显示的选项菜单中选择搜索选项。

   ![searchproducts菜单图像](assets/searchproductsmenu.png)

   搜索选项包括：

   * ALL  — 使用OR逻辑搜索所有其他搜索标准的内容。
   * 名称
   * 品牌
   * 类别
   * ID
   * 消息

1. 您现在可以滚动浏览搜索结果中的项目，以查看缩略图和其他产品信息。

   下图显示了使用“全部”选项“自行车”的结果。

   ![自行车目录搜索](/help/main/c-recommendations/c-products/assets/bike-results.png)

   “产品”旁边显示的数字表示指定环境的可用产品总数中与搜索词相匹配的产品数量。

   请注意，您可以使用搜索自动完成功能。 在下图中，键入“bik”将返回包含“bike”一词的所有产品。

   ![搜索自动完成](/help/main/c-recommendations/c-products/assets/bike-results-2.png)

   >[!NOTE]
   >
   >对具有数字值的自定义属性执行目录搜索时，结果将该自定义属性视为字符串类型，而非数字值。
   >
   >目前，没有功能可让您更改属性类型。 要作出改变，请[提出客户问题](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)，其中引用需要将类型从字符串变为数字的属性。

1. 您还可以使用过滤器来查找所需的产品。 在以下示例中，通过将 [!UICONTROL 收藏集] facet和选择“Bike Tools”（自行车工具），目录显示中的所有自行车工具。

   ![自行车工具](/help/main/c-recommendations/c-products/assets/bike-results-3.png)

1. 您可以通过输入搜索词（例如“链”）在结果列表中进一步搜索。

   ![搜索链](/help/main/c-recommendations/c-products/assets/bike-results-4.png)

### 执行高级搜索 {#advanced-search}

您可以使用 [!UICONTROL 高级搜索] 以进一步优化搜索结果或将搜索结果保存为 [收藏集](/help/main/c-recommendations/c-products/collections.md) 或 [排除](/help/main/c-recommendations/c-products/exclusions.md).

1. 单击 **[!UICONTROL 高级搜索]** 链接。

   ![高级搜索页面](/help/main/c-recommendations/c-products/assets/advances-search.png)

1. 使用下拉列表为搜索指定参数、运算符和值。

1. （可选）单击 **[!UICONTROL 添加规则]** 添加其他搜索规则。

   每个其他搜索规则都使用AND运算符联接。

1.  单击&#x200B;**[!UICONTROL 搜索]**。

1. （可选）单击 **[!UICONTROL 另存为]**，然后单击 **[!UICONTROL 收藏集]** 或 **[!UICONTROL 排除]**.

   ![另存为选项](/help/main/c-recommendations/c-products/assets/save-as.png)

   有关更多信息，请参阅 [根据高级搜索创建收藏集或排除项](#save-as) 下。

## 查看项目的详细信息

您可以通过查看单个项目的详细信息来查看其详细信息，包括ID、名称、消息、类别等。

1. 单击搜索结果中的某个项目可查看其详细信息。

   ![产品详细信息](/help/main/c-recommendations/c-products/assets/bike-results-5.png)

## 从目录中删除项目

1. 单击搜索结果中的某个项目可查看其详细信息。

1. 单击 **[!UICONTROL 从目录中删除]**.

1. 确认要删除该项目。

该项目的所有信息都会从目录索引中删除。 只有在数据馈送中再次添加该项目时，该项目才会包含在您的目录中。 已删除的项目必须从馈送中单独删除。

## 刷新目录

当您上传第一个信息源时，将自动创建目录索引，并根据 [指定计划](/help/main/c-recommendations/c-products/feeds.md#steps).

通过信息源文件、API 或 mbox 更新接收更新时，目录将自动刷新。更新通常在一小时内完成。如果更新正在进行，则显示最近的更新开始时间。如果没有正在进行的更新，则显示最近的更新开始时间和结束时间。

## 基于高级搜索创建收藏集或排除项 {#save-as}

您可以使用“目录搜索”页面上的“高级搜索”（[](/help/main/c-recommendations/c-products/collections.md)[](/help/main/c-recommendations/c-products/exclusions.md)推荐[!UICONTROL  > ]目录搜索[!UICONTROL  > ]高级搜索[!UICONTROL ）来创建]收藏集[!UICONTROL 或]排除项。

1. 执行 [高级搜索](#advanced-search).

1. 单击 **[!UICONTROL 另存为]**，然后单击 **[!UICONTROL 收藏集]** 或 **[!UICONTROL 排除]**.

   ![另存为选项](/help/main/c-recommendations/c-products/assets/save-as.png)

   >[!IMPORTANT]
   >
   >的 [!UICONTROL 高级搜索] 功能不区分大小写；但是，在交付时返回的产品基于区分大小写的搜索。 这种不匹配可能会导致产生混淆。在使用 [!UICONTROL 高级搜索] 功能。 例如，如果您搜索“Holiday”，初始搜索会列出包含“Holiday”和“holiday”的结果。如果您随后创建一个目录，以用于返回包含“holiday”的产品，则只会返回包含“holiday”的产品，而不会返回包含“Holiday”的产品。可以采用类似的方式处理排除项。

## 更改环境

[环境](/help/main/administrating-target/environments.md) 可让您组织网站和预生产环境，以便轻松管理和分隔报表。

1. 单击Environment（环境）链接。

   ![环境链接](/help/main/c-recommendations/c-products/assets/environment.png)

1. 选择所需的环境。

## 修改“目录搜索”页面（过滤器和列）

您可以在 [!UICONTROL 目录搜索] 页面。

### 修改过滤器

您可以向 [!UICONTROL 目录搜索] 页面。

1. 在 **[!UICONTROL 过滤器]** 面板，单击 **[!UICONTROL 修改]**.

   ![修改过滤器链接](/help/main/c-recommendations/c-products/assets/modify-filters.png)

1. 选择所需的搜索彩块化（ID、名称、消息等），然后单击 **[!UICONTROL 保存]**.

   ![添加过滤器](/help/main/c-recommendations/c-products/assets/add-filters.png)

请记住，附加的过滤器彩块化仅在当前会话中可用。

### 修改列

您可以临时修改 [!UICONTROL 目录搜索] 页面。

1. 单击 **[!UICONTROL 列]** 链接。

   ![列选项](/help/main/c-recommendations/c-products/assets/columns.png)

1. （视情况而定）要重新排序活动列的顺序，请拖放 **[!UICONTROL 活动列]** 的次数。

1. （视情况而定）从 **[!UICONTROL 活动列]** 到 **[!UICONTROL 非活动列]** （反之亦然）。

   您还可以单击要从活动区域移动到非活动区域的列旁边的删除图标(x)。

请记住，您所做的任何更改都仅应用于当前会话。
