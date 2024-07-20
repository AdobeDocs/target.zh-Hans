---
keywords: 定位；受众筛选器；受众；筛选器
description: 了解如何在 [!DNL Adobe Target] 中使用受众筛选器查看共享特征的访客的数据。
title: 能否将受众筛选器用于报表？
feature: Audiences
exl-id: af8dae97-4b10-4edb-a0e6-0d8daf2f0d22
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 72%

---

# 适用于报表的受众筛选器

[!DNL Adobe Target]中的受众筛选器（或称受众）是指共享特定特征或一组特征的访客组。

使用受众筛选器可指定要用于报表的受众。您可以选择一个受众，然后将该受众的表现与总体流量进行比较。您可能想要知道与常规流量产生的入选者相比，各种流量源产生的入选者是否有所不同。受众筛选器可帮助您发现可能面向不同内容的受众。 很多情况下，一个入选者并不会适合所有流量。

例如，通过某个搜索引擎访问您页面的访客可以构成一个受众。其他受众可以基于性别、年龄、位置、注册状态、购买历史记录，或您可以收集到的与访客有关的任何其他详细信息。使用受众筛选器可拆分访客流量，并比较每个流量区段的体验表现。

如果您计划在活动中使用受众筛选器，请考虑以下准则：

* **访客可以属于多个受众。**&#x200B;如果设置了两个受众(例如，“新访客”和“来自Google的访客”)，并且人员同时符合这两个条件，则两个受众中都会计数和跟踪此访客。 因此，受众中的访客总和并不等于活动中的访客数。
* **在启动活动之前设置受众。**&#x200B;不能以追溯方式检索受众数据。如果在启动活动之前您并未配置受众筛选器，而是决定在活动运行一段时间后再使用受众筛选器，则您将无法收集到已经运行的这段时间的数据。
* **在开始时使用 2 到 4 个受众。**&#x200B;将重点放在基本信息上，例如流量源。
* **根据需要重命名受众。**&#x200B;您可以在不影响数据的情况下重命名受众，以使受众名称对收集到的结果更有意义，即使活动处于活跃状态也可重命名。
* **输入精确值。**&#x200B;受众筛选器的值区分大小写。例如，如果您使用的是按城市筛选的受众，则应当使用“或”条件，以包括所有可能的拼写和大小写变体，例如“Vienna”、“vienna”、“wien”和“Wien”。
* **从[!UICONTROL Audiences]列表中创建的受众可重复使用。**&#x200B;作为活动的一部分创建的受众不能重复使用。

以下部分提供了有关设置和报告受众的更多信息：

| 任务 | 主题 |
|--- |--- |
| 创建适当的活动或测试。 | [活动和测试](/help/main/c-intro/target-key-concepts.md) |
| 创建受众（如有需要）。 | [创建受众](/help/main/c-target/c-audiences/create-audience.md) |
| 合并多个受众（如有需要）。 | [合并多个受众](/help/main/c-target/combining-multiple-audiences.md) |
| 在活动的“目标和设置”页面上应用受众。 | A/B测试： [目标和设置](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)<br>Automated Personalization： [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<br>体验定位： [目标和设置](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md)<br>多变量测试： [目标和设置](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md)<br>Recommendations： [Recommendations活动设置](/help/main/c-recommendations/t-create-recs-activity/recs-activity-settings.md)<br>活动设置： [活动设置](/help/main/c-activities/activity-settings.md) |
| 查看包含受众筛选器相关信息的报表。 | [报表设置](/help/main/c-reports/c-report-settings/report-settings.md) |
