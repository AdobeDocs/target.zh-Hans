---
keywords: 自动定位;定位;流量分配;常见问题;常见问题;故障排除;故障排除;流量
description: 探索有关以下内容的故障排除主题和常见问题 [!UICONTROL 自动定位] 活动。
title: 如何排除故障 [!UICONTROL 自动定位] 活动？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="请参阅Target Premium中包含的内容。"
feature: Auto-Target
exl-id: 934f738e-560a-4847-9608-432ecfa2afe7
source-git-commit: 3e8c2d77f300bf0e2ca83a53d30e7b9eee48894e
workflow-type: tm+mt
source-wordcount: '1925'
ht-degree: 40%

---

# [!UICONTROL 自动定位] 常见问题解答和疑难解答

关于的故障排除和常见问题(FAQ) [!UICONTROL 自动定位] 中的活动 [!DNL Adobe Target].

## [!UICONTROL 自动定位常见问题解答] {#section_5C120A2B11D14D9BAF767BBAB50FED23}

在使用[!UICONTROL 自动定位]活动时，可查阅以下常见问题和答案：

### 设置[!UICONTROL 自动定位]活动的最佳实践是什么？

+++回答
* 决定业务价值 [!UICONTROL 每次访问的收入] (RPV)成功量度值得满足其他流量要求。 与转化相比，RPV 通常要求每个体验至少有 1,000 次转化才能完成工作。
* 开始活动之前，根据您的目标确定控制体验和个性化体验之间的流量分配。
* 确定您是否有足够的流量访问您的页面， [!UICONTROL 自动定位] 会运行活动，以便在合理的时间内构建个性化模型。
* 如果您正在测试个性化算法，则不应在活动开始时更改体验，也不应添加或删除用户档案属性。
* 考虑在您计划使用的选件和位置之间完成一个A/B活动 [!UICONTROL 自动定位] 活动，以确保位置和选件会对优化目标产生影响。 如果A/B活动未能显示显着差异， [!UICONTROL 自动定位] 也可能无法生成提升。

  如果 A/B 测试在体验之间没有显示出具有统计意义的显著差异，则意味着：您考虑使用的选件可能并不具备足够的差异，您选择的位置不会影响成功量度，或者优化目标位于转化漏斗中较远的位置，不会受到所选选件的影响。

* 尽量不要在活动期间对体验进行重大更改。

+++

### 是 [!UICONTROL Adobe] 您推荐使用 [!UICONTROL 自动定位] 以90（对照）/10（针对性）的分摊直到构建模型吗？

+++答案最优流量分配分摊取决于要实现的目标。

如果您的目标是使尽可能多的流量个性化，则可以在整个活动期内保持90%的目标分配和10%的控制。 如果您的目标是运行一项比较个性化算法与控制体验的实验，则50/50的分割比例最适合活动生命周期。

最佳实践是在整个活动期内保持流量分配分摊，这样访客就不会在针对性体验与对照体验之间切换。

<!-- 
### Do the check marks indicating a model is built for that experience update if the report date range changes?

No, check marks for model generation show only the models built to date. There's no way to go back and see when a model was completed.
-->

+++

### 如果访客这样做 **非** 请参见 [!UICONTROL 自动定位] 活动并转化，该转化是否会计入我的活动中？

+++答案否，仅限符合条件并查看了 [!UICONTROL 自动定位] 活动将被计入报表中。

+++

### 为什么我的 [!UICONTROL 自动定位] 活动似乎在带来任何提振。

+++回答： [!UICONTROL 自动定位] 用于生成提升度的活动：

* 选件必须足够不同，才能影响访客。
* 选件必须位于对优化目标有所影响的位置。
* 测试中必须有足够的流量和统计“功效”，才能检测到提升度。
* 个性化算法必须运行良好。

最好的做法是，首先使用简单、非个性化的 A/B 测试来确保组成活动体验的内容和位置对整体响应率真正地产生了影响。务必提前计算样本量，以确保有足够的样本以便看到合理的提升，并在一段固定的时间内运行 A/B 测试，且不要终止或对其进行任何更改。

