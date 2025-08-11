---
keywords: 活动；活动类型；编辑活动；编辑；复制
description: 了解可用于编辑现有活动的各种方式。
title: 如何编辑活动？
feature: Activities
exl-id: 5f2a930a-9950-430e-a898-50af1f917ec1
source-git-commit: b46ff78a9145e2e837a849d72adc4a7fb8797d00
workflow-type: tm+mt
source-wordcount: '962'
ht-degree: 22%

---

# 编辑活动

了解如何在[!DNL Adobe Target]中编辑现有活动。 本文介绍[!DNL Target]界面中用于修改活动的各种方法。 无论您是更新体验、调整定位规则还是配置目标，[!DNL Target]都可以确保在激活之前安全地保存您的更改。

[!DNL Target]在UI中提供了多个可编辑现有活动的位置。 此过程因您选择的方法而异。

## 在“活动”页面上通过使用悬停[!UICONTROL More Actions]图标来编辑活动 {#section_29EE2ECA6B88473A8F9AC5600FFBB174}

1. 在&#x200B;**[!UICONTROL Activities]**&#x200B;页面中，单击要编辑的活动旁边的&#x200B;**[!UICONTROL More Actions]**&#x200B;图标（![更多操作图标](/help/main/assets/icons/MoreSmall.svg)），然后单击&#x200B;[!UICONTROL **编辑**]。

   [!DNL Target]在[!UICONTROL Visual Experience Composer] (VEC)中打开活动，您会看到[!UICONTROL Experiences]页面（三步引导式工作流的步骤1）。

1. 根据需要使用 [VEC 选项](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)编辑活动。

1. 单击&#x200B;**[!UICONTROL Next]**&#x200B;进入下一步，然后进行任何必要的编辑。

1. 当您进入&#x200B;**目标和设置**&#x200B;页面时，您具有以下选项：

   * **[!UICONTROL Save & Close]：**&#x200B;单击&#x200B;**[!UICONTROL Save and Close]**&#x200B;以保存更改并显示活动的[!UICONTROL Overview]页面。
   * **保存：**&#x200B;单击&#x200B;**[!UICONTROL More Actions]**&#x200B;图标（![更多操作图标](/help/main/assets/icons/MoreSmallListVert.svg) ），然后选择&#x200B;**[!UICONTROL Save]**&#x200B;以保存您的更改并保留在VEC中，以便您可以继续做出更改。 等待保存完成后，可进行其他更改。保存完成后，VEC 会重新加载以显示刷新的更改。

## 从[!UICONTROL Activities]页面中单击活动名称以编辑该活动 {#section_176180DAD17E40CEA441903F39E0AA1C}

1. 要避免逐步完成此工作流，请从[!UICONTROL Activities]页面中单击所需的活动以将其打开，从&#x200B;**[!UICONTROL Edit Activity]**&#x200B;下拉列表中选择一个选项，然后选择所需的选项。

   * **编辑体验：**&#x200B;使您直接转到[!UICONTROL Experiences]页面（三步引导式工作流的步骤1）。
   * **编辑定位**：使您直接转到[!UICONTROL Targeting]页面（三步引导式工作流中的第二步）。
   * **[!UICONTROL Goals & Settings]**：使您直接转到[!UICONTROL Goals & Settings]页面（三步引导式工作流的第三步）。

1. 进行所需的更改，然后保存活动。

   * **[!UICONTROL Save & Close]：**&#x200B;单击&#x200B;**[!UICONTROL Save and Close]**&#x200B;以保存更改并显示活动的[!UICONTROL Overview]页面。
   * **保存：**&#x200B;单击&#x200B;**[!UICONTROL More Actions]**&#x200B;图标（![更多操作图标](/help/main/assets/icons/MoreSmallListVert.svg) ），然后选择&#x200B;**[!UICONTROL Save]**&#x200B;以保存您的更改并保留在VEC中，以便您可以继续做出更改。 等待保存完成后，可进行其他更改。保存完成后，VEC 会重新加载以显示刷新的更改。

## 使用工作区时复制/编辑活动 {#section_45A92E1DD3934523B07E71EF90C4F8B6}

工作区允许组织为一组特定用户分配一组特定属性。工作区在许多方面与 [!DNL Adobe Analytics] 中的报表包相似。

