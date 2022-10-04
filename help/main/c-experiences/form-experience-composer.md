---
keywords: 基于表单的体验编辑器;基于表单的编辑器;细化
description: 了解如何使用Adobe [!DNL Target] 基于表单的体验编辑器，用于创建非可视化体验。 当VEC不可用或不实用时，可使用此编辑器。
title: 如何使用基于表单的体验编辑器？
feature: Form-based Experience Composer
exl-id: d06a271b-f058-4c83-af75-da2a29774967
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 45%

---

# 基于表单的体验编辑器

的 [!DNL Adobe Target] [!UICONTROL 基于表单的体验编辑器] 是一个非可视化体验和选件创建界面，在创建要在中使用的体验时非常有用 [!UICONTROL A/B测试], [!UICONTROL 体验定位], [!UICONTROL Automated Personalization]和 [!UICONTROL Recommendations] 活动 [!UICONTROL 可视化体验编辑器] (VEC)不可用或实用。 例如，您可以使用基于表单的体验编辑器为电子邮件、网亭和语音助理中的交付创建体验和选件。

如果您要创建 [!UICONTROL Recommendations] 活动时，没有体验。 需选择您的标准和设计。如果您选择多个标准或设计， [!UICONTROL Target] 会自动生成体验。

1. 单击&#x200B;**[!UICONTROL 创建活动]**，然后选择要创建的活动类型。

   的 [!UICONTROL 基于表单的体验编辑器] 可用 [!UICONTROL A/B测试], [!UICONTROL 体验定位], [!UICONTROL Automated Personalization]和 [!UICONTROL Recommendations] 活动。

1. 选择 **[!UICONTROL 表单]** 从 [!UICONTROL 创建活动] 对话框。

1. （视情况而定）选择工作区和属性。

1. 单击&#x200B;**[!UICONTROL 下一步]**。

   的 [!UICONTROL 基于表单的体验编辑器] 打开。

   ![location_refinements图像](assets/location_refinements.png)

   如果您创建的是 [!UICONTROL Recommendations] 活动。 [!UICONTROL “推荐”活动不包含体验。]

1. 通过单击“[!UICONTROL 无标题活动].&quot;
1. 选择位置。

   在 [!UICONTROL 选择位置] 框中，将显示可用位置列表。 从这些位置中选择一个位置。

   您还可以输入一个未在此处列出的位置。如果尚未在页面上创建或查看 mbox，则可以使用此方法。键入位置的名称。输入尚不存在的位置时务必要仔细。如果位置拼写或大小写与调用 mbox 时使用的拼写和大小写不匹配，则活动将无法交付。手动输入的位置会保存到可用位置列表。 下次尝试选择手动输入的位置时，该位置将可从 [!UICONTROL 选择位置] 该活动的下拉列表。

   >[!NOTE]
   >
   >在活动创建期间创建手动输入的位置不会自动创建新位置。 位置名称仅在活动的上下文中保存。 当存在内容交付调用时，将创建位置。 创建位置后，即可在其他活动中使用，用于创建受众等。 从可用位置的下拉列表中。

1. 单击 **[!UICONTROL 添加受众细化]**，选择一个或多个 [受众](/help/main/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522) 对于此活动，单击 **[!UICONTROL 完成]**.

   ![location_refinements_2图像](assets/location_refinements_2.png)

   在 [!UICONTROL 基于表单的体验编辑器]，则细化已被替换为完整的受众功能。 现有活动的细化已迁移至 [仅限该活动的受众](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483).

1. 选择要在该位置中显示的内容类型。

   ![form_content图像](assets/form_content.png)

1. 为选定的内容类型指定内容。

   **更改 HTML 选件：**&#x200B;选择一个 HTML 选件。

   **更改图像选件：**&#x200B;选择 Target 内容库中保存的某个图像。

   您还可以添加指向图像的链接（点进链接、目标链接、登陆链接，等等）。

   1. 单击[!UICONTROL 更改图像选件]。
   1. 选择所需的图像，然后单击[!UICONTROL 编辑链接]。
   1. 指定您网站上的所需 URL 或页面，然后单击[!UICONTROL 更新]。

   **更改 JSON 选件：**&#x200B;选择一个 JSON 选件。

   **更改体验片段：**&#x200B;选择一个体验片段。有关更多信息，请参阅 [体验片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

   **更改重定向选件：**&#x200B;选择一个重定向选件。有关更多信息，请参阅 [创建重定向选件](/help/main/c-experiences/c-manage-content/offer-redirect.md).

   **更改远程选件：**&#x200B;选择一个远程选件。有关更多信息，请参阅 [创建远程选件](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

   **创建 HTML 选件:**

   1. 单击[!UICONTROL 选件]，然后选择[!UICONTROL 代码选件]选项卡。
   1. 单击[!UICONTROL 创建] > [!UICONTROL HTML 选件]。
   1. 键入选件名称。
   1. 在代码框中键入或粘贴您的 HTML 代码。
   1. 单击[!UICONTROL 保存]。

   **创建 JSON 选件：**

   1. 单击[!UICONTROL 选件]，然后选择[!UICONTROL 代码选件]选项卡。
   1. 单击[!UICONTROL 创建] > [!UICONTROL JSON 选件]。
   1. 键入选件名称。
   1. 在代码框中键入或粘贴您的 JSON 代码。
   1. 单击[!UICONTROL 保存]。

   **添加推荐：**

   对于Recommendations活动，“内容”下拉列表会为您提供 [!UICONTROL 添加推荐] 选项。 单击&#x200B;**[!UICONTROL 添加推荐]**，然后选择页面类型。接下来，按照界面中定义的常规步骤[创建“推荐”活动](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md)。

   在基于表单的体验编辑器中选择推荐标准时，现在有一个指向所选标准卡片的直接链接，以便您快速方便地对标准进行编辑。

   ![change_criteria图像](assets/change_criteria.png)

   从 Target 三步引导式工作流的“定位”页面中：

   ![change_criteria_2图像](assets/change_criteria_2.png)

   **添加选件决策：**

   添加在中创建的选件 [!DNL Adobe Journey Optimizer] (AJO)到 [!DNL Adobe Target] 活动，在您的网站或移动设备网站上使用offer decisioning向访客展示最佳的动态选件和体验。 此选项可手动使用 [!UICONTROL A/B测试] 和 [!UICONTROL 体验定位] (XT)活动。

   有关更多信息，请参阅 [使用优惠决策](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md)。

1. (可选，对于 [!UICONTROL A/B测试], [!UICONTROL Automated Personalization]和 [!UICONTROL 体验定位] 活动)要对其他位置重复此过程，请单击 **[!UICONTROL 添加位置]** 和配置位置和内容。
1. 单击 **[!UICONTROL 下一个]**，然后按照常规方式完成活动类型的活动创建步骤。

* [创建 A/B 测试](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
* [创建体验定位活动](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
* [创建“推荐”活动](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

## 培训视频：基于表单的编辑器 ![教程徽章](/help/main/assets/tutorial.png)

以下视频演示了基于表单的编辑器。

* 使用基于表单的体验编辑器创建活动
* 了解何时使用基于表单的体验编辑器，何时使用可视化体验编辑器
* 使用细化来定位位置

>[!VIDEO](https://video.tv.adobe.com/v/17390)
