---
keywords: form-based experience composer;form-based composer;refinements
description: Adobe Target基于表单的体验书写器提供非视觉体验创建。
title: 基于表单的体验编辑器
feature: Form-based Experience Composer
translation-type: tm+mt
source-git-commit: 7f4ecf9963bca54439f81688dbde1340499b795d
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 68%

---


# 基于表单的体验编辑器{#form-based-experience-composer}

[!DNL Adobe Target] [!UICONTROL 基于表单的体验书写器]是一个非可视体验和优惠创建界面，当可视体验书写器不可用或无法实际使用时，该界面可用于创建用于A/B测试、体验定位、Automated Personalization和Recommendations活动的体验。 例如，您可以使用基于表单的编辑器为电子邮件、网亭和语音助手中的交付创建体验和选件。

如果您创建的是“推荐”活动，则不存在任何体验。需选择您的标准和设计。如果您选择多个标准或设计，则 Target 会自动生成体验。

1. 单击&#x200B;**[!UICONTROL 创建活动]**，然后选择要创建的活动类型。

   基于表单的体验编辑器适用于 A/B 测试活动、体验定位活动、自动个性化活动和“推荐”活动。
1. 从[!UICONTROL 创建活动]对话框中选择&#x200B;**[!UICONTROL 基于表单的体验书写器]**。

1. （视情况而定）选择工作区和属性。

1. 单击&#x200B;**[!UICONTROL 下一步]**。

   此时会打开基于表单的体验编辑器。

   ![](assets/location_refinements.png)

   如果您创建的是“推荐”活动，此屏幕会有所不同。“推荐”活动不包含体验。
1. 单击“[!UICONTROL 未命名活动]”命名活动。
1. 选择位置。

   单击[!UICONTROL 选择位置]框时，将显示可用位置列表。 从这些位置中选择一个位置。要选择通过 target.js 交付的全局位置，请选择“target-global-mbox”。

   您还可以输入一个未在此处列出的位置。如果尚未在页面上创建或查看 mbox，则可以使用此方法。键入位置的名称。输入尚不存在的位置时务必要仔细。如果位置拼写或大小写与调用 mbox 时使用的拼写和大小写不匹配，则活动将无法交付。手动输入的位置将保存到可用位置的列表。 下次尝试选择手动输入的位置时，该位置将从该活动的[!UICONTROL 选择位置]下拉列表中可用。

   >[!NOTE]
   >
   >在创建活动时创建手动输入的位置不会自动创建新位置。 位置名称仅保存在活动的上下文中。 当有内容投放调用时，将创建该位置。 在创建位置后，它将可用于其他活动，用于创建受众等。 从可用位置的下拉列表。

1. 单击&#x200B;**[!UICONTROL 添加受众细化]**，然后为此活动选择一个或多个[受众](/help/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522)。

   ![](assets/location_refinements_2.png)

   在基于表单的体验编辑器中，已将“细化”替换为完整受众功能。现有活动的细化功能已迁移到[仅限该活动的受众](/help/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)。
1. 选择要在该位置中显示的内容类型。

   ![](assets/form_content.png)

1. 为选定的内容类型指定内容。

   **更改 HTML 选件：**&#x200B;选择一个 HTML 选件。

   **更改图像选件：**&#x200B;选择 Target 内容库中保存的某个图像。

   您还可以添加指向图像的链接（点进链接、目标链接、登陆链接，等等）。

   1. 单击[!UICONTROL 更改图像选件]。
   1. 选择所需的图像，然后单击[!UICONTROL 编辑链接]。
   1. 指定您网站上的所需 URL 或页面，然后单击[!UICONTROL 更新]。

   **更改 JSON 选件：**&#x200B;选择一个 JSON 选件。

   **更改体验片段：**&#x200B;选择一个体验片段。

   **更改重定向选件：**&#x200B;选择一个重定向选件。有关详细信息，请参阅[创建重定向优惠](/help/c-experiences/c-manage-content/offer-redirect.md)。

   **更改远程选件：**&#x200B;选择一个远程选件。有关详细信息，请参阅[创建远程优惠](/help/c-experiences/c-manage-content/about-remote-offers.md)。

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

   对于“推荐”活动，“内容”下拉列表中提供了“添加推荐”选项。单击&#x200B;**[!UICONTROL 添加推荐]**，然后选择页面类型。接下来，按照界面中定义的常规步骤[创建“推荐”活动](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md)。

   在基于表单的体验编辑器中选择推荐标准时，现在有一个指向所选标准卡片的直接链接，以便您快速方便地对标准进行编辑。

   ![](assets/change_criteria.png)

   从 Target 三步引导式工作流的“定位”页面中：

   ![](assets/change_criteria_2.png)

1. (可选，对于AB活动、Automated Personalization和体验定位)要对其他位置重复此过程，请单击&#x200B;**[!UICONTROL 添加位置]**&#x200B;并配置位置和内容。
1. 单击&#x200B;**[!UICONTROL 下一步]**，然后按照您的活动类型的惯例完成活动创建步骤。

* [创建 A/B 测试](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
* [创建体验定位活动](/help/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
* [创建“推荐”活动](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

## 培训视频：基于表单的编辑器  ![教程徽章](/help/assets/tutorial.png)

以下视频演示了基于表单的编辑器。

* 使用基于表单的体验编辑器创建活动
* 了解何时使用基于表单的体验编辑器，何时使用可视化体验编辑器
* 使用细化来定位位置

>[!VIDEO](https://video.tv.adobe.com/v/17390)