---
keywords: a4t；A4T；Analytics作为Target报表源；Analytics for Target
description: 了解如何在 [!DNL Target] 中创建使用 [!DNL Analytics] 作为报表源(A4T)的[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]活动。
title: A4T是否支持[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]活动？
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: 80e4741f5f501a48b15b718c6c0bf55a86c4d676
workflow-type: tm+mt
source-wordcount: '1146'
ht-degree: 1%

---

# 对[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]活动的A4T支持

[!DNL Adobe Target]到 — [!DNL Adobe Analytics]的集成，称为[Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)，支持[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]活动。

通过A4T集成，您可以：

* 使用[自动分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)多臂赌博机功能将流量引导至入选体验。
* 使用[自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md)集成机器学习算法为每个访客选择最佳体验。 [!UICONTROL Auto-Target]会根据每个用户的配置文件、行为和上下文选择最佳体验，同时使用[!DNL Adobe Analytics]目标量度和[!DNL Adobe Analytics]的丰富报告和分析功能。

确保您已实施[用于A/B测试和体验定位活动的A4T](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md)。 如果您使用`analyticsLogging = client_side`，则还必须将`sessionId`值传递给[!DNL Analytics]。 有关详细信息，请参阅&#x200B;*Adobe Target开发人员指南*&#x200B;中的[Analytics for Target (A4T)报表](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html?lang=zh-Hans){target=_blank}。

若要开始，请执行以下操作：

