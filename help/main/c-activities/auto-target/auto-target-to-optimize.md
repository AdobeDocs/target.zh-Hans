---
keywords: 自动定位；定位；流量分配；常见问题；faq；故障诊断；故障排除
description: 了解[!UICONTROL Auto-Target]活动如何根据客户配置文件和类似访客的行为，为每位访客提供量身定制的体验。
title: 什么是[!UICONTROL Auto-Target]活动？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Auto-Target
exl-id: 59ca30dc-45a0-4129-b832-84e1132d3b69
source-git-commit: 32a91a41cd182d3a55ded7dea8c1c6ea6f46aa71
workflow-type: tm+mt
source-wordcount: '1828'
ht-degree: 18%

---

# [!UICONTROL Auto-Target]概述

[!DNL Adobe Target]中的[!UICONTROL Auto-Target]活动使用高级机器学习从多个高性能、营销人员定义的体验中进行选择，以便个性化内容并促进转化。 [!UICONTROL Auto-Target]根据每位访客的个人客户配置文件和具有相似配置文件的先前访客的行为，为每位访客提供量身定制的体验。

>[!NOTE]
>
>* [!UICONTROL Auto-Target]作为[!DNL Target Premium]解决方案的一部分提供。 如果没有 [!DNL Target Premium] 许可证，则此功能在 [!DNL Target Standard] 中不可用。有关此许可证提供的各项高级功能的更多信息，请参阅 [Target Premium](/help/main/c-intro/intro.md)。
>
>* [!UICONTROL Analytics for Target] (A4T)支持[!UICONTROL Auto-Target]活动。 有关详细信息，请参阅自动分配和自动定位活动支持[A4T](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)。

## 使用自动定位的真实成功案例 {#success}

一家主要服装零售商最近使用具有十个基于产品类别的体验（加上随机控制）的[!UICONTROL Auto-Target]活动为每位访客提供正确的内容。 已选择“[!UICONTROL Add to Cart]”作为主要优化指标。 目标体验的平均提升度为29.09%。 构建[!UICONTROL Auto-Target]模型后，活动设置为90%个性化体验。

在短短10天内，就实现了超过170万美元的提升。

继续阅读以了解如何使用[!UICONTROL Auto-Target]提高组织的提升度和收入。

## 概述 {#section_972257739A2648AFA7E7556B693079C9}

使用三步引导式工作流[创建A/B活动](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)时，请在&#x200B;**[!UICONTROL Targeting]**&#x200B;页面上选择&#x200B;**[!UICONTROL Auto-Target for personalized experiences]**&#x200B;选项（步骤2）。

![流量分配方法设置](/help/main/c-activities/automated-traffic-allocation/assets/auto-target.png)

通过A/B活动流程中的[!UICONTROL Auto-Target]选项，您可以利用机器学习功能，只需一次单击即可根据营销人员定义的一组体验进行个性化。 与传统A/B测试或[!UICONTROL Auto Allocate]相比，[!UICONTROL Auto-Target]旨在通过确定为每个访客显示哪个体验来实现最大程度的优化。 与目标是找到一个入选者的A/B活动不同，[!UICONTROL Auto-Target]会自动确定适用于给定访客的最佳体验。 最佳体验基于访客的个人资料和其他上下文信息，以提供高度个性化的体验。

与[!UICONTROL Automated Personalization]类似，[!UICONTROL Auto-Target]使用[随机林算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)（一种领先的数据科学组合方法）来确定要向访客显示的最佳体验。 由于[!UICONTROL Auto-Target]可以适应访客行为的变化，因此它可以一直运行以实现提升。 此方法有时称为“始终运行”模式。

与A/B活动不同，A/B活动为给定访客分配的体验是具有粘性的，[!UICONTROL Auto-Target]会优化每次访问的指定业务目标。 与[!UICONTROL Auto Personalization]一样，[!UICONTROL Auto-Target]默认情况下将部分活动流量保留为控制组以测量提升。 在活动中，控制组的访客会得到随机体验。

## 注意事项

使用[!UICONTROL Auto-Target]时要记住以下重要注意事项：

* 您不能将特定活动从[!UICONTROL Auto-Target]切换到[!UICONTROL Automated Personalization]，反之亦然。
* 您无法从[!UICONTROL Manual]流量分配（传统[!UICONTROL A/B Test]）切换到[!UICONTROL Auto-Target]，而在将活动另存为草稿后，情况正好相反。
* 我们构建了一个模型，用来识别个性化策略相对于随机提供流量的表现，以及如何将所有流量发送到整个入选体验。 此模型仅考虑默认环境中的点击和转化。

  为每个建模组(AP)或体验(AT)构建来自第二组模型的流量。 对于这些模型中的每一个，都会考虑所有环境中的点击量和转化量。

  无论环境如何，使用相同的模型为请求提供服务。 但是，多个流量应来自默认环境，以确保标识的整体入选体验与真实世界行为一致。

* 至少使用两个体验。

## 术语 {#section_A309B7E0B258467789A5CACDC1D923F3}

讨论[!UICONTROL Auto-Target]时，以下术语很有用：

