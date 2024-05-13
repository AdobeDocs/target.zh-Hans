---
keywords: 内容库;资产;注释;复制;删除资产;下载资产;编辑内容;共享卡片;查看内容属性
description: 了解如何在中管理代码和图像优惠 [!DNL Target] [!UICONTROL Offers] 库。
title: 如何使用中的内容 [!UICONTROL Offers] 图书馆？
feature: Experiences and Offers
hide: true
hidefromtoc: true
source-git-commit: 5931aef4a16e6e9777112fdda4b3277f8e6f7386
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 33%

---

# 处理资产库中的内容

有关您对内容库中资产所能执行的任务的信息，请参见 [!DNL Adobe Target] 包括注释、复制、删除、下载、编辑、共享和查看属性。

1. 单击 **[!UICONTROL Offers]** > **[!UICONTROL Code Offers]** 或 **[!UICONTROL Image Offers]**.

   ![“代码选件”和“图像选件”选项卡](/help/main/c-experiences/c-manage-content/assets/offers-both.png)

   有关搜索选件库和创建智能收藏集的更多信息，请参阅[过滤和搜索内容](/help/main/c-experiences/c-manage-content/filter-and-search-content.md#concept_3B59B8F025BF4CEA82ECC5199D365276)。

1. （可选）在 [!UICONTROL Card View] 和 [!UICONTROL List View]，单击 [!UICONTROL Card View] 图标或 [!UICONTROL List View] 图标（位于内容库的右上角）。 您还可以使用 [!UICONTROL View Settings] 以进一步配置在查看 [!UICONTROL List View].

   下图显示了查看 [!UICONTROL List View]：

   ![列表视图选项](/help/main/c-experiences/c-manage-content/assets/view-settings-options.png)

1. 按照以下部分所述，执行所需的操作：

## 代码选件选项

查看 [!UICONTROL Code Offers] 页面上，您可以对项目执行以下操作（方法是将鼠标悬停在选件或文件夹上，然后选择相应的操作图标）。

![代码选件选项卡上的悬停图标](/help/main/c-experiences/c-manage-content/assets/code-offers-hover-icons.png)

* **信息**：查看选件信息。
* **编辑**：编辑文件夹或选件。
* **复制**：复制选件。 通过复制并编辑选件，您可以轻松创建类似的新选件。
* **移动**：单击移动图标，导航到要将选件或文件夹移动到的位置，然后单击 **[!UICONTROL Drop]** 图标。 例如，您可以将一个或多个文件夹移动到另一个文件夹以创建子文件夹。 单击 [!UICONTROL Clear Selection] 以取消选择您选择的选件或文件夹。
* **删除**：删除选件或文件夹。 请参阅 [删除项目时的注意事项](#delete).

## 图像选件选项

查看 [!UICONTROL Image Offers] 页面上，您可以对项目执行以下操作（方法是将鼠标悬停在选件或文件夹上，然后选择相应的操作图标）。

下图显示了查看 [!UICONTROL Card View].

![在卡片视图中，将鼠标悬停在“图像选件”选项卡上](/help/main/c-experiences/c-manage-content/assets/image-offers-hover-icons.png)

下图显示了查看 [!UICONTROL List View]. 要显示图标，请单击列表中的项目。

![在列表视图中，将鼠标悬停在“图像选件”选项卡上](/help/main/c-experiences/c-manage-content/assets/list-view-hover.png)

* **选择**：选择要对其执行以下操作：

   * 下载
   * 复制
   * 移动
   * 删除(请参阅 [删除项目时的注意事项](#delete).)

  选择要对其执行以下操作：

   * 共享
   * 下载
   * 查看属性
   * 编辑
   * 注释
   * 移动

* **下载**：下载图像选件或文件夹及其内容。
* **查看属性**：查看项目的属性。 确保单击 [!UICONTROL Basic] 选项卡和 [!UICONTROL Advanced] 选项卡查看所有可用信息。 单击属性页面上的铅笔图标，可编辑属性并添加更多信息。您可以添加元数据信息、发布状态和许可证数据。
* **更多操作**：在中时显示其他选项 [!UICONTROL Card View].
* **编辑**：编辑文件夹或选件。
* **批注**：向资源添加注释。 单击资产，选择要添加注释的区域，然后键入注释。
* **复制**：复制选件。 通过复制并编辑选件，您可以轻松创建类似的新选件。

## 删除项目时的注意事项 {#delete}

* 您可以删除包含任意数量的资产和子文件夹的整个文件夹。 此功能在 Target UI 以及 Adobe Experience Cloud Assets UI 中均可用。
* 如果删除含有大量图像的文件夹，则在UI刷新以显示最终状态之前，后台运行的进程可能需要花费一些时间（几分钟）。 所需的时间与图像数量成正比，而与图像大小无关。删除 2,000 张图像预计需要 10 分钟。您可以继续执行其他工作，并在几分钟后检查最终状态以验证是否已完成删除。
* 可以删除“图像选件”库中的非空文件夹。如果该文件夹中的所有图像均未在任何活动中引用，则将删除整个文件夹及其内容。如果在任何活动中引用了该文件夹中的某些图像，则将删除所有未引用的图像，但会保留已引用的图像和包含这些图像的文件夹。

## 培训视频：内容存储库 ![“概述”标记](/help/main/assets/overview.png)

以下视频包含有关管理内容的信息。(4:56)

* [Experience Cloud 资产库](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html)与 Target 内容库之间的关联
* 自定义 HTML 选件
* 可视化体验编辑器中的自定义 HTML 选件

>[!VIDEO](https://video.tv.adobe.com/v/17387)