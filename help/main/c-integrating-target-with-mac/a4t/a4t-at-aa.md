---
keywords: a4t;A4T;Analytics 作为 Target 报表源
description: 了解如何在Adobe中创建自动分配和自动定位活动 [!DNL Target] 使用Analytics作为报表源(A4T)的报表包。
title: A4T是否支持自动分配和自动定位活动？
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: e8fc28ef2497c1dfea523a769c9c817cbd74fea2
workflow-type: tm+mt
source-wordcount: '1695'
ht-degree: 3%

---

# 自动分配和自动定位活动支持 A4T

的 [!DNL Adobe Target] — 对 — [!DNL Adobe Analytics] 集成，称为 [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)支持 [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位] 活动。

A4T集成允许您：

* 使用 [自动分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)提供多臂老虎机功能，可引导流量获得成功体验。
* 使用 [自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md)的集成机器学习算法，为每个访客选择最佳体验。 自动定位在使用 [!DNL Adobe Analytics] 目标量度和 [!DNL Adobe Analytics]“丰富的报告和分析功能。

确保您已 [实施了用于A/B测试和体验定位活动的A4T](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). 如果您使用 `analyticsLogging = client_side`，则还必须通过 `sessionId` 值 [!DNL Analytics]. 有关更多信息，请参阅 [Analytics for Target(A4T)报表](https://developer.adobe.com/target/implement/server-side/sdk-guides/integration-with-experience-cloud/a4t-reporting/){target=_blank} *Adobe Target SDK* 的双曲余切值。

若要开始，请执行以下操作：

1. 创建A/B测试活动时，在 **[!UICONTROL 定位]** ，请选择以下选项之一作为 **[!UICONTROL 流量分配方法]**:

   * [!UICONTROL 自动分配到最佳体验]
   * [!UICONTROL 自动定位以提供个性化体验]

   ![流量分配方法选项：手动、自动分配和自动定位](/help/main/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   有关更多信息和分步说明，请参阅 [创建自动分配活动](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) 和 [创建自动定位活动](/help/main/c-activities/auto-target/create-auto-target.md).

1. 选择 **[!UICONTROL Adobe Analytics]** , **[!UICONTROL 报表源]** 在 **[!UICONTROL 目标和设置]** ，然后选择与所需优化目标对应的报表包。

   ![“目标和设置”页面上的“报表源”部分](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. 选择主要目标量度。 第一个下拉菜单允许您在 [!DNL Adobe Target] (随后将由 [!DNL Adobe Analytics] 作为“活动转化”量度)，或者 [!DNL Analytics] 量度。

   * 使用 [!DNL Adobe Target] 要指定优化目标，请选择 **[!UICONTROL 转化]**，然后指定受众必须执行的操作以指示已实现转化目标。
   * 如果改为选择 **[!UICONTROL 使用Analytics量度]**，则会为您提供应使用哪种类型的优化标准的选项。  请参阅 [支持的目标量度和优化标准](#supported) 下面以了解更多信息。 指定优化条件后，您可以从中选择一个兼容的量度 [!DNL Analytics] ，用作优化目标。 您可以使用现成的 [!DNL Analytics] 转化量度或 [!DNL Analytics] 自定义事件。


1. 保存并激活您的活动。

   [!UICONTROL 自动分配] 会使用您选择的量度来优化活动，从而引导访客体验最大化您的目标量度。

   或

   [!UICONTROL 自动定位] 会使用您选择的量度来优化活动，从而引导访客获得个性化的最佳体验。

1. 使用 **[!UICONTROL 报表]** 选项卡，以查看活动的报表并单击 **[!UICONTROL 在Analytics中查看]** 可在Adobe Analytics工作区中深入挖掘和进一步细分报表数据。 您可以按照以下教程查看如何在Workspace中设置报表：
* 自动分配：请参阅 [如何在Analysis Workspace中为自动分配活动设置A4T报表](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) in *Adobe TargetTutorials*
* 自动定位：请参阅 [如何在Analysis Workspace中为自动定位活动设置A4T报表](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) in *Adobe TargetTutorials*.

## 支持的目标量度和优化标准 {#supported}

[!UICONTROL A4T] 表示 [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位] 允许您选择以下任意量度类型作为优化的主要目标量度：

* [!DNL Adobe Target] 转化量度
* [!DNL Adobe Analytics] 转化量度
* [!DNL Adobe Analytics] 个自定义事件

但是， [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位] 模型将针对 **归一化** 这些量度的版本，并根据活动类型进行精确标准化。 下表说明了每种活动类型的优化标准选项：

| 活动类型 | 量度源 | 优化标准 | 描述 |
|---------------|---------------|-----------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 自动分配 | Analytics | 最大化独特访客转化率 | 模型会尝试查找具有最高独特访客转化率的体验，该转化率定义为分析量度为非零的访客数除以总访客数（接收到该体验的访客数）。 这意味着量度将被视为二进制文件 — 对于活动中的每个独特访客，为0或1。   如果您只关心执行特定操作的用户比例，或者单个用户的多个转化事件没有意义，则使用此选项。 |
| 自动分配 | Analytics | 最大化每位访客的量度值 | 模型会尝试查找每个访客具有最高量度值的体验，该量度值被定义为向该体验显示的所有用户的量度总值除以该体验的访客总数。 这意味着量度可以为活动中的每个独特访客获取任何值。 例如，如果访客进行多次转化，则每次转化都会被计为一次。  如果您希望最大化连续量度（如总收入），或者如果单个用户的多个转化事件比一个更有意义（例如，多个订单的价值大于一个），请使用此选项 |
| 自动分配 | Target | （不可配置） | 量度将被视为二进制文件，并且独特访客转化率会最大化。 |
| 自动定位 | Analytics | 最大化独特访问转化率 | 与自动分配或手动A/B测试不同，自动定位的个性化性质意味着访客在每次新访问时看到的体验可能会发生更改。 然后，相应的比率是访问标准化转化率，该转化率定义为在其中记录非零量度的访问次数百分比。 这是通过自动定位优化的转化率。   与自动分配类似，当您关心发生转化的访问比例时，应选择此选项，例如，当单次访问发生多个转化事件并不重要时。 |
| 自动定位 | Analytics | 最大化每次访问量度值 | 当要优化的量度是连续的（例如收入），或在单次访问中存在多个转化事件有意义（例如多个订单）时，您可以选择最大化每次访问的量度值。 优化的“比率”是量度的总值除以访问次数。 |
| 自动定位 | Target | （不可配置） | 量度将被视为二进制文件，并且独特访问转化率会最大化。 |



请注意，根据优化标准， [!DNL Adobe Analytics] 将不支持量度。

* [!DNL Adobe Analytics] 不支持计算量度。
* [!DNL Adobe Analytics] 量度必须始终可分段，并且如果每个访客/访问的值正在优化，则量度必须具有正极性（即，正值优于负值）
* [!DNL Adobe Analytics] 用于 [!DNL Auto-Target] 活动必须在DataWarehouse导出中可用。

## 限制和说明

某些限制和说明同时适用于 [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位] 活动。 其他限制和说明适用于一种活动类型或另一种活动类型。

### 自动分配和自动定位 {#both}

* 使用 [!DNL Adobe Analytics] 作为报表源 [!UICONTROL 自动分配] 或 [!UICONTROL 自动定位]，则应始终在 [!DNL Analytics].
* 报表源不能从 [!DNL Analytics] to [!DNL Target] 或者，在活动激活后执行相反的操作。
* 尽管计算量度不支持作为主要目标量度，但通常可以通过选择自定义事件作为主要目标量度来实现预期结果。 例如，如果要优化量度（如“每位访客的表单完成次数”），请选择与“表单完成次数”对应的自定义事件作为主要目标量度。 如 [支持的目标量度和优化标准](#supported)，具体取决于活动类型和优化标准， [!DNL Target] 将自动标准化转化量度，因此无需使用计算量度来执行标准化。


### 自动分配 {#aa}

* **培训频度**: [!UICONTROL 自动分配] 和往常一样，模特们继续每小时训练一次。
* **归因模型**: [!DNL Target] 使用 [!DNL Adobe Analytics] 默认归因模型[!UICONTROL  自动分配] 使用A4T的活动。
* **置信度**:使用的置信度公式 [!UICONTROL 自动分配] 活动与 [!DNL Adobe Analytics] [!UICONTROL A4T] 的上界。 [如下所述](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [!UICONTROL 自动分配] 使用比常规更保守的置信区间 [!UICONTROL A/B测试] 活动。 这些保守的置信水平补偿了重复的数据评价(peek)。 因此， [!DNL Adobe Analytics] 显示的置信区间比使用的置信区间窄 [!UICONTROL 自动分配] 算法。 但是，您可以根据哪些体验具有更多独特访客被发送到该体验，来确定算法最喜欢哪个体验。
* **入选者状态**:目前， [“还没有入选者”和“入选者”徽章](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) 在 [!UICONTROL A4T] 面板 [!DNL Analysis Workspace]. 如果在中查看同一报表，则这些徽章也将不可用 [!DNL Target]. 入选者“星形”标记，显示在 [!DNL Target] 报表 [!UICONTROL 自动分配] 应忽略使用A4T的活动。 此徽章反映的是常规的置信度计算，而不是 [!UICONTROL 自动分配].

### 自动定位 {#at}

* **培训频度**: [!UICONTROL 自动定位] 与往常一样，模特每24小时继续训练一次。 但是，转化事件数据来自 [!DNL Analytics] 多拖6到24小时。 此延迟表示流量的分布方式 [!DNL Target] 跟踪中记录的最新事件 [!DNL Analytics]. 在活动初始激活后的前48小时内，此延迟产生的影响最大。 活动的性能将更加相似 [!DNL Analytics] 5天后的转化行为。 请考虑使用 [!UICONTROL 自动分配] 而不是 [!UICONTROL 自动定位] 在短期活动中，大多数流量在活动生命周期的前五天内发生。
* 使用 [!DNL Analytics] 作为 [!UICONTROL 自动定位] 活动，会话在6小时后结束。 六小时后发生的转化不会被计算在内。

有关更多信息，请参阅 [归因模型和回顾时间范围](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) 在 *Analytics工具指南*.

## 如何在Analysis Workspace中设置A4T报表以用于自动定位和自动分配活动 {#tutorial}

尽管在 [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace]，对默认值进行一些修改 [!UICONTROL Analytics for Target] 面板才能正确解释自动分配和自动定位活动。

由于转换率在 [支持的目标量度和优化标准](#supported)，以及实验活动(手动A/B和 [!UICONTROL 自动分配])和个性化活动([!UICONTROL 自动定位])。

这些教程将指导您完成为分析而推荐的修改 [!UICONTROL A4T] [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位] 活动 [!UICONTROL 工作区].

有关更多信息，请参阅
* [如何在Analysis Workspace中为自动分配活动设置A4T报表](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) in *Adobe TargetTutorials*.
* [如何在Analysis Workspace中为自动定位活动设置A4T报表](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) in *Adobe TargetTutorials*.
