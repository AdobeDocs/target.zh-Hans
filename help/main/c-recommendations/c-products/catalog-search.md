---
keywords: 目录搜索；目录；搜索；排除项；收藏集；过滤器；推荐
description: 了解如何使用 [!DNL Recommendations] [!UICONTROL Catalog Search]查找产品或内容、从目录中删除项目等。
title: 如何使用 [!DNL Recommendations] [!UICONTROL Catalog Search]？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: 925fea97-e2c5-4883-84e3-fd357a8ee8d9
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 22%

---

# [!UICONTROL Catalog Search]

[!UICONTROL Catalog Search]中的[!DNL Adobe Recommendations]页面可帮助您在目录中查找产品或内容。 您可以在此页面上执行的最基本任务是搜索项目。 此外，您还可以更改环境、筛选Facet、修改表中的列、添加新搜索Facet等。

目录指代您的整个产品集（实体）。您的目录可以包含许多收藏集，这是一种在逻辑存储桶中组织产品的方法。

## 访问[!UICONTROL Catalog Search]

1. 要访问[!UICONTROL Catalog Search]页面，请单击&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL Catalog Search]**。

1. （可选）要将过滤器应用于搜索，请单击&#x200B;**[!UICONTROL Show Filters]**&#x200B;图标（ ![显示过滤器图标](/help/main/assets/icons/Filter.svg) ）。 您可以按[!UICONTROL Environment]、[!UICONTROL Collections]、[!UICONTROL Category]、[!UICONTROL Brand]、[!UICONTROL Inventory]和[!UICONTROL Value]进行筛选。

## 执行简单搜索

1. 在&#x200B;**[!UICONTROL Search In]**&#x200B;字段中键入搜索词。

1. （可选）您可以通过从单击[!UICONTROL Search In]字段中的向下箭头时显示的选项菜单中选择搜索选项来优化搜索。

   搜索选项包括：

   * ID
   * 名称
   * 消息

1. 滚动查看搜索结果中的项目以查看缩略图和其他产品信息。

   >[!NOTE]
   >
   > 对具有数字值的自定义属性执行目录搜索时，结果将该自定义属性视为字符串类型，而非数字值。
   >
   >目前没有可让您更改属性类型的功能。 要作出改变，请[提出客户问题](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)，其中引用需要将类型从字符串变为数字的属性。

<!-- ### Perform an advanced search {#advanced-search}

You can use [!UICONTROL Advanced Search] to further refine your search results or to save your search results as a [collection](/help/main/c-recommendations/c-products/collections.md) or [exclusion](/help/main/c-recommendations/c-products/exclusions.md).

1. Click the **[!UICONTROL Advanced Search]** link.

   ![Advanced Search page](/help/main/c-recommendations/c-products/assets/advances-search.png)

1. Use the drop-down lists to specify the parameter, operator, and values for your search.

1. (Optional) Click **[!UICONTROL Add Rule]** to add an additional search rule.

   Each additional search rule is joined with the AND operator.

1. Click **[!UICONTROL Search]**.

1. (Optional) Click **[!UICONTROL Save As]**, then click **[!UICONTROL Collection]** or **[!UICONTROL Exclusion]**.

   ![Save as options](/help/main/c-recommendations/c-products/assets/save-as.png)

   For more information, see [Create a collection or exclusion based on Advanced Search](#save-as) below.-->

## 查看项目的详细信息

您可以通过查看单个项目的详细信息来查看其详细信息，包括ID、名称、消息、类别等。

1. 单击搜索结果中的项目可查看其详细信息。

## 从目录中删除项目

1. 单击搜索结果中的项目可查看其详细信息。

1. 单击 **[!UICONTROL Remove from Catalog]**。

1. 确认您要移除该项目。

从目录索引中删除有关该项的所有信息。 只有当该项目再次添加到数据馈送中时，它才会包含在您的目录中。 必须从信息源中单独删除已删除的项目。

## 刷新目录

上传第一个信息源时，将自动创建目录索引，并根据[指定的计划](/help/main/c-recommendations/c-products/feeds.md#steps)刷新。

通过信息源文件、API 或 mbox 更新接收更新时，目录将自动刷新。更新通常在一小时内完成。 如果更新正在进行，则显示最近的更新开始时间。如果没有正在进行的更新，则显示最近的更新开始时间和结束时间。

<!-- ## Create a collection or exclusion based on Advanced Search {#save-as}

You can create [collections](/help/main/c-recommendations/c-products/collections.md) or [exclusions](/help/main/c-recommendations/c-products/exclusions.md) using [!UICONTROL Advanced Search] on the [!UICONTROL Catalog Search] page ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

1. Perform an [advanced search](#advanced-search).

1. Click **[!UICONTROL Save As]**, then click **[!UICONTROL Collection]** or **[!UICONTROL Exclusion]**.

   ![Save as options](/help/main/c-recommendations/c-products/assets/save-as.png)

   >[!IMPORTANT]
   >
   >The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create collections or exclusions based on results using the [!UICONTROL Advanced Search] functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create a catalog with the intent to return products containing "holiday," only products containing "holiday" are returned. Products containing "Holiday" are not returned. Exclusions are handled in a similar fashion.-->

## 更改环境

[环境](/help/main/administrating-target/environments.md)允许您组织站点和生产前环境，以便轻松管理和分隔报表。

1. 单击“显示筛选器”图标（![显示筛选器图标](/help/main/assets/icons/Filter.svg)）。

1. 从&#x200B;**[!UICONTROL Environment]**&#x200B;下拉列表中选择所需的环境。

<!-- ## Modify the Catalog Search page (filters and columns)

You can temporarily modify the available filters and columns on the [!UICONTROL Catalog Search] page for the current session.

### Modify filters

You can add additional filter facets to the [!UICONTROL Catalog Search] page.

1. In the **[!UICONTROL Filters]** panel, click **[!UICONTROL Modify]**.

   ![Modify filters link](/help/main/c-recommendations/c-products/assets/modify-filters.png)

1. Select the desired search facets (ID, name, message, etc.), then click **[!UICONTROL Save]**.

   ![Add filters](/help/main/c-recommendations/c-products/assets/add-filters.png)

Keep in mind that the additional filter facets are available in the current session only.-->

## 修改列

您可以修改[!UICONTROL Catalog Search]页面上的活动列。

1. 单击&#x200B;**[!UICONTROL Customize Table]**&#x200B;图标（![自定义表格图标](/help/main/assets/icons/ColumnSetting.svg)）。

1. 选择或取消选择要显示或隐藏的所需列。

您所做的任何更改都会跨会话持续进行。
