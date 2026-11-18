---
keywords: 重复数据删除；允许重复项；排除重复的选件；自动个性化；不允许重复的选件；排除；默认内容；
description: 管理[!UICONTROL Automated Personalization] (AP)活动中的排除项。
title: 如何管理[!UICONTROL Automated Personalization]活动中的排除项？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Automated Personalization
solution: Target,Analytics
exl-id: d9e9f2a2-5914-4b81-acae-eaf388646652
TQID: 'https://experienceleague.adobe.com/ERpNwQPsIRBmU0vTZbGa-lYg30BYl-uJxA8UT0f6060'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 4%
---
# 管理排除项 {#manage-exclusions}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何在&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动中阻止重复的选件、排除特定体验和排除默认内容。

>[!ENDSHADEBOX]

排除项控制&#x200B;**[!UICONTROL Automated Personalization]** (AP)活动提供哪些优惠和体验。 它们可防止同一选件显示两次，删除不兼容的选件组合，并删除默认内容，以使活动提供与您的目标和受众一致的更清晰、更相关的体验。

## 允许或禁止重复的选件 {#allow-duplicate-offers}

<a id="concept_4EF78013F80E48EFA024AE0274C9F037"></a>

在AP活动中的不同位置使用选件库中的选件时，请防止重复这些选件。

例如，一个活动在具有12个选件的页面上可以有6个位置，因此同一选件可以放置在多个位置。 不允许重复的选件，这会阻止在同一活动中的不同位置同时显示同一选件。

1. 在[创建或编辑AP活动](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity)时，单击&#x200B;**[!UICONTROL 配置]**&#x200B;图标（![配置图标](/help/main/assets/icons/Setting.svg)）。

1. 单击&#x200B;**[!UICONTROL 允许重复的选件]**&#x200B;可根据需要打开或关闭此功能。

   ![配置图标](../assets/exclusion-1.png)

## 排除特定体验 {#exclude-experiences}

<a id="task_C17D36EF58AF4908B17A3D84CA6DE85A"></a>

排除特定体验，以从AP活动中删除某些选件组合。 某些组合可能无法正常工作，或者您可以限制测试的体验数量以降低活动的流量要求。

1. 在[创建或编辑AP活动](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity)时，单击&#x200B;**[!UICONTROL 管理内容]**&#x200B;图标（![管理内容图标](/help/main/assets/icons/Experience.svg)）。

   “**[!UICONTROL 体验]**”列表显示了所有内容和位置选项经过排列组合而生成的各个体验。

1. 排除您不想测试的体验。

   * 要排除单个体验，请单击&#x200B;**[!UICONTROL 更多操作]**&#x200B;图标（![更多操作图标](/help/main/assets/icons/MoreSmall.svg)），然后单击&#x200B;**[!UICONTROL 排除]**。
   * 要同时排除多个体验，请选中每个体验对应的复选框，然后单击&#x200B;**[!UICONTROL 排除]**。 选择一个或多个体验时，将显示&#x200B;**[!UICONTROL 排除]**&#x200B;图标。

   ![批量排除体验](/help/main/c-activities/t-automated-personalization/assets/exclude1.png)

   体验现已从活动中排除，其&#x200B;**[!UICONTROL 状态]**&#x200B;显示为&#x200B;**[!UICONTROL 已排除]**。

## 排除默认内容 {#exclude-default-content}

<a id="task_DCB4528989DF4C05A3A4729E5891D18F"></a>

如果不希望默认内容成为AP活动的一部分，请将其排除，这样某个位置将只包含一个与默认内容不同的选件。 此方法还允许您更改页面其余部分的外观，以适合您测试的选件。 例如，要匹配选件的调色板，您可以更改页面的背景颜色并排除默认的背景颜色。

1. 在[创建或编辑AP活动](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity)时，选择要替换的内容，然后单击&#x200B;**[!UICONTROL 更改文本/HTML]**、**[!UICONTROL 更改图像选件]**&#x200B;或&#x200B;**[!UICONTROL 更改背景颜色]**。 可用选项因内容类型而异。

   ![更改选项](../assets/exclusion-1.png)

1. 创建新内容。

1. 单击&#x200B;**[!UICONTROL 更多操作]**&#x200B;图标（![更多操作图标](/help/main/assets/icons/Setting.svg)），然后单击&#x200B;**排除默认选件/包含默认选件**&#x200B;切换以排除或包含默认选件。

   <!--
   Depending on the content or offer type, the [!UICONTROL Include] checkbox is in a slightly different place. 

   For Text/HTML content: 

   ![Include checkbox in Edit Text/HTML dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   For Image/Video content: 

   ![Include checkbox in Select Content dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   For background color: 

   ![Include checkbox in Edit Background Color dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)
   -->

<!--
1. Click **[!UICONTROL Save]**.

   You can see the experiences created from the offers you specified under [!UICONTROL Manage Content]. You notice that no experiences are created in [!UICONTROL Manage Content] using the default offer you excluded. 

   ![exclude_content_vec_4 image](assets/exclude_content_vec_4.png)

**To exclude default content using the [!UICONTROL Form-Based Experience Composer]:** 

1. While creating or editing an AP activity, click **[!UICONTROL Change Text/HTML]** or **[!UICONTROL Change Image Offer]** under **[!UICONTROL Content]**. 
1. In the dialog box, create your new content and uncheck **[!UICONTROL Include]** to the right of the default content (or uncheck the Default Image/Video in the [!UICONTROL Select Content] screen). 

   Depending on the content or offer type, the [!UICONTROL Include] checkbox is in a slightly different place. 

   For Text/HTML content: 

   ![exclude_content_form_1 image](assets/exclude_content_form_1.png)

   For Image/Video content: 

   ![exclude_content_form_2 image](assets/exclude_content_form_2.png)

1. Click **[!UICONTROL Save]**. 

   You can see the experiences created from the offers you specified under [!UICONTROL Manage Content]. You notice that no experiences are created in [!UICONTROL Manage Content] using the default offer you excluded. 

   ![exclude_content_form_3 image](assets/exclude_content_form_3.png)
-->
