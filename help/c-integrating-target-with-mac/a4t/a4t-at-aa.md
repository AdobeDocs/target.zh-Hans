---
keywords: a4t;A4T;Analytics 作为 Target 报表源
description: 了解如何在将Analytics用作报告源(A4T)的Adobe [!DNL Target] 中创建自动分配和自动目标活动。
title: A4T是否支持自动分配和自动目标活动?
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '963'
ht-degree: 2%

---

# A4T支持自动分配和自动目标活动

[!DNL Adobe Target]-to-[!DNL Adobe Analytics]集成，称为[Analytics for 目标](/help/c-integrating-target-with-mac/a4t/a4t.md)(A4T)支持[!UICONTROL 自动分配]和[!UICONTROL 自动目标]活动。

A4T集成允许您：

* 使用[自动分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)的多臂强盗功能，将流量带入赢取的体验。
* 使用[自动目标](/help/c-activities/auto-target/auto-target-to-optimize.md)的集成机器学习算法为每个访客选择最佳体验。 自动目标根据用户的用户档案、行为和上下文选择最佳体验，同时使用[!DNL Adobe Analytics]目标量度和[!DNL Adobe Analytics]的丰富报告和分析功能。

确保您已实施[A4T，以用于A/B测试和体验定位活动](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)。 如果使用`analyticsLogging = client_side`，则还必须将`sessionId`值传递给[!DNL Analytics]。 有关详细信息，请参阅&#x200B;*Adobe Target SDK*&#x200B;指南中的[目标分析(A4T)报告](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting)。

若要开始，请执行以下操作：

