---
keywords: 创建自动定位；A/B测试；自动定位活动；新建A/B活动；自动定位；自动定位以提供个性化体验；个性化；优化
description: 了解如何在Adobe中使用可视化体验编辑器(VEC) [!DNL Target] 要直接在 [!DNL Target]-enabled页面。
title: 如何创建自动定位活动？
feature: Auto-Target
exl-id: 5521740c-eee2-4ba2-8931-cf56d56a4561
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '928'
ht-degree: 49%

---

# ![PREMIUM](/help/main/assets/premium.png) 创建自动定位活动

使用 [!UICONTROL 可视化体验编辑器] (VEC) [!DNL Adobe Target] 创建 [!UICONTROL 自动定位] [!UICONTROL A/B测试] 直接在 [!DNL Target] — 启用页面，并在 [!DNL Target].

>[!NOTE]
>
>[!UICONTROL 自动定位]作为 [!DNL Target Premium] 解决方案的一部分提供。如果没有 [!DNL Target Premium] 许可证，则此功能在 [!DNL Target Standard] 中不可用。有关此许可证提供的各项高级功能的更多信息，请参阅 [Target Premium](/help/main/c-intro/intro.md)。
>
>除 [!UICONTROL 自动定位] [!UICONTROL A/B测试] 活动（在本文中讨论）、 [!DNL Target] 提供了另外两种类型 [!UICONTROL A/B测试] 活动： [!UICONTROL 手动（默认）] 和 [!UICONTROL 自动分配].
>
>请参阅 [A/B测试活动的类型](/help/main/c-activities/t-test-ab/test-ab.md#types) in *A/B测试概述*.

创建 [!UICONTROL 自动定位] 活动：

1. 从“**[!UICONTROL 活动]**”列表中，单击&#x200B;**[!UICONTROL 创建活动]** > **[!UICONTROL A/B 测试]**。

   ![“创建活动”下拉列表](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >可用的活动类型取决于您的 [!DNL Target] 帐户。有些活动类型可能不会显示在列表中。例如， [!UICONTROL 自动定位] 和 [!UICONTROL Recommendations] are [Target Premium功能](/help/main/c-intro/intro.md#premium).
   >
   >有关各种活动类型的信息，请参阅[活动](/help/main/c-activities/activities.md)和 [Target 活动指南](/help/main/c-activities/target-activities-guide.md)。

1. 如有必要，选择&#x200B;**[!UICONTROL 可视（默认）]**。

   ![创建A/B测试活动](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/create-ab.png)

   如果您希望使用 [!UICONTROL 基于表单的体验编辑器]，选择 [!UICONTROL 表单]. 请参阅[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)，以了解更多信息。

   >[!NOTE]
   >
   >除了VEC和 [!UICONTROL 基于表单的体验编辑器], [!DNL Target] 提供了单页应用程序VEC。 有关各种编辑器的更多信息，请参阅[体验和选件](/help/main/c-experiences/experiences.md)。
   >
   >如需 VEC 的故障诊断信息，或者当您遇到问题时，请参阅[可视化体验编辑器故障诊断](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。
   >
   >上图中的“[[!UICONTROL 选择工作区]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)”选项是一项 [Target Premium](/help/main/c-intro/intro.md) 功能。贵组织具有 [!UICONTROL Target Standard] 许可证。

1. 选择 [工作区](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. 指定[活动 URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md)，然后单击&#x200B;**[!UICONTROL 下一步]**。

   如果您的帐户配置了默认 URL，则默认情况下将显示该 URL。您可以将默认 URL 更改为其他 URL。

   此时会打开[!UICONTROL 可视化体验编辑器]，其中显示了在 URL 中指定的页面。

   ![VEC](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/vec-new.png)

1. 在提供的空白处键入该活动的名称。

   ![名称字段](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_newname-new.png)

   活动名称不能以以下任何字符开头：

   | 字符 | 描述 |
   |--- |--- |
   | `=` | 等号 |
   | `+` | 加号 |
   | `-` | 减号 |
   | `@` | @ 符号 |

1. 通过更改页面上的元素创建任何体验。

   的 [!UICONTROL 可视化体验编辑器] 创建活动后，左侧会显示两个选项卡：体验A和体验B。体验A是控制体验。 您的焦点在体验B选项卡上，您可以根据需要对该选项卡进行修改。 体验 B 是可添加到测试中的替代体验。您可以在测试中添加多个体验。如果您不想在体验选项中包含默认的网站体验，则也可以从活动中删除体验 A。

   有关如何在[!UICONTROL 可视化体验编辑器]中添加和修改体验的更多信息，请参阅[添加体验](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md)。要修改体验 B，请从步骤 3 开始操作。

1. 在&#x200B;**[!UICONTROL 可视化体验编辑器]**&#x200B;的顶部单击[!UICONTROL 定位]，以进入三步引导式工作流中的下一个步骤。

   此时会打开流程图。

   ![A/B 测试定位步骤](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   流程图会引导您完成以下步骤：选择活动的受众和设置体验。

1. 在 [!UICONTROL 受众] 框中，单击“编辑”图标（三个垂直省略号），然后单击 **[!UICONTROL 替换受众]**，则 [选择受众](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) 的URL。

   默认情况下，受众设置为 [!UICONTROL 所有访客].

1. 选择您希望参加活动的符合条件的访客所占的百分比。

   ![受众百分比](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   例如，您可以将准入资格限制为 50% 的访客或 45% 的“加州”受众。

1. 设置流量分配。

   您可以向同一个受众显示多个体验。将会有一个图表显示您选择的受众，以及您已添加到该活动的各个体验。

   选择所需的流量分配方法。 创建 [!UICONTROL 自动定位] 活动，选择 **[!UICONTROL 自动定位以提供个性化体验]**.

   流量分配的三种类型如下所述：

   * **[!UICONTROL 手动（默认）]**：指定您希望看到各个体验的参加者所占的百分比。您可以将百分比平分到所有体验，或者也可以为每个体验指定较高或较低的百分比。所有体验的百分比总和必须等于 100%。有关更多信息，请参阅 [创建A/B测试](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

   * **[!UICONTROL 自动分配到最佳体验]**:大多数活动参加者会自动被定向到具有更高性能的体验。 为继续探索各体验并识别性能趋势的变化，某些访客会分配到所有体验。有关更多信息，请参阅 [自动分配概述](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).

   * **[!UICONTROL 自动定位以提供个性化体验]**: [!DNL Target] 使用先进的机器学习技术，确定多个高性能、由营销人员定义的体验，然后根据访客的个人客户配置文件和过去类似访客的行为，向访客提供量身定制的体验，从而个性化内容并促进转化。
   您还可以单击 **[!UICONTROL 添加]** 以向活动添加其他体验。

1. 如果您对受众、体验选项和流量分配选项满意，请单击 **[!UICONTROL 下一个]** 以进入三步引导式工作流的第三步。

1. 指定活动的[目标和设置](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)。

   ![A/B 活动设置](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_settings-new.png)

   >[!NOTE]
   >
   >如果您想使用 [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)，请参阅 [对自动分配和自动定位活动的A4T支持](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

1. 单击 **[!UICONTROL 保存并关闭]** 或 **[!UICONTROL 保存]**.

创建活动后， [!UICONTROL 概述] 选项卡显示了有关活动的信息，包括活动图。

## 培训视频：创建A/B测试(8:36) ![教程徽章](/help/main/assets/tutorial.png)

以下视频演示了如何使用 [!DNL Target] 三步引导式工作流创建 A/B 测试。

* 创建 [!UICONTROL A/B测试] 活动 [!DNL Adobe Target]
* 使用手动拆分或自动流量分配来分配流量

>[!VIDEO](https://video.tv.adobe.com/v/17391)
