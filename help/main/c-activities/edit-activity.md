---
keywords: 活动;活动类型;编辑活动;编辑;草稿
description: 了解在Adobe Target中编辑现有活动的各种方式，包括以草稿形式保存活动。
title: 如何编辑活动或另存为草稿？
feature: Activities
exl-id: 5f2a930a-9950-430e-a898-50af1f917ec1
source-git-commit: e458793e4d0110d97f3f5124cbe6e54520d3f0e9
workflow-type: tm+mt
source-wordcount: '1169'
ht-degree: 52%

---

# 编辑活动或另存为草稿

有关您可以在[!DNL Adobe Target]中编辑现有活动的不同方式的信息，包括将活动保存为草稿。

您可以在 Target UI 中的多个位置编辑现有活动。根据您选择的方法，编辑过程会有所不同。

## 在活动页面上通过使用悬停鼠标显示的按钮来编辑活动 {#section_29EE2ECA6B88473A8F9AC5600FFBB174}

1. 在&#x200B;**[!UICONTROL Activities]**&#x200B;页面中，将鼠标悬停在要编辑的活动上，然后单击&#x200B;**[!UICONTROL Edit]**&#x200B;图标。

   ![“编辑”图标](/help/main/c-activities/assets/hover_edit.png)

   Target会在可视化体验编辑器(VEC)中打开活动，此时您会看到[!UICONTROL Experiences]页面（三步引导式工作流的步骤1）。

1. 根据需要使用 [VEC 选项](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)编辑活动。

1. 单击拆分按钮以前进到下一步或保存活动。

   ![拆分按钮](/help/main/c-activities/assets/edit_split_button_2.png)

   * **下一步：**&#x200B;若要在三步式工作流中编辑其他页面，请单击&#x200B;**[!UICONTROL Next]**&#x200B;进入所需的步骤。 例如，在上图中，单击[!UICONTROL Next]会显示[!UICONTROL Targeting]步骤。
   * **保存并关闭：**&#x200B;在当前步骤中进行所需的更改，单击拆分按钮中的下拉列表，然后选择&#x200B;**[!UICONTROL Save and Close]**&#x200B;以保存所做更改并显示活动的[!UICONTROL Overview]页面。
   * **保存：**&#x200B;在任一步骤中进行所需的更改，单击拆分按钮中的下拉列表，然后选择&#x200B;**[!UICONTROL Save]**&#x200B;以保存所做更改并停留在当前步骤，以便能够继续进行更改。 等待保存完成后，可进行其他更改。保存完成后，VEC 会重新加载以显示刷新的更改。

## 在活动页面上通过单击活动名称以将其打开来编辑活动 {#section_176180DAD17E40CEA441903F39E0AA1C}

1. 要避免逐步完成此工作流，请从“活动”页面中单击所需的活动以将其打开，然后从&#x200B;**[!UICONTROL Edit Activity]**&#x200B;下拉列表中选择相应的选项。

   ![“编辑活动”下拉列表](/help/main/c-activities/assets/edit_activity.png)

1. 选择所需的选项：

   * **编辑体验：**&#x200B;使您直接转到[!UICONTROL Experiences]页面（引导式工作流中的第一步）。 可进行所需的更改，然后使用拆分按钮（如上所述）保存活动。

      * 单击&#x200B;**[!UICONTROL Save & Close]**&#x200B;以保存更改并显示活动的“概述”页面。
      * 单击&#x200B;**[!UICONTROL Save]**&#x200B;可保存所做更改并停留在当前步骤，以便能够继续进行更改。 等待保存完成后，可进行其他更改。保存完成后，VEC 会重新加载以显示刷新的更改。

   * **编辑定位：**&#x200B;使您直接转到[!UICONTROL Targeting]页面（引导式工作流中的第二步）。 可进行所需的更改，然后使用拆分按钮（如上所述）保存活动。

      * 单击&#x200B;**[!UICONTROL Save & Close]**&#x200B;以保存更改并显示活动的“概述”页面。
      * 单击&#x200B;**[!UICONTROL Save]**&#x200B;可保存所做更改并停留在当前步骤，以便能够继续进行更改。 等待保存完成后，可进行其他更改。保存完成后，VEC 会重新加载以显示刷新的更改。

   * **编辑目标和设置：**&#x200B;使您直接转到[!UICONTROL Goals & Settings]页面（引导式工作流中的最后一步）。 可进行所需的更改，然后使用拆分按钮（如上所述）保存活动。

      * 单击&#x200B;**[!UICONTROL Save & Close]**&#x200B;以保存更改并显示活动的“概述”页面。
      * 单击&#x200B;**[!UICONTROL Save]**&#x200B;可保存所做更改并停留在当前步骤，以便能够继续进行更改。 等待保存完成后，可进行其他更改。保存完成后，VEC 会重新加载以显示刷新的更改。

