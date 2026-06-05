---
keywords: 内容;资产;管理内容;产品建议;管理资产;进入选择模式;选择模式
description: 了解如何使用[!UICONTROL 选件]库高效地管理代码和图像选件。
title: 如何管理代码和图像选件？
feature: Experiences and Offers
exl-id: d8c24656-64d6-4a4b-a5f2-bcde57180007
TQID: https://experienceleague.adobe.com/A8ZLHW-FrWHGPJR7P-mhl2pO6SPoDc--LWpFEjtQzBY
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 958
ht-degree: 8%

---

# 产品建议

了解如何使用[!DNL Adobe Target]中的[!UICONTROL 选件]库高效地管理代码和图像选件。

要显示[!UICONTROL 选件]库，请单击[!DNL Target] UI顶部的&#x200B;**[!UICONTROL 选件]**&#x200B;选项卡。

![“产品建议”页面](/help/main/c-experiences/c-manage-content/assets/offers-page-new.png)

[!UICONTROL 选件]库包含已通过[!DNL Target Standard/Premium]、[!DNL Target Classic]、[!DNL Adobe Experience Manager] (AEM)、[!DNL Adobe Mobile Services] (AMS)和API设置的选件。 在 [!DNL Target Classic] 或其他解决方案中创建的产品建议可以在 [!DNL Target Standard/Premium] 中进行编辑。

[!UICONTROL 选件]库提供了所有代码和图像选件的概览，并允许您执行各种操作：

