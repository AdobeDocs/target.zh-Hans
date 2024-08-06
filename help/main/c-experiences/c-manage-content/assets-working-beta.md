---
keywords: 内容库;资产;注释;复制;删除资产;下载资产;编辑内容;共享卡片;查看内容属性
description: 了解在 [!DNL Target] [!UICONTROL Offers]库中组织和优化代码和图像选件的过程。
title: '[!UICONTROL Offers]库中的主内容管理'
feature: Experiences and Offers
hide: true
hidefromtoc: true
exl-id: 5d836037-3f51-4c63-8717-65de72e5c793
source-git-commit: c9d987a7e27bbaa605f4d7b45975c854b61783de
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 20%

---

# 处理资产库中的内容

有关您可以在[!DNL Adobe Target]中对[!UICONTROL Content Library]中的资产执行的任务的信息。 任务包括注释、复制、删除、下载、编辑、共享和查看属性。

1. 单击&#x200B;**[!UICONTROL Offers]** > **[!UICONTROL Code Offers]**&#x200B;或&#x200B;**[!UICONTROL Image Offers]**。

   有关搜索[!UICONTROL Offer library]和创建[!UICONTROL Smart Collections]的详细信息，请参阅[筛选和搜索内容](/help/main/c-experiences/c-manage-content/filter-and-search-content.md#concept_3B59B8F025BF4CEA82ECC5199D365276)。

1. （视情况而定）对于图像选件，在[!UICONTROL Card View]和[!UICONTROL List View]之间切换，单击内容库右上角的[!UICONTROL Card View]图标或[!UICONTROL List View]图标。 您还可以在查看[!UICONTROL List View]时使用[!UICONTROL View Settings]配置列。

   下图显示了查看[!UICONTROL List View]时可用的选项：

   ![列表视图选项](/help/main/c-experiences/c-manage-content/assets/view-settings-options.png)

1. 按照以下部分所述，执行所需的操作：

## [!UICONTROL Code Offers]选项

查看[!UICONTROL Code Offers]页面时，您可以对项目执行以下操作（方法是将鼠标悬停在选件或文件夹上，然后选择相应的操作图标）。

![代码选件选项卡上的悬停图标](/help/main/c-experiences/c-manage-content/assets/code-offers-hover-icons-new.png)

* **信息**：单击[!UICONTROL Information]图标可查看选件的信息，包括[!UICONTROL Offer ID]、[!UICONTROL Type]、[!UICONTROL Last Modified]（日期、时间和修饰符名称）。 单击[!UICONTROL Full Details]可查看其他信息，包括选件属性和活动使用情况（活动名称、状态、工作区以及修改日期和时间）。
* **编辑**：编辑文件夹或选件。
* **复制**：复制选件。 通过复制并编辑选件，您可以轻松创建类似的新选件。
* **删除**：删除选件或文件夹。 请参阅[删除项](#delete)时的注意事项。
* **移动**：单击[!UICONTROL Move]图标，导航到要将选件或文件夹移动到的位置，然后单击&#x200B;**[!UICONTROL Move]**。 例如，您可以将一个或多个文件夹移动到另一个文件夹以创建子文件夹。

## [!UICONTROL Image Offers]选项

查看[!UICONTROL Image Offers]页面时，您可以对项目执行以下操作（方法是将鼠标悬停在选件或文件夹上，然后选择相应的操作图标）。

下图显示了查看[!UICONTROL Card View]时悬停的图标。

在卡片视图中，![将图标悬停在“图像选件”选项卡上](/help/main/c-experiences/c-manage-content/assets/image-offers-hover-icons.png)

下图显示了查看[!UICONTROL List View]时悬停的图标。 要显示图标，请单击列表中的项目。

处于列表视图时，![将图标悬停在“图像选件”选项卡上](/help/main/c-experiences/c-manage-content/assets/list-view-hover.png)

* **选择**：选择一个或多个要对其执行以下操作：

   * 下载
   * 复制
   * 移动
   * 删除（请参阅删除项](#delete)时的[注意事项。）

  选择要对其执行以下操作：

   * 共享
   * 下载
   * 查看属性
   * 编辑
   * 注释
   * 移动

* **下载**：下载图像选件或文件夹及其内容。
* **查看属性**：查看项目的属性。 确保单击[!UICONTROL Basic]选项卡和[!UICONTROL Advanced]选项卡以查看所有可用信息。 您可以编辑属性并添加更多信息。 您可以添加元数据信息、发布状态和许可证数据。
* **更多操作**：在[!UICONTROL Card View]中显示其他选项。
* **编辑**：编辑文件夹或选件。
* **批注**：为资源添加注释。 单击资产，选择要添加注释的区域，然后键入注释。
* **复制**：复制选件。 通过复制并编辑选件，您可以轻松创建类似的新选件。
* **移动**：单击[!UICONTROL Move]图标，导航到要将选件或文件夹移动到的位置，然后单击&#x200B;**[!UICONTROL Move]**。 例如，您可以将一个或多个文件夹移动到另一个文件夹以创建子文件夹。

## 删除项目时的注意事项 {#delete}

* 您可以删除包含任意数量的资产和子文件夹的整个文件夹。 此功能在[!DNL Target] UI以及[!DNL Adobe Experience Cloud Assets] UI中均可用。
* 如果删除含有大量图像的文件夹，则在UI刷新以显示最终状态之前，后台运行的进程可能需要花费一些时间（几分钟）。 所需的时间与图像数量成正比，而与图像大小无关。删除 2,000 张图像预计需要 10 分钟。您可以继续执行其他工作，并在几分钟后检查最终状态以验证是否已完成删除。
* 可以删除[!UICONTROL Image Offer library]中的非空文件夹。 如果该文件夹中的所有图像均未在任何活动中引用，则将删除整个文件夹及其内容。如果在任何活动中引用了该文件夹中的某些图像，则将删除所有未引用的图像，但会保留已引用的图像和包含这些图像的文件夹。
