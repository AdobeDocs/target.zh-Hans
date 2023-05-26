---
keywords: a4t；A4T；Analytics作为Target报表源；Analytics for Target
description: 了解如何创建 [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位] 中的活动 [!DNL Target] 使用 [!DNL Analytics] 作为报表源(A4T)。
title: A4T是否支持 [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位] 活动？
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: 99bd509988a7d1545a6a1fe59aa59f35ef0a7d11
workflow-type: tm+mt
source-wordcount: '1271'
ht-degree: 7%

---

# [!UICONTROL 自动分配]和[!UICONTROL 自动定位]活动支持 A4T

此 [!DNL Adobe Target]-to-[!DNL Adobe Analytics] 集成，称为 [目标分析](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)，支持 [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位] 活动。

通过A4T集成，您可以：

* 使用 [自动分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) 多臂老虎机功能可将流量引向入选的体验。
* 使用 [自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md) 集成机器学习算法，用于为每个访客选择最佳体验。 [!UICONTROL 自动定位] 在使用时，根据每个用户的个人资料、行为和上下文选择最佳体验 [!DNL Adobe Analytics] 的目标量度和丰富的报告和分析功能 [!DNL Adobe Analytics].

确保您拥有 [实施了A4T以用于A/B测试和体验定位活动](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). 如果您使用 `analyticsLogging = client_side`，您还必须传递 `sessionId` 值至 [!DNL Analytics]. 有关更多信息，请参阅 [Analytics for Target (A4T)报表](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html){target=_blank} 在 *Adobe Target开发人员指南*.

若要开始，请执行以下操作：

