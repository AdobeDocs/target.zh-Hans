---
keywords: a4t；A4T；Analytics作为Target报表源；Analytics for Target
description: 了解如何在 [!DNL Target] 中创建使用 [!DNL Analytics] 作为报表源(A4T)的[!UICONTROL 自动分配]和[!UICONTROL 自动定位]活动。
title: A4T是否支持[!UICONTROL 自动分配]和[!UICONTROL 自动定位]活动？
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
TQID: https://experienceleague.adobe.com/VVbjMp7jYDyslZ8ubn8ntPufLK8nKGI9k3ZGh1DLWWs
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
subfeature_v2:
  - id: df62f171-ac37-440f-8f0f-f41a72ebdd34
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1509
ht-degree: 6%

---

# 对[!UICONTROL 自动分配]和[!UICONTROL 自动定位]活动的A4T支持

[!DNL Adobe Target]到 — [!DNL Adobe Analytics]的集成，称为[Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)，支持[!UICONTROL 自动分配]和[!UICONTROL 自动定位]活动。

通过A4T集成，您可以：

* 使用[自动分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)多臂赌博机功能将流量引导至入选体验。
* 使用[自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md)集成机器学习算法为每个访客选择最佳体验。 [!UICONTROL 自动定位]会根据每个用户的配置文件、行为和上下文选择最佳体验，同时使用[!DNL Adobe Analytics]目标量度和[!DNL Adobe Analytics]的丰富报告和分析功能。

确保您已实施[用于A/B测试和体验定位活动的A4T](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md)。 如果您使用`analyticsLogging = client_side`，则还必须将`sessionId`值传递给[!DNL Analytics]。 有关详细信息，请参阅&#x200B;*Adobe Target开发人员指南*&#x200B;中的[Analytics for Target (A4T)报表](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html){target=_blank}。

若要开始，请执行以下操作：

1. 在[创建[!UICONTROL A/B测试]活动](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)时，在&#x200B;**[!UICONTROL 定位]**&#x200B;页面上单击&#x200B;**[!UICONTROL 流量分配]**&#x200B;控件，然后在右窗格中选择所需的流量分配方法。

   ![流量分配方法设置](/help/main/c-activities/assets/auto-target.png)

   可以使用以下流量分配方法：

   * **[!UICONTROL 手动（默认）]**：指定您希望看到每个体验的参加者所占的百分比。 您可以将百分比平分到所有体验，或者也可以为每个体验指定较高或较低的百分比。 所有体验的百分比总和必须等于 100%。

   * **[!UICONTROL 自动分配到最佳体验]**：将大多数活动参加者自动定向到具有更高性能的体验。 为继续探索各体验并识别性能趋势的变化，某些访客会分配到所有体验。 有关详细信息，请参阅[[!UICONTROL 自动分配]概述](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)。

   * **[!UICONTROL 自动定位以提供个性化体验]**： [!DNL Target]使用先进的机器学习技术，确定多个高性能、由营销人员定义的体验，然后根据访客各自的客户配置文件和过去类似访客的行为，为其提供量身定制的体验，从而个性化内容并促进转化。 有关详细信息，请参阅[自动定位概述](/help/main/c-activities/auto-target/auto-target-to-optimize.md)。

   有关更多信息和分步说明，请参阅[创建自动分配活动](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)和[创建自动定位活动](/help/main/c-activities/auto-target/create-auto-target.md)。

