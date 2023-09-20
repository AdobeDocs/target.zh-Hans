---
keywords: 故障诊断；常见问题解答；FAQ；自动个性化；控制；默认体验；最佳实践
description: 探索常见问题(FAQ)及其答案的列表 [!UICONTROL Automated Personalization] (AP)中的活动 [!UICONTROL Adobe Target].
title: 如何查找关于的常见问题解答 [!UICONTROL Automated Personalization] 活动？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="请参阅Target Premium中包含的内容。"
feature: Automated Personalization
exl-id: 2bf62cc1-1781-4021-a400-2884e0bae893
source-git-commit: 336da9dd876243a0eea662b4604a8fc1e6a69b1a
workflow-type: tm+mt
source-wordcount: '2054'
ht-degree: 24%

---

# Automated Personalization 常见问题

在使用时，可查阅以下常见问题和答案 [!UICONTROL Automated Personalization] 中的活动 [!DNL Adobe Target].

## 我是否可以指定特定体验来作为中的控制 [!UICONTROL Automated Personalization] 活动？

+++查看详细信息

在创建体验时，您可以选择要用作控制的体验 [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP)或 [自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT)活动。

通过此功能，您可以根据活动中配置的流量分配百分比，将整个控制流量路由到特定体验。然后，您可以根据该体验的控制流量评估个性化流量的性能报表。

有关更多信息，请参阅[使用特定体验作为控制](/help/main/c-activities/t-automated-personalization/experience-as-control.md)。

+++

## 如何进行比较 [!UICONTROL Automated Personalization] 默认体验？ {#section_46C1A620A2384C2C8392D6716DD18495}

+++查看详细信息

没有用于比较的按键选项 [!UICONTROL Automated Personalization] 默认体验。 但是，作为解决方法，如果整个活动中存在默认选件或体验，要了解其基线性能，请单击“[!UICONTROL 控件]”区段，并在生成的选件级别报表中查找该特定选件。 此选件记录的转化率可用于与整个“随机林”区段的会话率进行比较。 这有助于将其运行情况与默认选件进行比较。

+++

## 设置的最佳实践是什么 [!UICONTROL Automated Personalization] 活动？ {#section_E155B26282BE49B58EA2683413D11DE6}

+++查看详细信息

* 如果要使低流量页面个性化，或者希望对要个性化的体验进行结构性更改，请考虑使用 [!UICONTROL 自动定位] 活动取代 [!UICONTROL Automated Personalization]. 请参阅 [自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md).
* 考虑完成 [!UICONTROL A/B测试] 您计划在中使用的选件和位置之间的活动 [!UICONTROL Automated Personalization] 活动，以确保位置和选件会对优化目标产生影响。 如果 [!UICONTROL A/B测试] 活动未能显示显着差异， [!UICONTROL Automated Personalization] 也可能无法生成提升。

   * 如果A/B...N测试显示体验之间没有统计学上的显着差异，则可能是以下一种或多种情况造成的：

      * 这些选件可能彼此差别不大。
      * 您选择的位置不会影响成功量度。
      * 转化漏斗中的优化目标过大，无法受所选选件的影响。

* 确保使用 [流量估算器](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) 因此，您可以了解在中构建个性化模型需要多长时间。 [!UICONTROL Automated Personalization] 活动。
* 在开始活动之前，根据您的目标，确定控制与目标之间的分配。

  根据活动的目标和您选择的控制类型，可以考虑以下三种方案：

   * **将随机体验作为控制，且活动目标是测试个性化算法的有效性**：如果您的目标是评估个性化算法，则希望更准确地了解提升度。 此外，如果您只执行了 [!UICONTROL A/B测试] （随机提供的控制）。 在这种情况下，建议向随机提供体验的控制分配 50% 的流量。
   * **将随机体验作为控制，且活动目标是最大化个性化流量**：如果您习惯使用算法并希望最大化个性化流量，则建议向控制分配10%到30%的流量。 这里做出的权衡是您在提升度信息中看到的准确性。 控制流量的置信区间更大，因为流向它们的流量更少。
   * **将特定体验作为控制，且采用任一目标类型**：如果您要将特定营销人员驱动的体验与个性化模型相比较，那么建议向控制分配 10% 到 30% 的流量。仅选择一个体验作为控制时，该流量不会分布到活动中的每个选件或体验。

