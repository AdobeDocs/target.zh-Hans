---
keywords: 自动流量分配；定位；自动分配；自动分配
description: 了解[!DNL Adobe Target]中的[!UICONTROL 自动分配]活动如何在两个或更多体验中识别入选者，并自动为入选者重新分配更多流量。
title: '[!UICONTROL 自动分配]活动能否获得更快的结果和更高的收入？'
feature: Auto-Allocate
exl-id: 104ad88f-044b-4c2f-bdaf-f023fd1787a5
TQID: 'https://experienceleague.adobe.com/aSxZ0Zp3cm0x-fVBXHWW4OiXd3Riz-tuhBiw0f8m4lk'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f2d0aafb-18af-41a0-a32e-2788eafacc2b
    internal-label: Auto-allocate
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 878df20c7fb08c893239135c20f358b5606d0c6f
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 0%
---
# [!UICONTROL 自动分配]如何优于手动测试 {#faster-results-higher-revenue}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解为什么&#x200B;**[!UICONTROL 自动分配]**&#x200B;活动比手动A/B测试产生更快的结果和更高的收入，它的工作方式，以及何时手动流量分配仍然是更好的选择。

>[!ENDSHADEBOX]

手动A/B活动可能会失去转化，因为在该活动完成之前，您无法将入选体验交付给整个受众。 即使在您了解到某些体验优于其他体验之后，您的流量分配仍保持不变，并且活动必须运行其整个课程，然后才能对入选者执行操作。

## 自动分配流量 {#auto-allocating-traffic}

如果您要在活动中更频繁和更早地提供入选体验，同时消除或减少挑选样本量、置信度级别和其他统计概念的设置和计算成本，则&#x200B;**[!UICONTROL 自动分配]**&#x200B;是您的最佳选择。

## [!UICONTROL 自动分配]如何工作？ {#how-it-works}

**[!UICONTROL 自动分配]**&#x200B;使用多臂老虎机的原理。 独臂老虎机是老虎机的俗语。 将流量自动分配想象为一组老虎机，在这个例子中是测试变体，其句柄在开始时是等拉取的。 随着时间的推移，一台或多台机器或测试变体可能比其他机器支付得更多。 当这种情况发生时，赌徒会自然而然地开始拉取获胜次数更多的机器的手柄。 在流量分配术语中，[!DNL Target]为更多的访客提供获益更多的体验或体验。

下图显示了一个为期两周的A/B活动。 通过&#x200B;**[!UICONTROL 自动分配]**，当出现入选体验时，[!DNL Target]会在测试早期将更多流量分配给该入选者。

![自动分配插图](/help/main/c-activities/automated-traffic-allocation/assets/Auto-Allocate-test.png)

## [!UICONTROL 自动分配]如何提供更快的结果？ {#faster-results}

更多访客会看到表现最佳的变体。 由于单个变体拉在前面，因此在测试仍在运行时，会有更多访客转向该入选体验。 如果A/B活动在核心业务时刻（例如，假日、产品发布或世界新闻事件）运行，此方法将特别有用。

## [!UICONTROL 自动分配]如何提供更高的收入？ {#higher-revenue}

**[!UICONTROL 自动分配]**&#x200B;查找入选者的速度快于手动A/B拆分，允许您立即利用该入选者，从而捕获在传统或手动方法中会损失的追加收入。 **[!UICONTROL 自动分配]**&#x200B;会将更多流量引向转化率最高的体验，这样可以在活动运行和学习时增加您的收入。

在以下示例中，**[!UICONTROL 自动分配]**&#x200B;通过将更多流量(40%)推送到转化率最高的体验D，在测试期间获得了更多收入。

![自动分配提供更高的收入图示](/help/main/c-activities/automated-traffic-allocation/assets/five-experiences.png)

## 在哪些情况下我应该坚持手动流量分配？ {#manual-allocation}

手动A/B测试是最适用的选项，因为您必须对每个体验的执行方式相对于其他体验进行排名。 **[!UICONTROL 自动分配]**&#x200B;查找和利用表现最好的体验，但不保证表现不佳的体验之间有区别。 使用手动流量分配完全控制访客流量有多少会看到每个测试变体，并自定义与您的业务相关的统计阈值。

## 快速入门 {#get-started}

准备好启动您的第一个&#x200B;**[!UICONTROL 自动分配]**&#x200B;活动吗？ 请参阅[创建自动分配活动](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)和[自动分配概述](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)。
