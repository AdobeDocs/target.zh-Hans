---
keywords: a4t;A4T;Analytics 作为 Target 报表源
description: 了解如何在Adobe [!DNL Target] 中创建使用Analytics作为报表源(A4T)的自动分配和自动定位活动。
title: A4T是否支持自动分配和自动定位活动？
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: 103ee22a4bf37569f8a02a91af194ebcdc79f3b4
workflow-type: tm+mt
source-wordcount: '979'
ht-degree: 3%

---

# 自动分配和自动定位活动支持 A4T

[!DNL Adobe Target]-to-[!DNL Adobe Analytics]集成(称为[Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md)(A4T))支持[!UICONTROL 自动分配]和[!UICONTROL 自动定位]活动。

A4T集成允许您：

* 使用[自动分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)的多臂老虎机功能，引导流量进入入选体验。
* 使用[自动定位](/help/c-activities/auto-target/auto-target-to-optimize.md)的组合机器学习算法为每个访客选择最佳体验。 自动定位在使用[!DNL Adobe Analytics]目标量度和[!DNL Adobe Analytics]`丰富的报告和分析功能时，会根据用户的配置文件、行为和上下文选择最佳体验。

确保您已实施[A4T，以用于A/B测试和体验定位活动](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)。 如果您使用的是`analyticsLogging = client_side`，则还必须将`sessionId`值传递到[!DNL Analytics]。 有关更多信息，请参阅&#x200B;*Adobe Target SDK*&#x200B;指南中的[Analytics for Target(A4T)报表](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting)。

若要开始，请执行以下操作：

1. 创建A/B测试活动时，在&#x200B;**[!UICONTROL 定位]**&#x200B;页面上，选择以下选项之一作为&#x200B;**[!UICONTROL 流量分配方法]**:

   * [!UICONTROL 自动分配到最佳体验]
   * [!UICONTROL 自动定位以提供个性化体验]

   ![流量分配方法选项：手动、自动分配和自动定位](/help/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   有关更多信息和分步说明，请参阅[创建自动分配活动](/help/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)和[创建自动定位活动](/help/c-activities/auto-target/create-auto-target.md)。

1. 在&#x200B;**[!UICONTROL 目标和设置]**&#x200B;页面上为&#x200B;**[!UICONTROL 报表源]**&#x200B;选择&#x200B;**[!UICONTROL Adobe Analytics]**，然后选择与所需优化目标对应的报表包。

   ![“目标和设置”页面上的“报表源”部分](/help/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. 选择主要目标量度。

   * 要使用[!DNL Adobe Target]指定优化目标，请选择&#x200B;**[!UICONTROL 转化]** 。
   * 选择&#x200B;**[!UICONTROL 使用Analytics量度]**，然后从[!DNL Analytics]中选择一个量度以用作优化目标。 您可以使用现成的[!DNL Analytics]转化量度或[!DNL Analytics]自定义事件。

   有关更多信息，请参阅下面的[支持的目标量度](#supported)。

1. 保存并激活您的活动。

   [!UICONTROL 自动分配] 会使用您选择的量度来优化活动，从而促使访客体验到可最大化您的目标量度的体验。

   或

   [!UICONTROL 自动定位] 使用您选择的量度来优化活动，从而引导访客获得个性化的最佳体验。

1. 使用&#x200B;**[!UICONTROL 报表]**&#x200B;选项卡，按您选择的[!DNL Adobe Analytics]量度查看活动的报表。 单击&#x200B;**[!UICONTROL 在Analytics中查看]**&#x200B;可深入挖掘报表数据并进一步细分报表数据。

## 支持的目标量度 {#supported}

[!UICONTROL A4] 自动 [!UICONTROL 分配] 和自动 [!UICONTROL 定] 位允许您选择以下任何量度类型作为优化的主要目标量度：

* [!DNL Adobe Target] 转化量度
* [!DNL Adobe Analytics] 转化量度
* [!DNL Adobe Analytics] 个自定义事件

[!UICONTROL A4] 自动 [!UICONTROL 分配] 和自动 [!UICONTROL 定] 位要求您选择基于二项式事件的量度。二项式事件是否发生。 二项式事件包括点击、转换、订购等。 这些类型的事件有时也称为伯努利、二进制或离散事件。

[!UICONTROL A4] 自动分 [!UICONTROL 配] 和自动 [!UICONTROL 定] 位不支持对连续量度进行优化。连续量度包括收入、订购的产品数量、会话持续时间、会话中的页面查看次数，等等。 这些不受支持的量度类型有时也称为非二项式或非伯努利量度。

不支持将以下量度类型作为主要目标量度：

* [!DNL Adobe Target] 参与度和收入量度
* [!DNL Adobe Analytics] 参与度和收入量度

   可以选择[!DNL Analytics]参与度或收入量度作为主要目标量度，因为[!DNL Target]无法识别和排除[!DNL Analytics]中的所有参与度和收入量度。 仅选择[!DNL Analytics]中的二项式转化量度或自定义事件。

* [!DNL Adobe Analytics] 计算量度

## 限制和说明

某些限制和说明适用于[!UICONTROL 自动分配]和[!UICONTROL 自动定位]活动。 其他限制和说明适用于一种活动类型或另一种活动类型。

### 自动分配和自动定位

* 使用[!DNL Adobe Analytics]作为[!UICONTROL 自动分配]或[!UICONTROL 自动定位]的报表源时，应始终查看[!DNL Analytics]中的报表。
* 活动激活后，报表源不能从[!DNL Analytics]更改为[!DNL Target]，或者反过来也不能更改。
* 尽管计算量度不支持作为主要目标量度，但通常可以通过选择自定义事件作为主要目标量度来实现预期结果。 例如，如果要优化量度（如“每位访客的表单完成次数”），请选择与“表单完成次数”对应的自定义事件作为主要目标量度。 [!DNL Target] 自动按每次访问标准化转化量度，以考虑不均匀的流量分配，因此无需使用计算量度来执行标准化。
* [!DNL Target] 在自动分配功能中使用“同一接触” [!UICONTROL 归因] 模型：Analytics for Target(A4T)。

### 自动分配

* [!UICONTROL 与往常一样，] 自动分配模型会继续每两小时进行一次培训。

### 自动定位

* [!UICONTROL 与往常一样，] 自动定位模型会继续每24小时进行一次培训。但是，来自[!DNL Analytics]的转化事件数据会额外延迟6到24小时。 此延迟表示[!DNL Target]的流量分配跟踪[!DNL Analytics]中记录的最新事件。 在活动初始激活后的前48小时内，此延迟产生的影响最大。 活动的性能将更密切地反映5天后的[!DNL Analytics]转化行为。 考虑对短时间活动使用[!UICONTROL 自动分配]，而不是[!UICONTROL 自动定位]，在短时间活动中，大多数流量会在活动生命周期的前五天内发生。
* 使用[!DNL Analytics]作为[!UICONTROL 自动定位]活动的数据源时，会话会在经过六小时后结束。 六小时后发生的转化不会被计算在内。

有关更多信息，请参阅&#x200B;*Analytics工具指南*&#x200B;中的[归因模型和回顾窗口](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html)。

## 教程：如何在Analysis Workspace中为自动定位活动设置A4T报表 {#tutorial}

尽管[!DNL Adobe Analytics] [!UICONTROL Analysis Workspace]中提供了丰富的分析功能，但需要对默认的[!UICONTROL Analytics for Target]面板进行一些修改，才能正确解释自动定位活动。 由于实验活动（手动A/B和[!UICONTROL 自动分配]）与个性化活动（[!UICONTROL 自动定位]）之间存在差异，因此需要进行这些修改。

本教程将指导您完成建议的修改，以便在[!UICONTROL Workspace]中分析[!UICONTROL 自动定位]活动。

有关更多信息，请参阅&#x200B;*Adobe TargetTutorials*&#x200B;中的[如何在Analysis Workspace中为自动定位活动设置A4T报表](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html)。
