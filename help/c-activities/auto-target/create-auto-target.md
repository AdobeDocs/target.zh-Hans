---
keywords: 创建自动目标;A/B测试；自动目标活动；新的a/b活动；自动目标；个性化体验的自动目标；个性化体验
description: 使用Adobe Target的可视体验书写器(VEC)直接在启用目标的页面上创建自动目标A/B测试活动，并修改目标中页面的部分。
title: 创建自动目标活动
feature: Auto-Target
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '940'
ht-degree: 57%

---


# ![](/help/assets/premium.png) PREMUMC创建自动目标活动

使用[!DNL Adobe Target]中的[!UICONTROL 可视体验书写器](VEC)，直接在启用[!DNL Target]的页面上创建[!UICONTROL 自动目标] [!UICONTROL A/B测试]活动，并修改[!DNL Target]中的页面部分。

>[!NOTE]
>
>[!UICONTROL 自动定位]作为 [!DNL Target Premium] 解决方案的一部分提供。如果没有 [!DNL Target Premium] 许可证，则此功能在 [!DNL Target Standard] 中不可用。有关此许可证提供的各项高级功能的更多信息，请参阅 [Target Premium](/help/c-intro/intro.md)。
>
>除了[!UICONTROL 自动目标] [!UICONTROL A/B测试]活动（本文讨论）之外，[!DNL Target]还提供了两种附加类型的[!UICONTROL A/B测试]活动:[!UICONTROL 手动（默认）]和[!UICONTROL 自动分配]。
>
>请参阅&#x200B;*A/B测试概述*&#x200B;中的[A/B测试活动类型](/help/c-activities/t-test-ab/test-ab.md#types)。

要创建[!UICONTROL 自动目标]活动:

1. 从“**[!UICONTROL 活动]**”列表中，单击&#x200B;**[!UICONTROL 创建活动]** > **[!UICONTROL A/B 测试]**。

   ![“创建活动”下拉列表](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >可用的活动类型取决于您的 [!DNL Target] 帐户。有些活动类型可能不会显示在列表中。例如，[!UICONTROL 自动目标]和[!UICONTROL Recommendations]是[目标高级功能](/help/c-intro/intro.md#premium)。
   >
   >有关各种活动类型的信息，请参阅[活动](/help/c-activities/activities.md)和 [Target 活动指南](/help/c-activities/target-activities-guide.md)。

1. 如有必要，选择&#x200B;**[!UICONTROL 可视（默认）]**。

   ![创建A/B测试活动](/help/c-activities/t-test-ab/t-test-create-ab/assets/create-ab.png)

   如果您希望使用[!UICONTROL 基于表单的体验书写器]，请选择[!UICONTROL 表单]。 请参阅[基于表单的体验编辑器](/help/c-experiences/form-experience-composer.md)，以了解更多信息。

   >[!NOTE]
   >
   >除VEC和[!UICONTROL 基于表单的体验书写器]外，[!DNL Target]还优惠单页应用程序VEC。 有关各种编辑器的更多信息，请参阅[体验和选件](/help/c-experiences/experiences.md)。
   >
   >如需 VEC 的故障诊断信息，或者当您遇到问题时，请参阅[可视化体验编辑器故障诊断](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。
   >
   >上图中的“[[!UICONTROL 选择工作区]](/help/administrating-target/c-user-management/property-channel/property-channel.md)”选项是一项 [Target Premium](/help/c-intro/intro.md) 功能。如果您未看到此选项，则您的组织具有[!UICONTROL 目标标准]许可证。

1. 选择[工作区](/help/administrating-target/c-user-management/property-channel/property-channel.md)。

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

   有关如何在[!UICONTROL 可视化体验编辑器]中添加和修改体验的更多信息，请参阅[添加体验](/help/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md)。要修改体验 B，请从步骤 3 开始操作。

1. 在&#x200B;**[!UICONTROL 可视化体验编辑器]**&#x200B;的顶部单击[!UICONTROL 定位]，以进入三步引导式工作流中的下一个步骤。

   此时会打开流程图。

   ![A/B 测试定位步骤](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   流程图会引导您完成以下步骤：选择活动的受众和设置体验。

1. 在[!UICONTROL 受众]框中，单击编辑图标（三个垂直椭圆），单击&#x200B;**[!UICONTROL 替换受众]**，然后[选择活动](/help/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)。

   默认情况下，受众设置为[!UICONTROL 所有访客]。

1. 选择您希望参加活动的符合条件的访客所占的百分比。

   ![受众百分比](/help/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   例如，您可以将准入资格限制为 50% 的访客或 45% 的“加州”受众。

1. 设置流量分配。

   您可以向同一个受众显示多个体验。将会有一个图表显示您选择的受众，以及您已添加到该活动的各个体验。

   选择所需的流量分配方法。 要创建[!UICONTROL 自动目标]活动，请选择&#x200B;**[!UICONTROL 自动目标以获得个性化体验]**。

   流量分配的三种类型如下所述：

   * **[!UICONTROL 手动（默认）]**：指定您希望看到各个体验的参加者所占的百分比。您可以将百分比平分到所有体验，或者也可以为每个体验指定较高或较低的百分比。所有体验的百分比总和必须等于 100%。有关详细信息，请参阅[创建A/B测试](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)。

   * **[!UICONTROL 自动分配到最佳体验]**：将大多数活动参加者自动定向到具有更高性能的体验。为继续探索各体验并识别性能趋势的变化，某些访客会分配到所有体验。有关详细信息，请参阅[自动分配概述](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)。

   * **[!UICONTROL 自动目标，提供个性化体验]**: [!DNL Target] 使用高级机器学习来识别多个高性能的营销人员定义体验，从而个性化内容并推动转化，然后根据访客的个人用户档案和相似访客的过去行为，为客户提供最为定制的体验。
   您还可以单击&#x200B;**[!UICONTROL 添加]**&#x200B;以向活动添加其他体验。

1. 如果您对受众、体验选择和流量分配选择感到满意，请单击&#x200B;**[!UICONTROL 下一步]**&#x200B;以转到三步指导式工作流的第三步。

1. 指定活动的[目标和设置](/help/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)。

   ![A/B 活动设置](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_settings-new.png)

   >[!NOTE]
   >
   >如果要对此目标使用[分析](/help/c-integrating-target-with-mac/a4t/a4t.md)(A4T)，请参阅[A4T支持自动分配和自动目标活动](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md)中的重要信息。

1. 单击&#x200B;**[!UICONTROL 保存并关闭]**&#x200B;或&#x200B;**[!UICONTROL 保存]**。

创建活动后，[!UICONTROL 概述]选项卡显示有关活动的信息，包括活动的图。

## 培训视频：创建A/B测试(8:36)![教程标记](/help/assets/tutorial.png)

以下视频演示了如何使用 [!DNL Target] 三步引导式工作流创建 A/B 测试。

* 在[!DNL Adobe Target]中创建[!UICONTROL A/B测试]活动
* 使用手动拆分或自动流量分配来分配流量

>[!VIDEO](https://video.tv.adobe.com/v/17391)