| 术语 | 定义 |
|---|---|
| [多臂老虎机](https://en.wikipedia.org/wiki/Multi-armed_bandit){target=_blank} | 多臂老虎机优化方法可在探索式学习和对该学习的利用之间进行平衡。 |
| [随机森林](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | 随机林是一种领先的机器学习方法。在数据科学中，它是一种集成分类方法，或回归方法，通过构建基于访客和访问属性的多个决策树来工作。 在[!DNL Target]内，随机林用于确定哪个体验对于每个特定访客具有最高的转化可能性（或每次访问的最高收入）。 |
| [汤普森采样](https://en.wikipedia.org/wiki/Thompson_sampling){target=_blank} | 汤普森采样的目标是确定哪个体验是最佳的整体（非个性化）体验，同时最大限度地降低找到该体验的“成本”。 汤普森抽样总是挑选入选者，即使两个体验之间没有统计上的差异。 |

## [!UICONTROL Auto-Target]的工作方式 {#section_77240E2DEB7D4CD89F52BE0A85E20136}

通过以下链接，了解与[!UICONTROL Auto-Target]和[!UICONTROL Automated Personalization]相关的数据和算法的更多信息：

| 术语 | 详细信息 |
|--- |--- |
| [随机林算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | [!DNL Target]在[!UICONTROL Auto-Target]和[!UICONTROL Automated Personalization]中使用的主要个性化算法是随机林。 集成方法（如随机森林）使用多种学习算法以获得比任何组成学习算法都更好的预测性能。 [!UICONTROL Automated Personalization]和[!UICONTROL Auto-Target]活动中的随机林算法是一种分类或回归方法，它通过在训练时构建大量决策树来运行。 |
| [正在上传 [!DNL Target]的Personalization算法的数据](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | 有几种方法可输入[!UICONTROL Auto-Target]和[!UICONTROL Automated Personalization]模型的数据。 |
| [为 [!DNL Target]的Personalization算法收集数据](/help/main/c-activities/t-automated-personalization/ap-data.md) | [!DNL Target]的个性化算法自动收集各种数据。 |

## 确定流量分配 {#section_AB3656F71D2D4C67A55A24B38092958F}

根据您的活动目标，您可以选择向控制体验和个性化体验分配不同的流量。最佳实践是在活动开始之前确定此目标。

[!UICONTROL Custom Allocation]下拉列表允许您从以下选项中进行选择：

* [!UICONTROL Evaluate Personalization Algorithm (50/50)]
* [!UICONTROL Maximize Personalization Traffic (90/10)]
* [!UICONTROL Custom Allocation]

![“分配目标”下拉列表](/help/main/c-activities/assets/split-new-ui.png)

下表说明了三个选项：

| 活动目标 | 建议的流量分配 | 权衡 |
|--- |--- |--- |
| **[!UICONTROL Evaluate Personalization Algorithm (50/50)]**：如果您的目标是测试算法，则可以在控制和目标算法之间按50/50的百分比拆分访客。 这种拆分可让您对提升进行最精确的评估。建议将“随机体验”用作控制。 | 按 50% 控制体验/ 50% 个性化体验进行拆分 | <ul><li>最大限度地提高控制体验和个性化体验之间提升度的准确性</li><li>具有个性化体验的访客相对较少</li></ul> |
| **[!UICONTROL Maximize Personalization Traffic (90/10)]**：如果您的目标是创建“一直开启”的活动，则可以在控制中放入10%的访客，以确保算法有足够的数据来不断学习。 这里做出的权衡是，为了对更大比例的流量进行个性化，提升度的准确性将会降低。 无论您的目标如何，在使用特定体验作为控制时，都建议按此比例拆分流量。 | 最佳实践是使用 10% - 30% 控制体验 / 70% - 90% 个性化体验的拆分方式 | <ul><li>最大限度地增加具有个性化体验的访客数量</li><li>最大化提升度</li><li>对于该活动具有的提升度，准确度较低</li></ul> |
| **自定义分配** | 根据需要手动拆分百分比。 | <ul><li>您可能无法获得所需的结果。如果您不确定，请按照上述任一选项的建议进行操作</li></ul> |

要调整[!UICONTROL Control]百分比，请单击[!UICONTROL Traffic Allocation]窗格中的[!UICONTROL Experiences]，然后根据需要调整百分比。 您不能将控制组降至 10% 以下。

您可以[选择特定体验作为控制](/help/main/c-activities/t-automated-personalization/experience-as-control.md)，也可以使用“随机体验”选项。

## 何时应选择[!UICONTROL Auto-Target]而不是[!UICONTROL Automated Personalization]？{#section_BBC4871C87944DD7A8B925811A30C633}

在以下几种情况中，您可能会偏向使用[!UICONTROL Auto-Target]，而不是[!UICONTROL Automated Personalization]：

* 如果您想定义整个体验，而不是单个选件（会自动组合形成体验）。
* 如果要使用[!UICONTROL Auto Personalization]不支持的整套[!UICONTROL Visual Experience Composer] (VEC)功能：自定义代码编辑器、多个体验受众等。
* 如果您想在不同的体验中对页面进行结构性更改。例如，如果您想重新排列主页上的元素，[!UICONTROL Auto-Target]比[!UICONTROL Automated Personalization]更适合使用。

## [!UICONTROL Auto-Target]与[!UICONTROL Automated Personalization]有什么共同点？{#section_2A601F482F9A44E38D4B694668711319}

### 算法会针对每次访问的有利结果进行优化。

* 该算法预测访客的转化倾向（或估计的转化收入）以提供最佳体验。
* 访客有资格在现有会话结束后获得新体验（除非访客位于控制组中，在这种情况下，首次访问时分配的访客体验在后续访问中保持不变）。
* 在会话内，预测不会更改，以保持视觉一致性。

### 算法可适应访客行为的变化。

* 多臂老虎机确保模型始终“花费”一小部分流量以在活动学习的整个生命周期中继续学习，并防止过度利用之前学习到的趋势。
* 使用最新的访客行为数据每24小时重建一次基础模型，以确保[!DNL Target]始终利用不断变化的访客偏好设置。
* 如果该算法无法为个人用户确定入选体验，则会自动切换为显示总体性能最佳的体验，同时仍继续查找个性化入选者。使用[汤普森采样](https://en.wikipedia.org/wiki/Thompson_sampling)查找性能最佳的体验。

### 算法会不断针对单个目标量度进行优化。

* 此量度可以基于转化，也可以基于收入（更具体地说，[!UICONTROL Revenue per Visit]）。

### [!DNL Target]自动收集关于访客的信息以构建个性化模型。

* 有关[!UICONTROL Auto-Target]和[!UICONTROL Automated Personalization]中使用的参数的详细信息，请参阅[Automated Personalization数据收集](/help/main/c-activities/t-automated-personalization/ap-data.md)。

### [!DNL Target]自动使用所有[!DNL Adobe Experience Cloud]共享受众来构建个性化模型。

* 您无需执行任何特定操作来将受众添加到模型中。有关将 [!DNL Experience Cloud Audiences] 与 [!DNL Target] 配合使用的信息，请参阅 [Experience Cloud 受众](/help/main/c-integrating-target-with-mac/mmp.md)。

### 营销人员可以上传离线数据、倾向得分或其他自定义数据来构建个性化模型。

* 了解有关[上传[!UICONTROL Auto-Target]和[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md)数据的更多信息。

## [!UICONTROL Auto-Target]与[!UICONTROL Automated Personalization]有何不同？{#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

### [!UICONTROL Auto-Target]通常需要少于[!UICONTROL Automated Personalization]的流量才能构建个性化模型。

尽管生成[!UICONTROL Auto-Target]或[!UICONTROL Auto Personalization]模型所需的每个体验&#x200B;*的流量*&#x200B;相同，但[!UICONTROL Automated Personalization]活动中的体验通常比[!UICONTROL Auto-Target]活动中的体验多。

例如，如果您的[!UICONTROL Auto Personalization]活动中有两个位置，且您已为每个位置创建两个选件，则该活动中将共包含四个(2 = 4)体验（不含排除项）。 使用[!UICONTROL Auto-Target]，您可以将体验1设置为在位置1中包含选件1，在位置2中包含选件2，将体验2设置为在位置1中包含选件1，在位置2中包含选件2。 由于[!UICONTROL Auto-Target]允许您选择在一个体验中进行多次更改，因此您可以减少活动中的体验总数。

对于[!UICONTROL Auto-Target]，可以使用简单的经验规则来了解流量要求：

* **当[!UICONTROL Conversion]是您的成功量度时：** 1,000次访问和每个体验每天至少50次转化，此外，活动必须具有至少7,000次访问和350次转化。
* **当[!UICONTROL Revenue per Visit]是您的成功量度时：** 1,000次访问和每个体验每天至少50次转化，此外，活动每个体验必须至少具有1,000次转化。 RPV 通常需要更多的数据才能构建模型，这是因为与转化率相比，访问收入通常存在着较大的数据差异。

### [!UICONTROL Auto-Target]具有完整的设置功能。

* 由于[!UICONTROL Auto-Target]嵌入到A/B活动工作流中，因此[!UICONTROL Auto-Target]将从更成熟且功能齐全的[!UICONTROL Visual Experience Composer] (VEC)中受益。 您还可以将[QA链接](/help/main/c-activities/c-activity-qa/activity-qa.md)与[!UICONTROL Auto-Target]一起使用。

### [!UICONTROL Auto-Target]提供了广泛的在线测试框架。

* 多臂老虎机是更大的在线测试框架的一部分，该框架允许[!DNL Adobe]数据科学家和研究人员了解其在真实世界条件下的持续改进的好处。
* 将来，此测试台将允许我们向数据精通的客户打开[!DNL Adobe]机器学习平台，以便他们能够引入自己的模型来增强[!DNL Target]模型。

## 报告和[!UICONTROL Auto-Target] {#section_42EE7F5E65E84F89A872FE9921917F76}

有关详细信息，请参阅[报告和自动定位](/help/main/c-activities/auto-target/reporting-and-auto-target.md)。
