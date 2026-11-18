---
keywords: 故障诊断；常见问题解答；FAQ；自动个性化；控制；默认体验；最佳实践
description: 在[!UICONTROL Adobe Target]中浏览有关[!UICONTROL Automated Personalization] (AP)活动的常见问题解答(FAQ)和答案列表。
title: 如何查找有关[!UICONTROL Automated Personalization]活动的常见问题解答？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Automated Personalization
exl-id: 2bf62cc1-1781-4021-a400-2884e0bae893
TQID: 'https://experienceleague.adobe.com/cYdFwvkJDlfGYdcxql9iWGwNiTed4Lb2kC7JdN7xgdo'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '2088'
ht-degree: 6%
---
# Automated Personalization常见问题解答 {#ap-faq}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;查找有关&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动的常见问题解答。

>[!ENDSHADEBOX]

以下问题和答案涵盖如何在[!DNL Adobe Target]中设置&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动、如何构建个性化模型、如何分配流量以及如何读取结果。

## 设置活动 {#set-up-an-activity}

+++ 设置[!UICONTROL Automated Personalization]活动的最佳实践是什么？

* 请密切关注&#x200B;*活动形状*（位置数量×选件数量），而不仅仅是体验总数。 位置和选件的笛卡尔组合对创作时间性能的影响大于原始体验数。 为获得最佳性能和可管理性，请将&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;和&#x200B;**[!UICONTROL 自动定位]**&#x200B;活动限制为4-6个位置，每个位置提供4-6个选件，如“Automated Personalization有哪些限制？”问题中所述。 在此部分中。 不建议使用较大的配置，这可能会导致在&#x200B;**[!UICONTROL 可视化体验编辑器]**&#x200B;中加载或编辑缓慢。
* 若要个性化较低流量的页面，或对要个性化的体验进行结构性更改，请考虑使用[**[!UICONTROL 自动定位&#x200B;]**&#x200B;活动](/help/main/c-activities/auto-target/auto-target-to-optimize.md)，而不是&#x200B;**[!UICONTROL &#x200B; Automated Personalization &#x200B;]**。
* 请考虑在您计划于&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动中使用的选件和位置之间运行&#x200B;**[!UICONTROL A/B测试]**&#x200B;活动，以确认位置和选件对优化目标有影响。 如果&#x200B;**[!UICONTROL A/B测试]**&#x200B;活动未能显示显着差异，则&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;可能也无法生成提升。

  如果A/B...N测试显示体验之间没有统计学上的显着差异，则可能是以下一种或多种情况造成的：

  * 这些选件可能彼此差别不大。
  * 您选择的位置不会影响成功量度。
  * 优化目标在转化funnel中太远，无法受到所选选件的影响。

* 使用[流量估算器](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#use-traffic-estimator)了解在&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动中构建个性化模型需要多长时间。
* 在开始活动之前，根据您的目标，确定控制与目标流量之间的分配。 下表列出了根据活动目标和所选控制类型考虑的三种方案。

  | 控制和活动目标 | 建议的控制分配 | 详细信息 |
  | --- | --- | --- |
  | **[!UICONTROL 随机体验]**&#x200B;作为控制，目标是测试个性化算法的有效性 | 50% | 此目标要求更准确地了解提升度。 您还很可能希望将体验或选件的转化率与简单&#x200B;**[!UICONTROL A/B测试]**（随机提供的控制）获得的转化率进行比较。 |
  | 将&#x200B;**[!UICONTROL 随机体验]**&#x200B;作为控制，目标是最大化个性化流量 | 10%到30% | 如果您熟悉算法并希望最大流量个性化，请使用此选项。 权衡因素是提升信息的准确性：控制流量的置信区间越大，流向控制流量的流量就越少。 |
  | 将&#x200B;**[!UICONTROL 特定体验]**&#x200B;作为控制，具有任一目标 | 10%到30% | 使用此选项可将特定营销人员驱动的体验与个性化模型进行比较。 仅选择一个体验作为控制时，该流量不会分布到活动中的每个选件或体验。 |

* 尽量少用定位规则，因为它们可能会干扰模型的优化能力。 有关更多信息，请参阅 [Target 自动个性化产品建议](/help/main/c-activities/t-automated-personalization/ap-target-offers.md)。
* 报表组可以限制&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动的成功，因此只能在特定条件下使用它们。 有关详细信息，请参阅[Automated Personalization中的选件报表组](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md)。

  * 仅当满足以下所有条件时，才使用报表组：

    * 您计划在活动运行时替换或添加选件。
    * 报表组中的选件对同一访客很有吸引力。
    * 报表组中的选件具有大致相同的整体响应率。

  * 报表组中的选件之间不进行个性化。 个性化模型会将所有选件视为相同。
  * 切勿将一个活动中的所有选件都放到一个报表组中。 这样做会导致向活动中的所有访客均匀随机提供所有选件。

+++

+++ [!UICONTROL Automated Personalization]中有哪些限制？

[!DNL Target]具有30,000个体验的硬性限制，但在创建少于10,000个体验时它可以正常工作。 当活动启用了&#x200B;**[!UICONTROL 不允许重复项]**&#x200B;选项时，也适用同样的限制。

虽然&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;和&#x200B;**[!UICONTROL 自动定位]**&#x200B;活动可以支持大量体验，但创作性能在很大程度上取决于&#x200B;*活动形状*（位置数×选件数）。 某些配置会创建大型笛卡尔组合，这些组合会显着影响负载和编辑性能，即使低于记录的体验限制也是如此。

为获得最佳性能和可管理性，请将&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;和&#x200B;**[!UICONTROL 自动定位]**&#x200B;活动限制为4-6个位置，每个位置提供4-6个选件。 不建议使用较大的配置，并且可能限制在[!DNL Target] UI中。

在当前[!DNL Target] UI中，**[!UICONTROL Automated Personalization]**&#x200B;和&#x200B;**[!UICONTROL 自动定位]**&#x200B;活动是直接在&#x200B;**[!UICONTROL 体验]**&#x200B;步骤中配置的。 当配置超出支持的阈值时，[!DNL Target]可能会显示内联警告或阻止您保存活动，并且会在&#x200B;**[!UICONTROL 下一个]**、**[!UICONTROL 保存]**&#x200B;和&#x200B;**[!UICONTROL 发布]**&#x200B;上重新验证活动形状。

有关影响[!DNL Target]中活动和其他元素的字符限制和其他限制（选件大小、受众、配置文件、值、参数等）的更多信息，请参阅[限制](/help/main/r-troubleshooting-target/target-limits.md)。

+++

+++ 能否指定特定体验以用作[!UICONTROL Automated Personalization]活动中的控制？

在创建[**[!UICONTROL Automated Personalization]**](/help/main/c-activities/t-automated-personalization/automated-personalization.md#automated-personalization-overview) (AP)或[**[!UICONTROL 自动定位]**](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT)活动时，您可以选择要用作控制的特定体验。

通过此功能，您可以根据活动中配置的流量分配百分比，将整个控制流量路由到该体验。 然后，您可以根据该体验的控制流量评估个性化流量的性能报表。

有关详细信息，请参阅[选择控制体验](/help/main/c-activities/t-automated-personalization/experience-as-control.md)。

+++

+++ 如何实施选件级别的定位？

当每个访客到达时，选件级别的定位规则将确定访客可以查看的选件集。 然后，算法从这些选件中选择模型预测的选件具有最佳预期收入或转化机会。 选件定位会影响[!DNL Target]机器学习算法的效率，因此请尽量谨慎使用。 有关更多信息，请参阅 [Target 自动个性化产品建议](/help/main/c-activities/t-automated-personalization/ap-target-offers.md)。

+++

## 模型构建和流量分配 {#models-and-traffic}

+++ [!UICONTROL Automated Personalization]如何分配我的活动流量？

**[!UICONTROL Automated Personalization]**&#x200B;根据最新的[随机林](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)模型，将访客路由到具有最高预测成功量度的体验。 此预测基于访客的特定信息和访问上下文。

例如，假设&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动具有两个位置，每个位置具有两个选件。 在第一个位置中，对于某位特定访客，选件 A 的预测转化率为 3%，而选件 B 的预测转化率为 1%。 在第二个位置中，对于同一访客，选件 C 的预测转化率为 2%，而选件 D 的预测转化率为 5%。 因此，**[!UICONTROL Automated Personalization]**&#x200B;通过选件A和选件D为该访客提供体验。

+++

+++ [!UICONTROL Automated Personalization]如何针对环境构建模型？

我们构建了一个模型，用来识别个性化策略相对于随机提供流量的表现，以及如何将所有流量发送到整个入选体验。 此模型仅考虑默认环境中的点击和转化。

为每个报表组(**[!UICONTROL Automated Personalization]**)或体验（**[!UICONTROL 自动定位]**）生成第二组模型。 对于这些模型中的每一个，都会考虑所有环境中的点击量和转化量。

因此，无论环境如何，都将使用相同的模型为请求提供服务。 但是，多个流量应来自默认环境，以确保标识的整体入选体验与真实世界行为一致。

+++

+++ 我需要等待多久才能构建模型？

在活动中构建模型的时间通常取决于流向所选活动位置的流量以及活动成功量度。 使用[流量估算器](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#use-traffic-estimator)确定在您的活动中构建模型预计所需的时间。

+++

+++ 如何缩短在[!UICONTROL Automated Personalization]活动中构建模型所需的时间？

查看活动设置，了解可提高模型构建速度的更改。 例如，将RPV成功量度更改为转化，在sales funnel中选择一个更接近您的活动体验的成功量度，从活动中删除一些体验，或使用流量较高的页面。 有关详细信息，请参阅[Automated Personalization疑难解答](/help/main/c-activities/t-automated-personalization/ap-trouble.md)。

+++

+++ 我的[!UICONTROL Automated Personalization]活动中已构建一个模型。 对该体验的访问是否为个性化的？

否. 必须在活动中至少构建两个模型，才能开始个性化。

+++

## 结果和提升 {#results-and-lift}

+++ 何时可以查看[!UICONTROL Automated Personalization]活动的结果？

在至少有两个体验已构建模型（以绿色复选标记指示）后，您就可以开始查看&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动的结果。

+++

+++ 为何我的[!UICONTROL Automated Personalization]活动未显示提升？

**[!UICONTROL Automated Personalization]**&#x200B;活动需要四个因素才能生成提升：

* 每个位置中的选件必须足够不同，才能影响访客。
* 位置必须位于对优化目标有所影响的位置。
* 在活动中必须具有足够的流量和统计功效才能检测到提升。
* 个性化算法必须运行良好。

最佳操作方法是首先通过使用简单的非个性化&#x200B;**[!UICONTROL A/B测试]**&#x200B;活动，确保构成该活动体验的内容和位置对整体响应率真正发挥了作用。 有关完整过程，请参阅[Automated Personalization疑难解答](/help/main/c-activities/t-automated-personalization/ap-trouble.md)。

+++

+++ 如何将[!UICONTROL Automated Personalization]与默认体验进行比较？

没有可将&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;与默认体验进行比较的全包选项。 作为解决方法，如果活动中存在默认选件或体验，请单击报表中的&#x200B;**[!UICONTROL 控制]**&#x200B;区段，然后在生成的选件级别报表中查找该选件。 此选件记录的转化率可与整个“随机林”区段的转化率进行比较。 此比较显示模型相对于默认选件的表现。

+++

## 管理实时活动 {#manage-live-activity}

+++ 我应何时停止[!UICONTROL Automated Personalization]活动？

**[!UICONTROL Automated Personalization]**&#x200B;可用作“始终运行”且不断优化的个性化设置。 特别是对于一直使用的内容，无需停止&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动。 如果您希望对内容进行重大更改，而这些更改与当前活动中的选件不同，则最佳实践是启动新活动。 开始新活动可帮助审阅报表的其他用户避免将过去的结果与不同内容混淆或相关联。

+++

+++ 能否在[!UICONTROL Automated Personalization]活动中途更改目标指标？

[!DNL Adobe]不建议您在活动中途更改目标指标。 尽管可以使用[!DNL Target] UI在活动期间更改目标量度，但始终改为启动新活动。 [!DNL Adobe]无法保证您在活动运行后更改其中的目标量度会发生什么情况。

此推荐适用于使用[!DNL Target]或[!DNL Analytics] (A4T)作为报表源的&#x200B;**[!UICONTROL 自动分配]**、**[!UICONTROL 自动定位]**&#x200B;和&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动。

+++

+++ 运行[!UICONTROL Automated Personalization]活动时能否使用[!UICONTROL 重置报表数据]选项？

[!DNL Adobe]不建议对&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动使用&#x200B;**[!UICONTROL 重置报表数据]**&#x200B;选项。 虽然它删除可见的报表数据，但此选项并不从&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;模型中删除所有训练记录。 不要使用&#x200B;**[!UICONTROL 重置报表数据]**&#x200B;选项，而要创建新活动并停用原始活动。 本指导还适用于&#x200B;**[!UICONTROL 自动分配]**&#x200B;和&#x200B;**[!UICONTROL 自动定位]**&#x200B;活动。

+++

+++ 为什么访客在[!UICONTROL Automated Personalization]活动中看到他们不应看到的体验？

每个会话评估一次&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动。 如果存在符合特定体验条件的活动会话，并且在该会话中添加了新选件，则访客将看到新内容以及之前显示的选件。 这些访客之前符合这些体验的资格，因此在会话期间他们仍会看到这些体验。 要在每次访问页面时评估活动，请更改为&#x200B;**[!UICONTROL 体验定位]** (XT)活动类型。

+++
