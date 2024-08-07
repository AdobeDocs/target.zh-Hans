---
keywords: 自动流量分配；定位；自动分配；自动分配
description: 了解 [!DNL Adobe Target] 中的[!UICONTROL Auto Allocate]活动如何在两个或更多体验中找出入选者，并自动为入选者重新分配更多流量。
title: '[!UICONTROL Auto-Allocate]活动能否获得更快的结果和更高的收入？'
feature: Auto-Allocate
exl-id: 104ad88f-044b-4c2f-bdaf-f023fd1787a5
source-git-commit: e9976135c46f6658030b07fce384364f0c9ff0ed
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 0%

---

# [!UICONTROL Auto-Allocate]比手动测试产生测试结果更快和收入更高

使用手动A/B活动时，您可能会丢失转化，因为直到活动完成才能将入选体验交付给整个受众。 即使在您了解到某些体验优于其他体验之后，您的流量分配仍保持不变，并且活动必须运行其整个课程，然后才能对入选者执行操作。

## 自动分配流量

如果您希望某个选项在活动中更早更频繁地提供入选体验，同时删除或减少选择样本量、置信度级别和其他统计概念的设置和计算成本，那么[!UICONTROL Auto-Allocate]是您的最佳选项。

## [!UICONTROL Auto-Allocate]的工作原理是什么？

[!UICONTROL Auto-Allocate]使用多臂老虎机的原理。 如果这个词不熟悉，单臂老虎机就是老虎机的俗语（想想：拉斯维加斯）。 将流量的自动分配可视化为具有多个老虎机（在此例中是测试变体），并在开始时均匀提取所有句柄。 随着时间的推移，一台或多台机器或测试变体可能比其他机器支付得更多。 当这种情况发生时，赌徒会自然而然地开始拉那些获胜更频繁的赌徒的把手。 在流量分配术语中，[!DNL Target]为更多的访客提供获益更多的体验或体验。

请考虑下图，其中显示了一个为期两周的A/B活动。 在[!UICONTROL Auto-Allocate]中，随着入选体验的出现，[!UICONTROL Target]会在测试早期将更多流量分配给该入选者。

![自动分配插图](/help/main/c-activities/automated-traffic-allocation/assets/Auto-Allocate-test.png)

## [!UICONTROL Auto-Allocate]如何提供更快的结果？

好处显而易见：更多访客会看到表现最佳的变体。 当一个变数拉到前面时，会有更多的访客在测试仍在运行时，被引导到入选体验。 如果正在运行的A/B活动发生在核心业务时刻（例如，假日、产品发布或全球新闻活动），此方法特别有用。

## [!UICONTROL Auto-Allocate]如何提供更高的收入？

[!UICONTROL Auto-Allocate]发现入选者的速度比手动A/B拆分更快，并且允许您利用入选者立即捕获在传统或手动方法中会损失的追加收入。 由于[!UICONTROL Auto-Allocate]将更多流量引向转化率最高的体验，因此它可以提高您的收入，同时促进活动运行和学习。

在以下示例中，[!UICONTROL Auto-Allocate]通过将更多流量(40%)推送到转化率最高的体验D，在测试期间获得了更多收入。

![自动分配提供更高的收入图示](/help/main/c-activities/automated-traffic-allocation/assets/five-experiences.png)

## 在哪些情况下我应该坚持手动流量分配？

如果必须将每个体验的执行方式相对于其他体验进行排序，则最适用的人工A/B测试。 [!UICONTROL Auto-Allocate]查找并利用表现最佳的体验，但不保证区分表现较差的体验。 使用手动流量分配完全控制访客流量有多少会看到每个测试变体，并自定义与您的业务相关的统计阈值。

## 快速入门

准备好启动您的第一个[!UICONTROL Auto-Allocate]活动吗？ [在这里了解详情](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)。
