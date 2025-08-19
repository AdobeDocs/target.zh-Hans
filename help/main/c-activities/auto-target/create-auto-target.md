---
keywords: 创建自动定位；A/B测试；自动定位活动；新建A/B活动；自动定位；自动定位以提供个性化体验；个性化；优化
description: 了解如何使用[!UICONTROL Visual Experience Composer] (VEC)创建[!UICONTROL Auto-Target] A/B测试活动。
title: 如何创建[!UICONTROL Auto-Target]活动？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Auto-Target
exl-id: 5521740c-eee2-4ba2-8931-cf56d56a4561
source-git-commit: 32a91a41cd182d3a55ded7dea8c1c6ea6f46aa71
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 19%

---

# 创建[!UICONTROL Auto-Target]活动

在[!UICONTROL Visual Experience Composer]中使用[!DNL Adobe Target] (VEC)直接在启用了[!UICONTROL Auto-Target]的页面上创建您的[!UICONTROL A/B Test] [!DNL Target]活动，并在[!DNL Target]内修改页面的各个部分。

>[!NOTE]
>
>[!UICONTROL Auto-Target]作为[!DNL Target Premium]解决方案的一部分提供。 如果没有 [!DNL Target Premium] 许可证，则此功能在 [!DNL Target Standard] 中不可用。有关此许可证提供的各项高级功能的更多信息，请参阅 [Target Premium](/help/main/c-intro/intro.md)。

要创建[!UICONTROL Auto-Target]活动，请执行以下操作：

1. 从&#x200B;**[!UICONTROL Activities]**&#x200B;列表中，单击&#x200B;**[!UICONTROL Create Activity]** > **[!UICONTROL A/B Test]**。

