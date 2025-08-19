---
keywords: 定位;体验;添加体验;体验添加
description: 了解如何在[!UICONTROL Visual Experience Composer]中使用 [!DNL Adobe Target] (VEC)。
title: 如何在A [!DNL Target] A/B活动中添加体验？
feature: A/B Tests
exl-id: c0f1b5a7-07b0-46c2-97f3-95dcc0fcbe3d
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 43%

---

# 添加体验

[!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC)提供了一个可视化界面，用于添加和编辑页面上的体验。

有关体验的更多详细信息，请参阅[体验](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)。

1. 在VEC的&#x200B;**[!UICONTROL Experiences]**&#x200B;页面中，单击&#x200B;**[!UICONTROL Add Experience]**。

   ![“添加体验”选项](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/add-experience.png)

   >[!NOTE]
   >
   >如果您要将体验定位到某个受众，则必须先选择该受众，然后才能添加体验。此时将显示一则消息提醒您选择受众。

1. 选择要更改的元素，然后进行所需的更改。

   将鼠标悬停在页面上的元素上时，这些元素会高亮显示。 任何高亮显示的元素都可以使用VEC进行更改。

   如果您使用[!DNL Target]（以前为[!DNL Target Classic]）在页面上创建了[!DNL Test&Target]请求，则[!DNL Target]请求将显示为一个元素，该元素显示请求名称，并且可以像任何其他元素一样进行修改。

   有关可对显示页面上的元素执行以更改体验的操作列表，请参阅[可视化体验编辑器选项](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)。

   >[!NOTE]
   >
   >如果您交付的图像来自主页以外的其他来源（例如将一个在 `akamai.net` 上托管的图像交付到 `example.com`），则该图像不会出现在流程图中显示的页面缩览图中。

1. 完成体验设计后，请单击&#x200B;**[!UICONTROL Save]**。

## 重命名体验

1. 单击&#x200B;**[!UICONTROL Rename Experience]**&#x200B;或[!UICONTROL A/B Test] (XT)活动中体验的[!UICONTROL Experience Targeting]图标，为体验提供一个新名称。

   ![重命名体验](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/rename-experience.png)

2. 指定新名称。

   在命名或重命名体验时，不允许使用以下字符：

   | 字符 | 描述 |
   |--- |--- |
   | / | 正斜线 |
   | ? | 问号 |
   | # | 数字符号 |
   | : | 冒号 |
   | = | 等号 |
   | + | 加号 |
   | - | 减号 |
   | @ | @ 符号 |

## 重新定向到 URL

1. 单击&#x200B;**[!UICONTROL More]**&#x200B;或[!UICONTROL A/B Test] (XT)活动中某个体验的[!UICONTROL Experience Targeting]图标（垂直省略号）图标，然后单击&#x200B;**[!UICONTROL Redirect to URL]**。

   有关更多信息，请参阅[重定向到 URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md)。

   **注意**：在命名或重命名体验时，不允许使用以下字符：

   | 字符 | 描述 |
   |--- |--- |
   | / | 正斜线 |
   | ? | 问号 |
   | # | 数字符号 |
   | : | 冒号 |
   | = | 等号 |
   | + | 加号 |
   | - | 减号 |
   | @ | @ 符号 |

1. 指定要将体验重定向到的URL。

1. （视情况而定）选中&#x200B;**[!UICONTROL Include Current Query Parameters]**&#x200B;复选框。

## 复制体验

您可以复制[!UICONTROL A/B Test]中的体验，以便可以对其进行细微更改，而无需重头开始重新创建体验。

1. 在&#x200B;**[!UICONTROL Experiences]**&#x200B;页面（三步引导式工作流的步骤1）中，单击垂直省略号图标> **[!UICONTROL Duplicate]**。

   ![复制体验选项](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/duplicate-experience.png)

## 删除体验

1. 在&#x200B;**[!UICONTROL Experiences]**&#x200B;页面（三步引导式工作流的步骤1）中，单击垂直省略号图标> **[!UICONTROL Duplicate]**。

   ![删除体验选项](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/delete-experience.png)

## 培训视频：使用[!UICONTROL Visual Experience Composer]

以下视频提供了有关使用[!UICONTROL Visual Experience Composer]选项的信息。 (7:17)

* 更改页面的内容
* 更改页面的布局

>[!VIDEO](https://video.tv.adobe.com/v/30331?captions=chi_hans)
