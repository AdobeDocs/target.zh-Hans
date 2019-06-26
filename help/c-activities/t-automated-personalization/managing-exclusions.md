---
description: 通过创建排除组、排除重复的选件、排除特定体验以及排除自动个性化(AP)活动中的默认内容来管理排除。
keywords: 重复数据删除技术;允许重复项;排除重复的选件;自动个性化;不允许重复的选件
seo-description: 通过创建排除组、排除重复的选件、排除特定体验以及排除Adobe Target自动个性化(AP)活动中的默认内容来管理排除。
seo-title: 管理排除项
solution: Target,Analytics
title: 管理排除项
uuid: c67901d2-19cd-47d3-b8c4-abdcb046f404
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# ![高级徽章](/help/assets/premium.png) 管理排除{#manage-exclusions}

通过创建排除组、排除重复的选件、排除特定体验以及排除自动个性化(AP)活动中的默认内容来管理排除。

## Create exclusion groups {#task_AAAA6C7239A84F7696C8492F04B575A2}

可在自动个性化 (AP) 活动中创建排除组，以确保自动排除具有指定选件的体验。

排除组是一种非常有用的方法，可确保不同位置的相同体验中不会出现不兼容的选件。例如，假设您有两个选件：一个选件是所有商品八折优惠，而另一个选件是所有商品八五折优惠。您一定不希望在同一个体验中同时向访客显示这两个选件。如果您将这两个选件添加到一个排除组，便可以确保永远不会出现这种情况。

您还可以限制哪些受众可以在AP活动中查看特定优惠。For more information, see [Target Automated Personalization offers](/help/c-activities/t-automated-personalization/ap-target-offers.md).

**创建排除组：**

1. [创建或编辑AP活动时](/help/c-activities/t-automated-personalization/create-ap-activity.md)，单击 **[!UICONTROL 标题栏中的“管理内容]** ”。

   ![管理内容链接](/help/c-activities/t-automated-personalization/assets/manage-content.png)

1. 在[!UICONTROL 管理内容]对话框中，单击 **[!UICONTROL 排除组]**。

   ![“管理内容”&gt;“排除组”对话框](/help/c-activities/t-automated-personalization/assets/exclusion_group_create-new.png)

   如果您之前已经创建一些排除组，它们会显示在列表中。如果您尚未创建排除组，系统会提示您创建一个排除组。

1. 单击 **[!UICONTROL 创建排除组]**。

   ![“创建排除组”对话框](/help/c-activities/t-automated-personalization/assets/exclusion_group_create_dialog-new.png)

1. （必需）为排除组指定一个描述性名称。

   描述性名称可以帮助您或他人快速找到排除组并了解其用途。

1. 查找并选择要添加到排除组的所需选件。

   您可以在排除组中选择来自相同位置的多个选件。

1. 单击 **[!UICONTROL 保存]**。

之后，排除组中的选件将自动从相同的体验中排除。

## Exclude duplicate offers {#concept_4EF78013F80E48EFA024AE0274C9F037}

在[!UICONTROL 自动个性化]活动的不同位置中使用来自选件库的选件时，应防止选件出现重复。

例如，在您的一个活动中，一个页面上可能有 6 个位置和 12 个选件。活动中的多个位置可能存在相同的选件。此功能可阻止同一个活动中的不同位置同时显示重复的选件。

单击 **[!UICONTROL 配置]** &gt; **[!UICONTROL 重复的选件]**，然后单击 **[!UICONTROL 允许重复项]** 或 **[!UICONTROL 不允许重复项]**。

![选件选项重复](/help/c-activities/t-automated-personalization/assets/duplicate_offers-new.png)

## Exclude specific experiences {#task_C17D36EF58AF4908B17A3D84CA6DE85A}

如果您想要从自动个性化活动中排除某些选件组合，则可以排除特定的体验。

某些体验可能不适合组合在一起使用，或者您可能想要限制测试的体验数量，以减少活动所需的流量。