1. 在[创建[!UICONTROL A/B Test]活动](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)时，在&#x200B;**[!UICONTROL Targeting]**&#x200B;页面上，选择以下选项之一作为&#x200B;**[!UICONTROL Traffic Allocation Method]**：

   * [!UICONTROL Auto-Allocate to best experience]
   * [!UICONTROL Auto-Target for personalized experiences]

   ![流量分配方法选项：“手动”、“自动分配”和“自动定位”](/help/main/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   有关更多信息和分步说明，请参阅[创建自动分配活动](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)和[创建自动定位活动](/help/main/c-activities/auto-target/create-auto-target.md)。

1. 在&#x200B;**[!UICONTROL Goals & Settings]**&#x200B;页面上为&#x200B;**[!UICONTROL Reporting Source]**&#x200B;选择&#x200B;**[!UICONTROL Adobe Analytics]**，然后选择与所需优化目标对应的报表包。

   在“目标和设置”页面上![报告Source部分](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. 选择[!UICONTROL Primary Goal]量度。

   * 要使用[!DNL Adobe Target]指定优化目标，请选择&#x200B;**[!UICONTROL Conversion]** 。
   * 选择&#x200B;**[!UICONTROL Use an Analytics metric]**，然后从[!DNL Analytics]中选择一个量度以用作优化目标。 您可以使用现成的[!DNL Analytics]转化量度或[!DNL Analytics]自定义事件。

   有关详细信息，请参阅下面的[支持的目标指标](#supported)。

1. 保存并激活您的活动。

   [!UICONTROL Auto-Allocate]使用您选择的量度优化活动，促使访客获得最大化您的目标量度的体验。

   或

   [!UICONTROL Auto-Target]使用您选择的量度来优化活动，从而推动访客获得个性化的最佳体验。

1. 使用&#x200B;**[!UICONTROL Reports]**&#x200B;选项卡可查看您选择的[!DNL Adobe Analytics]指标所生成的活动报表。 单击&#x200B;**[!UICONTROL View in Analytics]**&#x200B;以深入分析并进一步细分您的报表数据。

## 支持的目标量度 {#supported}

[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]的[!UICONTROL A4T]允许您选择以下任一指标类型作为优化的主要目标指标：

* [!DNL Adobe Target]转化量度
* [!DNL Adobe Analytics]转化量度
* [!DNL Adobe Analytics]自定义事件

>[!NOTE]
>
>选择[!UICONTROL Use an Analytics Metric]后，选择[!UICONTROL Maximize Unique Visitor Conversion Rate]以查看可用的[!DNL Adobe Analytics]转化量度，选择[!UICONTROL Maximize Metric Value per Visitor]以浏览[!DNL Adobe Analytics]自定义事件。

在为[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]活动使用[!UICONTROL A4T]时，[!DNL Target]允许您选择基于二项式事件的量度或基于连续事件的量度。

* **基于二项式事件的量度**：二项式事件不会发生。 二项式事件包括点击、转化、排序等。 这些事件类型有时也称为伯努利事件、二元事件或离散事件。

* **基于连续事件的量度**。 连续量度包括收入、订购的产品数量、会话持续时间、会话中的页面查看次数等。 这些类型的事件有时也称为非二项式或非伯努利量度。

>[!IMPORTANT]
>
>自[!DNL Adobe Target Standard/Premium] 22.15.1版本（2023年3月8日和9日）起，[!DNL Target]将继续支持其量度现在不受支持的现有活动（如下表所列）。 但是，在2023年9月9日之后，现有活动将不再支持这些量度，并将停止所有使用不受支持的量度的活动，以强制现有活动迁移到新行为。

### 对[!UICONTROL Auto-Allocate]活动的影响

| 量度名称 | 不再支持： |
| --- | --- |
| [!UICONTROL averagepagedepth] | 转化率，最大化量度值 |
| [!UICONTROL averagetimespentonsite] | 转化率，最大化量度值 |
| [!UICONTROL bouncerate] | 转化率，最大化量度值 |
| [!UICONTROL bounces] | 转化率，最大化量度值 |
| [!UICONTROL entries] | 转化率，最大化量度值 |
| [!UICONTROL exits] | 转化率，最大化量度值 |
| [!UICONTROL pageviews] | 最大化量度值 |
| [!UICONTROL reloads] | 最大化量度值 |
| [!UICONTROL visitors] | 转化率，最大化量度值 |
| [!UICONTROL visits] | 最大化量度值 |

### 对[!UICONTROL Auto-Target]活动的影响

| 量度名称 | 不再支持： |
| --- | --- |
| [!UICONTROL cartremovals] | 最大化量度值 |
| [!UICONTROL pageviews] | 最大化量度值 |
| [!UICONTROL visitors] | 转化率，最大化量度值 |
| [!UICONTROL visits] | 最大化量度值 |

## 限制和注释

某些限制和注释同时适用于[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]活动。 其他限制和注释适用于一种活动类型或另一种活动类型。

### 自动分配和自动定位 {#both}

* 使用[!DNL Adobe Analytics]作为[!UICONTROL Auto-Allocate]或[!UICONTROL Auto-Target]的报告源时，您应始终在[!DNL Analytics]中查看报告。
* 激活活动后，无法将报表源从[!DNL Analytics]更改为[!DNL Target]，反之亦然。
* 尽管不支持将计算量度作为主要目标量度，但通常可以通过选择自定义事件作为主要目标量度来实现预期结果。 例如，如果要优化某个量度（例如“每位访客的表单完成次数”），请选择与“表单完成次数”对应的自定义事件作为主要目标量度。 [!DNL Target]基于每次访问自动标准化转化量度，以解决流量分配不均衡的问题，因此无需使用计算量度来执行标准化。

### 自动分配 {#aa}

* **训练频率**：像往常一样，每小时继续训练[!UICONTROL Auto-Allocate]个模型。
* **归因模型**： [!DNL Target]对使用A4T的[!UICONTROL &#x200B; Auto-Allocate]活动使用[!DNL Adobe Analytics]默认归因模型。
* **置信度**： [!UICONTROL Auto-Allocate]活动使用的置信度公式与[!DNL Adobe Analytics] [!UICONTROL A4T]面板中默认显示的公式不同。 [如此处](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)所述，[!UICONTROL Auto-Allocate]使用比常规[!UICONTROL A/B Test]活动更保守的置信区间。 这些保守的置信水平可补偿对数据的重复评估（窥视）。 因此，[!DNL Adobe Analytics]中的默认报表显示的置信区间比[!UICONTROL Auto-Allocate]算法所使用的那些区间窄。 但是，您可以根据向哪个体验发送了更多独特访客，来确定哪个体验受到算法青睐。
* **获胜者状态**：当前，[!DNL Analysis Workspace]中的[!UICONTROL A4T]面板中不存在[“还没有获胜者”和“获胜者”徽章](/help/main/c-activities/automated-traffic-allocation/determine-winner.md)。 如果在[!DNL Target]中查看了同一报告，则这些徽章也将不可用。 使用A4T的[!UICONTROL Auto-Allocate]活动的[!DNL Target]报表中显示的入选者“星”徽章应当被忽略。 此徽章反映的是常规置信度计算，而不是[!UICONTROL Auto-Allocate]使用的计算。

### 自动锁定 {#at}

* [!UICONTROL Auto-Target]模型继续像往常一样每24小时训练一次。 但是，来自[!DNL Analytics]的转化事件数据将再延迟6到24小时。 此延迟意味着[!DNL Target]的流量分配将跟踪[!DNL Analytics]中记录的最新事件。 在活动最初激活后的前48小时内，此延迟具有最大的影响。 该活动的性能在五天后更密切地反映[!DNL Analytics]转化行为。

  对于大多数流量发生在活动生命周期前五天的短期活动，请考虑使用[!UICONTROL Auto-Allocate]而不是[!UICONTROL Auto-Target]。

* 使用[!DNL Analytics]作为[!UICONTROL Auto-Target]活动的数据源时，会话在六小时后结束。 六小时后发生的转化不计算在内。

有关详细信息，请参阅&#x200B;*Analytics工具指南*&#x200B;中的[归因模型和回顾窗口](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html?lang=zh-Hans)。

## 教程

尽管[!DNL Adobe Analytics] [!UICONTROL Analysis Workspace]中提供了丰富的分析功能，但需要对默认[!UICONTROL Analytics for Target]面板进行一些修改才能正确解释[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]活动。 由于试验活动（手动A/B和[!UICONTROL Auto-Allocate]）和个性化活动([!UICONTROL Auto-Target])之间存在差异，因此需要进行这些修改。

### 在[!DNL Analysis Workspace]中为[!UICONTROL Auto-Allocate]活动设置A4T报表

本教程将指导您完成为分析[!DNL Analysis Workspace]中的[!UICONTROL Auto-Allocate]活动而建议的修改。

有关详细信息，请参阅&#x200B;*Analysis Workspace教程*&#x200B;中的[如何在Adobe Target中为自动分配活动设置A4T报表](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=zh-Hans){target=_blank}。

### 在[!DNL Analysis Workspace]中为[!UICONTROL Auto-Target]活动设置A4T报表

本教程将指导您完成为分析[!DNL Analysis Workspace]中的[!UICONTROL Auto-Target]活动而建议的修改。

有关详细信息，请参阅&#x200B;*Analysis Workspace教程*&#x200B;中的[如何在Adobe Target中为自动定位活动设置A4T报告](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=zh-Hans){target=_blank}。


