---
keywords: 报表；自动定位；AT；报表
description: 了解如何在Adobe Target中解释自动定位摘要报表。 您可以从此报表切换到自动化区段和重要属性报表。
title: 如何使用自动定位摘要报表？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Reports
exl-id: 098fcc0e-8e17-4898-ab2f-ec74472562ff
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 37%

---

# [!UICONTROL Auto-Target Summary report]

有关如何解释[!UICONTROL Auto-Target Summary]中的[!DNL Adobe Target]报表的信息。

>[!NOTE]
>
>[!UICONTROL Auto-Target]作为[!DNL Target Premium]解决方案的一部分提供。 在没有[!DNL Target Standard]Target Premium许可证[的](/help/main/c-intro/intro.md#premium)中不包括它。

要显示[!UICONTROL Auto-Target Summary]报告：

1. 从[!UICONTROL Activities]页面，单击所需的[!UICONTROL Auto-Target]活动。

   如果您有许多活动，请单击“筛选器”（![筛选器图标](/help/main/assets/icons/Filter.svg)）图标以通过从[!UICONTROL Type]、[!UICONTROL Status]、[!UICONTROL Reporting Source]、[!UICONTROL Experience Composer]、[!UICONTROL Metrics Type]和[!UICONTROL Activity Source]下拉列表中选择选项来筛选列表。

1. 单击&#x200B;**[!UICONTROL Reports]**&#x200B;选项卡，然后单击所需的图标：

   * **[!UICONTROL Table View]** （ ![表格视图图标](/help/main/assets/icons/Table.svg) ）
   * **[!UICONTROL Graph View]** （ ![图形视图图标](/help/main/assets/icons/GraphTrend.svg) ）
   * **[!UICONTROL Automated Segments]** （![自动化区段报表](/help/main/assets/icons/AutomatedSegment.svg) ）
   * [!UICONTROL Important Attributes]** （![重要属性图标](/help/main/assets/icons/ViewList.svg) ）

## 表格视图

解释[!UICONTROL Auto-Target]报表时的一些提示和注意事项：

* 表中的各行可帮助您了解活动表现。

   * 报表页面上表的前两行显示的是分配给控制的访客（即随机提供的体验）与分配给个性化算法的访客之间的A/B测试结果。 此信息可用于衡量个性化算法与随机提供控制相比的执行情况。
   * 其余的行显示体验级别的结果。对于每个体验，系统会将以下两类访客的平均响应进行比较：向其显示随机提供控制体验的访客，以及向其显示使用了个性化算法的体验的访客。

* 报表中每个体验旁边的绿色复选标记表示已为该体验生成个性化的机器学习模型。时钟图标表示用于构建模型的流量不足。

   * 由于该模型是根据每个体验构建的，因此可以根据绿色复选标记查看其中部分体验的模型，并使用时钟图标查看其他体验的模型。
   * 在这种情况下，要提高为所有体验构建模型的活动的速度，需将额外流量发送到未构建模型的体验。
   * 必须至少有两个具有已构建模型（绿色复选标记）的体验，才能开始个性化。

* 将体验A的转化率与体验B的转化率进行比较在[!UICONTROL Auto-Target]中不是正确的比较。 问题在于，与随机提供体验 A 的方式相比（换言之，与控制体验相比），以智能方式提供体验 A 时，体验 A 的性能是否更好。此外，营销人员还应谨慎解读个人体验的提升，因为个性化算法会尝试优化整个活动的成功量度，而不是针对每一个个人体验进行优化。
* 可以这样理解：具有最高提升度的体验在人群中具有最大的差异。也就是说，算法发现了一个最喜爱该特定体验的区段。
* 表中的各种列显示访问次数、转化率、平均提升度和置信水平以及置信度。 有关详细信息，请参阅[A/B测试中的统计计算](/help/main/c-reports/statistical-methodology/statistical-calculations.md)。

## 图形视图

使用两个下拉列表选择所需的量度、计数方法等。 有关详细信息，请参阅[报表设置概述](/help/main/c-reports/c-report-settings/report-settings.md)：

## 自动化区段

此报表可显示不同访客对您的AP/AT活动中的选件/体验做出的不同响应。 此报表显示[!DNL Target]个性化模型定义的不同自动化区段如何响应活动中的选件/体验。

有关详细信息，请参阅[自动化区段报表](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md)。

## 重要属性

此报表显示了在不同活动中，不同属性对模型如何决定进行个性化的重要性如何。 此报表可显示影响模型的排名靠前的属性及其相对重要性。

有关详细信息，请参阅[重要属性报表](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md)。
