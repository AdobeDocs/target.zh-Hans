---
description: 受众筛选器（或称受众群）是指共同拥有某一特定特征或一组特征的访客群体。
keywords: 定位;受众筛选器;受众；过滤器
seo-description: Adobe Target中的受众过滤器（或受众）是共享特定特征或一组特征的访客组。
seo-title: Audience filters for reporting in Adobe Target
solution: Target
title: 适用于报表的受众筛选器
uuid: ca2632c0-87e4-4a85-95e6-e63cf800ab2f
translation-type: tm+mt
source-git-commit: 8ec84183de4c5a7c2a7a1f30e0196cd021ce937f

---


# 适用于报表的受众筛选器{#audience-filters-for-reporting}

受众筛选器（或称受众群）是指共同拥有某一特定特征或一组特征的访客群体。

使用受众筛选器可指定要用于报表的受众。您可以选择一个受众，然后将该受众的表现与总体流量进行比较。您可能想要知道与常规流量产生的入选者相比，各种流量源产生的入选者是否有所不同。这有助于您了解不同的内容可以分别定位到哪些受众。很多情况下，一个入选者并不会适合所有流量。

例如，通过某个搜索引擎访问您页面的访客可以构成一个受众。其他受众可以基于性别、年龄、位置、注册状态、购买历史记录，或您可以收集到的与访客有关的任何其他详细信息。使用受众筛选器可拆分访客流量，并比较每个流量区段的体验表现。

如果您计划在活动中使用受众筛选器，请考虑以下准则：

* **访客可以属于多个受众。** 如果设置了两个受众（例如，“新访客”和“来自Google的访客”），并且某个人符合这两个标准，则会在两个受众中计数和跟踪此访客。 因此，受众中的访客总和并不等于活动中的访客数。
* **在启动活动之前设置受众。**&#x200B;不能以追溯方式检索受众数据。如果在启动活动之前您并未配置受众筛选器，而是决定在活动运行一段时间后再使用受众筛选器，则您将无法收集到已经运行的这段时间的数据。
* **在开始时使用 2 到 4 个受众。**&#x200B;将重点放在基本信息上，例如流量源。
* **根据需要重命名受众。**&#x200B;您可以在不影响数据的情况下重命名受众，以使受众名称对收集到的结果更有意义，即使活动处于活跃状态也可重命名。
* **输入精确值。**&#x200B;受众筛选器的值区分大小写。例如，如果您使用的是按城市筛选的受众，则应当使用“或”条件，以包括所有可能的拼写和大小写变体，例如“Vienna”、“vienna”、“wien”和“Wien”。
* **从受众列表中创建的受众可重复使用。**&#x200B;作为活动的一部分创建的受众不能重复使用。

以下部分提供了有关设置和报告受众的更多信息：

| 任务 | 主题 |
|--- |--- |
| 创建适当的活动或测试。 | [活动和测试](/help/c-intro/target-key-concepts.md) |
| 创建受众（如有需要）。 | [创建受众](/help/c-target/c-audiences/create-audience.md) |
| 合并多个受众（如有需要）。 | [合并多个受众](/help/c-target/combining-multiple-audiences.md) |
| 在活动的“目标和设置”页面上应用受众。 | A/B Test: [Goals and Settings](/help/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)<br>Automated Personalization:  [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md)<br>Experience Targeting: [Goals and Settings](/help/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md)<br>Multivariate Test:  [Goals and Settings](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md)<br>Recommendations: [Recommendations activity settings](/help/c-recommendations/t-create-recs-activity/recs-activity-settings.md)<br>Activity Settings: [Activity Settings](/help/c-activities/activity-settings.md) |
| 查看包含受众筛选器相关信息的报表。 | [报表设置](/help/c-reports/c-report-settings/report-settings.md) |

