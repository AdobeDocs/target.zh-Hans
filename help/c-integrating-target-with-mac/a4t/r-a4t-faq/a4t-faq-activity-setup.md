---
keywords: faq;frequently asked questions;analytics for target;a4T;activity setup
description: 本主题包含有关活动设置和使用 Analytics 作为 Target 报表源 (A4T) 的常见问题解答。
title: 活动设置 - A4T 常见问题解答
feature: a4t troubleshooting
translation-type: tm+mt
source-git-commit: 146eecd331fc1a676c4bfc61e6fc8a414084a2d5
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 42%

---


# 活动设置 - A4T 常见问题解答

This topic contains answers to questions that are frequently asked about activity setup and using [!DNL Analytics] as the reporting source for [!DNL Target] (A4T).

## 哪些活动类型支持将 Analytics 作为报表源 (A4T)？{#section_5E4F58CD25A5424E869E6FE0803968EF}

有关完整列表，请参阅[将 Adobe Analytics 作为 Adobe Target 报表源 (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) 中的“支持的活动类型”。

## 我刚刚创建了一个活动。但是为何看不到任何数据？ {#section_9F8092BE4225442896F926540292F221}

When an activity is created, [!DNL Target] sends a classification file to [!DNL Analytics]. Although [!DNL Analytics] is capturing the and processing the data, it does not show in the reports until the classification file has been updated. 该过程最长可能需要 24 小时。如果 48 小时后您还没有看到数据，请[联系客户关怀团队](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。或者，如果您知道自己将启动某个活动，您可以提前几天创建该活动，在保存该活动后，便会发送分类。这样一来，数据在活动启动时就会显示在报表中。Please note that it takes 45-90 minutes for data to be processed in [!DNL Analytics].

## 创建新活动时，我为何不能选择 Analytics 作为报表源？{#section_9F4F69C3085F4C2480AF439127EB27CD}

You can change your [!UICONTROL Reporting Settings] options in [!UICONTROL Administration].

1. 在中， [!DNL Target]单击“ **[!UICONTROL 管理”]**。
1. 在&#x200B;**[!UICONTROL 用于报表的 Experience Cloud 解决方案]**&#x200B;下拉列表中，单击&#x200B;**[!UICONTROL 为每个活动选择]**。

![](assets/select-per-activity.png)

随即会在&#x200B;**[!UICONTROL 目标和设置]**&#x200B;屏幕中启用&#x200B;**[!UICONTROL 报表源]**&#x200B;下拉列表，以用于创建和编辑活动。

To always use [!DNL Analytics] as the reporting source, select **[!UICONTROL Adobe Analytics]** from the drop-down list in [!UICONTROL Administration].

## 在使用A4T的自动访客活动中，是否可以在不同访问中的目标体验和受控体验之间切换？

假设visitorId不因访问之间的访客而发生更改，则情况如下。

如果中活动调整了流量分配百分比，则访客可能会在目标体验和控制体验之间移动。

如果百分比未在中活动调整，则最初看到控件的访客将始终发送到控件。 发送到目标体验的访客将始终发送到目标体验。

* 在进入目标“客流量”后，如果机器学习模型确定新访问的相关体验不同，则访客可以发送到访问的不同体验。
* 在分配给流量的控制“存储段”后，访客将始终看到相同的体验，因为体验分配基于访客的visitorId的确定性伪随机哈希。
