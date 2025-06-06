---
keywords: 重复数据删除；允许重复项；排除重复的选件；自动个性化；不允许重复的选件；排除；默认内容；排除组；
description: 管理 [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP)活动中的排除项。 创建排除组并排除重复的选件、特定体验和默认内容。
title: 如何管理[!UICONTROL Automated Personalization]活动中的排除项？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Automated Personalization
solution: Target,Analytics
exl-id: d9e9f2a2-5914-4b81-acae-eaf388646652
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 41%

---

# 管理排除项

通过创建排除组、排除重复的选件、排除特定体验以及排除[!DNL Adobe Target]中[!UICONTROL Automated Personalization] (AP)活动中的默认内容来管理排除项。

## 创建排除组 {#task_AAAA6C7239A84F7696C8492F04B575A2}

在[!UICONTROL Automated Personalization] (AP)活动中创建排除组以确保自动排除具有指定选件的体验。

排除组是一种非常有用的方法，可确保不同位置的相同体验中不会出现不兼容的选件。例如，假设您有两个优惠：一个是所有商品20%的折扣，另一个是15%的折扣。 您绝不希望向同一体验中的访客展示这两个选件。 如果将这两个选件添加到排除组，则可以确保绝不会出现这种情况。

您还可以限制能够在 AP 活动中查看特定产品建议的受众。有关更多信息，请参阅 [Target 自动个性化产品建议](/help/main/c-activities/t-automated-personalization/ap-target-offers.md)。

**创建排除组：**

