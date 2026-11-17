---
keywords: 自动定位;定位;流量分配;常见问题;常见问题;故障排除;故障排除;流量
description: 浏览有关[!UICONTROL 自动定位]活动的故障排除主题和常见问题。
title: 如何为[!UICONTROL 自动定位]活动排除故障？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Auto-Target
exl-id: 934f738e-560a-4847-9608-432ecfa2afe7
TQID: 'https://experienceleague.adobe.com/LXOa1Ma0y8VbncCPN1Az33p-GDsd-bW-BDqJjSGbVQU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
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
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 878df20c7fb08c893239135c20f358b5606d0c6f
workflow-type: tm+mt
source-wordcount: '1841'
ht-degree: 10%
---
# [!UICONTROL 自动定位]常见问题解答和疑难解答 {#auto-target-faqs}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;查找有关&#x200B;**[!UICONTROL 自动定位]**&#x200B;活动的常见问题解答以及常见问题的建议解决方案。

>[!ENDSHADEBOX]

此页面回答了常见问题解答(FAQ)，并介绍了[!DNL Adobe Target]中&#x200B;**[!UICONTROL 自动定位]**&#x200B;活动的故障排除步骤。

## 常见问题解答 {#section_5C120A2B11D14D9BAF767BBAB50FED23}

在使用&#x200B;**[!UICONTROL 自动定位]**&#x200B;活动时，请咨询以下问题和答案。

+++ 设置[!UICONTROL 自动定位]活动的最佳实践是什么？

* 确定&#x200B;**[!UICONTROL 每次访问收入]** (RPV)成功量度的业务值是否值得额外的流量要求。 与转化相比，RPV通常需要每个体验至少1,000次转化才能使活动正常工作。
* 在开始活动之前，根据您的目标，确定控制与个性化体验之间的分配。
* 确定您是否有足够的流量访问运行&#x200B;**[!UICONTROL 自动定位]**&#x200B;活动的页面，以使个性化模型在合理的时间内生成。
* 如果您正在测试个性化算法，请勿在活动开始时更改体验，或添加或删除配置文件属性。
* 考虑在您计划于&#x200B;**[!UICONTROL 自动定位]**&#x200B;活动中使用的选件和位置之间完成一个A/B活动，以确保位置和选件会对优化目标产生影响。 如果A/B活动未能显示显着差异，则&#x200B;**[!UICONTROL 自动定位]**&#x200B;可能也无法生成提升。

  如果A/B测试显示体验之间没有统计上的显着差异，则您考虑的选件之间可能没有足够大的差异、您选择的位置不会影响成功量度，或者转化funnel中的优化目标太远，不会受到您选择的选件的影响。

* 在活动期间不要对体验进行重大更改。

+++

+++ Adobe是否建议以90（对照）/10（针对性）的分摊使用自动定位直到构建模型为止？

最优的流量分配分摊取决于要实现的目标。

如果您的目标是使尽可能多的流量个性化，则在活动期间，您可以保持90%的目标分配和10%的控制。 如果您的目标是运行一项对比个性化算法与控制体验的实验，则50/50的分割比例最适合活动期限。

最佳实践是在整个活动期内保持流量分配分摊，这样访客就不会在针对性体验与对照体验之间切换。

<!-- 
### Do the check marks indicating a model is built for that experience update if the report date range changes?

No, check marks for model generation show only the models built to date. There is no way to go back and see when a model was completed.
-->

+++

+++ 如果访客未看到[!UICONTROL 自动定位]活动但进行了转化，则此转化是否会计入到我的活动中？

否. 只有符合条件并查看了&#x200B;**[!UICONTROL 自动定位]**&#x200B;活动的访客才会计入报表中。

+++

+++ 为何我的[!UICONTROL 自动定位]活动不产生任何提升？

