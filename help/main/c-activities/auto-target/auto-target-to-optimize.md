---
keywords: 自动定位；定位；流量分配；常见问题；faq；故障诊断；故障排除
description: 了解[!UICONTROL 自动定位]活动如何根据客户个人资料和类似访客的行为，为每位访客提供量身定制的体验。
title: 什么是[!UICONTROL 自动定位]活动？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Auto-Target
exl-id: 59ca30dc-45a0-4129-b832-84e1132d3b69
TQID: 'https://experienceleague.adobe.com/uKmfIlOcT-tZgOjuvERXuif-Y5-2Jw3prtPbuBjv1is'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: fff07a91-d479-45f4-ae95-9762e79b1b7c
    internal-label: Shared audiences
  - id: db15a02f-03cd-46fe-a53e-02064cdeadfa
    internal-label: Auto target
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
    internal-label: Customer profiles
source-git-commit: 878df20c7fb08c893239135c20f358b5606d0c6f
workflow-type: tm+mt
source-wordcount: '2070'
ht-degree: 12%
---
# [!UICONTROL 自动定位]概述 {#auto-target-overview}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解&#x200B;**[!UICONTROL 自动定位]**&#x200B;活动如何向每位访客提供量身定制的体验、工作原理、流量分配选择以及与&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;的比较。

>[!ENDSHADEBOX]

[!DNL Adobe Target]中的&#x200B;**[!UICONTROL 自动定位]**&#x200B;活动使用高级机器学习从多个高性能、营销人员定义的体验中进行选择，以便个性化内容并促进转化。 **[!UICONTROL 自动定位]**&#x200B;根据每位访客的个人客户配置文件和具有相似配置文件的先前访客的行为，为每位访客提供量身定制的体验。

>[!NOTE]
>
>* **[!UICONTROL 自动定位]**&#x200B;作为[!DNL Target Premium]解决方案的一部分提供。 如果没有 [!DNL Target Premium] 许可证，则此功能在 [!DNL Target Standard] 中不可用。 有关此许可证提供的各项高级功能的更多信息，请参阅 [Target Premium](/help/main/c-intro/intro.md)。
>
>* **[!UICONTROL Analytics for Target]** (A4T)支持&#x200B;**[!UICONTROL 自动定位]**&#x200B;活动。 有关详细信息，请参阅自动分配和自动定位活动支持[A4T](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)。

使用三步引导式工作流[创建A/B活动](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)时，请在&#x200B;**[!UICONTROL 定位]**&#x200B;页面上选择&#x200B;**[!UICONTROL 自动定位以提供个性化体验]**&#x200B;选项（步骤2）。 有关步骤，请参阅[创建自动定位活动](/help/main/c-activities/auto-target/create-auto-target.md)。

![流量分配方法设置](/help/main/c-activities/automated-traffic-allocation/assets/auto-target.png)

通过A/B活动流程中的此选项，可使用机器学习技术根据营销人员定义的一组体验通过一次单击对内容进行个性化。 与传统A/B测试或&#x200B;**[!UICONTROL 自动分配]**&#x200B;相比，**[!UICONTROL 自动定位]**&#x200B;旨在通过确定为每个访客显示哪个体验来实现最大程度的优化。 与目标是找到一个入选者的A/B活动不同，**[!UICONTROL 自动定位]**&#x200B;会自动确定适用于给定访客的最佳体验。 最佳体验基于访客个人资料和其他上下文信息。

与&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;类似，**[!UICONTROL 自动定位]**&#x200B;使用[随机林算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)（一种领先的数据科学组合方法）来确定要向访客显示的最佳体验。 **[!UICONTROL 自动定位]**&#x200B;可以适应访客行为的变化，因此它可以一直运行以实现提升。 此方法有时称为“始终运行”模式。

与A/B活动不同，A/B活动为给定访客分配的体验是具有粘性的，**[!UICONTROL 自动定位]**&#x200B;会优化每次访问的指定业务目标。 与&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;一样，**[!UICONTROL 自动定位]**&#x200B;默认情况下将部分活动流量保留为控制组以测量提升。 在活动中，控制组的访客会得到随机体验。

