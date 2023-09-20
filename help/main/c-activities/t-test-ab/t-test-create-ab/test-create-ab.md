---
keywords: 创建A/B；A/B测试；A/B活动；新建a/b活动；创建a/b
description: 了解如何在Adobe中使用可视化体验编辑器(VEC) [!DNL Target] 直接在创建A/B测试活动的步骤 [!DNL Target]-enabled页。
title: 如何创建A/B测试？
feature: A/B Tests
exl-id: 76002873-0b7c-44a8-8e89-8ad28b63eccb
source-git-commit: ec1041fd1823d1ab7f1af147af5825c3ae8662b5
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 44%

---

# 创建 A/B 测试

使用 [!UICONTROL 可视化体验编辑器] (VEC)位于 [!DNL Adobe Target] 创建您的 [!UICONTROL A/B测试] 活动直接在 [!DNL Target]启用页面，并在中修改页面的各个部分 [!DNL Target].

>[!NOTE]
>
>除手动（默认）外， [!UICONTROL A/B测试] 活动（将在本文中讨论）， [!DNL Target] 提供了两种附加类型 [!UICONTROL A/B测试] 活动： [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位].
>
>请参阅 [A/B测试活动的类型](/help/main/c-activities/t-test-ab/test-ab.md#types) 在 *A/B测试概述*.

创建手动 [!UICONTROL A/B测试] 活动：

1. 从“**[!UICONTROL 活动]**”列表中，单击&#x200B;**[!UICONTROL 创建活动]** > **[!UICONTROL A/B 测试]**。

   ![“创建活动”下拉列表](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >可用的活动类型取决于您的 [!DNL Target] 帐户。有些活动类型可能不会显示在列表中。例如，“[!UICONTROL 推荐]”是一项 [Target Premium 功能](/help/main/c-intro/intro.md#premium)。
   >
   >有关各种活动类型的信息，请参阅[活动](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)和 [Target 活动指南](/help/main/c-activities/target-activities-guide.md)。

1. 从创建A/B测试活动对话框中，选择 **[!UICONTROL 可视（默认）]**（如有必要）。

   如果您希望使用 [!UICONTROL 基于表单的体验编辑器]，选择 [!UICONTROL 表单]. 请参阅[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)，以了解更多信息。

   >[!NOTE]
   >
   >除了VEC和 [!UICONTROL 基于表单的体验编辑器]， [!DNL Target] 提供单页应用程序VEC。 有关各种编辑器的更多信息，请参阅[体验和选件](/help/main/c-experiences/experiences.md)。
   >
   >如需 VEC 的故障诊断信息，或者当您遇到问题时，请参阅[可视化体验编辑器故障诊断](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。

1. （视情况而定）如果您是 [Target Premium客户](/help/main/c-intro/intro.md#premium)，来自 **[!UICONTROL 选择工作区]** 下拉列表，选择 [工作区](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

   此 [[!UICONTROL 选择工作区]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) 上图中的选项为 [Target Premium](/help/main/c-intro/intro.md) 功能，如果您的组织具有 [!UICONTROL Target Standard] 许可证。

1. 在 **[!UICONTROL 输入活动URL]** 框中，指定您的 [活动URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md)，然后单击 **[!UICONTROL 创建]**.

   如果您的帐户[配置了默认 URL](/help/main/administrating-target/visual-experience-composer-set-up.md)，则默认情况下将显示该 URL。您可以根据需要将默认URL更改为其他URL。

   此时会打开[!UICONTROL 可视化体验编辑器]，其中显示了在 URL 中指定的页面。

1. 单击 **[!UICONTROL 无标题活动]** 然后，在VEC顶部提供的空间中指定活动的名称。

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
   | ;+ | 分号，加号 |
   | ;- | 分号，减号 |
   | ;@ | 分号， At sign |
   | ,= | 逗号，等于 |
   | ,+ | 逗号，加号 |
   | ,- | 逗号，减 |
   | ,@ | 逗号， At sign |
   | `[`&quot; | 左方括号，双引号 |
   | &quot;`]` | 双引号，右方括号 |

1. 创建任何新体验（通过更改页面上的元素）。

   创建新活动后，[!UICONTROL 可视化体验编辑器]会在左侧显示两个选项卡：“体验 A”和“体验 B”。其中，“体验 A”是控制体验。您的焦点位于体验B选项卡上，您可以根据需要对其进行修改。 体验B是可以添加到测试中的替代体验。 您可以在测试中添加多个体验。如果您不想在体验选项中包含默认的网站体验，则也可以从活动中删除体验 A。

   有关如何在[!UICONTROL 可视化体验编辑器]中添加和修改体验的更多信息，请参阅[添加体验](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00)。要修改体验 B，请从步骤 2 开始操作。

1. 在&#x200B;**[!UICONTROL 可视化体验编辑器]**&#x200B;的顶部单击[!UICONTROL 定位]，以进入三步引导式工作流中的下一个步骤。

   此时会打开流程图。

   ![A/B 测试定位步骤](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   流程图会引导您完成以下步骤：选择活动的受众和设置体验。

1. 在 **[!UICONTROL 受众]** 框中，单击编辑图标（垂直省略号），然后单击 **[!UICONTROL 替换受众]**，则 [选择受众](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) （对于您的活动）。

   默认情况下，受众设置为 [!UICONTROL 所有访客].

1. 选择您希望参加活动的符合条件的访客所占的百分比。

   ![受众百分比](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   例如，您可以将准入资格限制为 50% 的访客或 45% 的“加州”受众。

1. 设置流量分配。

   您可以向同一个受众显示多个体验。系统将显示一个图表，其中显示了您选择的受众以及添加到该活动的体验。

   选择所需的流量分配方法：

   * **[!UICONTROL 手动（默认）]**：指定您希望看到各个体验的参加者所占的百分比。 您可以将百分比平分到所有体验，或者也可以为每个体验指定较高或较低的百分比。所有体验的百分比总和必须等于 100%。

   * **[!UICONTROL 自动分配到最佳体验]**：将大多数活动参加者自动定向到具有更高性能的体验。为继续探索各体验并识别性能趋势的变化，某些访客会分配到所有体验。有关更多信息，请参阅 [[!UICONTROL 自动分配] 概述](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

   * **[!UICONTROL 自动定位以提供个性化体验]**： [!DNL Target] 使用先进的机器学习技术，确定多个高性能、由营销人员定义的体验，然后根据访客各自的客户配置文件和过去类似访客的行为，为其提供量身定制的体验，从而实现内容的个性化并推动转化。 有关更多信息，请参阅 [自动定位概述](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

   您还可以单击 **[!UICONTROL 添加]** 以向活动添加其他体验。

1. 如果您对受众、体验选择和流量分配选择满意，请单击 **[!UICONTROL 下一个]** 转到三步引导式工作流的第三步。

1. 指定活动的[目标和设置](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)。

1. 单击 **[!UICONTROL 保存并关闭]** 或 **[!UICONTROL 保存]**.

创建活动后， [!UICONTROL 概述] 选项卡显示有关活动的信息，包括活动图。

## 培训视频：创建A/B测试(8:36) ![教程徽章](/help/main/assets/tutorial.png)

以下视频演示了如何使用 [!DNL Target] 三步引导式工作流创建 A/B 测试。

* 创建 [!UICONTROL A/B测试] 中的活动 [!DNL Adobe Target]
* 使用手动拆分或自动流量分配来分配流量

>[!VIDEO](https://video.tv.adobe.com/v/17391)