有关生成提升所需的四个因素和建议的解决方案，请参阅故障排除项目[我的自动定位活动未生成任何提升](#section_23995AB813F24525AF294D20A20875C8)。

+++

+++ 我应何时停止[!UICONTROL 自动定位]活动？

**[!UICONTROL 自动定位]**&#x200B;可用作“始终运行”且不断优化的个性化设置。 特别是对于一直使用的内容，无需停止&#x200B;**[!UICONTROL 自动定位]**&#x200B;活动。

如果要对&#x200B;**[!UICONTROL 自动定位]**&#x200B;活动中的内容进行重大更改，最佳实践是启动一个新活动，以便查看报表的其他用户不会将过去的结果与不同内容混淆或相关联。

+++

+++ 我需要等待多久才能构建模型？

在&#x200B;**[!UICONTROL 自动定位]**&#x200B;活动中构建模型的时间通常取决于您选定活动位置的流量以及与活动成功量度关联的转化率。

**[!UICONTROL 自动定位]**&#x200B;不会尝试为给定体验构建个性化模型，直到该体验发生至少50次转化。 此外，如果所构建的模型质量缺佳（通过使用称为AUC](https://en.wikipedia.org/wiki/Receiver_operating_characteristic#Area_under_the_curve)的量度[对留出的“测试”数据进行离线评估而确定），则不会使用该模型以个性化的方式提供流量。

关于在&#x200B;**[!UICONTROL 自动定位]**&#x200B;中构建模型，请记住以下几点：

* 活动上线后，**[!UICONTROL 自动定位]**&#x200B;在尝试构建模型时最多考虑过去45天随机提供的数据。 例如，控制流量以及算法保留的一些额外的随机提供数据。
* 当&#x200B;**[!UICONTROL 每次访问收入]**&#x200B;是成功量度时，这些活动通常需要更多数据才能构建模型，因为访问收入的差异通常高于转化率。
* 模型是根据体验构建的，因此将一种体验替换为另一种意味着必须为新体验收集足够的流量（至少50次转化），然后才能重建个性化模型。

如果模型生成时间过长，请参阅[我的自动定位活动在生成模型时用时过长](#section_23995AB813F24525AF294D20A20875C8)。

+++

+++ 我的活动中已构建一个模型。 对该体验的访问是否为个性化的？

否. 必须在活动中至少构建两个模型，才能开始个性化。

+++

+++ 何时可以开始查看[!UICONTROL 自动定位]活动的结果？

在至少两个体验已构建模型（绿色复选标记）后，您就可以开始查看&#x200B;**[!UICONTROL 自动定位]**&#x200B;活动的结果。

+++

+++ 我可以指定特定体验作为控制吗？

在创建[Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP)或[自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT)活动时，您可以选择要用作控制的体验。

通过此功能，您可以根据活动中配置的流量分配百分比，将整个控制流量路由到特定体验。 然后，您可以根据该体验的控制流量评估个性化流量的性能报表。

有关更多信息，请参阅[使用特定体验作为控制](/help/main/c-activities/t-automated-personalization/experience-as-control.md)。

+++

+++ 能否在[!UICONTROL 自动定位]活动中途更改目标指标？

Adobe不建议您在活动中途更改目标指标。 虽然可在活动期间使用 [!DNL Target] UI 更改目标指标，但总是应开始新的活动。 如果在活动运行后更改其中的目标指标，Adobe不保证会出现什么情况。

此推荐适用于使用[!DNL Target]或[!DNL Analytics] (A4T)作为报表源的&#x200B;**[!UICONTROL 自动分配]**、**[!UICONTROL 自动定位]**&#x200B;和&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动。

+++

+++ 运行[!UICONTROL 自动定位]活动时能否使用[!UICONTROL 重置报表数据]选项？

不建议对&#x200B;**[!UICONTROL 自动定位]**&#x200B;活动使用&#x200B;**[!UICONTROL 重置报表数据]**&#x200B;选项。 虽然它删除可见的报表数据，但此选项不会从&#x200B;**[!UICONTROL 自动定位]**&#x200B;模型中删除所有训练记录。 不要使用&#x200B;**[!UICONTROL 重置报表数据]**&#x200B;选项，而要创建新活动并停用原始活动。

本指导还适用于&#x200B;**[!UICONTROL 自动分配]**&#x200B;和&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动。

+++

+++ 如果我从[!UICONTROL 自动定位]活动中删除单个体验会发生什么情况？

[!DNL Target]为每个体验构建一个模型，因此删除一个体验意味着[!DNL Target]少构建一个模型，并且不会影响其他体验的模型。

例如，假设您有一个包含八个体验的&#x200B;**[!UICONTROL 自动定位]**&#x200B;活动，而您不满意其中一个体验的表现。 您可以删除该体验，这不会影响剩余七个体验的模型。

+++

## [!UICONTROL 自动定位]故障诊断 {#section_23995AB813F24525AF294D20A20875C8}

有时候，活动没有按预期进行。 以下项目描述了使用&#x200B;**[!UICONTROL 自动定位]**&#x200B;时可能面临的潜在挑战，以及建议的解决方案。

+++ 我的[!UICONTROL 自动定位]活动在构建模型时用时过长。

更改几项活动设置可以减少构建模型所需的预计时间，包括&#x200B;**[!UICONTROL 自动定位]**&#x200B;活动中的体验数量、您网站的流量以及您选择的成功量度。

**解决方案：**&#x200B;查看您的活动设置，看看是否愿意进行任何更改以提高模型构建的速度。

* 如果成功量度设置为&#x200B;**[!UICONTROL RPV]**，是否可以更改为转化？ 转化活动需要用来构建模型的流量通常较少。 如果将成功量度从RPV更改为转化，则不会丢失活动数据。
* 您的成功量度在活动体验的销售漏斗中是否位于较远的位置？ 较低的活动转化率会增加要构建模型的流量要求，因为需要达到最低转化次数。
* 是否有一些体验可从活动中删除？ 减少活动中的体验数量会减少构建模型的时间。
* 是否存在更高流量的页面可以提高此活动的成功率？ 活动位置的流量和转化越多，模型构建的速度就越快。

有关模型所需时间的详细信息，请参阅[我需要等待多久才能生成模型？](#section_5C120A2B11D14D9BAF767BBAB50FED23)。

+++

+++ 我的[!UICONTROL 自动定位]活动未生成任何提升。

**[!UICONTROL 自动定位]**&#x200B;活动需要四个因素才能生成提升：

* 选件必须足够不同，才能影响访客。
* 选件必须位于对优化目标有所影响的位置。
* 测试中必须有足够的流量和统计“功效”，才能检测到提升度。
* 个性化算法必须运行良好。

**解决方法：**&#x200B;首先，确保您的活动对流量进行了个性化。 如果没有针对所有体验都构建了模型，则您的&#x200B;**[!UICONTROL 自动定位]**&#x200B;活动仍会为大量访问随机提供体验，以尽可能快地构建所有模型。 如果未构建模型，则&#x200B;**[!UICONTROL 自动定位]**&#x200B;不会对流量进行个性化。

接下来，使用简单的非个性化A/B测试，确保选件和活动位置对整体响应率真正发挥了作用。 提前计算样本大小以确保有足够的能力来查看合理的提升，并在固定持续时间内运行A/B测试而不会停止它或进行任何更改。 如果A/B测试结果显示一个或多个体验在统计上显着提升，则个性化活动可能会正常工作。 即使这些体验的总体响应率没有差异，Personalization也可以正常工作。 通常，问题源于选件和位置对优化目标的影响不足以被检测出具有统计显着性的情况。

+++

+++ 依赖于转化量度的所有量度从不转化。

这是符合预期的。

在&#x200B;**[!UICONTROL 自动定位]**&#x200B;活动中，转化量度（无论是优化目标还是后期目标）发生转化后，用户将会从体验中释放，并且活动会重新启动。

例如，一个活动拥有一个转化量度 (C1) 和一个其他量度 (A1)。 A1依赖于C1。 当访客首次进入活动，并且不满足转化A1和C1的条件时，由于成功量度依赖关系，量度A1未转化。 如果访客先转换C1，然后再转换A1，则A1仍不会转换，因为转换C1时，访客将会释放。

+++
