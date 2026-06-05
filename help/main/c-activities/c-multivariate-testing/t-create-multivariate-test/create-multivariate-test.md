---
keywords: MVT;多变量测试;多变量测试创建;MVT 创建;MVT 工作原理;多变量测试工作原理
description: 了解如何在 [!DNL Adobe Target] 中使用[!UICONTROL 可视化体验编辑器] (VEC)来创建[!UICONTROL 多变量测试] (MVT)。
title: 如何创建[!UICONTROL 多变量测试]？
feature: Multivariate Tests
exl-id: 7712b747-543a-4e19-b689-bea36c44805c
TQID: https://experienceleague.adobe.com/gxrnY43A7OWsiW48Rlq1Orp7ZxBswdAPZEAbRQrCDZA
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 809
ht-degree: 23%

---

# 创建多变量测试

通过[!DNL Adobe Target]中的[!UICONTROL 可视化体验编辑器] (VEC)，可以轻松创建[!UICONTROL 多变量测试]，并在[!DNL Target]内修改页面的各个部分。

使用[!DNL Target]点击式编辑器，您可以选择任意位置并添加多个选件。

[!UICONTROL 多变量测试] (MVT)生成页面优先报表。 换言之，多变量测试会在某个特定的 URL 上运行，而测试中包含为该页面设计的所有体验。

1. 单击&#x200B;**[!UICONTROL 创建活动]** > **[!UICONTROL 多变量测试]**。

   >[!NOTE]
   >
   >有关 [!DNL Target] 中可用的各种活动类型及其差异的更多信息，请参阅[活动](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)。 请参阅 [Target 活动类型](/help/main/c-activities/target-activities-guide.md)，以帮助您确定最符合自己需求的活动类型。

1. （视情况而定）选择传递类型：[!UICONTROL Web]、[!UICONTROL Mobile]、[!UICONTROL 电子邮件]或[!UICONTROL 其他/API]。

1. （视情况而定）如果您是[Target Premium](/help/main/c-intro/intro.md#premium)客户，请[选择工作区](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

1. [为要测试的页面指定URL](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/url.md#concept_C12E4A85FF3B4E518E3110F6CF1AF9C0)，然后单击&#x200B;**[!UICONTROL 创建]**。

   >[!NOTE]
   >
   >请使用完整的URL，即在开头包含HTTP或HTTPS。

   如果显示了一条消息，要求您为浏览器启用混合内容，请按消息中的说明进行操作。 为浏览器启用混合内容后，重新从步骤 1 开始操作。

   [!UICONTROL 可视化体验编辑器]打开。

1. 要命名该活动，请单击“[!UICONTROL 无标题的活动]”旁边的&#x200B;**[!UICONTROL 编辑]**&#x200B;图标（![编辑图标](/help/main/assets/icons/Edit.svg)），指定该活动的描述性名称，然后单击&#x200B;**[!UICONTROL 保存]**。

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
   | ;= | 分号，等于 |
   | ;+ | 分号，加号 |
   | ;- | 分号，减号 |
   | ;@ | 分号， At sign |
   | ,= | 逗号，等于 |
   | ,+ | 逗号，加号 |
   | ,- | 逗号，减 |
   | ,@ | 逗号， At sign |
   | `[`&quot; | 左方括号，双引号 |
   | &quot;`]` | 双引号，右方括号 |

1. [在每个位置中创建产品建议](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/add-offers.md#concept_DCE6B45C30F7419B8EC17AFDEE8D8AA6)。

   您可以添加以下类型的选件：

   * HTML
   * 图像
   * 文本

1. 单击&#x200B;**[!UICONTROL 预览]**&#x200B;以[预览您的体验](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md)。

1. 单击&#x200B;**[!UICONTROL 显示体验]**&#x200B;图标（![显示体验图标](/help/main/assets/icons/WebPages.svg)）以显示左侧框架中的所有体验列表。

1. 单击列表中的特定体验，以查看该体验。

1. （视情况而定）要从活动中排除一个或多个体验，请单击&#x200B;**[!UICONTROL 管理内容]**&#x200B;图标（![管理体验图标](/help/main/assets/icons/Experience.svg)）以显示[!UICONTROL 管理体验]对话框。

1. （视情况而定）在[!UICONTROL 管理体验]对话框中，单击要排除的体验旁边的&#x200B;**[!UICONTROL 更多操作]**&#x200B;图标（![更多操作图标](/help/main/assets/icons/MoreSmallList.svg)），然后单击&#x200B;**[!UICONTROL 排除]**。

   您可能会选择排除显示冲突变体的体验，或在美学上未实现平衡的体验。

1. （视情况而定）要排除多个体验，请选中所需体验对应的复选框，然后单击&#x200B;**[!UICONTROL 排除]**。

1. [使用流量估算器](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714)来检验测试计划的可行性。

1. 单击&#x200B;**[!UICONTROL 下一步]**&#x200B;前进到[!UICONTROL 定位]页面。

   如果您使用过其他[!DNL Target]活动类型，则&#x200B;**定位**&#x200B;步骤看起来会很熟悉。 在此步骤中，您可以选择受众，并指定查看每个体验的访客百分比。

   流程图会引导您完成以下步骤：分配受众及其流量百分比，选择流量分配方法，以及指定活动中每个体验的流量分配。

1. （视情况而定）单击&#x200B;**[!UICONTROL 所有访客]**&#x200B;控件为该活动选择其他受众。

   已将[!UICONTROL 所有访客]受众设置为默认受众。 如果选择其他受众，则其名称将显示在最左侧的控件中。

   此时将显示正确的框架，您可以在其中添加或删除受众，并分配活动的访客百分比。

   1. 要更改受众，请单击右框架中的&#x200B;**[!UICONTROL 替换]图标** （![替换图标](/help/main/assets/icons/Retweet.svg) ）。
   1. 在[!UICONTROL 添加受众]对话框中，[选择所需的受众](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)，然后单击&#x200B;**[!UICONTROL 分配受众]**。

      您可以单击&#x200B;**合并受众**&#x200B;到[创建合并多个受众的受众](/help/main/c-target/combining-multiple-audiences.md)。

      如果需要创建一个不在[!UICONTROL 受众库]中的新受众，请单击&#x200B;**创建受众**。 在[创建受众工作流](/help/main/c-target/c-audiences/audiences.md)期间，您可以从以下选项中进行选择：

      * **[!UICONTROL 受众库]**：创建保存到[!UICONTROL 受众库]的按需受众，该受众可在其他活动中重复使用。
      * **[!UICONTROL 仅限此活动]**：创建未保存到[!UICONTROL 受众库]且只能用于当前活动的[特定活动受众](/help/main/c-target/creating-activity-only-audience.md)。

   1. 单击右框中的&#x200B;**[!UICONTROL 访客百分比]**，然后选择您希望参加活动的符合条件的访客所占的百分比。

   例如，您可以将准入资格限制为 50% 的访客或 45% 的“加州”受众。

1. [查看测试摘要](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md#reference_971AB225963A4DC18EEB5B0E20F0A4A7)并进行任何所需的更改，然后单击&#x200B;**[!UICONTROL 下一步]**。

1. [指定测试的目标和设置](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)。

1. 单击&#x200B;**[!UICONTROL 保存并关闭]**&#x200B;以创建该活动。

## 培训视频：创建多变量测试(9:25) ![教程徽章](/help/main/assets/tutorial.png)

本视频演示了如何使用[!DNL Target]三步引导式工作流规划和创建多变量测试。

* 定义和设计多变量测试
* 创建多变量测试

>[!VIDEO](https://video.tv.adobe.com/v/17395)
