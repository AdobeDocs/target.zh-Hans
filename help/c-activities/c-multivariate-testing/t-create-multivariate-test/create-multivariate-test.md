---
description: 使用 Target 中的可视化体验编辑器，可以轻松地在启用了 Target 的页面上直接创建测试，并在 Target 中修改页面的各个部分。
keywords: MVT;多变量测试;多变量测试创建;MVT 创建;MVT 工作原理;多变量测试工作原理
seo-description: 使用 Target 中的可视化体验编辑器，可以轻松地在启用了 Target 的页面上直接创建测试，并在 Target 中修改页面的各个部分。
seo-title: 创建多变量测试
solution: Target
title: 创建多变量测试
uuid: 876441bd-d841-4974-b1ec-3ad7cb6ef3ee
translation-type: tm+mt
source-git-commit: 5405e95cf516f973b69834ac114a1e351cd3040a

---


# 创建多变量测试{#create-a-multivariate-test}

使用 Target 中的可视化体验编辑器，可以轻松地在启用了 Target 的页面上直接创建测试，并在 Target 中修改页面的各个部分。

使用 Target 点击式编辑器，您可以选择任意位置，然后添加多个选件。

多变量测试会生成单页报表。换言之，多变量测试会在某个特定的 URL 上运行，而测试中包含为该页面设计的所有体验。

1. 单击**[!UICONTROL 创建活动]** &gt; **[!UICONTROL 多变量测试]**。

   ![](assets/create_mvt.png)

1. 为要测试的页面[指定 URL](../../../c-activities/c-multivariate-testing/t-create-multivariate-test/url.md#concept_C12E4A85FF3B4E518E3110F6CF1AF9C0)，然后单击**[!UICONTROL 创建活动]**。

   ![](assets/url.png)

   >[!NOTE]
   >
   >请使用完整的 URL，即在开头包含 HTTP 或 HTTPS。

   如果显示了一条消息，要求您为浏览器启用混合内容，请按消息中的说明进行操作。为浏览器启用混合内容后，重新从步骤 1 开始操作。

   此时会打开可视化体验编辑器。

   如需 VEC 的故障诊断信息，或者当您遇到问题时，请参阅[可视化体验编辑器故障诊断](../../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md#reference_77743144F10143A3A89D56E116D296E4)。
1. 键入活动的名称。

   ![](assets/activityname.png)

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

   ![](assets/editoffers.png)

   您可以添加以下类型的选件：

   * HTML
   * 图像
   * 文本

1. [预览体验](../../../c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md#task_21A700587E88453A9FC2210C0DE53A28)。

   ![](assets/preview.png)

   您可以查看每个体验，并排除不希望包含在测试中的任何体验。
1. [使用流量估算器](../../../c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714)来检验测试计划的可行性。

   ![](assets/estimator.png)  ![](assets/estimator2.png)

1. 选择受众，以及您希望参加活动的符合条件的访客所占的百分比。

   ![](assets/mvt_audperc.png)

   例如，您可以将准入资格限制为 50% 的访客或 45% 的“加州”受众。

   >[!NOTE]
   >
   >除了选择现有受众之外，您还可以合并多个受众来创建临时组合受众，而不是创建新受众。有关更多信息，请参阅[合并多个受众](../../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

1. [查看测试摘要](../../../c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md#reference_971AB225963A4DC18EEB5B0E20F0A4A7)，做出任何所需的更改，然后单击**[!UICONTROL 下一个]**。

   ![](assets/mvtflow.png)

1. [指定测试的目标和设置](../../../c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)。

   ![](assets/settings.png)

1. 单击**[!UICONTROL 保存并关闭]**以创建活动。

## 培训视频：创建多变量测试 (9:25)

以下视频演示了如何使用 Target 三步引导式工作流规划并创建多变量测试。

* 定义和设计多变量测试
* 创建多变量测试

>[!VIDEO](https://video.tv.adobe.com/v/17395)
