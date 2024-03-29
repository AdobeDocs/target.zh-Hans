---
keywords: 重复数据删除；允许重复项；排除重复的选件；自动个性化；不允许重复的选件；排除；默认内容；排除组；
description: 在中管理排除项 [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP)活动。 创建排除组并排除重复的选件、特定体验和默认内容。
title: 如何在中管理排除项 [!UICONTROL Automated Personalization] 活动？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="请参阅Target Premium中包含的内容。"
feature: Automated Personalization
solution: Target,Analytics
exl-id: d9e9f2a2-5914-4b81-acae-eaf388646652
source-git-commit: b5f06878a6ca8b4c571bfe05a52bfb3f471a697e
workflow-type: tm+mt
source-wordcount: '1011'
ht-degree: 57%

---

# 管理排除项

通过创建排除组、排除重复的选件、排除特定体验以及排除中的默认内容来管理排除项。 [!UICONTROL Automated Personalization] (AP)中的活动 [!DNL Adobe Target].

## 创建排除组 {#task_AAAA6C7239A84F7696C8492F04B575A2}

在中创建排除组 [!UICONTROL Automated Personalization] (AP)活动，以确保自动排除具有指定选件的体验。

排除组是一种非常有用的方法，可确保不同位置的相同体验中不会出现不兼容的选件。例如，假设您有两个优惠：一个是所有商品20%的折扣，另一个是15%的折扣。 您绝不希望向同一体验中的访客展示这两个选件。 如果将这两个选件添加到排除组，则可以确保绝不会出现这种情况。

您还可以限制能够在 AP 活动中查看特定选件的受众。有关更多信息，请参阅 [Target 自动个性化选件](/help/main/c-activities/t-automated-personalization/ap-target-offers.md)。

**创建排除组：**

