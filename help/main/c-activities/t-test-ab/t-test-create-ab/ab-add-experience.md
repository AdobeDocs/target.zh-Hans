---
keywords: 定位;体验;添加体验;体验添加
description: 使用[!UICONTROL 可视化体验编辑器] (VEC)向活动添加体验。
title: 如何在A/B活动中添加体验？
feature: A/B Tests
exl-id: c0f1b5a7-07b0-46c2-97f3-95dcc0fcbe3d
TQID: https://experienceleague.adobe.com/7qEiUXkfMbPmtB2eMio0LztOYM3naHxG-WRQZOyMmlU
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 420
ht-degree: 30%

---

# 添加体验

[!DNL Adobe Target] [!UICONTROL 可视化体验编辑器] (VEC)提供了一个可视化界面，用于添加和编辑您页面上的体验。

有关体验的更多详细信息，请参阅[体验](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)。

1. 在VEC的&#x200B;**[!UICONTROL 体验]**&#x200B;页面中，单击[!UICONTROL 体验]窗格顶部的[!UICONTROL 添加]图标（![添加图标](/help/main/assets/icons/Add.svg)）。

   创建新活动后，VEC在左侧显示两个选项卡：体验A和体验B。体验A是控制体验。 您可以在测试中添加多个体验。

1. 选择要更改的元素，然后进行所需的更改。

   将鼠标悬停在页面上的元素上时，这些元素会高亮显示。 任何高亮显示的元素都可以使用 VEC 进行更改。

   如果您使用[!DNL Target Classic]（以前为[!DNL Test&Target]）在页面上创建了[!DNL Target]请求，则[!DNL Target]请求将显示为一个元素，该元素显示请求名称，并且可以像任何其他元素一样进行修改。

   有关可对显示页面上的元素执行以更改体验的操作列表，请参阅[可视化体验编辑器选项](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)。

   >[!NOTE]
   >
   >如果您交付的图像来自主页以外的其他来源（例如将一个在 `akamai.net` 上托管的图像交付到 `example.com`），则该图像不会出现在流程图中显示的页面缩览图中。

1. 完成体验设计后，单击&#x200B;**[!UICONTROL 下一步]**。

## 重命名体验

1. 单击体验旁边的&#x200B;**[!UICONTROL 重命名体验]**&#x200B;图标（![重命名图标](/help/main/assets/icons/Rename.svg)），为体验提供一个新名称。

2. 指定新名称，然后单击&#x200B;**[!UICONTROL 保存]**。

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

1. 在&#x200B;**[!UICONTROL 体验]**&#x200B;窗格中，单击体验旁边的&#x200B;**[!UICONTROL 更多]**&#x200B;图标（![更多图标](/help/main/assets/icons/MoreSmall.svg)），然后单击&#x200B;**[!UICONTROL 重定向到URL]**。

   有关更多信息，请参阅[重定向到 URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md)。

1. 指定要将体验重定向到的URL。

1. （视情况而定）选中&#x200B;**[!UICONTROL 包含当前查询参数]**&#x200B;复选框。

1. 单击&#x200B;**[!UICONTROL 保存]**。

## 复制体验

您可以复制[!UICONTROL A/B测试]中的体验，以便可以对其进行细微更改，而无需重新创建体验。

1. 在&#x200B;**[!UICONTROL 体验]**&#x200B;窗格中，单击体验旁边的&#x200B;**[!UICONTROL 更多]**&#x200B;图标（![更多图标](/help/main/assets/icons/MoreSmall.svg)），然后单击&#x200B;**[!UICONTROL 复制]**。

## 删除体验

1. 在&#x200B;**[!UICONTROL 体验]**&#x200B;窗格中，单击体验旁边的&#x200B;**[!UICONTROL 更多]**&#x200B;图标（![更多图标](/help/main/assets/icons/MoreSmall.svg)），单击&#x200B;**[!UICONTROL 删除]**，然后单击&#x200B;**[!UICONTROL 删除]**&#x200B;以确认操作。
