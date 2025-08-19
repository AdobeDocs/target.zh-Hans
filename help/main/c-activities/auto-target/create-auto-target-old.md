---
keywords: 创建自动定位；A/B测试；自动定位活动；新建A/B活动；自动定位；自动定位以提供个性化体验；个性化；优化
description: 了解如何在[!UICONTROL Visual Experience Composer]中使用 [!DNL Adobe Target]  (VEC)来创建[!UICONTROL Auto-Target] A/B测试活动。
title: 如何创建[!UICONTROL Auto-Target]活动？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Auto-Target
exl-id: 5521740c-eee2-4ba2-8931-cf56d56a4561
source-git-commit: 32a91a41cd182d3a55ded7dea8c1c6ea6f46aa71
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 42%

---

# 创建[!UICONTROL Auto-Target]活动

在[!UICONTROL Visual Experience Composer]中使用[!DNL Adobe Target] (VEC)直接在启用了[!UICONTROL Auto-Target]的页面上创建您的[!UICONTROL A/B Test] [!DNL Target]活动，并在[!DNL Target]内修改页面的各个部分。

>[!NOTE]
>
>[!UICONTROL Auto-Target]作为[!DNL Target Premium]解决方案的一部分提供。 如果没有 [!DNL Target Premium] 许可证，则此功能在 [!DNL Target Standard] 中不可用。有关此许可证提供的各项高级功能的更多信息，请参阅 [Target Premium](/help/main/c-intro/intro.md)。

要创建[!UICONTROL Auto-Target]活动，请执行以下操作：

1. 从&#x200B;**[!UICONTROL Activities]**&#x200B;列表中，单击&#x200B;**[!UICONTROL Create Activity]** > **[!UICONTROL A/B Test]**。

   ![“创建活动”下拉列表](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   可用的活动类型取决于您的 [!DNL Target] 帐户。有些活动类型可能不会显示在列表中。例如，[!UICONTROL Recommendations]是[Target Premium功能](/help/main/c-intro/intro.md#premium)。 有关各种活动类型的信息，请参阅[活动](/help/main/c-activities/activities.md)和 [Target 活动指南](/help/main/c-activities/target-activities-guide.md)。

1. 根据需要选择&#x200B;**[!UICONTROL Visual]**。

   如果您希望使用[!UICONTROL Form-Based Experience Composer]，请选择[!UICONTROL Form]。 请参阅[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)，以了解更多信息。

   >[!NOTE]
   >
   >除了VEC和[!UICONTROL Form-Based Experience Composer]之外，[!DNL Target]还提供单页应用程序VEC。 有关各种编辑器的更多信息，请参阅[体验和产品建议](/help/main/c-experiences/experiences.md)。
   >
   >如需 VEC 的故障诊断信息，或者当您遇到问题时，请参阅[可视化体验编辑器故障诊断](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。

1. （视情况而定）如果您是一位 [Target Premium 客户](/help/main/c-intro/intro.md#premium)，请选择一个[工作区](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

1. 指定您的[活动URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md)，然后单击&#x200B;**[!UICONTROL Next]**。

   如果您的帐户配置了默认 URL，则默认情况下将显示该 URL。您可以将默认 URL 更改为其他 URL。

   [!UICONTROL Visual Experience Composer]将打开，显示在URL中指定的页面。

   ![VEC](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/vec-new.png)

1. 在提供的空白处键入该活动的名称。

   ![名称字段](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_newname-new.png)

   活动名称不能以下列任何字符开头：

   | 字符 | 描述 |
   |--- |--- |
   | `=` | 等号 |
   | `+` | 加号 |
   | `-` | 减号 |
   | `@` | @ 符号 |

1. 通过更改页面上的元素创建任何体验。

   创建活动后，[!UICONTROL Visual Experience Composer]在左侧显示两个选项卡：体验A和体验B。体验A是控制体验。 您的焦点位于体验B选项卡上，您可以根据需要对其进行修改。 体验B是可以添加到测试中的替代体验。 您可以在测试中添加多个体验。如果您不想在体验选项中包含默认的网站体验，则也可以从活动中删除体验 A。

   有关在[!UICONTROL Visual Experience Composer]中添加和修改体验的详细信息，请参阅[添加体验](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md)。 要修改体验 B，请从步骤 2 开始操作。

1. 单击&#x200B;**[!UICONTROL Targeting]**&#x200B;顶部的[!UICONTROL Visual Experience Composer]以进入三步引导式工作流中的下一个步骤。

   此时会打开流程图。

   ![A/B 测试定位步骤](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   流程图会引导您完成以下步骤：选择活动的受众和设置体验。

1. 在[!UICONTROL Audience]框中，单击编辑图标（垂直省略号），单击&#x200B;**[!UICONTROL Replace Audience]**，然后[为您的活动选择受众](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)。

   默认情况下，受众设置为[!UICONTROL All Visitors]。

1. 选择您希望参加活动的符合条件的访客所占的百分比。

   ![受众百分比](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   例如，您可以将准入资格限制为 50% 的访客或 45% 的“加州”受众。

1. 设置流量分配。

   您可以向同一个受众显示多个体验。系统将显示一个图表，其中显示了您选择的受众以及已添加到该活动中的体验。

   选择所需的流量分配方法。 要创建[!UICONTROL Auto-Target]活动，请选择&#x200B;**[!UICONTROL Auto-Target for personalized experiences]**。

   下面介绍了三种类型的流量分配：

   * **[!UICONTROL Manual (Default)]**：指定您希望看到每个体验的参加者所占的百分比。 您可以将百分比平分到所有体验，或者也可以为每个体验指定较高或较低的百分比。所有体验的百分比总和必须等于 100%。有关详细信息，请参阅[创建A/B测试](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)。

   * **[!UICONTROL Auto-Allocate to best experience]**：将大多数活动参加者自动定向到具有更高性能的体验。 为继续探索各体验并识别性能趋势的变化，某些访客会分配到所有体验。有关详细信息，请参阅[自动分配概述](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)。

   * **[!UICONTROL Auto-Target for personalized experiences]**： [!DNL Target]使用先进的机器学习技术，确定多个高性能、营销人员定义的体验，然后根据访客各自的客户配置文件和过去类似访客的行为，为其提供量身定制的体验，从而个性化内容并促进转化。

   您还可以单击&#x200B;**[!UICONTROL Add]**&#x200B;以向该活动添加其他体验。

1. 如果您对受众、体验选择和流量分配选择感到满意，请单击&#x200B;**[!UICONTROL Next]**&#x200B;以进入三步引导式工作流的第三步。

1. 指定活动的[目标和设置](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)。

   >[!NOTE]
   >
   >如果要将[Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)与此活动一起使用，请参阅自动分配和自动定位活动支持[A4T的重要信息](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)。

1. 单击&#x200B;**[!UICONTROL Save & Close]**&#x200B;或&#x200B;**[!UICONTROL Save]**。

创建活动后，[!UICONTROL Overview]选项卡会显示有关该活动的信息，包括活动图。

## 培训视频：创建A/B测试(8:36)

以下视频演示了如何使用 [!DNL Target] 三步引导式工作流创建 A/B 测试。

* 在[!UICONTROL A/B Test]中创建[!DNL Adobe Target]活动
* 使用手动拆分或自动流量分配来分配流量

>[!VIDEO](https://video.tv.adobe.com/v/17391)
