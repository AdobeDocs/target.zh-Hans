---
keywords: 内容库;资产;注释;复制;删除资产;下载资产;编辑内容;共享卡片;查看内容属性
description: 了解如何管理Adobe [!DNL Target] 优惠库中的代码和图像优惠。 了解如何视图优惠的详细信息以及如何编辑、复制、移动或删除优惠。
title: 如何处理优惠库中的内容？
feature: 体验和优惠
exl-id: 2668ba68-29c8-4c3f-bebc-ba62760a8a61
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 36%

---

# 使用资源库中的内容

有关您可以对[!DNL Adobe Target]中内容库中的资产执行的任务的信息，包括添加注释、复制、删除、下载、编辑、共享和查看属性。

1. 单击&#x200B;**[!UICONTROL 优惠]** > **[!UICONTROL 代码优惠]**&#x200B;或&#x200B;**[!UICONTROL 图像优惠]**。

   ![代码优惠和图像优惠选项卡](/help/c-experiences/c-manage-content/assets/offers-both.png)

   有关搜索选件库和创建智能收藏集的更多信息，请参阅[过滤和搜索内容](/help/c-experiences/c-manage-content/filter-and-search-content.md#concept_3B59B8F025BF4CEA82ECC5199D365276)。

1. （可选）在[!UICONTROL 卡视图]和[!UICONTROL 列表视图]之间切换，单击内容库右上角的[!UICONTROL 卡视图]图标或[!UICONTROL 列表视图]图标。 在查看[!UICONTROL 视图视图]时，还可以使用[!UICONTROL 列表设置]进一步配置列。

   下图显示了查看[!UICONTROL 列表视图]时可用的选项：

   ![列表视图选项](/help/c-experiences/c-manage-content/assets/view-settings-options.png)

1. 执行所需的操作，如以下部分中所述：

## 代码选件选项

查看[!UICONTROL 代码优惠]页面时，可以将鼠标悬停在优惠或文件夹上，然后选择相应的图标对项目执行以下操作。

![“代码优惠”选项卡上的悬停图标](/help/c-experiences/c-manage-content/assets/code-offers-hover-icons.png)

* **信息**:视图优惠的信息。
* **编辑**:编辑文件夹或优惠。
* **复制**:复制优惠。通过复制然后编辑优惠，您可以轻松创建类似的新优惠。
* **移动**:单击移动图标，导航到要将优惠或文件夹移动到的位置，然后单击 **** Dropicon。例如，您可以将一个或多个文件夹移动到另一个文件夹以创建子文件夹。 单击[!UICONTROL 清除选择]以取消选择已选择的优惠或文件夹。
* **删除**:删除优惠或文件夹。请参阅[删除项目](#delete)时的注意事项。

## 图像选件选项

在查看[!UICONTROL 图像优惠]页面时，可以将鼠标悬停在优惠或文件夹上，然后选择相应的图标，对项目执行以下操作。

下图显示了查看[!UICONTROL 卡视图]时的悬停图标。

![在卡优惠中时，将鼠标图标悬停在“图像视图”选项卡上](/help/c-experiences/c-manage-content/assets/image-offers-hover-icons.png)

下图显示了查看[!UICONTROL 列表视图]时的悬停图标。 要显示图标，请单击列表中的项目。

![当处于列表优惠时，将图标悬停在“图像视图”选项卡上](/help/c-experiences/c-manage-content/assets/list-view-hover.png)

* **选择**:选择一个或多个要执行以下操作的文件夹：

   * 下载
   * 复制
   * 移动
   * 删除（请参阅[删除项目](#delete)时的注意事项。）

   选择要对其执行以下操作的一个或多个图像优惠:

   * 共享
   * 下载
   * 查看属性
   * 编辑
   * 注释
   * 移动


* **下载**:下载图像优惠或文件夹及其内容。
* **视图属性**:视图项的属性。请务必单击[!UICONTROL 基本]选项卡和[!UICONTROL 高级]选项卡以视图所有可用信息。 单击属性页面上的铅笔图标，可编辑属性并添加更多信息。您可以添加元数据信息、发布状态和许可证数据。
* **更多操作**:在卡中视图时显示其 [!UICONTROL 他选项]。
* **编辑**:编辑文件夹或优惠。
* **注释**:为资产添加注释。单击资产，选择要添加注释的区域，然后键入注释。
* **复制**:复制优惠。通过复制然后编辑优惠，您可以轻松创建类似的新优惠。

## 删除项{#delete}时的注意事项

* 您可以删除包含任意数量的资产和子文件夹的整个文件夹。此功能在 Target UI 以及 Adobe Experience Cloud Assets UI 中均可用。
* 如果删除含有大量图像的文件夹，则在 UI 刷新以显示最终状态之前，后台运行的进程可能需要花费一些时间（几分钟）。所需的时间与图像数量成正比，而与图像大小无关。删除 2,000 张图像预计需要 10 分钟。您可以继续执行其他工作，并在几分钟后检查最终状态以验证是否已完成删除。
* 可以删除“图像选件”库中的非空文件夹。如果该文件夹中的所有图像均未在任何活动中引用，则将删除整个文件夹及其内容。如果在任何活动中引用了该文件夹中的某些图像，则将删除所有未引用的图像，但会保留已引用的图像和包含这些图像的文件夹。

## 培训视频：内容存储库![概述徽章](/help/assets/overview.png)

以下视频包含有关管理内容的信息。(4:56)

* [Experience Cloud 资产库](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html)与 Target 内容库之间的关联
* 自定义 HTML 选件
* 可视化体验编辑器中的自定义 HTML 选件

>[!VIDEO](https://video.tv.adobe.com/v/17387)
