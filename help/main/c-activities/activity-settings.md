---
keywords: 目标和设置；目标；优先级；持续时间
description: 了解如何使用Adobe [!DNL Target] 中的活动设置来管理活动的目标、优先级和持续时间。
title: 如何指定活动设置？
feature: Activities
exl-id: 7f34080b-d2ed-4fe5-80ff-3aba16961223
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 71%

---

# 活动设置

在[!UICONTROL Activity Settings]中使用[!DNL Adobe Target]管理活动的目标、优先级和持续时间。

1. 输入有关活动目标的注释。

   键入有关您活动的任何信息，以便您自己或其他团队成员可随时使用这些信息。拖动以调整[!UICONTROL Objective]字段的大小。
1. 设置活动优先级。

   根据您的设置，[!UICONTROL Priority]的UI和选项会有所不同。 您可以使用“低”、“中”或“高”的传统优先级设置，也可以启用 0 至 999 的细粒度优先级设置。

   如果将具有相同受众的多个活动分配到同一个位置，则需使用优先级。如果将两个或更多活动分配到同一个位置，则会显示具有最高优先级的活动。

   如果未在[!UICONTROL Administration] > [!UICONTROL Reporting]中启用此选项（默认），请指定以下优先级：“低”、“Medium”或“高”。

   要启用细粒度优先级，请单击[!UICONTROL Administration] > [!UICONTROL Reporting]，然后将[!UICONTROL Enable Fine-Grained Priorities]选项切换到“开”位置。

   如果已启用此选项，请指定一个介于 0 到 999 之间值：

   * 0 = 低
   * 999 = 高

   对于在以前的 [!DNL Target Standard/Premium] 版本中创建的活动，“低”优先级会转换为 0，“中”优先级会转换为 5，“高”优先级会转换为 10。您可以根据需要调整这些值。

   >[!NOTE]
   >
   >在使用细粒度优先级后，您可以禁用此选项，但在此之前，必须将所有优先级重新设置为 0、5、10。

1. 设置活动的持续时间。

   您可以手动激活和停用活动，也可以指定活动交付的日期和时间。时间控制使用24小时时钟，00:00为午夜。 时区设置为在浏览器中配置的时区。要使用不同的时区，请将浏览器设置为其他时区并重新启动浏览器。

   >[!NOTE]
   >
   >为活动设置时间计划可控制活动的交付期限；但是，必须先明确激活活动，然后才能根据指定的时间计划交付活动。

[!UICONTROL Goal & Settings]页面包含的其他设置因您创建的活动类型而异。 有关这些设置的更多信息，请参阅您的活动类型所对应的内容：

* [A/B 测试](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [自动个性化](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9)
* [体验定位](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [多变量测试](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [推荐](/help/main/c-recommendations/t-create-recs-activity/recs-activity-settings.md#reference_3FDA8388CEEC4159949151C1829E2FBB)

## 培训视频：活动设置![教程徽章](/help/main/assets/tutorial.png)

以下视频包含有关活动设置的信息。

* 输入活动的目的
* 设置活动的优先级
* 计划活动的开始和结束时间
* 添加报表受众以创建报表筛选器
* 输入活动的注释

  >[!VIDEO](https://video.tv.adobe.com/v/17381)