1. 从[!UICONTROL Create A/B Test Activity]对话框中，根据需要选择&#x200B;**[!UICONTROL Visual]**。

   如果您希望使用[!UICONTROL Form-Based Experience Composer]，请选择[!UICONTROL Form]。 请参阅[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)，以了解更多信息。

   >[!NOTE]
   >
   >除了VEC和[!UICONTROL Form-Based Experience Composer]之外，[!DNL Target]还提供[!UICONTROL Single Page Application] VEC。 有关各种编辑器的更多信息，请参阅[体验和产品建议](/help/main/c-experiences/experiences.md)。
   >
   >有关VEC的故障诊断信息，请参阅[可视化体验编辑器故障诊断](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。

1. （视情况而定）如果您是[Target Premium客户](/help/main/c-intro/intro.md#premium)，请从&#x200B;**[!UICONTROL Choose Workspace]**&#x200B;下拉列表中选择一个[工作区](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

   [[!UICONTROL Choose Workplace]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)选项是[Target Premium](/help/main/c-intro/intro.md)功能，如果您的组织具有[!UICONTROL Target Standard]许可证，则可能无法显示。

1. 在&#x200B;**[!UICONTROL Enter Activity URL]**&#x200B;框中，指定您的[活动URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md)。

   如果您的帐户[配置了默认 URL](/help/main/administrating-target/visual-experience-composer-set-up.md)，则默认情况下将显示该 URL。您可以根据需要将默认URL更改为其他URL。

1. 单击 **[!UICONTROL Create]**。

   [!UICONTROL Visual Experience Composer]将打开，显示在URL中指定的页面。

1. 单击&#x200B;**[!UICONTROL Rename]**&#x200B;图标（![重命名图标](/help/main/assets/icons/MoreSmallListVert.svg)），单击&#x200B;**[!UICONTROL Rename]**，指定活动的名称，然后单击&#x200B;**[!UICONTROL Save]**。

   活动名称不能以下列任何字符开头：

   | 字符 | 描述 |
   |--- |--- |
   | `=` | 等号 |
   | `+` | 加号 |
   | `-` | 减号 |
   | `@` | @ 符号 |

   活动名称不能包含以下任何字符序列：

   | 字符序列 | 描述 |
   |--- |--- |
   | ；= | 分号，等于 |
   | ；+ | 分号，加号 |
   | ；- | 分号，减号 |
   | ；@ | 分号， At sign |
   | ，= | 逗号，等于 |
   | ，+ | 逗号，加号 |
   | ，- | 逗号，减 |
   | ，@ | 逗号， At sign |
   | `[`” | 左方括号，双引号 |
   | &quot;`]` | 双引号，右方括号 |

1. 通过更改页面上的元素创建新体验。

   创建新活动后，[!UICONTROL Visual Experience Composer]在左侧显示两个选项卡：[!UICONTROL Experience A]和[!UICONTROL Experience B]。 [!UICONTROL Experience A]是控制体验。 您关注的焦点是[!UICONTROL Experience B]选项卡，您可以根据需要对其进行修改。 [!UICONTROL Experience B]是可以添加到测试中的备用体验。 您可以通过单击[!UICONTROL Add]窗格顶部的![图标（](/help/main/assets/icons/Add.svg)添加图标[!UICONTROL Experiences]）将多个体验添加到测试中。 如果您不想在体验选项中包含默认的网站体验，则也可以从活动中删除体验 A。

   有关在[!UICONTROL Visual Experience Composer]中添加和修改体验的详细信息，请参阅[添加体验](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00)。 要修改体验 B，请从步骤 2 开始操作。

1. 单击&#x200B;**[!UICONTROL Targeting]**&#x200B;顶部的[!UICONTROL Visual Experience Composer]以进入三步引导式工作流中的下一个步骤。

   此时会打开流程图。

   ![A/B 测试定位步骤](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

   流程图会引导您完成以下步骤：分配受众及其流量百分比，选择流量分配方法，以及指定活动中每个体验的流量分配。

1. （视情况而定）单击&#x200B;**[!UICONTROL All Visitors]**&#x200B;控件以选择该活动的其他受众。

   [!UICONTROL All Visitors]受众设置为默认受众。 如果选择其他受众，则其名称将显示在最左侧的控件中。

   此时将显示正确的框架，您可以在其中添加或删除受众，并分配活动的访客百分比。

   1. 要更改受众，请单击右框架中的&#x200B;**[!UICONTROL Replace]图标** （ ![替换图标](/help/main/assets/icons/Retweet.svg) ）。
   1. 在[!UICONTROL Add Audience]对话框中，[选择所需的受众](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)，然后单击&#x200B;**[!UICONTROL Assign Audience]**。

      您可以单击&#x200B;**合并受众**&#x200B;到[创建合并多个受众的受众](/help/main/c-target/combining-multiple-audiences.md)。

      如果需要创建一个不在[!UICONTROL Audience Library]中的新受众，请单击&#x200B;**创建受众**。 在[创建受众工作流](/help/main/c-target/c-audiences/audiences.md)期间，您可以从以下选项中进行选择：

      * **[!UICONTROL Audience Library]**：创建保存到[!UICONTROL Audience Library]的按需受众，该受众可在其他活动中重复使用
      * **[!UICONTROL This activity only]**：创建未保存到[的](/help/main/c-target/creating-activity-only-audience.md)活动特定受众[!UICONTROL Audience Library]，该受众只能用于当前活动

   1. 单击右框中的&#x200B;**[!UICONTROL Visitor Percentage]**，然后选择符合条件的访客您希望参加活动的百分比。

   例如，您可以将准入资格限制为 50% 的访客或 45% 的“加州”受众。

1. 单击&#x200B;**[!UICONTROL Traffic Allocation]**&#x200B;控件，然后在右窗格中选择所需的流量分配方法。 在此方案中，单击&#x200B;**[!UICONTROL Auto-Taget for personalized experiences]**。

   ![流量分配方法设置](/help/main/c-activities/assets/auto-target.png)

   可以使用以下流量分配方法：

   * **[!UICONTROL Manual (Default)]**：指定您希望看到每个体验的参加者所占的百分比。 您可以将百分比平分到所有体验，或者也可以为每个体验指定较高或较低的百分比。所有体验的百分比总和必须等于 100%。

   * **[!UICONTROL Auto-Allocate to best experience]**：将大多数活动参加者自动定向到具有更高性能的体验。 为继续探索各体验并识别性能趋势的变化，某些访客会分配到所有体验。有关详细信息，请参阅[[!UICONTROL Auto-Allocate]概述](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)。

   * **[!UICONTROL Auto-Target for personalized experiences]**： [!DNL Target]使用先进的机器学习技术，确定多个高性能、营销人员定义的体验，然后根据访客各自的客户配置文件和过去类似访客的行为，为其提供量身定制的体验，从而个性化内容并促进转化。 有关详细信息，请参阅[自动定位概述](/help/main/c-activities/auto-target/auto-target-to-optimize.md)。

1. 单击右侧窗格中的&#x200B;**[!UICONTROL Experiences]**，然后为每个体验指定所需的流量分配。

1. 如果您对受众、体验选择和流量分配选择感到满意，请单击&#x200B;**[!UICONTROL Next]**&#x200B;以进入三步引导式工作流的第三步。

1. 指定活动的[目标和设置](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)。

   >[!NOTE]
   >
   >如果要将[Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)与此活动一起使用，请参阅自动分配和自动定位活动支持[A4T的重要信息](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)。

1. 单击&#x200B;**[!UICONTROL Save & Close]**&#x200B;或&#x200B;**[!UICONTROL Save]**。

创建活动后，[!UICONTROL Overview]选项卡会显示有关该活动的信息，包括活动图。