1. [创建或编辑 AP 活动](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)时，单击标题栏中的&#x200B;**[!UICONTROL 管理内容]**。

   ![“管理内容”链接](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

1. 在 [!UICONTROL 管理内容] 对话框中，单击 **[!UICONTROL 排除组]**.

   ![“管理内容”>“排除组”对话框](/help/main/c-activities/t-automated-personalization/assets/exclusion_group_create-new.png)

   如果您之前已经创建一些排除组，它们会显示在列表中。如果您尚未创建排除组，系统会提示您创建一个排除组。

1. 单击&#x200B;**[!UICONTROL 创建排除组]**。

   ![“创建排除组”对话框](/help/main/c-activities/t-automated-personalization/assets/exclusion_group_create_dialog-new.png)

1. （必需）为排除组指定一个描述性名称。

   描述性名称可以帮助您或他人快速找到排除组并了解其用途。

1. 查找并选择要添加到排除组的所需选件。

   您可以在排除组中选择来自相同位置的多个选件。

1. 单击&#x200B;**[!UICONTROL 保存]**。

之后，排除组中的选件将自动从相同的体验中排除。

## 排除重复的选件 {#concept_4EF78013F80E48EFA024AE0274C9F037}

在[!UICONTROL 自动个性化]活动的不同位置中使用来自选件库的选件时，应防止选件出现重复。

例如，在您的一个活动中，一个页面上可能有 6 个位置和 12 个选件。活动中的多个位置可能存在相同的选件。此功能可阻止同一个活动中的不同位置同时显示重复的选件。

单击 **[!UICONTROL 配置]** 齿轮选项> **[!UICONTROL 重复的选件]**，然后单击 **[!UICONTROL 允许重复项]** 或 **[!UICONTROL 不允许重复项]**.

![“重复的选件”选项](/help/main/c-activities/t-automated-personalization/assets/duplicate_offers-new.png)

## 排除特定体验 {#task_C17D36EF58AF4908B17A3D84CA6DE85A}

如果要从中排除某些选件组合，请排除特定体验 [!UICONTROL Automated Personalization] 活动。

可能有某些组合无法协同工作，或者您可能正在限制测试的体验数量，以降低活动的流量要求。

1. [创建或编辑 AP 活动](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)时，单击标题栏中的&#x200B;**管理内容**。

   ![“管理内容”链接](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   “[!UICONTROL 体验]”列表显示了所有内容和位置选项经过排列组合而生成的各个体验。

1. 根据需要排除相应的体验。

   要排除特定的体验，您可以将鼠标悬停在所需体验上，然后单击“排除”图标。

   ![通过悬停排除体验](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_1a.png)

   或者，您也可以批量排除体验，方法是选中相关体验的复选框，然后单击 **[!UICONTROL 排除]** 图标。 此 [!UICONTROL 排除] 图标在选中一个或多个体验时显示。

   ![批量排除体验](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_2a.png)

   您可以通过单击[!UICONTROL 状态]下拉列表来筛选此列表视图，以仅查看排除或包含的活动。

   该体验现已从活动中排除，其 [!UICONTROL 状态] 显示为 [!UICONTROL 已排除].

   ![已排除的体验](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_3a.png)

## 排除默认内容 {#task_DCB4528989DF4C05A3A4729E5891D18F}

有时，您可能不希望将默认内容包含在 [!UICONTROL Automated Personalization] 活动。 访问此设置的方式不同于创建排除组。通过此方法，您可以在 AP 活动中的某个位置仅使用一个选件（与默认内容不同）。

排除默认内容是一种非常有用的方法，可用于更改页面上其余内容的外观，以使其符合您在 AP 活动中所测试的选件。例如，假设您想要匹配所测试选件的调色板，则可以更改页面的背景颜色并排除默认的背景颜色。

**使用可视化体验编辑器 (VEC) 排除默认内容：**

1. 同时 [创建或编辑AP活动](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)，选择要替换的内容，然后单击以访问 **[!UICONTROL 更改文本/HTML]**， **[!UICONTROL 更改图像]**，或 **[!UICONTROL 更改背景颜色]**.
1. 在出现的对话框中，创建新的内容，然后取消选中默认内容右侧的&#x200B;**包含**&#x200B;复选框（或在“选择内容”屏幕中取消选中“默认图像/视频”）。

   根据内容或选件类型， [!UICONTROL 包括] 复选框的位置略有不同。

   对于文本/HTML 内容：

   ![“包含”复选框位于“编辑文本/HTML”对话框中](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   对于图像/视频内容：

   ![“包含”复选框位于“选择内容”对话框中](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   对于背景颜色：

   ![“包含”复选框位于“编辑背景颜色”对话框中](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)

1. 单击&#x200B;**[!UICONTROL 保存]**。

   您可以在“[!UICONTROL 管理内容]”下方看到使用指定的选件创建的体验。您注意到中并未创建任何体验 [!UICONTROL 管理内容] 使用您排除的默认选件。

   ![exclude_content_vec_4图像](assets/exclude_content_vec_4.png)

**要使用排除默认内容，请执行以下操作 [!UICONTROL 基于表单的体验编辑器]：**

1. 创建或编辑 AP 活动时，在&#x200B;**[!UICONTROL 内容]**&#x200B;下方单击&#x200B;**[!UICONTROL 更改文本/HTML]**&#x200B;或&#x200B;**[!UICONTROL 更改图像选件]**。
1. 在出现的对话框中，创建新的内容，然后取消选中默认内容右侧的&#x200B;**[!UICONTROL 包含]**&#x200B;复选框（或在“选择内容”屏幕中取消选中“默认图像/视频”）。

   根据内容或选件类型， [!UICONTROL 包括] 复选框的位置略有不同。

   对于文本/HTML 内容：

   ![exclude_content_form_1图像](assets/exclude_content_form_1.png)

   对于图像/视频内容：

   ![exclude_content_form_2图像](assets/exclude_content_form_2.png)

1. 单击&#x200B;**[!UICONTROL 保存]**。

   您可以在“[!UICONTROL 管理内容]”下方看到使用指定的选件创建的体验。您注意到中并未创建任何体验 [!UICONTROL 管理内容] 使用您排除的默认选件。

   ![exclude_content_form_3图像](assets/exclude_content_form_3.png)
