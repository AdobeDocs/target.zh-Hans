---
description: Visual Experience Composer(CMS)提供可视界面，用于在体验定位(XT)活动中编辑页面上的体验。
keywords: 创建体验;体验创建;优先级;受众;体验;可视化体验编辑器
seo-description: Adobe Target Visual Experience Composer(CMS)提供可视界面，用于在体验定位(XT)活动中编辑页面上的体验。
seo-title: 创建体验
solution: Target
title: 创建体验
topic: Advanced,Standard,Classic
uuid: ce559c3c-5a16-46b8-b2a7-df696626c7c0
translation-type: tm+mt
source-git-commit: 6911a91aba8505e8f91a7ab9723c54bd8e7082b7

---


# Create experience{#create-experience}

[!UICONTROL Visual Experience Composer] (CMS)提供可视界面，用于在 [!UICONTROL 体验定位] (XT)活动中编辑页面上的体验。

1. 选择要更改的元素，然后进行所需的更改。

   [创建XT活动](/help/c-activities/t-experience-target/t-xt-create/xt-create.md)时，三部分引导工作流([!UICONTROL 体验])中的步骤一将向所有访客受众显示默认 [!UICONTROL 体验A] 。

   ![所有访客受众](/help/c-activities/t-experience-target/t-xt-create/assets/all-visitors.png)

   Any changes you make now apply to Experience A. In a step below, you'll click **[!UICONTROL Add Experience Targeting]** to create additional experiences.

   将鼠标悬停在页面中的元素上时，这些元素会高亮显示。可以使用CMS更改任何高亮显示的元素。For a list of actions that can be performed on an element to change the experience, see [Visual Experience Composer Options](/help/c-experiences/c-visual-experience-composer/viztarget-options.md).

   If you created an mbox on the page using [!DNL Target Classic], that mbox appears as an element that shows the mbox name, and can be modified like any other element.

   >[!NOTE]
   >
   >默认情况下，CMS不允许对包含JavaScript的元素(如旋转横幅)进行更改。您可以选择禁用JavaScript以使用CMS更改这些元素。

1. To create additional experiences, click **[!UICONTROL Add Experience Targeting]**.

   ![添加体验定位链接](/help/c-activities/t-experience-target/t-xt-create/assets/add-experience-targeting.png)

   The [!UICONTROL Choose Audience] dialog box displays. 要将体验定位到受众，您必须先选择受众，然后再添加体验。

   The audience library contains audiences that have previously been defined, including some common audiences that are pre-built as a part of [!DNL Target]. You can select an audience from the library or [create a new audience](../../../c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271).

   >[!NOTE]
   >
   >除了选择现有受众之外，您还可以合并多个受众来创建临时组合受众，而不是创建新受众。有关更多信息，请参阅[合并多个受众](../../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

   在创建受众时，您可以选择一个位置 (mbox) 并指定该位置的参数。Under [!UICONTROL Custom] (Create Audience &gt; Add Rule &gt; Custom), select the mbox, then specify the desired parameters.

   >[!NOTE]
   >
   >打开受众列表时会在后台自动导入受众，导入的受众为 10 分钟之前的受众。

1. Select one or more audiences to target with the experience, then click **[!UICONTROL Done]**.

   ![体验 B](/help/c-activities/t-experience-target/t-xt-create/assets/experience-b.png)

   您会注意到，体验B现在显示在前面的插图中，此体验面向美国访客受众。

1. 选择要为此体验更改的元素并进行所需的更改，请参阅上面的步骤1。

1. 根据需要重复上述步骤以创建更多有针对性的体验。

1. Click **[!UICONTROL Next]** when you are finished designing your experiences.

   活动图显示如下：

   ![XT定位图](/help/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-new.png)

   >[!NOTE]
   >
   >If you deliver an image from a source other than your main page (such as an image hosted on `akamai.net` and delivered on `adobe.com`), that image does not display in the thumbnail of the page shown in the flow diagram.

1. (视情况而定)在创建或编辑XT活动时拖放受众/体验对以按所需顺序排列对。

   按顺序从上到下对访客进行评估。

   ![移动体验](/help/c-activities/t-experience-target/t-xt-create/assets/move_experiences-new.png)

   [!UICONTROL 体验定位假定排序至关重要。]如果访客属于第一个受众/体验对，则会交付第一个体验。

   例如，假定您在创建 XT 活动时并不知道排序的重要性。随后，您在测试过程中意识到，您认为应符合体验 B 或 C 的条件的访客而是符合了体验 A 的条件。这可能是因为受众之间不存在互斥关系，并且它们的顺序不正确（例如，体验 A = 美国，体验 B = 旧金山，体验 C = 加利福尼亚州）所导致。在此情景中，来自美国的所有用户都符合体验 A 的条件，无论他们在旧金山还是在加利福尼亚州的其他地区。您可以按限制性由高到低（旧金山 &gt; 加利福尼亚州 &gt; 美国）重新排列受众/体验对，而不必重新创建整个活动。

   If you have an [!UICONTROL All Visitors] audience, ensure that it is not the first audience in the diagram. 定位到“所有访客”的体验可以用作体验定位活动中的最后一个体验，以“捕获”所有还未进入任何其他体验的访客。

## 重命名或编辑体验

You can click the [!UICONTROL Edit] icon (three vertical ellipses) on an experience in an XT activity and choose from the following options, as necessary:

* 重命名
* 编辑

![重命名和编辑选项](/help/c-activities/t-experience-target/t-xt-create/assets/experience_edit-new.png)

## 删除体验

On the **[!UICONTROL Experiences]** page (the first step in the three-step guided workflow), click the three vertical ellipses &gt; **[!UICONTROL Delete]**.

![删除体验](/help/c-activities/t-experience-target/t-xt-create/assets/delete-experience.png)

## 复制体验

您可以复制XT活动中的体验，以便对其进行细微更改，而不必从头开始重新创建体验。

在&#x200B;**[!UICONTROL 体验]**&#x200B;页面（三步引导式工作流的步骤 1）中，依次单击三个垂直省略号图标 &gt; **[!UICONTROL 复制]**。

![体验重复](/help/c-activities/t-experience-target/t-xt-create/assets/duplicate_experience-new.png)

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

### 使用视觉体验书写器

以下视频提供了有关使用可视化体验编辑器选项的信息。

* 更改页面的内容
* 更改页面的布局

>[!VIDEO](https://video.tv.adobe.com/v/17399?captions=chi_hans)