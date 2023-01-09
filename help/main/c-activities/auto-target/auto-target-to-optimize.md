---
keywords: 自动定位；定位；流量分配；常见问题解答；FAQ；故障诊断；故障排除
description: 了解 [!UICONTROL 自动定位] 活动 [!DNL Target] 根据客户配置文件和类似访客的行为，向每位访客提供量身定制的体验。
title: 什么是 [!UICONTROL 自动定位] 活动？
feature: Auto-Target
exl-id: 59ca30dc-45a0-4129-b832-84e1132d3b69
source-git-commit: 3e567236b30db453e2cd1bbb7c92c58ae4528ff4
workflow-type: tm+mt
source-wordcount: '1970'
ht-degree: 50%

---

# ![PREMIUM](/help/main/assets/premium.png) [!UICONTROL 自动定位] 概述

[!UICONTROL 自动定位] 活动 [!DNL Adobe Target] 使用先进的机器学习技术从营销人员定义的多个高性能体验中进行选择，以个性化内容并促进转化。 [!UICONTROL 自动定位] 根据单个客户配置文件和具有相似配置文件的先前访客的行为，向每位访客提供量身定制的体验。

>[!NOTE]
>
>* [!UICONTROL 自动定位]作为 [!DNL Target Premium] 解决方案的一部分提供。如果没有 [!DNL Target Premium] 许可证，则此功能在 [!DNL Target Standard] 中不可用。有关此许可证提供的各项高级功能的更多信息，请参阅 [Target Premium](/help/main/c-intro/intro.md)。
>
>* [!UICONTROL Analytics for Target] (A4T)支持 [!UICONTROL 自动定位] 活动。 有关更多信息，请参阅[自动分配和自动定位活动支持 A4T](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)。


## 使用自动定位的真实世界成功案例 {#success}

一家大型服装零售商最近使用了 [!UICONTROL 自动定位] 活动，提供十个基于产品类别的体验（以及随机控制），以向每位访客提供正确的内容。 &quot;[!UICONTROL 添加到购物车]“ ”作为主要优化量度。 定位体验的平均提升率为29.09%。 在构建 [!UICONTROL 自动定位] 模型时，活动会设置为90%的个性化体验。

仅仅在10天内，就实现了170多万美元的提升。

继续阅读以了解如何使用 [!UICONTROL 自动定位] 以增加贵组织的提升和收入。

## 概述 {#section_972257739A2648AFA7E7556B693079C9}

[在使用三步引导式工作流创建 A/B 活动](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)时，您可以选择使用“[!UICONTROL 自动定位以提供个性化体验]”选项来分配流量：

![“自动定位以提供个性化体验”选项](/help/main/c-activities/assets/auto-target-ui-new.png)

通过 A/B 活动流程中的[!UICONTROL 自动定位]选项，您可以利用机器学习功能，只需一次单击即可根据营销人员定义的一组体验进行个性化。[!UICONTROL 自动定位] 与传统A/B测试或 [!UICONTROL 自动分配]，以确定要为每个访客显示的体验。 与目标是找到一个入选者的 A/B 活动不同，[!UICONTROL 自动定位]会自动确定适用于给定访客的最佳体验（根据其个人资料和其他相关信息），从而交付高度个性化的体验。

类似于 [!UICONTROL Automated Personalization], [!UICONTROL 自动定位] 使用 [随机林算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)是一种领先的数据科学组合方法，可确定要向访客显示的最佳体验。 由于[!UICONTROL 自动定位]可根据访客行为的变化而自行调整，因此它可以一直运行以实现提升。这有时被称为“始终运行”模式。

与 A/B 活动不同，[!UICONTROL 自动定位]会优化每次访问的指定业务目标，而 A/B 活动为给定访客分配的体验是具有粘性的。与[!UICONTROL 自动个性化]一样，默认情况下，[!UICONTROL 自动定位]会将部分活动流量作为控制组保留以便测量提升度。在活动中，控制组的访客会得到随机体验。

## 注意事项

使用 [!UICONTROL 自动定位]:

* 您无法从 [!UICONTROL 自动定位] to [!UICONTROL Automated Personalization]，反之亦然。
* 无法从 [!UICONTROL 手动] 流量分配(传统 [!UICONTROL A/B测试]) [!UICONTROL 自动定位]，反之亦然。
* 我们构建了一个模型，以识别个性化策略与随机提供流量的性能，以及将所有流量发送到整个入选体验的性能。 此模型仅考虑默认环境中的点击和转化。

   每个建模组(AP)或体验(AT)会生成第二组模型的流量。 对于其中每个模型，都会考虑所有环境中的点击和转化。

   请求会使用相同的模型来提供，而不管环境如何，但多个流量应来自默认环境，以确保已识别的整体入选体验与真实世界的行为一致。

* 至少使用两个体验。

## 术语 {#section_A309B7E0B258467789A5CACDC1D923F3}

讨论[!UICONTROL 自动定位]时，以下术语很有用：