1. [创建或编辑AP活动时](/help/c-activities/t-automated-personalization/create-ap-activity.md)，单击 **标题栏中的“管理内容** ”。

   ![管理内容链接](/help/c-activities/t-automated-personalization/assets/manage-content.png)

   “[!UICONTROL 体验]”列表显示了所有内容和位置选项经过排列组合而生成的各个体验。

1. 根据需要排除相应的体验。

   要排除特定的体验，您可以将鼠标悬停在所需体验上，然后单击“排除”图标。

   ![通过悬停排除体验](/help/c-activities/t-automated-personalization/assets/exclude_exp_1a.png)

   Or you can batch exclude/include experiences by selecting the checkbox for the relevant experiences and then clicking the **[UICONTROL Exclude]** icon in the top right corner of the dialog box. The [!UICONTROL Exclude] icon appears when one or more experiences are checked.

   ![批量排除体验](/help/c-activities/t-automated-personalization/assets/exclude_exp_2a.png)

   您可以通过单击“[!UICONTROL 状态]”下拉列表来筛选此列表视图，以仅查看排除或包含的体验。

   此时，选中的体验将从活动中排除，且其“[!UICONTROL 状态]”将显示为“[!UICONTROL 已排除]”。

   ![排除的体验](/help/c-activities/t-automated-personalization/assets/exclude_exp_3a.png)

## Exclude default content {#task_DCB4528989DF4C05A3A4729E5891D18F}

在某些情况下，您可能不希望将默认内容包含在自动个性化活动中。访问此设置的方式不同于创建排除组。您可以使用此方法在AP活动的一部分中仅有一个选件(不同于默认内容)。

排除默认内容是更改页面其余部分外观和感觉以满足您在AP活动中测试的选件的绝佳方法。例如，假设您想要匹配所测试选件的调色板，则可以更改页面的背景颜色并排除默认的背景颜色。

**使用可视化体验编辑器 (VEC) 排除默认内容：**

1. [创建或编辑AP活动](/help/c-activities/t-automated-personalization/create-ap-activity.md)时，选择要替换的内容，然后单击以访问 **[!UICONTROL 更改文本/HTML]**、 **[!UICONTROL 更改图像]** 或 **[!UICONTROL 更改背景颜色]**。
1. 在出现的对话框中，创建新的内容，然后取消选中默认内容右侧的 **包含** 复选框（或在“选择内容”屏幕中取消选中“默认图像/视频”）。

   “[!UICONTROL 包含]”复选框的位置可能会因内容/选件类型而略有不同。

   对于文本/HTML 内容：

   ![在“编辑文本/HTML”对话框中包含复选框](/help/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   对于图像/视频内容：

   ![在“选择内容”对话框中包含复选框](/help/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   对于背景颜色：

   ![在“编辑背景颜色”对话框中包含复选框](/help/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)

1. 单击 **[!UICONTROL 保存]**。

   您可以在“[!UICONTROL 管理内容]”下方看到使用指定的选件创建的体验。您会注意到，“[!UICONTROL 管理内容]”中不存在使用已排除的默认选件创建的任何体验。

   ![](assets/exclude_content_vec_4.png)

**使用基于表单的体验编辑器排除默认内容：**

1. 创建或编辑 AP 活动时，在 **[!UICONTROL 内容]** 下方单击 **[!UICONTROL 更改文本/HTML]** 或 **[!UICONTROL 更改图像选件]**。
1. 在出现的对话框中，创建新的内容，然后取消选中默认内容右侧的 **[!UICONTROL 包含]复选框（或在“选择内容”屏幕中取消选中“默认图像/视频”）。**

   “包含”复选框的位置可能会因内容/选件类型而略有不同。

   对于文本/HTML 内容：

   ![](assets/exclude_content_form_1.png)

   对于图像/视频内容：

   ![](assets/exclude_content_form_2.png)

1. 单击 **[!UICONTROL 保存]**。

   您可以在“[!UICONTROL 管理内容]”下方看到使用指定的选件创建的体验。您会注意到，“[!UICONTROL 管理内容]”中不存在使用已排除的默认选件创建的任何体验。

   ![](assets/exclude_content_form_3.png)
