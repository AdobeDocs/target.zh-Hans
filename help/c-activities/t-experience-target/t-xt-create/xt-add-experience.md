---
keywords: 创建体验;体验创建;优先级;受众;体验;可视化体验编辑器
description: Adobe Target 可视化体验编辑器 (VEC) 提供了一个可视化界面，用于编辑体验定位 (XT) 活动中的页面上的体验。
title: 创建体验
topic: Advanced,Standard,Classic
uuid: ce559c3c-5a16-46b8-b2a7-df696626c7c0
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 创建体验{#create-experience}

[!UICONTROL 可视化体验编辑器] (VEC) 提供了一个可视化界面，用于编辑[!UICONTROL 体验定位] (XT) 活动中的页面上的体验。

1. 选择要更改的元素，然后进行所需的更改。

   在[创建 XT 活动](/help/c-activities/t-experience-target/t-xt-create/xt-create.md)时，三步引导式工作流（[!UICONTROL 体验]）中的第一步会显示具有[!UICONTROL 所有访客]受众的默认[!UICONTROL 体验 A]。

   ![“所有访客”受众](/help/c-activities/t-experience-target/t-xt-create/assets/all-visitors.png)

   您现在所做的任何更改均会应用于体验 A。在下面的步骤中，您将单击&#x200B;**[!UICONTROL 添加体验定位]**&#x200B;以创建其他体验。

   将鼠标悬停在页面中的元素上时，这些元素会高亮显示。任何高亮显示的元素都可以使用 VEC 进行更改。有关为更改体验而可对元素执行的操作列表，请参阅[可视化体验编辑器选项](/help/c-experiences/c-visual-experience-composer/viztarget-options.md)。

   如果您曾使用 [!DNL Target Classic] 在页面上创建了 mbox，则该 mbox 将显示为一个元素，该元素会显示 mbox 名称，且可以像其他任何元素一样进行修改。

   >[!NOTE]
   >
   >默认情况下，VEC 不允许更改包含 JavaScript 的元素，如旋转横幅。您可以选择禁用 JavaScript 以使用 VEC 更改这些元素。

1. 要创建其他体验，请单击&#x200B;**[!UICONTROL 添加体验定位]**。

   ![“添加体验定位”链接](/help/c-activities/t-experience-target/t-xt-create/assets/add-experience-targeting.png)

   此时会显示“[!UICONTROL 选择受众]”对话框。要将体验定位到某个受众，必须先选择该受众，然后才能添加体验。

   受众库中包含以前定义的受众，其中包括作为 [!DNL Target] 的一部分预先构建的一些常用受众。您可以从库中选择受众或[创建新受众](../../../c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271)。

   >[!NOTE]
   >
   >除了选择现有受众之外，您还可以合并多个受众来创建临时组合受众，而不是创建新受众。有关更多信息，请参阅[合并多个受众](../../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

   在创建受众时，您可以选择一个位置 (mbox) 并指定该位置的参数。在“[!UICONTROL 自定义]”（“创建受众”&gt;“添加规则”&gt;“自定义”）下，选择 mbox，然后指定所需的参数。

   >[!NOTE]
   >
   >打开受众列表时会在后台自动导入受众，导入的受众为 10 分钟之前的受众。

1. 选择一个或多个要将体验定位到的受众，然后单击&#x200B;**[!UICONTROL 完成]**。

   ![体验 B](/help/c-activities/t-experience-target/t-xt-create/assets/experience-b.png)

   您会注意到，体验 B 现在显示在上图中，且此体验定位到美国访客受众。

1. 选择要为此体验更改的元素并进行所需的更改，如上面的步骤 1 中所述。

1. 根据需要重复上述步骤以创建更多目标体验。

1. 完成体验设计后，单击&#x200B;**[!UICONTROL 下一步]**。

   活动图显示如下：

   ![XT 定位图](/help/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-new.png)

   >[!NOTE]
   >
   >如果您交付的图像来自主页以外的其他来源（例如将一个在 `akamai.net` 上托管的图像交付到 `adobe.com`），则该图像不会出现在流程图中显示的页面缩览图中。

1. （视情况而定）在创建或编辑 XT 活动时，拖放受众/体验对以按所需的顺序排列受众/体验对。

   将按从上到下的顺序评估访客的体验。

   ![移动体验](/help/c-activities/t-experience-target/t-xt-create/assets/move_experiences-new.png)

   [!UICONTROL 体验定位]假定排序至关重要。如果访客属于第一个受众/体验对，则会交付第一个体验。

   例如，假定您在创建 XT 活动时并不知道排序的重要性。随后，您在测试过程中意识到，您认为应符合体验 B 或 C 的条件的访客而是符合了体验 A 的条件。这可能是因为受众之间不存在互斥关系，并且它们的顺序不正确（例如，体验 A = 美国，体验 B = 旧金山，体验 C = 加利福尼亚州）所导致。在此情景中，来自美国的所有用户都符合体验 A 的条件，无论他们在旧金山还是在加利福尼亚州的其他地区。您可以按限制性由高到低（旧金山 &gt; 加利福尼亚州 &gt; 美国）重新排列受众/体验对，而不必重新创建整个活动。

   如果您具有“[!UICONTROL 所有访客]”受众，请确保它不是图中的第一个受众。定位到“所有访客”的体验可以用作体验定位活动中的最后一个体验，以“捕获”所有还未进入任何其他体验的访客。

## 重命名或编辑体验

您可以单击 XT 活动中某个体验的“[!UICONTROL 编辑]”（三个垂直省略号）图标，并根据需要从以下选项中进行选择：

* 重命名
* 编辑

![“重命名”和“编辑”选项](/help/c-activities/t-experience-target/t-xt-create/assets/experience_edit-new.png)

## 删除体验

在&#x200B;**[!UICONTROL 体验]**&#x200B;页面（三步引导式工作流的步骤 1）中，依次单击三个垂直省略号图标 &gt; **[!UICONTROL 删除]**。

![删除体验](/help/c-activities/t-experience-target/t-xt-create/assets/delete-experience.png)

## 复制体验

您可以复制 XT 活动中的体验，以便可以对其进行细微更改，而无需重头开始重新创建体验。

在&#x200B;**[!UICONTROL 体验]**&#x200B;页面（三步引导式工作流的步骤 1）中，依次单击三个垂直省略号图标 &gt; **[!UICONTROL 复制]**。

![复制体验](/help/c-activities/t-experience-target/t-xt-create/assets/duplicate_experience-new.png)

## 培训视频：

以下视频包含有关本文中所讨论概念的详细信息。

### 从 A/B 测试到体验定位

以下视频介绍了如何使用体验定位 (XT) 将 A/B 测试提升到新的水平。

* 描述了用于配置 XT 活动的三步引导式工作流
* 描述了如何向位于不同地理区域的受众交付特定于位置的内容
* 描述如何对体验重新排序，以确保将适当的内容交付给适当的受众

>[!VIDEO](https://video.tv.adobe.com/v/22418/?captions=chi_hans)

### 活动类型 (9:03)

以下视频介绍了 Target Standard/Premium 中可用的活动类型。对体验定位的讨论开始于 5:15。

* 介绍 [!DNL Adobe Target] 中包含的活动类型
* 选择相应的活动类型以实现目标
* 介绍适用于所有活动类型的三步引导式工作流

>[!VIDEO](https://video.tv.adobe.com/v/17386?captions=chi_hans)

### 使用可视化体验编辑器

以下视频提供了有关使用可视化体验编辑器选项的信息。

* 更改页面的内容
* 更改页面的布局

>[!VIDEO](https://video.tv.adobe.com/v/17399?captions=chi_hans)