1. 创建A/B测试活动时，在&#x200B;**[!UICONTROL 定位]**&#x200B;页面上，选择以下选项之一作为&#x200B;**[!UICONTROL 流量分配方法]**:

   * [!UICONTROL 自动分配到最佳体验]
   * [!UICONTROL 自动目标，实现个性化体验]

   ![流量分配方法选项：手动、自动分配和自动目标](/help/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   有关详细信息和分步说明，请参阅[创建自动分配活动](/help/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)和[创建自动目标活动](/help/c-activities/auto-target/create-auto-target.md)。

1. 在&#x200B;**[!UICONTROL 目标和设置]**&#x200B;页面上，为&#x200B;**[!UICONTROL 报告源]**&#x200B;选择&#x200B;**[!UICONTROL Adobe Analytics]**，然后选择与所需优化目标对应的报表包。

   ![“目标和设置”页面上的“报告源”部分](/help/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. 选择“主要目标”量度。

   * 要使用[!DNL Adobe Target]指定优化目标，请选择&#x200B;**[!UICONTROL 转换]**。
   * 选择&#x200B;**[!UICONTROL 使用Analytics量度]**，然后从[!DNL Analytics]中选择一个量度以用作优化目标。 您可以使用现成的[!DNL Analytics]转换量度或[!DNL Analytics]自定义事件。

   有关详细信息，请参阅下面的[支持的目标量度](#supported)。

1. 保存并激活您的活动。

   [!UICONTROL 自动分] 配使用您选择的量度来优化活动，从而将访客推向可最大化目标量度的体验。

   或

   [!UICONTROL 自动定] 位使用您选择的量度优化活动，从而推动访客获得个性化的最佳体验。

1. 使用&#x200B;**[!UICONTROL 报表]**&#x200B;选项卡，根据您选择的[!DNL Adobe Analytics]量度视图活动的报告。 在Analytics ]**中单击**[!UICONTROL &#x200B;视图，深入细分和进一步细分报告数据。

## 支持的目标量度{#supported}

[!UICONTROL A4T]  for  [!UICONTROL Auto-] Allocate和 [!UICONTROL Auto-Target] 允许您选择以下任意量度类型作为优化的主要目标量度：

* [!DNL Adobe Target] 转化量度
* [!DNL Adobe Analytics] 转化量度
* [!DNL Adobe Analytics] 个自定义事件

[!UICONTROL A4T]  for  [!UICONTROL Auto-] Allocate和 [!UICONTROL Auto-Target] 要求您选择基于二项式事件的量度。“二项式”事件是否发生。 二项式事件包括点击、转换、订购等。 这些类型的事件有时也称为伯努利、二进制或离散事件。

[!UICONTROL A4T]  for  [!UICONTROL Auto-] Allocate [!UICONTROL 和Auto-] Target不支持对连续量度进行优化。连续量度包括收入、订购产品数量、会话持续时间、会话中的页面视图数量等。 这些不受支持的量度类型有时也称为非二项式或非伯努利量度。

不支持以下量度类型作为主要目标量度：

* [!DNL Adobe Target] 参与度和收入指标
* [!DNL Adobe Analytics] 参与度和收入指标

   可以选择[!DNL Analytics]参与度或收入量度作为主要目标量度，因为[!DNL Target]无法识别和排除[!DNL Analytics]中的所有参与度和收入量度。 只选择[!DNL Analytics]中的二项式转换量度或自定义事件。

* [!DNL Adobe Analytics] 计算量度

## 限制和说明

某些限制和说明适用于[!UICONTROL 自动分配]和[!UICONTROL 自动目标]活动。 其他限制和注释适用于一种活动类型或另一种。

### 自动分配和自动目标

* 不能将报告源从[!DNL Analytics]更改为[!DNL Target]，或者在激活活动后将其更改为。
* 虽然不支持将计算量度作为主要目标量度，但通常可以通过选择自定义事件作为主要目标量度来达到预期效果。 例如，如果您要优化某个量度(如“每个访客的表单完成情况”)，请选择与“表单完成情况”对应的自定义事件作为您的主要目标量度。 [!DNL Target] 根据每次访问自动标准化转化量度，以考虑流量分布不均，因此无需使用计算量度来执行标准化。
* [!DNL Target] 在“自动分配”功能中使用“同 [!UICONTROL 一触] ”归因模型：目标分析(A4T)。

### 自动分配

* [!UICONTROL 自动分] 配模型继续像往常一样每两小时进行一次培训。

### 自动定位

* [!UICONTROL 自动定] 位模型继续像往常一样每24小时进行一次培训。但是，来自[!DNL Analytics]的转换事件数据会额外延迟6到24小时。 此延迟表示[!DNL Target]的流量分布跟踪[!DNL Analytics]中记录的最新事件。 在活动初始激活后的头48小时内，这种延迟的影响最大。 活动的性能将更密切地反映经过五天后的[!DNL Analytics]转换行为。 考虑对短时活动使用[!UICONTROL 自动分配]而不是[!UICONTROL 自动目标]，在短时中，大多数流量在活动生命周期的前五天内发生。
* 当使用[!DNL Analytics]作为[!UICONTROL 自动目标]活动的数据源时，会话在经过六小时后结束。 六小时后发生的转换不计算在内。

有关详细信息，请参阅&#x200B;*分析工具指南*&#x200B;中的[归因模型和回顾窗口](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html)。

## 教程：如何在Analysis Workspace中设置自动目标活动{#tutorial}的A4T报告

尽管[!DNL Adobe Analytics] [!UICONTROL Analysis Workspace]中提供了丰富的分析功能，但要正确解释自动目标活动，需要对默认的[!UICONTROL 目标]分析面板进行一些修改。 由于实验活动（手动A/B和[!UICONTROL 自动分配]）与个性化活动([!UICONTROL 自动目标])之间的差异，需要进行这些修改。

本教程将指导您完成分析[!UICONTROL Workspace]中的[!UICONTROL 自动目标]活动的建议修改。

有关详细信息，请参阅[如何在Analysis Workspace中为&#x200B;*Adobe TargetTutorials*&#x200B;中的自动目标活动](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html)设置A4T报告。