如果 A/B 测试结果显示一个或多个体验具有统计意义上的显著提升，则个性化活动很可能会起作用。当然，即便体验的总体响应率没有差异，个性化也可能会起作用。通常，问题源于选件和位置对优化目标的影响不足以被检测出具有统计显着性的情况。

+++

### 我应何时停止[!UICONTROL 自动定位]活动？

+++回答
[!UICONTROL 自动定位] 可以作为“始终运行”的个性化使用，不断进行优化。 特别是对于一直使用的内容，无需停止[!UICONTROL 自动定位]活动。

如果您希望对 [!UICONTROL 自动定位] 活动，最佳实践是启动一个新活动，以便其他用户查看报表时不会将过去的结果与不同内容混淆或相关联。

+++

### 我需要等待多久才能构建模型？ {#how-long}

+++回答在 [!UICONTROL 自动定位] 活动通常取决于您选定活动位置的流量以及与活动成功量度关联的转化率。

[!UICONTROL 自动定位] 直到对于给定体验发生至少50次转化，才会尝试构建该体验的个性化模型。 此外，如果所构建的模型质量缺佳（通过对留出的“测试”数据进行离线评估而确定），则使用 [称为AUC的量度](https://en.wikipedia.org/wiki/Receiver_operating_characteristic#Area_under_the_curve))，模型不会用于以个性化方式提供流量。

关于[!UICONTROL 自动定位]的模型构建，还有如下几点要牢记：

* 活动上线后， [!UICONTROL 自动定位] 在尝试构建模型时，会考虑过去至多45天随机提供的数据。 例如，控制流量以及算法保留的一些额外的随机提供数据。
* 将[!UICONTROL 每次访问收入]作为成功指标时，这些活动一般需要更多数据才能构建模型，因为访问收入的数据偏差一般要比转化率的数据偏差高。
* 由于模型是根据体验构建的，因此将一种体验替换为另一种体验意味着必须为新体验收集足够的流量（至少50次转化），然后才能重建个性化模型。

+++

### 我的活动中已构建一个模型。对该体验的访问是否为个性化的？

+++答案否，您的活动中必须至少构建两个模型，才能开始个性化。

+++

### 我何时可以开始查看的结果 [!UICONTROL 自动定位] 活动？

+++答案您可以开始查看您的测试结果 [!UICONTROL 自动定位] 在至少有两个体验已构建模型（绿色复选标记）之后，针对已构建模型的体验进行测试。

+++

### 我可以指定特定体验作为控制吗？

+++答案您可以在创建体验时选择要用作控制的体验 [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP)或 [自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT)活动。

通过此功能，您可以根据活动中配置的流量分配百分比，将整个控制流量路由到特定体验。 然后，您可以根据该体验的控制流量评估个性化流量的性能报表。

有关更多信息，请参阅[使用特定体验作为控制](/help/main/c-activities/t-automated-personalization/experience-as-control.md)。

+++

### 能否在中途更改目标指标？ [!UICONTROL 自动定位] 活动？ {#change-metric}

+++回答Adobe不建议您在活动中途更改目标指标。 虽然可在活动期间使用 [!DNL Target] UI 更改目标指标，但总是应开始新的活动。如果在活动运行后更改其中的目标指标，则Adobe不保证会发生什么情况。

此建议适用于使用 [!DNL Target] 或 [!DNL Analytics] (A4T) 作为报表源的[!UICONTROL 自动分配]、[!UICONTROL 自动定位]和[!UICONTROL 自动个性化]活动。

+++

### 我可以使用 [!UICONTROL 重置报表数据] 选项 [!UICONTROL 自动定位] 活动？

+++使用 [!UICONTROL 重置报表数据] 选项 [!UICONTROL 自动定位] 不建议使用活动。 虽然它删除可见的报表数据，但此选项并不从[!UICONTROL 自动定位]模型中删除所有训练记录。不要对[!UICONTROL 自动定位]活动使用[!UICONTROL “重置报表数据”]选项，而是要创建新活动并停用原有活动。

本指导还适用于 [!UICONTROL 自动分配] 和 [!UICONTROL Automated Personalization] 活动。

+++

### 如果我从“ ”中删除单个体验，将发生什么情况 [!UICONTROL 自动定位] 活动？

+++回答
[!DNL Target] 针对每个体验构建一个模型，因此删除一个体验意味着 [!DNL Target] 减少构建一个模型，且不会影响其他体验的模型。

例如，假设您的[!UICONTROL 自动定位]活动有八个体验，而您不满意其中一个体验的表现。您可以删除该体验，这不会影响剩余七个体验的模型。

+++

## [!UICONTROL 自动定位]故障诊断 {#section_23995AB813F24525AF294D20A20875C8}

有时候，活动没有按预期进行。以下是您在使用时可能面临的一些潜在挑战 [!UICONTROL 自动定位] 并提出了一些解决方案。

### 在我的[!UICONTROL 自动定位]活动中，需要很长时间才能构建模型。

+++故障排除建议更改几项活动设置可以减少构建模型所需的预计时间，包括您的中的体验数量。 [!UICONTROL 自动定位] 活动、您网站的流量以及您选择的成功量度。

**解决方案：** 查看活动设置，了解是否愿意进行任何更改以提高构建模型的速度。

* 如果成功量度设置为 [!UICONTROL RPV]，能否更改为转化？ 转化活动需要用来构建模型的流量通常较少。如果将成功量度从 RPV 更改为转化，您并不会丢失活动数据。
* 您的成功量度在活动体验的销售漏斗中是否位于较远的位置？较低的活动转化率会增加构建模型所需的流量要求，因为需要达到最低转化次数。
* 是否有一些体验可从活动中删除？减少活动中的体验数量会减少构建模型的时间。
* 是否存在更高流量的页面可以提高此活动的成功率？活动位置的流量和转化越多，模型构建的速度就越快。

+++

### 我的[!UICONTROL 自动定位]活动不产生任何提升。

+++故障排除建议需要四个因素 [!UICONTROL 自动定位] 用于生成提升度的活动：

* 选件必须足够不同，才能影响访客。
* 选件必须位于对优化目标有所影响的位置。
* 测试中必须有足够的流量和统计“功效”，才能检测到提升度。
* 个性化算法必须运行良好。

**解决方法：**&#x200B;首先，确保您的活动对流量进行了个性化。如果没有针对所有体验都构建了模型，那么您的[!UICONTROL 自动定位]活动仍会为大量访问随机提供体验，以尽可能快地构建所有模型。如果未构建模型，则[!UICONTROL 自动定位]不会对流量进行个性化。

接下来，使用简单的非个性化A/B测试，确保选件和活动位置对整体响应率真正发挥了作用。 务必提前计算样本量，以确保有足够的样本以便看到合理的提升，并在一段固定的时间内运行 A/B 测试，且不要终止或对其进行任何更改。如果A/B测试结果在一个或多个体验上显示出统计上的显着提升，则个性化活动可能会正常工作。 即使体验的总体响应率没有差异，个性化也可以正常工作。 通常，问题源于选件和位置对优化目标的影响不足以被检测出具有统计显着性的情况。

+++

### 依赖于转化量度的所有量度从不转化。

+++故障排除建议这是正常情况。

在 [!UICONTROL 自动定位] 活动，转化量度（无论是优化目标还是后期目标）发生转化后，用户将会从体验中释放，并且活动会重新开始。

例如，一个活动拥有一个转化量度 (C1) 和一个其他量度 (A1)。A1依赖于C1。 当访客首次进入活动，并且转化 A1 和 C1 的标准并未实现转化，那么由于成功量度的依赖关系，量度 A1 不会进行转化。如果访客先转换C1，然后再转换A1，则仍不会转换A1，因为转换C1时，访客将会释放。

+++