| 术语 | 定义 |
|---|---|
| [多臂老虎机](https://en.wikipedia.org/wiki/Multi-armed_bandit){target=_blank} | 多臂老虎机优化方法可在探索式学习和对该学习的利用之间进行平衡。 |
| [随机森林](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | 随机林是一种领先的机器学习方法。在数据科学领域，它是一种组合分类或回归方法，通过基于访客和访问属性构建许多决策树来工作。 在 [!DNL Target]，随机林用于确定每个特定访客的转化可能性（或每次访问带来的最高收入）最高的体验。 |
| [汤普森采样](https://en.wikipedia.org/wiki/Thompson_sampling){target=_blank} | 汤普森采样的目标是确定哪个体验总体上最好（非个性化），同时最大限度地降低查找该体验的“成本”。 即便两种体检之间没有统计意义上的差异，汤普森采样算法还是会选出一个入选者。 |

## [!UICONTROL 自动定位]的工作方式 {#section_77240E2DEB7D4CD89F52BE0A85E20136}

请通过以下链接，了解与[!UICONTROL 自动定位]和自动个性化的数据和算法相关的更多信息：

| 术语 | 详细信息 |
|--- |--- |
| [随机林算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | Target 在[!UICONTROL 自动定位]和自动个性化中使用的主要个性化算法是随机林。相较于从任何组成学习算法获得的性能而言，诸如随机林之类的组合方法可使用多种学习算法获得更好的预测性能。在 [!UICONTROL Automated Personalization] 和 [!UICONTROL 自动定位] 活动是一种分类或回归方法，在培训时通过构建大量决策树来操作。 |
| [为 Target 个性化算法上传数据](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | 有几种方法可以为[!UICONTROL 自动定位]和自动个性化模型输入数据。 |
| [为 Target 个性化算法收集数据](/help/main/c-activities/t-automated-personalization/ap-data.md) | Target的个性化算法会自动收集各种数据。 |

## 确定流量分配 {#section_AB3656F71D2D4C67A55A24B38092958F}

根据您的活动目标，您可以选择向控制体验和个性化体验分配不同的流量。最佳实践是在活动开始之前确定此目标。

“[!UICONTROL 自定义分配]”下拉列表可让您从以下选项中进行选择：

* 评估个性化算法
* 最大化个性化流量
* 自定义分配

![“分配目标”下拉列表](/help/main/c-activities/assets/split-new.png)

| 活动目标 | 建议的流量分配 | 权衡 |
|--- |--- |--- |
| **评估个性化算法 (50/50)**：如果您的目标是测试算法，则可以在控制和目标算法之间按 50/50 的百分比拆分访客。这种拆分可让您对提升进行最精确的评估。建议将“随机体验”用作控制。 | 按 50% 控制体验/ 50% 个性化体验进行拆分 | <ul><li>最大限度地提高控制体验和个性化体验之间提升度的准确性</li><li>具有个性化体验的访客相对较少</li></ul> |
| **最大化个性化流量(90/10)**:如果您的目标是创建“一直开启”的活动，请将10%的访客置于控制中，以确保算法有足够的数据来不断学习。 请注意，这里做出的权衡是，为了对较大比例的流量进行个性化，提升度的准确度会降低。 无论您的目标如何，在使用特定体验作为控制时，都建议按此比例拆分流量。 | 最佳实践是使用 10% - 30% 控制体验 / 70% - 90% 个性化体验的拆分方式 | <ul><li>最大化拥有个性化体验的访客数量</li><li>最大化提升度</li><li>对于该活动具有的提升度，准确度较低</li></ul> |
| **自定义分配** | 根据需要手动拆分百分比。 | <ul><li>您可能无法获得所需的结果。如果您不确定，请按照上述任一选项的建议进行操作</li></ul> |

要调整 [!UICONTROL 控制] 百分比，单击 [!UICONTROL 分配] 列。 您不能将控制组降至 10% 以下。

![更改自动定位流量分配](/help/main/c-activities/assets/auto-target-control.png)

您可以[选择特定体验作为控制](/help/main/c-activities/t-automated-personalization/experience-as-control.md)，也可以使用“随机体验”选项。

## 您应何时选择 [!UICONTROL 自动定位] over [!UICONTROL Automated Personalization]? {#section_BBC4871C87944DD7A8B925811A30C633}

在以下几种情况中，您可能会希望使用 [!UICONTROL 自动定位] over [!UICONTROL Automated Personalization]:

* 如果您想定义整个体验，而不是单个选件（各选件会自动结合形成一个体验）。
* 如果要使用 [!UICONTROL 可视化体验编辑器] (VEC)不受支持的功能 [!UICONTROL 自动个性化]:自定义代码编辑器、多个体验受众，等等。
* 如果您想在不同的体验中对页面进行结构性更改。例如，如果要重新排列主页上的元素， [!UICONTROL 自动定位] 比 [!UICONTROL Automated Personalization].

## 功能 [!UICONTROL 自动定位] 与 [!UICONTROL Automated Personalization]? {#section_2A601F482F9A44E38D4B694668711319}

### 算法会对每次访问进行优化以获得有利的结果。

* 算法可预测访客的转化倾向（或来自转化的预计收入）以提供最佳体验。
* 现有会话结束后，访客有资格获得新体验（除非该访客位于控制组中，在这种情况下，在首次访问时分配给该访客的体验对于后续访问将保持不变）。
* 在会话中，预测不会更改，以保持可视一致性。

### 算法会根据访客行为的变化自行调整。

* 多臂老虎机可确保模型始终“花费”少量流量，以便在活动学习的整个生命周期中继续学习，并防止过度利用以前学到的趋势。
* 基础模型每24小时使用最新的访客行为数据重建一次，以确保 [!DNL Target] 始终在利用不断变化的访客偏好。
* 如果该算法无法为个人用户确定入选体验，则会自动切换为显示总体性能最佳的体验，同时仍继续查找个性化入选者。使用[汤普森采样](https://en.wikipedia.org/wiki/Thompson_sampling)查找性能最佳的体验。

### 算法会针对单个目标量度不断进行优化。

* 此量度可以基于转化，也可以基于收入（具体而言） [!UICONTROL 每次访问收入])。

### [!DNL Target] 会自动收集关于访客的信息来构建个性化模型。

* 有关[!UICONTROL 自动定位]和自动个性化中使用的参数的更多信息，请参阅[自动个性化数据收集](/help/main/c-activities/t-automated-personalization/ap-data.md)。

### [!DNL Target][!DNL Adobe Experience Cloud] 会自动使用所有 共享受众来构建个性化模型。

* 您无需执行任何特定操作来将受众添加到模型中。有关使用 [!DNL Experience Cloud Audiences] with [!DNL Target]，请参阅 [Experience Cloud受众](/help/main/c-integrating-target-with-mac/mmp.md)

### 营销人员可以上传离线数据、倾向得分或其他自定义数据来构建个性化模型。

* 了解更多有关[为自动定位和自动个性化上传数据[!UICONTROL 的信息。]](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md)

## 操作方法 [!UICONTROL 自动定位] 不同 [!UICONTROL Automated Personalization]? {#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

### 与自动个性化相比，自动定位通常需要较少的流量即可构建个性化模型。

尽管构建自动定位或自动个性化模型所需的&#x200B;*每个体验*&#x200B;的流量数量相同，但自动个性化活动中的体验通常多于自动定位活动中的体验。

例如，如果您的 [!UICONTROL 自动个性化] 在活动中，您已通过两个位置为每个位置创建了两个选件，则该活动中将共包含四个(2 = 4)体验（不含排除项）。 在使用[!UICONTROL 自动定位]时，您可以将体验 1 设置为在位置 1 中包含选件 1，在位置 2 中包含选件 2，将体验 2 设置为在位置 1 中包含选件 1，在位置 2 中包含选件 2。由于[!UICONTROL 自动定位]允许您选择在一个体验中进行多次更改，因此您可以减少活动中的体验总数。

对于[!UICONTROL 自动定位]，可以使用简单的经验规则来了解流量要求：

* **当“转化”是您的成功量度时：**&#x200B;每个体验每天有 1,000 次访问和至少 50 次转化，此外，该活动至少需要 7,000 次访问和 350 次转化。
* **当“每次访问带来的收入”(RPV) 是您的成功量度时：**&#x200B;每个体验每天有 1,000 次访问和至少 50 次转化，此外，该活动的每个体验必须至少有 1,000 次转化。RPV 通常需要更多的数据才能构建模型，这是因为与转化率相比，访问收入通常存在着较大的数据差异。

### 自动定位具有全面的设置功能。

* 因为 [!UICONTROL 自动定位] 嵌入在A/B活动工作流中， [!UICONTROL 自动定位] 从更成熟和成熟的 [!UICONTROL 可视化体验编辑器] (VEC)。 您还可以使用 [QA链接](/help/main/c-activities/c-activity-qa/activity-qa.md) with [!UICONTROL 自动定位].

### 自动定位提供广泛的在线测试框架。

* 多臂老虎机是更大的在线测试框架的一部分，该框架允许 [!DNL Adobe] 数据科学家和研究人员，了解他们在真实环境中不断改进的益处。
* 将来，这个试验台将允许我们打开 [!DNL Adobe] 向精通数据的客户提供机器学习平台，以便他们能够引入自己的模型来扩充 [!DNL Target] 模型。

## 报表和[!UICONTROL 自动定位] {#section_42EE7F5E65E84F89A872FE9921917F76}

有关更多信息，请参阅 [报表和自动定位](/help/main/c-activities/auto-target/reporting-and-auto-target.md).

## 培训视频：了解自动定位活动 ![概述徽章](/help/main/assets/overview.png)

本视频介绍了如何设置[!UICONTROL 自动定位] A/B 活动。

完成此培训后，您应该能够：

* 定义[!UICONTROL 自动定位]测试
* 将[!UICONTROL 自动定位][!UICONTROL 与自动个性化进行比较和对比]
* 创建[!UICONTROL 自动定位]活动

>[!VIDEO](https://video.tv.adobe.com/v/18558)