| 元素 | 描述 |
|--- |--- |
| 左侧导航边栏 | 在显示[!UICONTROL 代码选件]或[!UICONTROL 图像选件]之间切换。 |
| [!UICONTROL 显示文件夹] / [!UICONTROL 隐藏文件夹]<P>![显示筛选器/隐藏筛选器图标](/help/main/assets/icons/RailLeft.svg) | 单击&#x200B;**[!UICONTROL 显示文件夹]**&#x200B;或&#x200B;**[!UICONTROL 隐藏文件夹]**&#x200B;图标可在显示优惠文件夹结构或不显示文件夹结构之间进行切换。<P>有关详细信息，请参阅[创建选件文件夹](/help/main/c-experiences/c-manage-content/create-content-folder.md)。 |
| [!UICONTROL 显示筛选器]图标<P>![显示筛选器图标](/help/main/assets/icons/Filter.svg) | 单击&#x200B;**[!UICONTROL 显示筛选器]**&#x200B;图标可按[!UICONTROL 类型]、[!UICONTROL Source]和[!UICONTROL AEM类型]筛选选件。<P>有关详细信息，请参阅下面的[将筛选器应用到选件列表](#filters)。 |
| 搜索字段 | 使用&#x200B;**[!UICONTROL 搜索范围]**&#x200B;字段快速查找选件或减少[!UICONTROL 选件]库中显示的选件数。 您可以按[!UICONTROL 选件名称]、[!UICONTROL AEM路径]或[!UICONTROL AEM标记]进行搜索。 搜索选项是会话持久的。 |
| [!UICONTROL 创建文件夹] | 单击&#x200B;**[!UICONTROL 创建文件夹]**&#x200B;可在[!UICONTROL 选件]库中创建文件夹以保存代码选件、图像选件以及其他文件夹以创建子文件夹结构。<P>有关详细信息，请参阅[创建选件文件夹](/help/main/c-experiences/c-manage-content/create-content-folder.md)。 |
| [!UICONTROL [!UICONTROL 创建选件]] | 单击&#x200B;**[!UICONTROL 创建选件]**&#x200B;以创建选件。<P>有关创建各种选件类型的详细信息，请参阅： <ul><li>HTML 产品建议</li><li>[JSON选件](/help/main/c-experiences/c-manage-content/create-json-offer.md)</li><li>[重定向选件](/help/main/c-experiences/c-manage-content/offer-redirect.md)</li><li>[远程选件](/help/main/c-experiences/c-manage-content/about-remote-offers.md)</li></ul> |
| “批量操作”复选框<P>![批量操作图标](/help/main/assets/icons/Rectangle.svg) | 单击[!UICONTROL 批量操作]复选框可对所有选件或选定选件执行批量操作。<P>有关可用操作的列表（取决于您的权限和选件状态），请参阅下面的[执行快速操作](#quick-actions)。 |
| [!UICONTROL 名称] | 每个选件的名称。<P>单击每个选件名称旁边的&#x200B;**[!UICONTROL 快速信息]**&#x200B;图标（![快速信息图标](/help/main/assets/icons/InfoOutline.svg)）可在弹出卡片中查看有关该选件的更多信息，包括选件ID、类型、上次修改选件的日期以及修改者等。<p>单击每个选件名称旁边的&#x200B;**[!UICONTROL 更多操作]**&#x200B;图标（![更多操作图标](/help/main/assets/icons/MoreSmallList.svg)）以打开一个菜单，该菜单允许您对活动执行快速操作。 以下操作可用（取决于您的权限和选件状态）： [!UICONTROL 编辑]、[!UICONTROL 复制]、[!UICONTROL 删除]和[!UICONTROL 移动]。 有关每个操作的详细信息，请参阅下面的[执行快速操作](#quick-actions)。<P>单击表标题可按名称的字母升序或降序对列表进行排序。 |
| [!UICONTROL 类型] | 选件类型： [!UICONTROL HTML选件]、[[!UICONTROL 重定向选件]](/help/main/c-experiences/c-manage-content/offer-redirect.md)、[[!UICONTROL 远程选件]](/help/main/c-experiences/c-manage-content/about-remote-offers.md)和[[!UICONTROL JSON选件]](/help/main/c-experiences/c-manage-content/create-json-offer.md)。 |
| [!UICONTROL 来源] | 显示创建选件的位置： [!DNL Adobe Target]、[!DNL Adobe Target Classic]和[!DNL Adobe Experience Manager]。 |
| [!UICONTROL 上次更新时间] | 显示上次修改优惠的日期和时间以及修改者。<P>单击表标题可按日期对列表进行升序或降序排序。 |

## 将过滤器应用到选件库 {#filters}

单击&#x200B;**[!UICONTROL 显示筛选器]**&#x200B;图标（“选件”页面上的![显示筛选器图标](/help/main/assets/icons/Filter.svg)）可按[!UICONTROL 类型]、[!UICONTROL Source]和[!UICONTROL AEM类型]筛选选件。

通过&#x200B;**[!UICONTROL 显示筛选器]**&#x200B;图标，可按以下类别筛选选件：

* **[!UICONTROL 类型]**：[!UICONTROL HTML选件]、[[!UICONTROL 重定向选件]](/help/main/c-experiences/c-manage-content/offer-redirect.md)、[[!UICONTROL 远程选件]](/help/main/c-experiences/c-manage-content/about-remote-offers.md)和[[!UICONTROL JSON选件]](/help/main/c-experiences/c-manage-content/create-json-offer.md)。

* **[!UICONTROL Source]**： [!DNL Adobe Target]、[!DNL Adobe Target Classic]和[!DNL Adobe Experience Manager]。

* **AEM类型**：[内容片段](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md)和[体验片段](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md)。 有关各种片段类型的更多信息，请参阅[AEM体验片段和内容片段概述](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md)。

过滤器是会话持久性的。

## 执行快速操作 {#quick-actions}

通过单击相应的图标，可以执行以下快速操作：

### 快速信息

单击每个选件名称旁边的&#x200B;**[!UICONTROL 快速信息]**&#x200B;图标（![快速信息图标](/help/main/assets/icons/InfoOutline.svg)）可在弹出卡片中查看有关该选件的更多信息，包括选件ID、类型、上次修改选件的日期以及修改者等。 可用选项取决于选件类型： [!UICONTROL HTML选件]、[[!UICONTROL JSON选件]](/help/main/c-experiences/c-manage-content/create-json-offer.md)、[[!UICONTROL 重定向选件]](/help/main/c-experiences/c-manage-content/offer-redirect.md)、[[!UICONTROL 远程选件]](/help/main/c-experiences/c-manage-content/about-remote-offers.md)。

### 更多操作

[!UICONTROL 代码选件]和[!UICONTROL 图像选件]的可用操作略有不同。 以下部分包含更多信息：

#### [!UICONTROL 代码选件]选项

单击每个选件名称旁边的&#x200B;**[!UICONTROL 更多操作]**&#x200B;图标（![更多操作图标](/help/main/assets/icons/MoreSmallList.svg)）以打开一个菜单，该菜单允许您对活动执行快速操作。

以下操作可用（具体取决于您的权限和选件状态）：

* [!UICONTROL 编辑]
* [!UICONTROL 复制]
* [!UICONTROL 删除]
* [!UICONTROL 移动] （例如，要将一个或多个项目移动到文件夹中，请单击所需项目旁边的&#x200B;**[!UICONTROL 移动]**，单击所需文件夹，然后单击&#x200B;**[!UICONTROL 移动]**。）

根据您的权限，您可能不会看到所有选项的图标。 例如，具有[!UICONTROL 观察者]权限的用户无权使用[!UICONTROL 复制]选项。

有关可对选件和文件夹执行的任务的详细信息，请参阅[处理资源库中的内容](/help/main/c-experiences/c-manage-content/assets-working.md)。

#### [!UICONTROL 图像选件]选项

将鼠标悬停在[!UICONTROL 图像选件]选项卡上所需的图像选件或文件夹上，然后单击所需的图标，以执行其他任务。

选项包括：

* [!UICONTROL Select]
* [!UICONTROL 下载]
* [!UICONTROL 查看属性]
* [!UICONTROL 更多操作]
* [!UICONTROL 编辑]
* [!UICONTROL 批注]
* [!UICONTROL 复制]

有关可对选件和文件夹执行的任务的详细信息，请参阅[处理资源库中的内容](/help/main/c-experiences/c-manage-content/assets-working.md)。

>[!NOTE]
>
>图像选件不是[企业用户权限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)模型的一部分。

## 查看选件定义 {#section_6B059DD121434E6292CAB393507D010E}

要在不打开选件的情况下查看[!UICONTROL 选件]库中弹出卡片上的选件定义详细信息，请单击（ ![快速信息图标](/help/main/assets/icons/InfoOutline.svg) ）。

其中提供了以下信息：

* [!UICONTROL 名称]
* [!UICONTROL 选件ID]
* [!UICONTROL 类型]
* [!UICONTROL 上次修改时间]

单击[!UICONTROL 查看完整详细信息]链接可查看选件的属性和引用每个选件定义弹出卡片中的代码选件的活动。 此功能不适用于图像选件。 利用此功能，您可以避免在编辑选件时对其他活动造成影响。 此信息包括[!UICONTROL 已上线活动]和[!UICONTROL 非活动活动]的详细信息。