* 应尽可能谨慎地使用定位规则，因为它们可能会干扰模型的优化能力。
* 报表组可以限制您的报表包的成功 [!UICONTROL Automated Personalization] 活动。 仅在特定条件下使用报表组：

   * 仅在满足以下条件时才使用报表组：

      * 您计划在活动运行时替换或添加新选件。
      * 报表组中的选件对同一访客很有吸引力。
      * 该报表组中的选件具有大致相同的整体响应率。

   * 报表组中的选件之间不进行个性化。个性化模型会将所有选件视为相同内容。
   * 切勿将一个活动中的所有选件都放到一个报表组中。这样做会导致向活动中的所有访客均匀随机提供所有选件。

+++

## 有哪些限制 [!UICONTROL Automated Personalization]？ {#section_08BA09ED51B547299963C94FE6417CFA}

+++查看详细信息

[!DNL Target] 具有 30,000 个体验的硬限制，但在创建的体验少于 10,000 个时，它的效果最佳。

即使活动启用了 [!UICONTROL 不允许重复项] 选项。

有关影响中活动和其他元素的字符限制和其他限制（选件大小、受众、配置文件、值、参数等）的更多信息 [!DNL Target]，请参见 [限制](/help/main/r-troubleshooting-target/target-limits.md).

+++

## 如何实施选件级别的定位？ {#section_9D7A86EA93D74E9B8C81072A681263A4}

+++查看详细信息

当每个访客到达时，该访客可以看到的一组可能的选件取决于选件级别的定位规则。然后，算法从这些选件中选择模型预测的具有最佳预期收入或转化机会的选件。 选件定位会影响的效力 [!DNL Target] 因此，机器学习算法以及应该尽可能少地使用。

+++

## 为什么我的 [!UICONTROL Automated Personalization] 活动未显示提升？ {#section_BFA07C8C258F45318F73A461B8F32737}

+++查看详细信息

一个环境需要四个因素 [!UICONTROL Automated Personalization] 用于生成提升度的活动：

* 每个位置中的选件必须足够不同，才能影响访客。
* 这些位置必须位于对优化目标有所影响的位置。
* 在活动中必须具有足够的流量和统计功效才能检测到提升。
* 个性化算法必须运行良好。

最好的做法是首先通过简单的非个性化设置，确保构成活动体验的内容和位置对整体响应率真正发挥了作用 [!UICONTROL A/B测试] 活动。 务必提前计算样本量，以确保有足够的样本以便看到合理的提升，并在一段固定的时间内运行 A/B 测试，且不要终止或对其进行任何更改。如果A/B测试结果显示一个或多个体验在统计上显着提升，则个性化活动可能会成功。 即使体验的总体响应率没有差异，个性化也可以正常工作。 通常，问题源于选件或位置对优化目标的影响不足以被检测出具有统计显着性的情况。

