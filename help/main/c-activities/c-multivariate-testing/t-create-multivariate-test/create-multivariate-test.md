---
keywords: MVT;多变量测试;多变量测试创建;MVT 创建;MVT 工作原理;多变量测试工作原理
description: 了解如何使用 [!UICONTROL 可视化体验编辑器] (VEC)位于 [!DNL Adobe Target] 创建 [!UICONTROL 多变量测试] (MVT)。
title: 如何创建 [!UICONTROL 多变量测试]？
feature: Multivariate Tests
exl-id: 7712b747-543a-4e19-b689-bea36c44805c
source-git-commit: 7853d8c5934e40d1026e067dfa413f520ecba931
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 62%

---

# 创建多变量测试

此 [!UICONTROL 可视化体验编辑器] (VEC)位于 [!DNL Adobe Target] 使创建更容易 [!UICONTROL 多变量测试] 并在中修改页面的各个部分 [!DNL Target].

此 [!DNL Target] 使用点击式编辑器，您可以选择任意位置并添加多个选件。

[!UICONTROL 多变量测试] (MVT) 会生成单页报表。换言之，多变量测试会在某个特定的 URL 上运行，而测试中包含为该页面设计的所有体验。

1. 单击&#x200B;**[!UICONTROL 创建活动]** > **[!UICONTROL 多变量测试]**。

   ![创建多变量测试](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/create-multivariate.png)

   >[!NOTE]
   >
   >有关 [!DNL Target] 中可用的各种活动类型及其差异的更多信息，请参阅[活动](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)。请参阅 [Target 活动类型](/help/main/c-activities/target-activities-guide.md)，以帮助您确定最符合自己需求的活动类型。

1. （视情况而定）选择交货类型： [!UICONTROL Web]， [!UICONTROL 移动设备]， [!UICONTROL 电子邮件]，或 [!UICONTROL 其他/API].

1. （视情况而定）如果您是 [Target Premium](/help/main/c-intro/intro.md#premium) 客户， [选择工作区](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. [指定URL](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/url.md#concept_C12E4A85FF3B4E518E3110F6CF1AF9C0) ，然后单击 **[!UICONTROL 下一个]**.

   >[!NOTE]
   >
   >请使用完整的URL，即在开头包含HTTP或HTTPS。

   如果显示了一条消息，要求您为浏览器启用混合内容，请按消息中的说明进行操作。为浏览器启用混合内容后，重新从步骤 1 开始操作。

   此 [!UICONTROL 可视化体验编辑器] 打开。

1. 键入活动的名称。

   ![活动名称字段](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/activityname.png)

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

1. [在每个位置中创建选件](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/add-offers.md#concept_DCE6B45C30F7419B8EC17AFDEE8D8AA6)。

   ![“编辑文本/HTML”对话框](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/editoffers.png)

   您可以添加以下类型的选件：

   * HTML
   * 图像
   * 文本

1. 单击&#x200B;**[!UICONTROL 预览]**&#x200B;以[预览您的体验](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md)。

   ![预览体验](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt.png)

   您可以查看每个体验，并排除不希望包含在测试中的任何体验。要排除一个或多个体验，请选中所需的复选框，然后单击&#x200B;**[!UICONTROL 排除]**。

   ![排除体验](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt-exclude.png)

1. [使用流量估算器](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714)来检验测试计划的可行性。

   ![流量指示器](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-traffic-indicator.png)

   下图指示活动流量不足。

   ![估算器图像](assets/estimator.png)

   下图指示活动流量不足。

   ![estimator2图像](assets/estimator2.png)

1. 单击 **[!UICONTROL 下一个]** 以前进到 [!UICONTROL 定位] 页面。

1. 选择受众，以及您希望参加活动的符合条件的访客所占的百分比。

   ![MVT 活动中的“定位”页面](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_audperc.png)

   例如，您可以将准入资格限制为 50% 的访客或 45% 的“加州”受众。

   >[!NOTE]
   >
   >除了选择现有受众之外，您还可以合并多个受众来创建临时组合受众，而不是创建新受众。有关更多信息，请参阅[合并多个受众](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

1. [查看测试摘要](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md#reference_971AB225963A4DC18EEB5B0E20F0A4A7)，做出任何所需的更改，然后单击&#x200B;**[!UICONTROL 下一步]**。

1. [指定测试的目标和设置](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)。

1. 单击&#x200B;**[!UICONTROL 保存并关闭]**&#x200B;以创建活动。

## 培训视频：创建多变量测试(9:25) ![教程徽章](/help/main/assets/tutorial.png)

本视频演示如何使用规划和创建多变量测试 [!DNL Target] 三步引导式工作流。

* 定义和设计多变量测试
* 创建多变量测试

>[!VIDEO](https://video.tv.adobe.com/v/17395)
