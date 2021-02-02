---
keywords: a4t;A4T;Analytics 作为 Target 报表源
description: 我是否可以将A4T与自动目标和自动分配活动一起使用？
title: 自动分配和自动目标活动的A4T支持
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 4f0f1df1bcb6baad0e20c4dc1ae7e12751080d91
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 2%

---


# 自动分配和自动目标活动的A4T支持

[!DNL Adobe Target]-to-[!DNL Adobe Analytics]集成，称为[目标分析](/help/c-integrating-target-with-mac/a4t/a4t.md)(A4T)支持[!UICONTROL 自动分配]和[!UICONTROL 自动目标]活动。

A4T集成允许您：

* 使用[自动分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)的多武装强盗功能，推动流量增长，以赢得体验。
* 使用[自动目标](/help/c-activities/auto-target/auto-target-to-optimize.md)的集成机器学习算法，根据每个访客的用户档案、行为和上下文选择最佳体验，同时使用[!DNL Adobe Analytics]目标指标和[!DNL Adobe Analytics]的丰富报告和分析功能。

确保您已实施[ A4T，以与A/B测试和体验定位活动](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)一起使用。 如果您使用`analyticsLogging = client_side`，则还需要将`sessionId`值传递给[!DNL Analytics]。 有关详细信息，请参阅&#x200B;*Adobe TargetSDK*&#x200B;指南中的[目标分析(A4T)报告](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting)。

若要开始，请执行以下操作：

1. 在创建A/B测试活动时，在&#x200B;**[!UICONTROL 定位]**&#x200B;页面上，选择以下选项之一作为&#x200B;**[!UICONTROL 流量分配方法]**:

   * [!UICONTROL 自动分配到最佳体验]
   * [!UICONTROL 自动目标，实现个性化体验]

   ![流量分配方法选项：手动、自动分配和自动目标](/help/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   有关详细信息和分步说明，请参阅[创建自动分配活动](/help/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)和[创建自动目标活动](/help/c-activities/auto-target/create-auto-target.md)。

1. 在&#x200B;**[!UICONTROL 目标和设置]**&#x200B;页面上为&#x200B;**[!UICONTROL 报告源]**&#x200B;选择&#x200B;**[!UICONTROL Adobe Analytics]**，然后选择与所需优化目标对应的报表包。

1. 选择主要目标量度。

   * 选择&#x200B;**[!UICONTROL 转换]**&#x200B;以使用[!DNL Adobe Target]指定优化目标。
   * 选择&#x200B;**[!UICONTROL 使用Analytics度量]**，然后从[!DNL Analytics]中选择一个度量以用作优化目标。 您可以使用现成的[!DNL Analytics]转换度量或[!DNL Analytics]自定义事件。

1. 保存并激活活动。

   [!UICONTROL 自动分] 配将使用您选择的活动来优化访客，从而推动体验最大化目标指标。

   或

   [!UICONTROL 自动定] 位将使用您选定的指标优化活动，从而推动访客获得个性化的最佳体验。

1. 使用&#x200B;**[!UICONTROL 报告]**&#x200B;选项卡根据您选择的[!DNL Adobe Analytics]指标视图活动的报告。 单击Analytics ]**中的**[!UICONTROL &#x200B;视图，深入细分报告数据并进一步细分数据。

## 支持的目标指标

[!UICONTROL A4对于] 自 [!UICONTROL 动分] 配和自 [!UICONTROL 动定] 位，您可以选择以下任意指标类型作为优化的主要目标指标：

* [!DNL Adobe Target] 转化量度
* [!DNL Adobe Analytics] 转化量度
* [!DNL Adobe Analytics] 个自定义事件

[!UICONTROL A4] Tfor    [!UICONTROL Auto-] Allocate和Auto-Target要求您选择基于二项式事件(即不存在或未发生的事件)的度量，例如单击、转换、订单等。这些类型的事件有时也称为伯努利事件、二进制或离散数据。

[!UICONTROL A4T]  for  [!UICONTROL Auto-] Allocate和 [!UICONTROL Auto-Target不支持对连续指] 标(如收入、订购的产品数量、会话持续时间、会话中的页面视图数等)进行优化。这些不受支持的度量类型有时也称为非二项式或非伯努利度量。

不支持以下度量类型作为主要目标度量：

* [!DNL Adobe Target] 参与度和收入指标
* [!DNL Adobe Analytics] 参与度和收入指标

   可以选择[!DNL Analytics]参与度或收入指标作为主要目标指标，因为[!DNL Target]不能识别和排除来自[!DNL Analytics]的所有参与度和收入指标。 请务必从[!DNL Analytics]中仅选择二项式转换指标或自定义事件。

* [!DNL Adobe Analytics] 计算量度

## 限制和说明

某些限制和说明适用于[!UICONTROL 自动分配]和[!UICONTROL 自动目标]活动。 其他限制和注释适用于一种活动类型或另一种。

### 自动分配和自动目标

* 报告源在激活活动后不能从[!DNL Analytics]更改为[!DNL Target]，反之亦然。
* 尽管计算的指标不作为主要目标指标受支持，但通常可以通过选择自定义事件作为主要目标指标来达到预期效果。 例如，如果要优化诸如“每个访客的表单完成情况”之类的指标，请选择与“表单完成情况”对应的自定义事件作为主要目标指标。 [!DNL Target] 根据每次访问自动标准化转化量度，以考虑流量分布不均，因此无需使用计算量度来执行标准化。
* [!DNL Target] 在“自动分配”功能中使用“同 [!UICONTROL 一触] ”归因模型：目标分析(A4T)。

### 自动分配

* [!UICONTROL 自动分] 配模型继续像往常一样每两个小时进行一次培训。

### 自动定位

* [!UICONTROL 自动定] 位模型照常每24小时进行一次培训。但是，来自[!DNL Analytics]的转换事件数据会额外延迟6到24小时。 此延迟意味着[!DNL Target]的流量分配将跟踪[!DNL Analytics]中记录的最新事件。 在活动初始激活后的头48小时内，效果最大。 活动的性能将更密切地反映经过五天后的[!DNL Analytics]转换行为。 您应考虑对短时活动使用[!UICONTROL 自动分配]而不是[!UICONTROL 自动目标]，在短时间活动中，大多数流量在生命周期的前五天内发生。
* 当使用[!DNL Analytics]作为[!UICONTROL 自动目标]活动的数据源时，会话被视为在经过6小时后结束。 六小时后发生的转换不会计算在内。

有关详细信息，请参阅&#x200B;*分析工具指南*&#x200B;中的[归因模型和回顾窗口](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html)。