有关更多信息，请参阅[自动个性化故障诊断](/help/main/c-activities/t-automated-personalization/ap-trouble.md#reference_281954549C3E49E2B5498009BBDC62CA)。

+++

## 如何 [!UICONTROL Automated Personalization] 分配我的活动流量？ {#section_4369364F77804E0D9B78BEE551DA5659}

+++查看详细信息

自动个性化会根据为每个模型构建的最新[随机林](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)模型，将访客路由到具有最高预测成功量度的体验。这种预测是基于访客的具体信息和访问环境。

例如，假设 [!UICONTROL Automated Personalization] 活动有两个位置，每个位置提供两个选件。 在第一个位置中，对于某位特定访客，选件 A 的预测转化率为 3%，而选件 B 的预测转化率为 1%。在第二个位置中，对于同一访客，选件 C 的预测转化率为 2%，而选件 D 的预测转化率为 5%。因此， [!UICONTROL Automated Personalization] 为该访客提供具有选件A和选件D的体验。

+++

## 我何时应该停止我的 [!UICONTROL Automated Personalization] 活动？ {#section_C51F3DAB8887463BB147373F6FE06B93}

+++查看详细信息

[!UICONTROL Automated Personalization] 可以作为“始终运行”的个性化使用，不断进行优化。 特别是对于一直使用的内容，无需停止 [!UICONTROL Automated Personalization] 活动。 如果您希望对内容进行重大更改，而这些更改与当前您在中的选件不同 [!UICONTROL Automated Personalization] 活动，最佳实践是开始新活动。 启动新活动有助于其他用户查看报表，以免将过去的结果与不同内容混淆或联系起来。

+++

## 我需要等待多久才能构建模型？ {#section_6F6A5A9DB3564BE6B22FFEDFA5B29619}

+++查看详细信息

在活动中构建模型的时间通常取决于流向所选活动位置的流量和活动成功量度。 使用 [流量估算器](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) 以确定在您的活动中构建模型预计所需的时间。

+++

## 我的团队中已构建一个模型， [!UICONTROL Automated Personalization] 活动。 对该体验的访问是否为个性化的？ {#section_51EA953C6D1D4A3185FC9DD290D66621}

+++查看详细信息

不是，必须在活动中至少构建 2 个模型才能开始个性化。

+++

## 我何时可以查看我的测试结果 [!UICONTROL Automated Personalization] 活动？ {#section_05DB5ACAE6AD429C9510766A7268EE2C}

+++查看详细信息

您可以开始查看的结果 [!UICONTROL Automated Personalization] 活动，适用于至少有两个体验已构建模型（绿色复选标记）且已构建模型的体验。

+++

## 如何缩短在中构建模型所需的时间？ [!UICONTROL Automated Personalization] 活动？ {#section_CCB8CEE98DAA40BA93AADCD596C48D82}

+++查看详细信息

查看活动设置，了解是否愿意进行任何更改以提高构建模型的速度。

* 您的成功量度在活动体验的销售漏斗中是否位于较远的位置？由于存在最低转化次数要求，较低的活动转化率会提高构建模型所需的流量要求。
* 如果成功量度是设为 RPV，那么您是否可以改用转化作为成功量度？转化活动需要用来构建模型的流量通常较少。
* 是否有一些体验可从活动中删除？ 减少活动中的体验数量可缩短构建模型的时间。
* 是否有更高流量的页面可让此活动更成功？ 活动位置的流量和转化越多，模型构建的速度就越快。

+++

## 访客为何会查看的体验 [!UICONTROL Automated Personalization] 他们不应该看到的活动？ {#section_41CECEAE0881446A8D9F3B016857914B}

+++查看详细信息

[!UICONTROL 自动个性化活动会在每次会话中都进行一次评估。]如果存在符合特定体验条件的活动会话，且现在已有新选件添加到该会话，则访客将看到新内容以及之前显示的选件。 由于这些访客之前符合这些体验的资格，因此他们仍会在会话期间看到这些体验。 要在每次访问页面时对此进行评估，您应将更改为 [!UICONTROL 体验定位] (XT)活动类型。

+++

## 能否在中途更改目标指标？ [!UICONTROL Automated Personalization] 活动？ {#change-metric}

+++查看详细信息

[!DNL Adobe] 不建议您在活动中途更改目标指标。 虽然可在活动期间使用 [!DNL Target] UI 更改目标指标，但总是应开始新的活动。[!DNL Adobe] 如果在活动运行后更改其中的目标量度，则不保证将发生什么情况。

此建议适用于使用 [!DNL Target] 或 [!DNL Analytics] (A4T) 作为报表源的[!UICONTROL 自动分配]、[!UICONTROL 自动定位]和[!UICONTROL 自动个性化]活动。

+++

## 我可以使用 [!UICONTROL 重置报表数据] 选项 [!UICONTROL Automated Personalization] 活动？

+++查看详细信息

[!DNL Adobe] 不建议使用 [!UICONTROL 重置报表数据] 选项 [!UICONTROL Automated Personalization] 活动。 虽然它删除可见的报表数据，但此选项并不从 [!UICONTROL Automated Personalization] 模型。 不要使用 [!UICONTROL 重置报表数据] 选项 [!UICONTROL Automated Personalization] 活动，创建新活动并取消激活原始活动。 本指导还适用于 [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位] 活动。

+++

## 如何 [!UICONTROL Automated Personalization] 是否构建有关环境的模型？

+++查看详细信息

我们构建了一个模型，用来识别个性化策略相对于随机提供流量的表现，以及如何将所有流量发送到整个入选体验。 此模型仅考虑默认环境中的点击和转化。

为每个建模组构建来自第二组模型的流量([!UICONTROL Automated Personalization])或体验([!UICONTROL 自动定位])。 对于这些模型中的每一个，都会考虑所有环境中的点击量和转化量。

因此，无论环境如何，都将使用相同的模型为请求提供服务。 但是，多个流量应来自默认环境，以确保标识的整体入选体验与真实世界行为一致。

+++
