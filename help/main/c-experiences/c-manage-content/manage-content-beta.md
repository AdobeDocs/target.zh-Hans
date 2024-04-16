---
keywords: 内容;资产;管理内容;选件;管理资产;进入选择模式;选择模式
description: 了解如何使用选件库管理代码和图像选件。
title: 如何管理代码和图像选件？
feature: Experiences and Offers
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip=" [!DNL Adobe Target] 中有哪些 Beta 功能。"
hide: true
hidefromtoc: true
exl-id: f64aec3d-5f83-4bd1-8e64-df1779809812
source-git-commit: 14e800deda4a26c02555c4a653993737f062f686
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 6%

---

# 选件

使用 [!UICONTROL Offers] 库位于 [!DNL Adobe Target] 以管理代码和图像选件内容。

>[!NOTE]
>
>本文包含有关对的更新信息 [!DNL Target] 当前为测试版计划一部分的用户界面。 此 [!DNL Adobe Target] 团队经常为特定客户启用新功能以进行测试和提供反馈。 在测试期结束后，将为所有客户启用这些功能 [!DNL Target Standard/Premium] 发行版本和发行说明中宣布。

单击 **[!UICONTROL Offers]** 选项卡顶部的 [!DNL Target] 用于显示 [!UICONTROL Offers] 库。

![Adobe Target中的选件库](/help/main/c-experiences/c-manage-content/assets/offers-page-new.png)

此 [!UICONTROL Offers] 库中包含已通过设置的选件 [!DNL Target Standard/Premium]， [!DNL Target Classic]， [!DNL Adobe Experience Manager] (AEM)， [!DNL Adobe Mobile Services] (AMS)和API。 在 [!DNL Target Classic] 或其他解决方案中创建的选件可以在 [!DNL Target Standard/Premium] 中进行编辑。

选件库提供了所有代码和图像选件的概述，并允许您执行各种操作：

