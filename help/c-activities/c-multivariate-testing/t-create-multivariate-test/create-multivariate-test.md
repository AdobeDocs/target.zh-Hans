---
keywords: mvt;multivariate test;multivariate test create;multivariate test creating;mvt create;mvt creating;mvt how;multivariate test how
description: 使用 Adobe Target 中的可视化体验编辑器，可以轻松地在启用了 Target 的页面上直接创建多变量测试 (MVT)，并在 Target 中修改页面的各个部分。
title: 创建多变量测试
uuid: 876441bd-d841-4974-b1ec-3ad7cb6ef3ee
translation-type: tm+mt
source-git-commit: 65a4fd0d05ad065c9291a83dc0b3066451f7373e

---


# 创建多变量测试{#create-a-multivariate-test}

使用 [!DNL Target] 中的[!UICONTROL 可视化体验编辑器] (VEC)，可以轻松地在启用了 Target 的页面上直接创建测试，并在 [!DNL Target] 中修改页面的各个部分。

使用 Target 点击式编辑器，您可以选择任意位置，然后添加多个选件。

[!UICONTROL 多变量测试] (MVT) 会生成单页报表。换言之，多变量测试会在某个特定的 URL 上运行，而测试中包含为该页面设计的所有体验。

1. 单击&#x200B;**[!UICONTROL 创建活动]** > **[!UICONTROL 多变量测试]**。

   ![创建多变量测试](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/create-multivariate.png)

   >[!NOTE]
   >
   >可用的活动类型取决于您的 Target 帐户。有些活动类型可能不会显示在列表中。例如，“[!UICONTROL 自动个性化]”是一项 [Target Premium 功能](/help/c-intro/intro.md#premium)。
   >
   >有关 [!DNL Target] 中可用的各种活动类型及其差异的更多信息，请参阅[活动](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)。请参阅 [Target 活动类型](/help/c-activities/target-activities-guide.md)，以帮助您确定最符合自己需求的活动类型。

1. 如有必要，选择&#x200B;**[!UICONTROL 可视（默认）]**。

   ![“创建多变量测试活动”对话框](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/create-mvt-dialog.png)

   >[!NOTE]
   >
   >如需 VEC 的故障诊断信息，或者当您遇到问题时，请参阅[可视化体验编辑器故障诊断](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。
   >
   >上图中的“[!UICONTROL 选择工作区]”选项是一项 [Target Premium](/help/c-intro/intro.md) 功能。如果您看不到此选项，则表明贵组织具有 Target Standard 许可证。

1. （视情况而定）如果您是一位 Target Premium 客户，请[选择一个工作区](/help/administrating-target/c-user-management/property-channel/property-channel.md)。

1. 为要测试的页面[指定 URL](../../../c-activities/c-multivariate-testing/t-create-multivariate-test/url.md#concept_C12E4A85FF3B4E518E3110F6CF1AF9C0)，然后单击&#x200B;**[!UICONTROL 下一步]**。

   >[!NOTE]
   >
   >请使用完整的 URL，即在开头包含 HTTP 或 HTTPS。

   如果显示了一条消息，要求您为浏览器启用混合内容，请按消息中的说明进行操作。为浏览器启用混合内容后，重新从步骤 1 开始操作。

   此时会打开可视化体验编辑器。

1. 键入活动的名称。

   ![活动名称字段](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/activityname.png)

   活动名称中不允许使用以下字符：

   | 字符 | 描述 |
   |--- |--- |
   | / | 正斜线 |
   | ? | 问号 |
   | # | 数字符号 |
   | : | 冒号 |
   | = | 等号 |
   | + | 加号 |
   | - | 减号 |
   | @ | @ 符号 |

1. [在每个位置中创建选件](../../../c-activities/c-multivariate-testing/t-create-multivariate-test/add-offers.md#concept_DCE6B45C30F7419B8EC17AFDEE8D8AA6)。

   ![“编辑文本/HTML”对话框](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/editoffers.png)

   您可以添加以下类型的选件：

   * HTML
   * 图像
   * 文本

1. 单击&#x200B;**[!UICONTROL 预览]**&#x200B;以[预览您的体验](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md)。

   ![预览体验](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt.png)

   您可以查看每个体验，并排除不希望包含在测试中的任何体验。要排除一个或多个体验，请选中所需的复选框，然后单击&#x200B;**[!UICONTROL 排除]**。

   ![排除体验](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt-exclude.png)

1. [使用流量估算器](../../../c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714)来检验测试计划的可行性。

   ![流量指示器](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-traffic-indicator.png)

   下图指示活动流量不足。

   ![](assets/estimator.png)

   下图指示活动流量不足。

   ![](assets/estimator2.png)

1. 单击&#x200B;**[!UICONTROL 下一步]**&#x200B;以前进到“[!UICONTROL 定位]”页面。

1. 选择受众，以及您希望参加活动的符合条件的访客所占的百分比。

   ![MVT 活动中的“定位”页面](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_audperc.png)

   例如，您可以将准入资格限制为 50% 的访客或 45% 的“加州”受众。

   >[!NOTE]
   >
   >除了选择现有受众之外，您还可以合并多个受众来创建临时组合受众，而不是创建新受众。有关更多信息，请参阅[合并多个受众](../../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

1. [查看测试摘要](../../../c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md#reference_971AB225963A4DC18EEB5B0E20F0A4A7)，做出任何所需的更改，然后单击&#x200B;**[!UICONTROL 下一步]**。

1. [指定测试的目标和设置](../../../c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)。

1. 单击&#x200B;**[!UICONTROL 保存并关闭]**&#x200B;以创建活动。

## 培训视频：创建Multivariate Tests(9:25)教 ![程徽章](/help/assets/tutorial.png)

以下视频演示了如何使用 Target 三步引导式工作流规划并创建多变量测试。

* 定义和设计多变量测试
* 创建多变量测试

>[!VIDEO](https://video.tv.adobe.com/v/17395)