1. 在[创建或编辑AP活动](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)时，单击标题栏中的&#x200B;**[!UICONTROL Manage Content]**。

   ![“管理内容”链接](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

1. 在[!UICONTROL Manage Content]对话框中，单击&#x200B;**[!UICONTROL Exclusion Groups]**。

   ![“管理内容”>“排除组”对话框](/help/main/c-activities/t-automated-personalization/assets/exclusion_group_create-new.png)

   如果您之前已经创建一些排除组，它们会显示在列表中。如果您尚未创建排除组，系统会提示您创建一个排除组。

1. 单击&#x200B;**[!UICONTROL Create Exclusion Group.]**

   ![“创建排除组”对话框](/help/main/c-activities/t-automated-personalization/assets/exclusion_group_create_dialog-new.png)

1. （必需）为排除组指定一个描述性名称。

   描述性名称可以帮助您或他人快速找到排除组并了解其用途。

1. 查找并选择要添加到排除组的所需产品建议。

   您可以在排除组中选择来自相同位置的多个产品建议。

1. 单击 **[!UICONTROL Save]**。

之后，排除组中的选件将自动从相同的体验中排除。

## 排除重复的选件 {#concept_4EF78013F80E48EFA024AE0274C9F037}

在[!UICONTROL Automated Personalization]活动中的不同位置使用选件库中的选件时，阻止系统复制这些选件。

例如，在您的一个活动中，一个页面上可能有 6 个位置和 12 个选件。活动中的多个位置可能存在相同的选件。此功能可阻止同一个活动中的不同位置同时显示重复的选件。

单击&#x200B;**[!UICONTROL Configure]**&#x200B;齿轮选项> **[!UICONTROL Duplicate Offers]**，然后单击&#x200B;**[!UICONTROL Allow Duplicates]**&#x200B;或&#x200B;**[!UICONTROL Disallow Duplicates]**。

![“重复的产品建议”选项](/help/main/c-activities/t-automated-personalization/assets/duplicate_offers-new.png)

## 排除特定体验 {#task_C17D36EF58AF4908B17A3D84CA6DE85A}

如果要从[!UICONTROL Automated Personalization]活动中排除某些选件组合，请排除特定体验。

可能有某些组合无法协同工作，或者您可能正在限制测试的体验数量，以降低活动的流量要求。

1. [创建或编辑 AP 活动](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)时，单击标题栏中的&#x200B;**管理内容**。

   ![“管理内容”链接](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   [!UICONTROL Experiences]列表显示了所有内容和位置选项经过排列组合而生成的每个体验。

1. 根据需要排除相应的体验。

   要排除特定的体验，您可以将鼠标悬停在所需体验上，然后单击“排除”图标。

   ![通过悬停排除体验](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_1a.png)

   或者，您也可以批量排除体验，方法是选中相关体验的复选框，然后单击对话框右上角的&#x200B;**[!UICONTROL Exclude]**&#x200B;图标。 选中一个或多个体验后，[!UICONTROL Exclude]图标即会显示。

   ![批量排除体验](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_2a.png)

   您可以通过单击[!UICONTROL Status]下拉列表来筛选此列表视图，以仅查看排除或包含的活动。

   体验现已从活动中排除，其[!UICONTROL Status]显示为[!UICONTROL Excluded]。

   ![已排除的体验](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_3a.png)

## 排除默认内容 {#task_DCB4528989DF4C05A3A4729E5891D18F}

有时，您可能不希望将默认内容包含在[!UICONTROL Automated Personalization]活动中。 访问此设置的方式不同于创建排除组。通过此方法，您可以在 AP 活动中的某个位置仅使用一个产品建议（与默认内容不同）。

排除默认内容是一种非常有用的方法，可用于更改页面上其余内容的外观，以使其符合您在 AP 活动中所测试的产品建议。例如，假设您想要匹配所测试选件的调色板，则可以更改页面的背景颜色并排除默认的背景颜色。

**使用[!UICONTROL Visual Experience Composer] (VEC)排除默认内容：**

1. 在[创建或编辑AP活动](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)时，选择要替换的内容，然后单击以访问&#x200B;**[!UICONTROL Change Text/HTML]**、**[!UICONTROL Change Image]**&#x200B;或&#x200B;**[!UICONTROL Change Background Color]**。
1. 在出现的对话框中，创建新的内容，然后取消选中默认内容右侧的&#x200B;**包含**（或在[!UICONTROL Select Content]屏幕中取消选中“默认图像/视频”）。

   根据内容或选件类型，[!UICONTROL Include]复选框的位置略有不同。

   对于文本/HTML 内容：

   ![“包含”复选框位于“编辑文本/HTML”对话框中](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   对于图像/视频内容：

   ![“包含”复选框位于“选择内容”对话框中](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   对于背景颜色：

   ![“包含”复选框位于“编辑背景颜色”对话框中](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)

1. 单击 **[!UICONTROL Save]**。

   您可以看到使用您在[!UICONTROL Manage Content]下指定的选件创建的体验。 您注意到在[!UICONTROL Manage Content]中并未使用您排除的默认选件创建任何体验。

   ![exclude_content_vec_4图像](assets/exclude_content_vec_4.png)

**要使用[!UICONTROL Form-Based Experience Composer]排除默认内容：**

1. 创建或编辑AP活动时，单击&#x200B;**[!UICONTROL Content]**&#x200B;下的&#x200B;**[!UICONTROL Change Text/HTML]**&#x200B;或&#x200B;**[!UICONTROL Change Image Offer]**。
1. 在出现的对话框中，创建新的内容，然后取消选中默认内容右侧的&#x200B;**[!UICONTROL Include]**（或在[!UICONTROL Select Content]屏幕中取消选中“默认图像/视频”）。

   根据内容或选件类型，[!UICONTROL Include]复选框的位置略有不同。

   对于文本/HTML 内容：

   ![exclude_content_form_1图像](assets/exclude_content_form_1.png)

   对于图像/视频内容：

   ![exclude_content_form_2图像](assets/exclude_content_form_2.png)

1. 单击 **[!UICONTROL Save]**。

   您可以看到使用您在[!UICONTROL Manage Content]下指定的选件创建的体验。 您注意到在[!UICONTROL Manage Content]中并未使用您排除的默认选件创建任何体验。

   ![exclude_content_form_3图像](assets/exclude_content_form_3.png)