## 注意事项 {#considerations}

使用&#x200B;**[!UICONTROL 自动定位]**&#x200B;时请记住以下几点：

* 请注意活动形状。 与原始体验计数相比，性能更多地取决于位置×选件的数量。 大型笛卡尔组合可能会减慢&#x200B;**[!UICONTROL 可视化体验编辑器]**&#x200B;中的加载和编辑速度，即使低于记录的体验限制也是如此。

  作为最佳实践，请将&#x200B;**[!UICONTROL 自动定位]**&#x200B;和&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动保留到4-6个位置，每个位置具有4-6个选件。 不建议使用较大的配置。 这些活动直接在&#x200B;**[!UICONTROL 体验]**&#x200B;步骤中构建，因此，当配置超出支持的阈值时，[!DNL Target] UI可能会显示内联警告或阻止保存。

* 您不能将特定活动从&#x200B;**[!UICONTROL 自动定位]**&#x200B;切换到&#x200B;**[!UICONTROL Automated Personalization]**，反之亦然。
* 将活动另存为草稿后，您无法从&#x200B;**[!UICONTROL 手动]**&#x200B;流量分配（传统&#x200B;**[!UICONTROL A/B测试]**）切换到&#x200B;**[!UICONTROL 自动定位]**，反之亦然。
* 我们构建了一个模型，用来识别个性化策略相对于随机提供流量的表现，以及如何将所有流量发送到整个入选体验。 此模型仅考虑默认环境中的点击和转化。

  为每个建模组(AP)或体验(AT)构建第二组模型。 对于这些模型中的每一个，都会考虑所有环境中的点击量和转化量。

  无论环境如何，使用相同的模型为请求提供服务。 但是，多个流量应来自默认环境，以确保标识的整体入选体验与真实世界行为一致。

* 至少使用两个体验。

## 术语 {#section_A309B7E0B258467789A5CACDC1D923F3}

讨论&#x200B;**[!UICONTROL 自动定位]**&#x200B;时，以下术语很有用：

