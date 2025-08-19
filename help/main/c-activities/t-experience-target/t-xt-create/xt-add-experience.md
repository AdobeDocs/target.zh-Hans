---
keywords: 创建体验;体验创建;优先级;受众;体验;可视化体验编辑器
description: 了解如何使用 [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC)在[!UICONTROL Experience Targeting] (XT)活动中的页面上创建和编辑体验。
title: 如何在[!UICONTROL Experience Targeting]活动中创建体验？
feature: Experience Targeting
exl-id: ec3fcd93-5557-4f69-8f9c-4d00569188ad
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '897'
ht-degree: 23%

---

# 在[!UICONTROL Experience Targeting] (XT)活动中创建体验

[!UICONTROL Visual Experience Composer]中的[!DNL Adobe Target] (VEC)提供了一个可视化界面，用于编辑[!UICONTROL Experience Targeting] (XT)活动中的页面上的体验。

1. 选择要更改的元素，然后进行所需的更改。

   在[创建[!UICONTROL Experience Targeting]活动](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)时，三步引导式工作流([!UICONTROL Experiences])中的第一步会显示具有[!UICONTROL Experience A]受众的默认[!UICONTROL All Visitors]。

   ![“所有访客”受众](/help/main/c-activities/t-experience-target/t-xt-create/assets/all-visitors-new.png)

   您现在所做的任何更改均适用于[!UICONTROL Experience A]。 在下面的步骤中，单击&#x200B;**[!UICONTROL Add Experience Targeting]**&#x200B;以创建其他体验。

   将鼠标悬停在页面上的元素上时，这些元素会高亮显示。 任何高亮显示的元素都可以使用 VEC 进行更改。有关为更改体验而可对元素执行的操作列表，请参阅[可视化体验编辑器选项](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)。

   >[!NOTE]
   >
   >默认情况下，VEC 不允许更改包含 JavaScript 的元素，如旋转横幅。您可以禁用JavaScript以使用VEC更改这些元素。

1. 要创建其他体验，请单击&#x200B;**[!UICONTROL Add]** （![添加按钮](/help/main/assets/icons/Add.svg) ）。

   此时将显示[!UICONTROL Add Audience]对话框。 要将体验定位到某个受众，请在添加体验之前选择该受众。

   受众库中包含以前定义的受众，其中包括作为 [!DNL Target] 的一部分预先构建的一些常用受众。您可以从库中选择受众或[创建新受众](/help/main/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271)。

   除了选择现有受众之外，您还可以合并多个受众以创建按需合并受众，而不是创建新受众。 有关更多信息，请参阅[合并多个受众](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

   创建受众时，您可以选择位置并指定该位置的参数。 在[!UICONTROL Custom] ([!UICONTROL Create Audience] > [!UICONTROL Custom])下，选择位置，然后指定所需的参数。

   >[!NOTE]
   >
   >打开受众列表时，系统会自动在后台导入受众，导入的受众为10分钟之前的受众。

1. 选择一个或多个要将体验定位到的受众，然后单击&#x200B;**[!UICONTROL Assign Audience]**。

   体验B现在显示在上图中，并且此体验已定位到相应的受众。

1. 选择要为此体验更改的元素，并进行所需的更改，如上面的步骤1中所述。

1. 根据需要重复上述步骤以创建更多目标体验。

1. 完成体验设计后，请单击&#x200B;**[!UICONTROL Next]**。

   活动图显示如下：

   ![XT 定位图](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-refresh.png)

   >[!NOTE]
   >
   >您可以从主页以外的来源（例如在`akamai.net`上托管并在`adobe.com`上交付的图像）交付图像。 在其他位置托管的图像不会显示在流程图中所显示页面的缩略图中。

1. （视情况而定）在创建或编辑[!UICONTROL Experience Targeting]活动时拖放受众和体验对以按所需顺序排列受众和体验对。

   单击“重新排序”图标（![重新排序图标](/help/main/assets/icons/Reorder.svg)）以在右侧显示[!UICONTROL Experiences]列，然后根据需要重新排列体验。

   将按从上到下的顺序评估访客的体验。

   [!UICONTROL Experience Targeting]假定顺序重要。 如果访客属于第一个受众和体验对，则交付第一个体验。

   例如，假设您在创建[!UICONTROL Experience Targeting]活动时不知道顺序很重要。 您稍后在测试期间意识到，您认为应该符合体验B或C的访客实际上符合体验A的资格。这种情况可能是因为受众并非相互排斥，并且顺序不正确（例如，体验A =美国，体验B =旧金山，体验C =加利福尼亚）。 在此情景中，所有来自美国的用户都有资格使用体验A，即使他们位于旧金山或加利福尼亚的其他地方也是如此。 您可以重新排序受众和体验对，从限制最严格到限制最少（旧金山>加利福尼亚>美国），而无需重新创建整个活动。

   如果您有[!UICONTROL All Visitors]受众，请确保它不是图中的第一个受众。 定位到“[!UICONTROL All Visitors]”的体验可以用作[!UICONTROL Experience Targeting]活动中的最后一个体验，以“捕获”所有还未进入任何其他体验的访客。

## 重命名、编辑、复制或删除体验

单击[!UICONTROL Experience Targeting]活动中关系图中的某个体验可在右侧显示[!UICONTROL Experiences]列。

![“重命名”和“编辑”选项](/help/main/c-activities/t-experience-target/t-xt-create/assets/experience_edit-refresh.png)

根据需要，从以下选项中进行选择：

* **[!UICONTROL Rename]**：在[!UICONTROL Name]字段中键入所需的名称。
* **[!UICONTROL Edit]**：单击“编辑”图标（![编辑图标](/help/main/assets/icons/Edit.svg)），然后进行所需的更改。
* **[!UICONTROL Duplicate]**：复制[!UICONTROL Experience Targeting]活动中的体验，以便可以对其进行细微更改，而无需重新创建整个体验。 单击[!UICONTROL Duplicate]图标（![复制图标](/help/main/assets/icons/Duplicate.svg)），然后根据需要编辑体验。
* **[!UICONTROL Delete]**：单击[!UICONTROL Delete]图标（![删除图标](/help/main/assets/icons/Delete.svg)），然后确认删除。

## 培训视频：

以下视频包含有关本文中所讨论概念的详细信息。

### 从A/B测试到[!UICONTROL Experience Targeting]

本视频介绍如何使用[!UICONTROL Experience Targeting] (XT)将A/B测试提升到新的水平。

* 描述用于配置[!UICONTROL Experience Targeting]活动的三步引导式工作流
* 描述如何向不同地理区域的受众交付特定于位置的内容
* 描述如何对体验重新排序，以确保将适当的内容交付给适当的受众

>[!VIDEO](https://video.tv.adobe.com/v/22418/)

### 活动类型(9:03)

以下视频介绍了 [!DNL Target] 中可用的活动类型。从5[!UICONTROL Experience Targeting]开始讨论:15。

* 介绍 [!DNL Adobe Target] 中包含的活动类型
* 选择相应的活动类型以实现目标
* 介绍适用于所有活动类型的三步引导式工作流

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### 使用[!UICONTROL Visual Experience Composer]

本视频提供有关使用[!UICONTROL Experience Targeting] (VEC)选项的信息。

* 更改页面的内容
* 更改页面的布局

>[!VIDEO](https://video.tv.adobe.com/v/17399)
