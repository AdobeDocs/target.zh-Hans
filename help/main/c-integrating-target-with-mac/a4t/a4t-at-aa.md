---
keywords: A4T;A4T;Analytics作为Target的报表源；Analytics for Target
description: 了解如何创建 [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位] 活动 [!DNL Target] 使用 [!DNL Analytics] 作为报表源(A4T)。
title: A4T是否支持 [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位] 活动？
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: 39b4c0363cde97b07265403b680ad4ed899f5a64
workflow-type: tm+mt
source-wordcount: '1271'
ht-degree: 7%

---

# [!UICONTROL 自动分配]和[!UICONTROL 自动定位]活动支持 A4T

的 [!DNL Adobe Target] — 对 — [!DNL Adobe Analytics] 集成，称为 [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)支持 [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位] 活动。

A4T集成允许您：

* 使用 [自动分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) 多臂老虎机功能，可引导流量获得成功体验。
* 使用 [自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md) 组合机器学习算法，为每个访客选择最佳体验。 [!UICONTROL 自动定位] 在使用 [!DNL Adobe Analytics] 目标量度以及 [!DNL Adobe Analytics].

确保您具有 [实施了用于A/B测试和体验定位活动的A4T](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). 如果您使用 `analyticsLogging = client_side`，则还必须通过 `sessionId` 值 [!DNL Analytics]. 有关更多信息，请参阅 [Analytics for Target(A4T)报表](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html){target=_blank} 在 *Adobe Target开发人员指南*.

若要开始，请执行以下操作：