## 使用在Recommendations Classic中创建的旧版活动 {#classic}

[!UICONTROL Activities]列表显示在各种源（包括[!DNL Recommendations Classic]）中创建的活动。 使用在 [!DNL Recommendations Classic] 中创建的旧版活动时，可以执行以下操作：

* [!UICONTROL Activate]
* [!UICONTROL Deactivate]
* [!UICONTROL Archive]
* [!UICONTROL Copy]
* [!UICONTROL Delete]

不能直接编辑 [!DNL Recommendations] 活动。如果想要编辑活动，则应使用 [!DNL Target Premium] 创建活动副本，并保存新创建的活动。然后，可以根据需要编辑新创建的活动。

## 以草稿形式保存活动 {#section_968CD7A63027432EBD8FAE3A0F7404C3}

创建新活动且尚未对其保存时，或编辑之前保存为草稿形式的活动时，拆分按钮中会显示“保存草稿”选项。

如果您已开始设置某个活动，但尚未准备好运行该活动，则可以将其保存为草稿。

1. 创建新活动，或编辑以草稿形式保存的现有活动。
1. 从拆分按钮中选择所需的选项：

   ![保存草稿](/help/main/c-activities/assets/save_draft.png)

   * **下一步：**&#x200B;若要在三步式工作流中编辑其他页面，请单击&#x200B;**[!UICONTROL Next]**&#x200B;进入所需的步骤。
   * **保存草稿并关闭：**&#x200B;在当前步骤中进行所需的更改，单击拆分按钮中的下拉列表，然后选择&#x200B;**[!UICONTROL Save Draft and Close]**&#x200B;以保存所做更改并显示活动的[!UICONTROL Overview]页面。
   * **保存草稿：**&#x200B;在任一步骤中进行所需的更改，单击拆分按钮中的下拉列表，然后选择&#x200B;**[!UICONTROL Save Draft]**&#x200B;以保存所做更改并停留在当前步骤。

## 使用工作区时复制/编辑活动 {#section_45A92E1DD3934523B07E71EF90C4F8B6}

工作区允许组织为一组特定用户分配一组特定属性。工作区在许多方面与 [!DNL Adobe Analytics] 中的报表包相似。

>[!NOTE]
>
>“属性和权限”功能作为 [!DNL Target Premium] 解决方案的一部分提供，而“工作区”又是“属性和权限”功能的一部分。如果没有 [!DNL Target Premium] 许可证，它们将无法在 [!DNL Target Standard] 中使用。

如果您所在的组织是跨国组织，则您可能拥有两个工作区：一个用于欧洲网页、属性或网站，而另一个用于美国网页、属性或网站。如果您所在的组织拥有多个品牌，则您的每个品牌可能有其独立的工作区。

有关工作区和企业用户权限功能的详细信息，请参阅[企业用户权限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#concept_E396B16FA2024ADBA27BC056138F9838)。

如果您的环境中启用了“企业用户权限”，则可以将活动复制到同一工作区或其他工作区。当前，无法将活动从一个工作区移到另一个工作区。要将活动复制到另一个工作区，请从[!UICONTROL Activities]页面中，将鼠标悬停在要复制的活动上，单击[!UICONTROL Copy]图标，然后从下拉列表中选择所需的工作区。

在工作区中使用复制/编辑功能时，请考虑以下信息：

* 如果是在同一工作区中复制活动，则会在编辑模式中打开新复制活动创建流程的第一步。
* 如果是将活动复制到其他工作区，则活动会被复制到其他工作区，而不是在活动创建流程中打开活动。成功复制活动后，会显示一条指示活动已成功复制的消息，消息中还包含用于打开新活动的链接。

如果您的环境未启用“企业用户权限”功能，则在复制之前所有活动都将在编辑模式中打开。

## 最佳实践

* 作为最佳实践，请尝试使用最初用于创建该活动的相同方法（UI 或 API）更新该活动。

  应通过[!DNL Target] UI更新使用[!DNL Target] UI创建的活动。 应通过 API 更新通过 API 创建的活动。例如，如果您最初使用API创建活动，但随后又通过[!DNL Target] UI编辑该活动，则并非所有更改都会更新。 所有更改都存储在后端，可通过再次调用API更新这些更改。


