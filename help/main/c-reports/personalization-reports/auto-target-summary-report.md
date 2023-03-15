---
keywords: 报表；自动定位；AT；报表
description: 了解如何解释Adobe Target中的自动定位摘要报表。 您可以从此报表切换到自动化区段和重要属性报表。
title: 如何使用自动定位摘要报表？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Reports
exl-id: 098fcc0e-8e17-4898-ab2f-ec74472562ff
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 52%

---

# 自动定位摘要报表

有关如何解释 [!UICONTROL 自动定位摘要] 报表 [!DNL Adobe Target].

>[!NOTE]
>
>[!UICONTROL 自动定位]作为 [!DNL Target Premium] 解决方案的一部分提供。它不包括在 [!DNL Target Standard] 没有 [Target Premium许可证](/help/main/c-intro/intro.md#premium).

显示 [!UICONTROL 自动定位摘要] 报表：

1. 从 [!UICONTROL 活动] 页面，单击所需的 [!UICONTROL 自动定位] 活动。

   如果您有多个活动，则可以通过从 [!UICONTROL 类型], [!UICONTROL 状态], [!UICONTROL 属性], [!UICONTROL 报表源], [!UICONTROL 体验编辑器], [!UICONTROL 量度类型]和 [!UICONTROL 活动源] 下拉列表。

1. 单击 [!UICONTROL 报表] 选项卡，然后单击所需的图标：

   * 表格视图
   * 图形视图
   * 自动化区段
   * 重要属性

## 表格视图

下图显示了 [!UICONTROL 表视图] 查看 [!UICONTROL 自动定位] 活动报表：

![自动定位表视图报表](/help/main/c-reports/assets/at-table-view.png)

在您解读 [!UICONTROL 自动定位] 报表：

* 表中的各行可帮助您了解活动性能。

   * 在报表页面中，表格的前两行显示以下两种访客之间的 A/B 测试结果：分配到控制体验（即随机提供的体验）的访客，以及分配到个性化算法的访客。此信息可以用来测量与随机提供的控制体验相比，个性化算法有多少性能优势。
   * 其余的行显示体验级别的结果。对于每个体验，系统会将以下两类访客的平均响应进行比较：向其显示随机提供控制体验的访客，以及向其显示使用了个性化算法的体验的访客。

* 报表中每个体验旁边的绿色复选标记表示已为该体验生成个性化的机器学习模型。时钟图标表示用于构建模型的流量不足。

   * 由于该模型是根据每个体验构建的，因此可以根据绿色复选标记查看其中部分体验的模型，并使用时钟图标查看其他体验的模型。
   * 在这种情况下，要提高为所有体验构建模型的活动的速度，需将额外流量发送到未构建模型的体验。
   * 要开始进行个性化，必须至少具有两个已构建模型的体验（绿色复选标记）。

* 将体验A的转化率与体验B的转化率进行比较，在 [!UICONTROL 自动定位]. 问题在于，与随机提供体验 A 的方式相比（换言之，与控制体验相比），以智能方式提供体验 A 时，体验 A 的性能是否更好。此外，营销人员还应谨慎解读个人体验的提升，因为个性化算法会尝试优化整个活动的成功量度，而不是针对每一个个人体验进行优化。
* 可以这样理解：具有最高提升度的体验在人群中具有最大的差异。也就是说，算法已找到一个最喜欢该特定体验的区段。
* 表中的各列显示访问次数、转化率、平均提升度和置信水平以及置信度。 有关更多信息，请参阅 [A/B测试中的统计计算](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## 图形视图

下图显示了 [!UICONTROL 图形视图] 查看 [!UICONTROL 自动定位] 活动报表：

![自动定位图形视图报表](/help/main/c-reports/assets/at-graph-view.png)

如下所示，您可以使用两个下拉列表来选择所需的量度、计数方法等。 请参阅 [报表设置概述](/help/main/c-reports/c-report-settings/report-settings.md) 有关详细信息：

![自动定位图形视图报表](/help/main/c-reports/assets/at-graph-view-2.png)

## 自动化区段

单击 [!UICONTROL 自动化区段] 图标。 此报表显示不同访客对您的AP/AT活动中的选件/体验做出的响应有何不同。 此报表可显示 Target 的个性化模型定义的不同自动化区段如何响应活动中的选件/体验。

![“自动化区段”图标](/help/main/c-reports/assets/icon-automated-sements.png)

有关更多信息，请参阅 [自动化区段报表](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## 重要属性

单击 [!UICONTROL 重要属性] 图标。 此报表显示在不同的活动中，不同属性对模型如何决定进行个性化的重要性如何高（或低）。 此报表可显示影响模型的排名靠前的属性及其相对重要性。

![“重要属性”图标](/help/main/c-reports/assets/icon-important-attributes.png)

有关更多信息，请参阅 [重要属性报表](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).