1. 在&#x200B;**[!UICONTROL 目标和设置]**&#x200B;页面上为&#x200B;**[!UICONTROL 报表Source]**&#x200B;选择&#x200B;**[!UICONTROL Adobe Analytics]**，然后选择与所需优化目标对应的公司和报表包。

   在“目标和设置”页面上![报告Source部分](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. 指定跟踪服务器和沙盒。

1. 选择一个[!UICONTROL 主要目标]指标。

   * 要使用[!DNL Adobe Target]指定优化目标，请选择&#x200B;**[!UICONTROL 转化]** 。
   * 选择&#x200B;**[!UICONTROL 使用Analytics量度]**，然后从[!DNL Analytics]中选择一个量度以用作优化目标。 您可以使用现成的[!DNL Analytics]转化量度或[!DNL Analytics]自定义事件。

   有关详细信息，请参阅下面的[支持的目标指标](#supported)。

1. 保存并激活您的活动。

   [!UICONTROL 自动分配]使用您选择的量度优化活动，促使访客获得最大化目标量度的体验。

   或

   [!UICONTROL 自动定位]使用您选择的量度来优化活动，从而推动访客获得个性化的最佳体验。

1. 使用&#x200B;**[!UICONTROL 报表]**&#x200B;选项卡可查看您选择的[!DNL Adobe Analytics]指标的活动报表。 单击&#x200B;**[!UICONTROL 在Analytics中查看]**&#x200B;以深入分析并进一步细分您的报表数据。

## 支持的目标量度 {#supported}

[!UICONTROL 自动分配]和[!UICONTROL 自动定位]的[!UICONTROL A4T]允许您选择以下任何量度类型作为优化的主要目标量度：

* [!DNL Adobe Target]转化量度
* [!DNL Adobe Analytics]转化量度
* [!DNL Adobe Analytics]自定义事件

>[!NOTE]
>
>选择[!UICONTROL 使用Analytics量度]后，选择[!UICONTROL 最大化独特访客转化率]以查看可用的[!DNL Adobe Analytics]转化量度，选择[!UICONTROL 最大化每位访客的量度值]以探索[!DNL Adobe Analytics]个自定义事件。

在为[!UICONTROL 自动分配]和[!UICONTROL 自动定位]活动使用[!UICONTROL A4T]时，[!DNL Target]允许您选择基于二项式事件的量度或基于连续事件的量度。

* **基于二项式事件的量度**：二项式事件不会发生。 二项式事件包括点击、转化、排序等。 这些事件类型有时也称为伯努利事件、二元事件或离散事件。

* **基于连续事件的量度**。 连续量度包括收入、订购的产品数量、会话持续时间、会话中的页面查看次数等。 这些类型的事件有时也称为非二项式或非伯努利量度。

>[!IMPORTANT]
>
>自[!DNL Adobe Target Standard/Premium] 22.15.1版本（2023年3月8日和9日）起，[!DNL Target]将继续支持其量度现在不受支持的现有活动（如下表所列）。 但是，在2023年9月9日之后，现有活动将不再支持这些量度，并将停止所有使用不受支持的量度的活动，以强制现有活动迁移到新行为。

### 对[!UICONTROL 自动分配]活动的影响

| 量度名称 | 不再支持： |
| --- | --- |
| [!UICONTROL averagepagedepth] | 转化率，最大化量度值 |
| [!UICONTROL averagetimespentonsite] | 转化率，最大化量度值 |
| [!UICONTROL 退回] | 转化率，最大化量度值 |
| [!UICONTROL 退回] | 转化率，最大化量度值 |
| [!UICONTROL 条目] | 转化率，最大化量度值 |
| [!UICONTROL 退出] | 转化率，最大化量度值 |
| [!UICONTROL 页面查看次数] | 最大化量度值 |
| [!UICONTROL 重新加载] | 最大化量度值 |
| [!UICONTROL 个访客] | 转化率，最大化量度值 |
| [!UICONTROL 次访问] | 最大化量度值 |

### 对[!UICONTROL 自动定位]活动的影响

| 量度名称 | 不再支持： |
| --- | --- |
| [!UICONTROL cartremovals] | 最大化量度值 |
| [!UICONTROL 页面查看次数] | 最大化量度值 |
| [!UICONTROL 个访客] | 转化率，最大化量度值 |
| [!UICONTROL 次访问] | 最大化量度值 |

## 限制和注释

某些限制和注释同时适用于[!UICONTROL 自动分配]和[!UICONTROL 自动定位]活动。 其他限制和注释适用于一种活动类型或另一种活动类型。

### 自动分配和自动定位 {#both}

* 使用[!DNL Adobe Analytics]作为[!UICONTROL 自动分配]或[!UICONTROL 自动定位]的报告源时，您应始终在[!DNL Analytics]中查看报告。
* 激活活动后，无法将报表源从[!DNL Analytics]更改为[!DNL Target]，反之亦然。
* 尽管不支持将计算量度作为主要目标量度，但通常可以通过选择自定义事件作为主要目标量度来实现预期结果。 例如，如果要优化某个量度（例如“每位访客的表单完成次数”），请选择与“表单完成次数”对应的自定义事件作为主要目标量度。 [!DNL Target]基于每次访问自动标准化转化量度，以解决流量分配不均衡的问题，因此无需使用计算量度来执行标准化。

### 自动分配 {#aa}

* **训练频率**： [!UICONTROL 自动分配]模型继续像往常一样每小时训练一次。
* **归因模型**： [!DNL Target]对使用A4T的[!UICONTROL 自动分配]活动使用[!DNL Adobe Analytics]默认归因模型。
* **置信度**： [!UICONTROL 自动分配]活动使用的置信度公式与[!DNL Adobe Analytics] [!UICONTROL A4T]面板中默认显示的公式不同。 [如此处](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)所述，[!UICONTROL 自动分配]使用比常规[!UICONTROL A/B测试]活动更保守的置信区间。 这些保守的置信水平可补偿对数据的重复评估（窥视）。 因此，与[!UICONTROL 自动分配]算法使用的置信区间相比，[!DNL Adobe Analytics]中的默认报表显示的置信区间更窄。 但是，您可以根据向哪个体验发送了更多独特访客，来确定哪个体验受到算法青睐。
* **获胜者状态**：当前，[!DNL Analysis Workspace]中的[!UICONTROL A4T]面板中不存在[“还没有获胜者”和“获胜者”徽章](/help/main/c-activities/automated-traffic-allocation/determine-winner.md)。 如果在[!DNL Target]中查看了同一报告，则这些徽章也将不可用。 使用A4T的[!UICONTROL 自动分配]活动的[!DNL Target]报表中显示的入选者“星级”徽章应当被忽略。 此徽章反映的是常规置信度计算，而不是[!UICONTROL 自动分配]使用的计算。

### 自动锁定 {#at}

* [!UICONTROL 自动定位]模型继续像往常一样每24小时训练一次。 但是，来自[!DNL Analytics]的转化事件数据将再延迟6到24小时。 此延迟意味着[!DNL Target]的流量分配将跟踪[!DNL Analytics]中记录的最新事件。 在活动最初激活后的前48小时内，此延迟具有最大的影响。 该活动的性能在五天后更密切地反映[!DNL Analytics]转化行为。

  考虑对大多数流量发生在活动生命周期前五天的短期活动使用[!UICONTROL 自动分配]，而不是[!UICONTROL 自动定位]。

* 使用[!DNL Analytics]作为[!UICONTROL 自动定位]活动的数据源时，会话在六小时后结束。 六小时后发生的转化不计算在内。

有关详细信息，请参阅&#x200B;*Analytics工具指南*&#x200B;中的[归因模型和回顾窗口](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html)。

## 教程

尽管[!DNL Adobe Analytics] [!UICONTROL Analysis Workspace]提供了丰富的分析功能，但是仍需要对默认[!UICONTROL Analytics for Target]面板进行一些修改，才能正确解释[!UICONTROL 自动分配]和[!UICONTROL 自动定位]活动。 由于实验活动（手动A/B和[!UICONTROL 自动分配]）与个性化活动（[!UICONTROL 自动定位]）之间存在差异，因此需要做出这些修改。

### 在[!DNL Analysis Workspace]中为[!UICONTROL 自动分配]活动设置A4T报表

本教程将指导您完成为分析[!DNL Analysis Workspace]中的[!UICONTROL 自动分配]活动而建议的修改。

有关详细信息，请参阅&#x200B;*Adobe Target教程*&#x200B;中的[如何在Analysis Workspace中为自动分配活动设置A4T报表](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=zh-Hans){target=_blank}。

### 在[!DNL Analysis Workspace]中为[!UICONTROL 自动定位]活动设置A4T报表

本教程将指导您完成为分析[!DNL Analysis Workspace]中的[!UICONTROL 自动定位]活动而建议的修改。

有关详细信息，请参阅&#x200B;*Analysis Workspace教程*&#x200B;中的[如何在Adobe Target中为自动定位活动设置A4T报告](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=zh-Hans){target=_blank}。


