---
keywords: Create A/B;A/B test;A/B activity;new a/b activity;create a/b
description: 使用Adobe Target的Visual Experience Composer直接在启用目标的页面上创建A/B测试活动，并修改目标中页面的部分。
title: 创建 A/B 测试
feature: ab
topic: Advanced,Standard,Classic
uuid: 2a255cf9-91c7-4710-bfd7-a4d8797ef24c
translation-type: tm+mt
source-git-commit: e18f18e6d6e0b8fc6eb5ada845e2fe5377d6c5d0
workflow-type: tm+mt
source-wordcount: '850'
ht-degree: 64%

---


# 创建 A/B 测试

Use the [!UICONTROL Visual Experience Composer] (VEC) in [!DNL Adobe Target] to create your [!UICONTROL A/B Test] activity directly on a [!DNL Target]-enabled page and to modify portions of the page within [!DNL Target].

>[!NOTE]
>
>除了手动（默认）A/ [!UICONTROL B测试活动] （在本节中讨论）之外，还 [!DNL Target] 提供了两种其他类型的  A/B测试活动: [!UICONTROL 自动分配] 和 [!UICONTROL 自动目标]。
>
>请参 [阅A/B测试概述中](/help/c-activities/t-test-ab/test-ab.md#types)*的A/B测试活动类型*。

要创建手动A/ [!UICONTROL B测试活动，请执行] :

1. 从“**[!UICONTROL 活动]**”列表中，单击&#x200B;**[!UICONTROL 创建活动]** > **[!UICONTROL A/B 测试]**。

   ![“创建活动”下拉列表](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >可用的活动类型取决于您的 [!DNL Target] 帐户。有些活动类型可能不会显示在列表中。例如，“[!UICONTROL 推荐]”是一项 [Target Premium 功能](/help/c-intro/intro.md#premium)。
   >
   >有关各种活动类型的信息，请参阅[活动](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)和 [Target 活动指南](/help/c-activities/target-activities-guide.md)。

1. 如有必要，选择&#x200B;**[!UICONTROL 可视（默认）]**。

   ![创建A/B测试活动](/help/c-activities/t-test-ab/t-test-create-ab/assets/create-ab.png)

   If you prefer to use the [!UICONTROL Form-Based Experience Composer], select [!UICONTROL Form]. 请参阅[基于表单的体验编辑器](/help/c-experiences/form-experience-composer.md)，以了解更多信息。

   >[!NOTE]
   >
   >除了VEC和基于表 [!UICONTROL 单的体验书写器], [!DNL Target] 还优惠单页应用程序VEC。 有关各种编辑器的更多信息，请参阅[体验和选件](/help/c-experiences/experiences.md)。
   >
   >如需 VEC 的故障诊断信息，或者当您遇到问题时，请参阅[可视化体验编辑器故障诊断](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。
   >
   >上图中的“[!UICONTROL 选择工作区](/help/administrating-target/c-user-management/property-channel/property-channel.md)”选项是一项 [Target Premium](/help/c-intro/intro.md) 功能。Your organization has a [!UICONTROL Target Standard] license if you do not see this option.

1. （视情况而定）如果您是一位 [Target Premium 客户](/help/c-intro/intro.md#premium)，请选择一个[工作区](/help/administrating-target/c-user-management/property-channel/property-channel.md)。

1. 指定[活动 URL](/help/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md)，然后单击&#x200B;**[!UICONTROL 下一步]**。

   如果您的帐户配置了默认 URL，则默认情况下将显示该 URL。您可以将默认 URL 更改为其他 URL。

   此时会打开[!UICONTROL 可视化体验编辑器]，其中显示了在 URL 中指定的页面。

   ![VEC](/help/c-activities/t-test-ab/t-test-create-ab/assets/vec-new.png)

1. 在提供的空白处键入该活动的名称。

   ![名称字段](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_newname-new.png)

   活动名称中不允许使用以下字符：

   | 字符 | 描述 |
   |--- |--- |
   | `/` | 正斜线 |
   | `?` | 问号 |
   | `#` | 数字符号 |
   | `:` | 冒号 |
   | `=` | 等号 |
   | `+` | 加号 |
   | `-` | 减号 |
   | `@` | @ 符号 |

1. 创建任何新体验（通过更改页面上的元素）。

   创建新活动后，[!UICONTROL 可视化体验编辑器]会在左侧显示两个选项卡：“体验 A”和“体验 B”。其中，“体验 A”是控制体验。“体验 B”选项卡将为您的主要关注对象，您可以根据需要修改此选项卡。体验 B 是可添加到测试中的替代体验。您可以在测试中添加多个体验。如果您不想在体验选项中包含默认的网站体验，则也可以从活动中删除体验 A。

   有关如何在[!UICONTROL 可视化体验编辑器]中添加和修改体验的更多信息，请参阅[添加体验](../../../c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00)。要修改体验 B，请从步骤 3 开始操作。

1. 在&#x200B;**[!UICONTROL 可视化体验编辑器]**&#x200B;的顶部单击[!UICONTROL 定位]，以进入三步引导式工作流中的下一个步骤。

   此时会打开流程图。

   ![A/B 测试定位步骤](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   流程图会引导您完成以下步骤：选择活动的受众和设置体验。

1. 在受众 [!UICONTROL 框中] ，单击编辑图标（三个垂直椭圆），单击 **[!UICONTROL 替换受众]**，然 [后选择活动的受众](/help/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) 。

   By default, the audience is set to [!UICONTROL All Visitors].

1. 选择您希望参加活动的符合条件的访客所占的百分比。

   ![受众百分比](/help/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   例如，您可以将准入资格限制为 50% 的访客或 45% 的“加州”受众。

1. 设置流量分配。

   您可以向同一个受众显示多个体验。将会有一个图表显示您选择的受众，以及您已添加到该活动的各个体验。

   选择所需的流量分配方法：

   * **[!UICONTROL 手动（默认）]**：指定您希望看到各个体验的参加者所占的百分比。您可以将百分比平分到所有体验，或者也可以为每个体验指定较高或较低的百分比。所有体验的百分比总和必须等于 100%。

   * **[!UICONTROL 自动分配到最佳体验]**：将大多数活动参加者自动定向到具有更高性能的体验。为继续探索各体验并识别性能趋势的变化，某些访客会分配到所有体验。请参阅[自动流量分配](../../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)。

   * **[!UICONTROL 自动目标，提供个性化体验]**: [!DNL Target] 使用高级机器学习来识别多个高性能的营销人员定义体验，从而个性化内容并推动转化，然后根据访客的个人用户档案和相似访客的过去行为，为客户提供最为定制的体验。 有关详细信息，请参 [阅自动目标](/help/c-activities/auto-target/auto-target-to-optimize.md)。
   You can also click **[!UICONTROL Add]** to add another experience to the activity.

1. When you are satisfied with your audience, experience choices, and traffic allocation choices, click **[!UICONTROL Next]** to move to the third step of the three-step guided workflow.

1. 指定活动的[目标和设置](/help/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)。

   ![A/B 活动设置](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_settings-new.png)

1. 单击 **[!UICONTROL 保存并关闭]** 或 **[!UICONTROL 保存]**。

After you create the activity, the [!UICONTROL Overview] tab shows information about the activity, including a diagram of your activity.

## Training video: Creating A/B Tests (8:36) ![Tutorial badge](/help/assets/tutorial.png)

以下视频演示了如何使用 [!DNL Target] 三步引导式工作流创建 A/B 测试。

* 在以下 [!UICONTROL 位置创建A/B测试] 活动: [!DNL Adobe Target]
* 使用手动拆分或自动流量分配来分配流量

>[!VIDEO](https://video.tv.adobe.com/v/17391)