1. While [创建 [!UICONTROL A/B测试] 活动](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)，位于 **[!UICONTROL 定位]** 页面上，选择以下选项之一作为 **[!UICONTROL 流量分配方法]**：

   * [!UICONTROL 自动分配到最佳体验]
   * [!UICONTROL 自动定位以提供个性化体验]

   ![流量分配方法选项：“手动”、“自动分配”和“自动定位”](/help/main/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   有关更多信息和分步说明，请参阅 [创建自动分配活动](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) 和 [创建自动定位活动](/help/main/c-activities/auto-target/create-auto-target.md).

1. 选择 **[!UICONTROL Adobe Analytics]** 您的 **[!UICONTROL 报表源]** 在 **[!UICONTROL 目标和设置]** 页面并选择与所需优化目标对应的报表包。

   ![“目标和设置”页面上的“报表源”部分](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. 选择 [!UICONTROL 主要目标] 量度。

   * 使用 [!DNL Adobe Target] 要指定优化目标，请选择 **[!UICONTROL 转化]** .
   * 选择 **[!UICONTROL 使用Analytics量度]** 然后从中选择一个量度 [!DNL Analytics] 用作优化目标。 您可以使用现成的 [!DNL Analytics] 转化量度或 [!DNL Analytics] 自定义事件。

   参见 [支持的目标量度](#supported) 有关更多信息，请参阅下文。

1. 保存并激活您的活动。

   [!UICONTROL 自动分配] 使用您选择的量度优化活动，促使访客体验最大化您的目标量度。

   或

   [!UICONTROL 自动定位] 使用您选择的量度优化活动，推动访客获得最佳个性化体验。

1. 使用 **[!UICONTROL 报告]** 选项卡以查看活动报表，方法是 [!DNL Adobe Analytics] 量度。 单击 **[!UICONTROL 在Analytics中查看]** 以深入了解并进一步细分您的报表数据。

## 支持的目标量度 {#supported}

[!UICONTROL A4T] 对象 [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位] 允许您选择以下任何量度类型作为优化的主要目标量度：

* [!DNL Adobe Target] 转化量度
* [!DNL Adobe Analytics] 转化量度
* [!DNL Adobe Analytics] 个自定义事件

通过 [!DNL Target]，可在使用 [!UICONTROL A4T] 进行[!UICONTROL 自动分配]和[!UICONTROL 自动定位]活动时，根据二项式事件或连续事件选择指标。

* **基于二项式事件的量度**：二项式事件不会发生。 二项式事件包括点击、转化、排序等。 这些事件类型有时也称为伯努利事件、二元事件或离散事件。

* **基于连续事件的量度**. 连续量度包括收入、订购的产品数量、会话持续时间、会话中的页面查看次数等。 这些类型的事件有时也称为非二项式或非伯努利量度。

>[!IMPORTANT]
>
>截至 [!DNL Adobe Target Standard/Premium] 22.15.1版（2023年3月8日和9日）， [!DNL Target] 通过现在不受支持的量度（如下表中所列）继续支持现有活动。 但是，在2023年9月9日之后，现有活动将不再支持这些量度，并且所有使用不受支持的量度的活动都将停止，以强制现有活动迁移到新行为。

### 对的影响 [!UICONTROL 自动分配] 活动

| Metric name（量度名称） | 不再支持： |
| --- | --- |
| [!UICONTROL averagepagedepth] | 转化率，最大化量度值 |
| [!UICONTROL averagetimespentonsite] | 转化率，最大化量度值 |
| [!UICONTROL 退回] | 转化率，最大化量度值 |
| [!UICONTROL bounces] | 转化率，最大化量度值 |
| [!UICONTROL 条目] | 转化率，最大化量度值 |
| [!UICONTROL 退出点] | 转化率，最大化量度值 |
| [!UICONTROL 页面查看次数] | 最大化量度值 |
| [!UICONTROL 重新载入] | 最大化量度值 |
| [!UICONTROL 访客数] | 转化率，最大化量度值 |
| [!UICONTROL 访问次数] | 最大化量度值 |

### 对的影响 [!UICONTROL 自动定位] 活动

| Metric name（量度名称） | 不再支持： |
| --- | --- |
| [!UICONTROL 卡特勒莫瓦尔] | 最大化量度值 |
| [!UICONTROL 页面查看次数] | 最大化量度值 |
| [!UICONTROL 访客数] | 转化率，最大化量度值 |
| [!UICONTROL 访问次数] | 最大化量度值 |

## 限制和注释

某些限制和注释同时适用于两者 [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位] 活动。 其他限制和注释适用于一种活动类型或另一种活动类型。

### 自动分配和自动定位 {#both}

* 使用时 [!DNL Adobe Analytics] 作为的报表源 [!UICONTROL 自动分配] 或 [!UICONTROL 自动定位]，您应始终在中查看报表 [!DNL Analytics].
* 无法更改报表源 [!DNL Analytics] 到 [!DNL Target] 在激活活动后，反之亦然。
* 尽管不支持将计算量度作为主要目标量度，但通常可以通过选择自定义事件作为主要目标量度来实现预期结果。 例如，如果要优化某个指标（如“每位访客的表单完成次数”），请选择与“表单完成次数”对应的自定义事件作为主要目标指标。 [!DNL Target] 自动标准化基于每次访问的转化量度以考虑不均衡的流量分布，因此无需使用计算量度来执行标准化。

### 自动分配 {#aa}

* **训练频率**： [!UICONTROL 自动分配] 和往常一样，模特们每小时都要训练一次。
* **归因模型**： [!DNL Target] 使用 [!DNL Adobe Analytics] 默认归因模型[!UICONTROL  自动分配] 使用A4T的活动。
* **置信度**：使用的置信度公式 [!UICONTROL 自动分配] 活动与中默认显示的公式不同 [!DNL Adobe Analytics] [!UICONTROL A4T] 面板。 [如此处所述](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)， [!UICONTROL 自动分配] 使用比常规置信区间更保守的置信区间 [!UICONTROL A/B测试] 活动。 这些保守的置信水平可补偿对数据的反复评估（窥视）。 因此，中的默认报表 [!DNL Adobe Analytics] 显示的置信区间比正使用的那些区间窄。 [!UICONTROL 自动分配] 算法。 但是，您可以根据向哪个体验发送了更多独特访客，来确定算法更喜欢哪个体验。
* **入选者状态**：目前， [“还没有入选者”和“入选者”徽章](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) 在中不可用 [!UICONTROL A4T] 面板位于 [!DNL Analysis Workspace]. 在以下位置查看同一报表时，这些徽章也将不可用： [!DNL Target]. 中显示的入选者“星”徽章 [!DNL Target] 报告 [!UICONTROL 自动分配] 使用A4T的活动应被忽略。 此徽章反映常规置信度计算，而不是由使用的计算。 [!UICONTROL 自动分配].

### 自动定位 {#at}

* [!UICONTROL 自动定位] 和往常一样，模型每隔24小时训练一次。 但是，转化事件数据来自 [!DNL Analytics] 又延迟了6到24小时。 这种延迟是指流量分配方式 [!DNL Target] 跟踪中记录的最新事件 [!DNL Analytics]. 在活动最初激活后的前48小时内，此延迟具有最大的影响。 该活动的性能镜像得更加紧密 [!DNL Analytics] 5天后的转化行为。

   考虑使用 [!UICONTROL 自动分配] 而不是 [!UICONTROL 自动定位] 对于短期活动，其大多数流量发生在活动寿命的前五天内。

* 使用时 [!DNL Analytics] 作为 [!UICONTROL 自动定位] 活动，会话在六小时后结束。 六小时后发生的转化不计算在内。

有关更多信息，请参阅 [归因模型和回顾时间范围](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) 在 *Analytics工具指南*.

## 教程

尽管中提供了丰富的分析功能， [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace]，对默认进行了一些修改 [!UICONTROL 目标分析] 需要面板才能正确解释 [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位] 活动。 由于试验活动之间的差异(手动A/B和 [!UICONTROL 自动分配])和个性化活动([!UICONTROL 自动定位])。

### 在 [!DNL Analysis Workspace] 中为[!UICONTROL 自动分配]活动设置 A4T 报表

本教程将指导您完成建议的用于分析的修改 [!UICONTROL 自动分配] 中的活动 [!DNL Analysis Workspace].

有关更多信息，请参阅 [如何在Analysis Workspace中为自动分配活动设置A4T报表](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank} 在 *Adobe TargetTutorials*.

### 在 [!DNL Analysis Workspace] 中为[!UICONTROL 自动定位]活动设置 A4T 报表

本教程将指导您完成建议的用于分析的修改 [!UICONTROL 自动定位] 中的活动 [!DNL Analysis Workspace].

有关更多信息，请参阅 [如何在Analysis Workspace中为自动定位活动设置A4T报表](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html){target=_blank} 在 *Adobe TargetTutorials*.