>[!NOTE]
>
>工作区是[!UICONTROL Properties and Permissions]解决方案中可用的[!DNL Target Premium]功能的一部分。 如果没有 [!DNL Target Premium] 许可证，它们将无法在 [!DNL Target Standard] 中使用。

如果您所在的组织是跨国组织，则您可能拥有两个工作区：一个用于欧洲网页、属性或网站，而另一个用于美国网页、属性或网站。如果您所在的组织拥有多个品牌，则您的每个品牌可能有其独立的工作区。

有关工作区和企业用户权限功能的详细信息，请参阅[企业用户权限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#concept_E396B16FA2024ADBA27BC056138F9838)。

如果您在环境中启用了[!UICONTROL Enterprise User Permissions]，则可以将活动复制到同一工作区或另一个工作区。 当前，无法将活动从一个工作区移到另一个工作区。要将活动复制到另一个工作区，请从[!UICONTROL Activities]页面中单击要复制的活动旁边的&#x200B;**[!UICONTROL More Actions]**&#x200B;图标（![更多操作图标](/help/main/assets/icons/MoreSmall.svg)），然后单击&#x200B;[!UICONTROL **复制**]。

在工作区中使用复制/编辑功能时，请考虑以下信息：

* 如果在同一工作区中复制活动，或者将活动从默认工作区复制到非默认工作区，则会自动打开“活动向导”。 在跨工作区副本中，您可能只需要更新活动属性。
* 将活动从非默认工作区复制到另一个工作区（默认或非默认）时，将打开活动向导，并且需要一些手动输入才能完成设置：
   * **[!UICONTROL Properties]**：不同工作区之间的属性可能不同。 此情况可能会触发警告：

      * 在[!UICONTROL Form-Based Experience Composer]中，警告将直接显示在用户界面中，以便立即可见。

        ![基于表单的工作区警告](/help/main/c-activities/assets/form-based-warning.png)

      * 在VEC中，单击[!UICONTROL Configure] > [!UICONTROL Properties]时会显示警告。

        ![vec警告](/help/main/c-activities/assets/vec-warning.png)

        要解决此问题，请单击[!UICONTROL Add/Remove]，以便只显示目标工作区中可用的属性以供选择。

   * **受众和选件**：将活动复制到新工作区时，所有关联的[!DNL Target]或原始工作区中的临时受众和选件将以下列格式复制： `<Entity Name> Copy <Date>`受众和[!DNL Target]的临时受众和选件`<Entity Name>`。

     行为详细信息：

      * 在保存并重新打开活动之前，复制的受众和选件不会显示在[!UICONTROL Audiences]和[!UICONTROL Offers]列表中。
      * 复制后无法立即编辑这些实体。 在初始编辑会话期间，客户可能会在VEC中看到这些项目的空内容。
      * 如果需要，客户可以使用目标工作区中的其他受众或选件替换复制的受众或选件。

     此过程可确保更平稳的跨工作区活动复制，同时保持自定义的灵活性。

     在复制活动时，必须手动替换未保存在当前工作区或默认工作区中的非目标受众和选件。

     手动替换这些非目标受众和选件可确保在复制的活动中仅使用有效、可访问的实体，并防止在编辑或交付期间出现错误。

     ![警告消息](/help/main/c-activities/assets/copy.png)

>[!NOTE]
>
>如果您的环境未启用[!UICONTROL Enterprise User Permissions]功能，则在复制之前，所有活动都会以编辑模式打开。

## 以草稿形式保存活动 {#section_968CD7A63027432EBD8FAE3A0F7404C3}

[!UICONTROL Save as Draft]功能不再可用。 有关详细信息，请参阅&#x200B;*[!UICONTROL Status]*&#x200B;将筛选器应用到活动列表[下的](/help/main/c-activities/activities.md#filters)。

## 使用在[!DNL Recommendations Classic]中创建的旧版活动 {#classic}

[!UICONTROL Activities]列表显示在各种源（包括[!DNL Recommendations Classic]）中创建的活动。 使用在 [!DNL Recommendations Classic] 中创建的旧版活动时，可以执行以下操作：

* [!UICONTROL Activate]
* [!UICONTROL Deactivate]
* [!UICONTROL Archive]
* [!UICONTROL Copy]
* [!UICONTROL Delete]

不能直接编辑 [!DNL Recommendations] 活动。如果想要编辑活动，则应使用 [!DNL Target Premium] 创建活动副本，并保存新创建的活动。然后，可以根据需要编辑新创建的活动。