| 术语 | 定义 |
|---|---|
| [多臂老虎机](https://en.wikipedia.org/wiki/Multi-armed_bandit){target=_blank} | 多臂老虎机优化方法可在探索式学习和对该学习的利用之间进行平衡。 |
| [随机森林](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | 随机林是一种领先的机器学习方法。 在数据科学术语中，它是一种集成分类方法，或回归方法，通过基于访客和访问属性构建许多决策树来工作。 在[!DNL Target]内，随机林用于确定哪个体验对于每个特定访客具有最高的转化可能性（或每次访问的最高收入）。 |
| [汤普森采样](https://en.wikipedia.org/wiki/Thompson_sampling){target=_blank} | 汤普森采样的目标是确定哪个体验是最佳的整体（非个性化）体验，同时最大限度地降低找到该体验的“成本”。 汤普森取样始终挑选入选者，即使两个体验之间没有统计上的差异。 |

## [!UICONTROL 自动定位]的工作方式 {#section_77240E2DEB7D4CD89F52BE0A85E20136}

以下页面描述了基础&#x200B;**[!UICONTROL 自动定位]**&#x200B;和&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;的数据和算法：

| 主题 | 详细信息 |
|--- |--- |
| [随机林算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | 在&#x200B;**[!UICONTROL 自动定位]**&#x200B;和&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;中使用的[!DNL Target]的主要个性化算法是随机林。 集成方法（如随机森林）使用多种学习算法以获得比任何组成学习算法都更好的预测性能。 **[!UICONTROL Automated Personalization]**&#x200B;和&#x200B;**[!UICONTROL 自动定位]**&#x200B;活动中的随机林算法是一种分类或回归方法，它通过在训练时构造大量决策树来运行。 |
| [正在上传 [!DNL Target] Personalization算法](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md)的数据 | 有几种方法可以为&#x200B;**[!UICONTROL 自动定位]**&#x200B;和&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;模型输入数据。 |
| [针对 [!DNL Target] Personalization算法的数据收集](/help/main/c-activities/t-automated-personalization/ap-data.md) | [!DNL Target]的个性化算法会自动收集各种数据。 |

## 确定流量分配 {#section_AB3656F71D2D4C67A55A24B38092958F}

根据活动的目标，您可以在控制和个性化体验之间选择不同的流量分配。 最佳实践是在活动开始之前确定此目标。

“**[!UICONTROL 自定义分配]**”下拉列表可让您从以下选项中进行选择：

* **[!UICONTROL 评估Personalization算法(50/50)]**
* **[!UICONTROL 最大化Personalization流量(90/10)]**
* **[!UICONTROL 自定义分配]**

![“分配目标”下拉列表](/help/main/c-activities/assets/split-new-ui.png)

下表说明了三个选项：

| 活动目标 | 建议的流量分配 | 权衡 |
|--- |--- |--- |
| **[!UICONTROL 评估个性化算法 (50/50)]**：如果您的目标是测试算法，则可以在控制和目标算法之间按 50/50 的百分比拆分访客。 这种拆分可让您对提升进行最精确的评估。 建议将“随机体验”用作控制。 | 按 50% 控制体验/ 50% 个性化体验进行拆分 | <ul><li>最大限度地提高控制体验和个性化体验之间提升度的准确性</li><li>具有个性化体验的访客相对较少</li></ul> |
| **[!UICONTROL 最大化Personalization流量(90/10)]**：如果您的目标是创建“一直开启”的活动，则可以在控制中放入10%的访客，以确保算法有足够的数据来不断学习。 这里做出的权衡是，为了对更大比例的流量进行个性化，提升度的准确性将会降低。 无论您的目标如何，在使用特定体验作为控制时，都建议按此比例拆分流量。 | 最佳实践是使用 10% - 30% 控制体验 / 70% - 90% 个性化体验的拆分方式 | <ul><li>最大限度地增加具有个性化体验的访客数量</li><li>最大化提升度</li><li>对于该活动具有的提升度，准确度较低</li></ul> |
| **[!UICONTROL 自定义分配]** | 根据需要手动拆分百分比。 | <ul><li>您可能无法获得所需的结果。 如果您不确定，请按照上述任一选项的建议进行操作</li></ul> |

要调整&#x200B;**[!UICONTROL 控制]**&#x200B;百分比，请单击&#x200B;**[!UICONTROL 流量分配]**&#x200B;窗格中的&#x200B;**[!UICONTROL 体验]**，然后根据需要调整百分比。 您不能将控制组降至 10% 以下。

您可以[选择特定体验作为控制](/help/main/c-activities/t-automated-personalization/experience-as-control.md)，也可以使用&#x200B;**[!UICONTROL 随机体验]**&#x200B;选项。

## 比较[!UICONTROL 自动定位]和[!UICONTROL Automated Personalization] {#compare-at-ap}

**[!UICONTROL 自动定位]**&#x200B;和&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;共享相同的算法和数据，但在如何构建体验以及模型所需的流量方面有所不同。

### 这两种活动类型的共同之处 {#section_2A601F482F9A44E38D4B694668711319}

* 每次访问的&#x200B;**优化。** 该算法预测访客进行转化的倾向（或转化的估计收入）以提供最佳体验。 访客有资格在现有会话结束时获得新体验。 但控制组中的访客除外，该访客保留在首次访问时分配的体验。 在会话内，预测不会更改，以保持视觉一致性。
* **适应访客行为的变化。** 多臂老虎机始终“花费”一小部分流量以在活动期间继续学习，并防止过度利用以前学习到的趋势。 使用最新的访客行为数据每24小时重建一次基础模型。 如果算法无法确定个人的入选体验，它会自动切换到显示使用[汤普森采样](https://en.wikipedia.org/wiki/Thompson_sampling)找到的总体性能最佳的体验，同时继续查找个性化入选者。
* **单个目标量度。** 算法会不断针对一个量度进行优化，该量度可以基于转化，也可以基于收入（更具体地说，每次访问产生&#x200B;**[!UICONTROL 收入]**）。
* **自动数据收集。** [!DNL Target]自动收集关于访客的信息以构建个性化模型。 有关所用参数的详细信息，请参阅[Automated Personalization数据收集](/help/main/c-activities/t-automated-personalization/ap-data.md)。
* **共享受众。** [!DNL Target]自动使用所有[!DNL Adobe Experience Cloud]共享受众来构建个性化模型。 您无需执行任何特定操作即可将受众添加到模型。 有关将 [!DNL Experience Cloud Audiences] 与 [!DNL Target] 配合使用的信息，请参阅 [Experience Cloud 受众](/help/main/c-integrating-target-with-mac/mmp.md)。
* **自定义数据。** 营销人员可以上传离线数据、倾向得分或其他自定义数据来构建个性化模型。 了解有关[为自动定位和Automated Personalization](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md)上传数据的更多信息。

### 这两种活动类型的差异 {#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

当您想要定义整个体验、使用全套&#x200B;**[!UICONTROL 可视化体验编辑器]** (VEC)功能或者对您的页面进行结构性更改时，请考虑&#x200B;**[!UICONTROL 自动定位]**，而不是&#x200B;**[!UICONTROL Automated Personalization]**。

| | [!UICONTROL Auto-Target（自动定位）] | [!UICONTROL 自动个性化] |
|---|---|---|
| **体验定义** | 您可以定义包含多项更改的整个体验。 | 单个选件会自动组合在一起以形成体验。 |
| **[!UICONTROL 可视化体验编辑器]功能** | **[!UICONTROL 自动定位]**&#x200B;嵌入到A/B活动工作流中，因此可以从更成熟且功能齐全的VEC中获益。 您还可以使用[QA链接](/help/main/c-activities/c-activity-qa/activity-qa.md)。 | 不支持自定义代码编辑器、多个体验受众和其他功能。 |
| **对页面的结构更改** | 更合适。 例如，您可以重新排列主页上的元素。 | 不太合适。 |
| **体验数** | 通常情况下，数量较少，因为一个体验可以包含多项更改。 | 通常更多，因为体验是选件和位置的所有组合。 |
| **生成模型所需的流量** | 通常总体较少。 | 通常总体而言更高。 |

两种活动类型中构建模型所需的每个体验&#x200B;*的流量*&#x200B;相同。 **[!UICONTROL 自动定位]**&#x200B;通常所需的总流量较少，因为它通常具有较少的体验。

例如，在每个位置有两个选件和两个位置的&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动中，该活动总计有四个(2 × 2 = 4)体验（不含排除项）。 在&#x200B;**[!UICONTROL 自动定位]**&#x200B;中，您可以将体验1设置为在位置1中包含选件1，在位置2中包含选件2，将体验2设置为在位置1中包含选件2，在位置2中包含选件1。 **[!UICONTROL 自动定位]**&#x200B;允许在一个体验中进行多项更改，因此您可以减少活动中的体验总数。

### [!UICONTROL 自动定位]的流量要求 {#traffic-requirements}

以下经验规则有助于了解流量要求：

* **当[!UICONTROL 转化]是您的成功量度时：** 1,000次访问，每个体验每天至少有50次转化。 此外，该活动必须至少具有7,000次访问和350次转化。
* **当[!UICONTROL 每次访问带来的收入]是您的成功量度时：** 1,000次访问，每个体验每天至少有50次转化。 此外，活动必须每个体验至少有1,000次转化。 **[!UICONTROL 每次访问带来的收入]**&#x200B;通常需要更多数据才能构建模型，因为访问收入中的差异通常高于转化率。

**[!UICONTROL 自动定位]**&#x200B;还提供广泛的联机测试框架。 多臂老虎机是更大的在线测试框架的一部分，该框架允许[!DNL Adobe]数据科学家和研究人员了解其在真实世界条件下的持续改进的好处。 将来，此测试台将允许[!DNL Adobe]向数据精通的客户打开其机器学习平台，以便他们能够引入自己的模型来增强[!DNL Target]模型。

有关报告的详细信息，请参阅[报告和自动定位](/help/main/c-activities/auto-target/reporting-and-auto-target.md)。