| 元素 | 描述 |
|--- |--- |
| 左侧导航边栏 | 在列表之间切换 [!UICONTROL Code Offers] 或 [!UICONTROL Image Offers]. |
| [!UICONTROL Show filters] 图标<P>![“显示过滤器”图标](/help/main/c-activities/assets/show-filters-icon.png) | 单击 **[!UICONTROL Show filters]** 用于筛选优惠的图标 [!UICONTROL Type]， [!UICONTROL Source]、和 [!UICONTROL AEM Type]<P>有关更多信息，请参阅 [将过滤器应用于选件列表](#filters) 下。 |
| 搜索字段 | 使用 **[!UICONTROL Search in]** 用于快速查找选件或减少 [!UICONTROL Offers] 库。 搜索依据 [!UICONTROL Offer Name]， [!UICONTROL AEM Paths]，或 [!UICONTROL AEM Tags]. |
| [!UICONTROL Create Folder] | 单击创建文件夹，以在 [!UICONTROL Offer] 库，用于保存代码选件、图像选件以及其他文件夹以创建子文件夹结构。 有关更多信息，请参阅 [创建选件文件夹](/help/main/c-experiences/c-manage-content/create-content-folder.md). |
| [!UICONTROL [!UICONTROL Create Offer]] | 创建选件。 有关创建各种选件类型的详细信息，请参阅： <ul><li>HTML 选件</li><li>[json选件](/help/main/c-experiences/c-manage-content/create-json-offer.md)</li><li>[重定向选件](/help/main/c-experiences/c-manage-content/offer-redirect.md)</li><li>[远程选件](/help/main/c-experiences/c-manage-content/about-remote-offers.md)</li></ul> |
| “批量操作”复选框 | 对所有活动或选定活动执行批量操作。<P>有关可用操作的列表（取决于您的权限和选件状态），请参阅 [执行快速操作](#quick-actions) 下。 |
| [!UICONTROL Name] | 每个选件的名称。<P>单击 **[!UICONTROL Quick Info]** 图标，以在弹出卡中查看有关该优惠的更多信息，包括优惠ID、类型、上次修改优惠的日期以及修改者，等等。<p>单击 **[!UICONTROL More actions]** 图标（水平省略号）以打开一个菜单，让您可对活动执行快速操作。 以下操作可用（具体取决于您的权限和选件状态）： [!UICONTROL Edit]， [!UICONTROL Copy]， [!UICONTROL Delete]、和 [!UICONTROL Move]. 有关每个操作的详细信息，请参阅 [执行快速操作](#quick-actions) 下。<P>单击表标题可按名称的字母升序或降序对列表进行排序。 |
| [!UICONTROL Type] | 选件类型：HTML选件， [重定向选件](/help/main/c-experiences/c-manage-content/offer-redirect.md)， [远程选件](/help/main/c-experiences/c-manage-content/about-remote-offers.md)、和 [json选件](/help/main/c-experiences/c-manage-content/create-json-offer.md). |
| [!UICONTROL Source] | 显示创建选件的位置： [!DNL Adobe Target]， [!DNL Adobe Target Classic]、和 [!DNL Adobe Experience Manager]. |

## 将过滤器应用到选件库 {#filters}

单击 **[!UICONTROL Show filters]** 图标( ![在“选件”页面上显示“筛选器”图标](/help/main/c-experiences/c-manage-content/assets/show-filters-icon.png) )以过滤选件 [!UICONTROL Type]， [!UICONTROL Source]、和 [!UICONTROL AEM Type].

![offers_filter图像](assets/offers-filter-new.png)

此 **[!UICONTROL Show filters]** 图标可让您按以下类别筛选选件：

* **类型**：HTML选件， [json选件](/help/main/c-experiences/c-manage-content/create-json-offer.md)， [重定向选件](/help/main/c-experiences/c-manage-content/offer-redirect.md)， [远程选件](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

* **来源**： [!DNL Adobe Target]， [!DNL Adobe Target Classic]、和 [!DNL Adobe Experience Manager].

* **AEM类型**： [内容片段](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md) 和 [体验片段](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md). 有关不同片段类型的更多信息，请参阅 [AEM体验片段和内容片段概述](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## 执行快速操作 {#quick-actions}

通过单击相应的图标，可以执行以下快速操作：

### 快速信息

单击 **[!UICONTROL Quick Info]** 图标，以在弹出卡中查看有关该优惠的更多信息，包括优惠ID、类型、上次修改优惠的日期以及修改者，等等。 可用选项取决于选件类型：HTML选件， [json选件](/help/main/c-experiences/c-manage-content/create-json-offer.md)， [重定向选件](/help/main/c-experiences/c-manage-content/offer-redirect.md)， [远程选件](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

![](/help/main/c-experiences/c-manage-content/assets/quick-actions.png)

### 更多操作

单击 **[!UICONTROL More actions]** 图标（水平省略号）以打开一个菜单，让您可对活动执行快速操作。 以下操作可用（具体取决于您的权限和选件状态）： [!UICONTROL Edit]， [!UICONTROL Copy]， [!UICONTROL Delete]、和 [!UICONTROL Move].

![Target选件库中的“更多操作”选项](/help/main/c-experiences/c-manage-content/assets/more-actions.png)

* 编辑
* 复制
* 删除
* 移动(例如，要将一个或多个项目移动到文件夹中，请单击 **[!UICONTROL Move]** 图标，单击所需的文件夹，然后单击 **[!UICONTROL Drop]**.)

根据您的权限，您可能不会看到所有选项的图标。 例如，用户具有 [!UICONTROL Observer] 权限无权使用 [!UICONTROL Copy] 选项。

有关可对选件和文件夹执行的任务的详细信息，请参阅 [处理资产库中的内容](/help/main/c-experiences/c-manage-content/assets-working.md).

将鼠标悬停在上的所需图像选件或文件夹上，执行其他任务。 [!UICONTROL Image Offers] 选项卡，然后单击所需的图标。

![“图像选件”选项](/help/main/c-experiences/c-manage-content/assets/image-offers-icons.png)

选项包括：

* 选择
* 下载
* 查看属性
* 编辑
* 注释
* 复制

有关可对选件和文件夹执行的任务的详细信息，请参阅 [处理资产库中的内容](/help/main/c-experiences/c-manage-content/assets-working.md).

>[!NOTE]
>
>图像选件不属于 [企业用户权限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) 模型。

<!--

## Viewing offer definitions {#section_6B059DD121434E6292CAB393507D010E}

You can view offer definition details on a pop-up card in the [!UICONTROL Offers] library without opening the offer.

For example, the following offer definition card for an HTML offer is accessed by hovering over an offer on the [!UICONTROL Content] list, then clicking the information icon:

![offer-card-html image](assets/offer-card-html.png)

The following information is available:

* Name 
* Source 
* Type 
* Offer ID 
* Offer path 
* Last Modified

Click the [!UICONTROL Offer Usage] tab to view the activities that reference a code offer in each offer's definition pop-up card. This functionality does not apply to image offers. This way you can avoid impact to other activities while editing offers. Information includes [!UICONTROL Live Activities] and [!UICONTROL Inactive Activities].

![offer-card-usage image](assets/offer-card-usage.png)

The following offer definition card for a Redirect offer:

![offer-card-redirect image](assets/offer-card-redirect.png)

The following information is available:

* Name 
* Source 
* Type 
* Offer ID 
* Offer Path 
* Last Modified 
* Redirect URL 
* Include all URL parameters (On or Off) 
* Pass mbox session ID (On or Off)

The following offer definition card for a Remote offer:

![offer-card-remote image](assets/offer-card-remote.png)

The following information is available:

* Name 
* Source 
* Type 
* Offer ID 
* Offer Path 
* Last Modified 
* Redirect URL Type 
* Absolute or Relative URL

## Training video: The Content Repository ![Overview badge](/help/main/assets/overview.png)

This video includes information about managing offers.

* Connection between the [Experience Cloud Asset Library](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) and the Target Content Library 
* Custom HTML Offers 
* Custom HTML Offer in the Visual Experience Composer

>[!VIDEO](https://video.tv.adobe.com/v/17387)

-->