1. While [创建 [!UICONTROL A/B测试] 活动](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)，在 **[!UICONTROL 定位]** ，请选择以下选项之一作为 **[!UICONTROL 流量分配方法]**:

   * [!UICONTROL 自动分配到最佳体验]
   * [!UICONTROL 自动定位以提供个性化体验]

   ![流量分配方法选项：手动、自动分配和自动定位](/help/main/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   有关更多信息和分步说明，请参阅 [创建自动分配活动](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) 和 [创建自动定位活动](/help/main/c-activities/auto-target/create-auto-target.md).

1. 选择 **[!UICONTROL Adobe Analytics]** , **[!UICONTROL 报表源]** 在 **[!UICONTROL 目标和设置]** ，然后选择与所需优化目标对应的报表包。

   ![“目标和设置”页面上的“报表源”部分](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. 选择 [!UICONTROL 主要目标] 量度。

   * 使用 [!DNL Adobe Target] 要指定优化目标，请选择 **[!UICONTROL 转化]** .
   * 选择 **[!UICONTROL 使用Analytics量度]** 然后，从 [!DNL Analytics] ，用作优化目标。 您可以使用现成的 [!DNL Analytics] 转化量度或 [!DNL Analytics] 自定义事件。

   请参阅 [支持的目标量度](#supported) 下面以了解更多信息。

1. 保存并激活您的活动。

   [!UICONTROL 自动分配] 会使用您选择的量度来优化活动，从而引导访客体验最大化您的目标量度。

   或

   [!UICONTROL 自动定位] 会使用您选择的量度来优化活动，从而引导访客获得个性化的最佳体验。

1. 使用 **[!UICONTROL 报表]** 选项卡，以按您选择的 [!DNL Adobe Analytics] 量度。 单击 **[!UICONTROL 在Analytics中查看]** 以深入挖掘和进一步细分报表数据。

## 支持的目标量度 {#supported}

[!UICONTROL A4T] 表示 [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位] 允许您选择以下任意量度类型作为优化的主要目标量度：

* [!DNL Adobe Target] 转化量度
* [!DNL Adobe Analytics] 转化量度
* [!DNL Adobe Analytics] 个自定义事件

通过 [!DNL Target]，可在使用 [!UICONTROL A4T] 进行[!UICONTROL 自动分配]和[!UICONTROL 自动定位]活动时，根据二项式事件或连续事件选择指标。

* **基于二项式事件的量度**:二项式事件是否发生。 二项式事件包括点击、转换、订购等。 这些类型的事件有时也称为伯努利、二进制或离散事件。

* **基于连续事件的量度**. 连续量度包括收入、订购的产品数量、会话持续时间、会话中的页面查看次数，等等。 这些类型的事件有时也称为非二项式或非伯努利量度。

>[!IMPORTANT]
>
>截至 [!DNL Adobe Target Standard/Premium] 22.15.1版本（2023年3月8日和9日）， [!DNL Target] 继续支持现有活动的量度，这些量度现在不受支持（下表中列出）。 但是，2023年9月9日之后，现有活动将不再支持这些量度，并且所有使用不受支持量度的活动都将停止，以强制现有活动迁移到新行为。

### 对 [!UICONTROL 自动分配] 活动

| Metric name（量度名称） | 不再支持： |
| --- | --- |
| [!UICONTROL averagepagedepth] | 转化率，最大化量度值 |
| [!UICONTROL averagetimespentonsite] | 转化率，最大化量度值 |
| [!UICONTROL 跳出] | 转化率，最大化量度值 |
| [!UICONTROL bounces] | 转化率，最大化量度值 |
| [!UICONTROL 条目] | 转化率，最大化量度值 |
| [!UICONTROL 退出] | 转化率，最大化量度值 |
| [!UICONTROL pageviews] | 最大化量度值 |
| [!UICONTROL 重新加载] | 最大化量度值 |
| [!UICONTROL 访客数] | 转化率，最大化量度值 |
| [!UICONTROL 访问次数] | 最大化量度值 |

### 对 [!UICONTROL 自动定位] 活动

| Metric name（量度名称） | 不再支持： |
| --- | --- |
| [!UICONTROL 卡特雷瓦斯] | 最大化量度值 |
| [!UICONTROL pageviews] | 最大化量度值 |
| [!UICONTROL 访客数] | 转化率，最大化量度值 |
| [!UICONTROL 访问次数] | 最大化量度值 |

## 限制和说明

某些限制和说明同时适用于 [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位] 活动。 其他限制和说明适用于一种活动类型或另一种活动类型。

### 自动分配和自动定位 {#both}

* 使用 [!DNL Adobe Analytics] 作为报表源 [!UICONTROL 自动分配] 或 [!UICONTROL 自动定位]，则应始终在 [!DNL Analytics].
* 报表源不能从 [!DNL Analytics] to [!DNL Target] 活动激活后，反之亦然。
* 尽管计算量度不支持作为主要目标量度，但通常可以通过选择自定义事件作为主要目标量度来实现预期结果。 例如，如果要优化量度（如“每位访客的表单完成次数”），请选择与“表单完成次数”对应的自定义事件作为主要目标量度。 [!DNL Target] 自动按每次访问标准化转化量度，以考虑不均匀的流量分配，因此无需使用计算量度来执行标准化。

### 自动分配 {#aa}

* **培训频度**: [!UICONTROL 自动分配] 和往常一样，模特们继续每小时训练一次。
* **归因模型**: [!DNL Target] 使用 [!DNL Adobe Analytics] 默认归因模型[!UICONTROL  自动分配] 使用A4T的活动。
* **置信度**:使用的置信度公式 [!UICONTROL 自动分配] 活动与 [!DNL Adobe Analytics] [!UICONTROL A4T] 的上界。 [如下所述](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [!UICONTROL 自动分配] 使用比常规更保守的置信区间 [!UICONTROL A/B测试] 活动。 这些保守的置信水平补偿了重复的数据评价(peek)。 因此， [!DNL Adobe Analytics] 显示的置信区间比使用的区间窄 [!UICONTROL 自动分配] 算法。 但是，您可以根据哪些体验具有更多独特访客被发送到该体验，来确定算法最喜欢哪个体验。
* **入选者状态**:目前， [“还没有入选者”和“入选者”徽章](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) 在 [!UICONTROL A4T] 面板 [!DNL Analysis Workspace]. 如果在中查看同一报表，则这些徽章也将不可用 [!DNL Target]. 入选者“星形”标记，显示在 [!DNL Target] 报表 [!UICONTROL 自动分配] 应忽略使用A4T的活动。 此徽章反映的是常规的置信度计算，而不是 [!UICONTROL 自动分配].

### 自动定位 {#at}

* [!UICONTROL 自动定位] 与往常一样，模特每24小时继续训练一次。 但是，转化事件数据来自 [!DNL Analytics] 多拖6到24小时。 此延迟表示流量的分布方式 [!DNL Target] 跟踪中记录的最新事件 [!DNL Analytics]. 在活动初始激活后的前48小时内，此延迟产生的影响最大。 活动的性能更为接近镜像 [!DNL Analytics] 5天后的转化行为。

   请考虑使用 [!UICONTROL 自动分配] 而不是 [!UICONTROL 自动定位] 在短期活动中，大多数流量在活动生命周期的前五天内发生。

* 使用 [!DNL Analytics] 作为 [!UICONTROL 自动定位] 活动，会话在6小时后结束。 六小时后发生的转化不会被计算在内。

有关更多信息，请参阅 [归因模型和回顾时间范围](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) 在 *Analytics工具指南*.

## 教程

尽管在 [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace]，对默认值进行一些修改 [!UICONTROL Analytics for Target] 面板需要正确解释 [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位] 活动。 由于实验活动(手动A/B和 [!UICONTROL 自动分配])和个性化活动([!UICONTROL 自动定位])。

### 在 [!DNL Analysis Workspace] 中为[!UICONTROL 自动分配]活动设置 A4T 报表

本教程将指导您完成建议的用于分析的修改 [!UICONTROL 自动分配] 活动 [!DNL Analysis Workspace].

有关更多信息，请参阅 [如何在Analysis Workspace中为自动分配活动设置A4T报表](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank} in *Adobe TargetTutorials*.

### 在 [!DNL Analysis Workspace] 中为[!UICONTROL 自动定位]活动设置 A4T 报表

本教程将指导您完成建议的用于分析的修改 [!UICONTROL 自动定位] 活动 [!DNL Analysis Workspace].

有关更多信息，请参阅 [如何在Analysis Workspace中为自动定位活动设置A4T报表](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html){target=_blank} in *Adobe TargetTutorials*.


