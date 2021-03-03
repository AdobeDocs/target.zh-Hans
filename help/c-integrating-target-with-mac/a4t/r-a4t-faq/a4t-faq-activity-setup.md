---
keywords: FAQ;常见问题解答;Analytics for Target;A4T;活动设置
description: 使用Analytics for 目标(A4T)时，查找有关活动设置的问题解答。 A4T允许您将Analytics报告用于目标活动。
title: 在哪里可以找到有关A4T活动设置的常见问题解答？
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: e45f0d2d2370f9c7aba2c2bd26afdd4c0e401db8
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 22%

---


# 活动设置 - A4T 常见问题解答

本主题包含有关活动设置和将[!DNL Analytics]用作[!DNL Target](A4T)的报告源的常见问题的解答。

## 哪些活动类型支持将 Analytics 作为报表源 (A4T)？{#section_5E4F58CD25A5424E869E6FE0803968EF}

有关完整列表，请参阅[将 Adobe Analytics 作为 Adobe Target 报表源 (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) 中的“支持的活动类型”。

## 配置我的目标量度时，为什么无法访问高级设置？

对于使用[!DNL Analytics]作为报告源(A4T)的活动，目标量度使用“[!UICONTROL 活动中的增量计数和保持用户”和“[!UICONTROL 每次印象]”设置。 ]这些设置&#x200B;*不可配置*。

有关详细信息，请参阅“配置目标量度时，为何无法访问高级设置选项？” 在[量度定义 — A4T常见问题解答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md)中。

## 我刚刚创建了一个活动。但是为何看不到任何数据？ {#section_9F8092BE4225442896F926540292F221}

创建活动时，[!DNL Target]会向[!DNL Analytics]发送分类文件。 尽管[!DNL Analytics]正在捕获和处理数据，但直到分类文件更新后，才会在报表中显示该信息。 此过程最多需要24小时。 如果 48 小时后您还没有看到数据，请[联系客户关怀团队](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。或者，如果您知道将启动活动，则可以提前几天创建活动，并在保存活动时发送分类。 这样一来，数据在活动启动时就会显示在报表中。请注意，在[!DNL Analytics]中处理数据需要45-90分钟。

## 创建报告时，为何不能选择Analytics作为活动源？{#section_9F4F69C3085F4C2480AF439127EB27CD}

您可以在[!UICONTROL 管理]中更改[!UICONTROL 报告设置]选项。

1. 在[!DNL Target]中，单击&#x200B;**[!UICONTROL 管理]**。
1. 在&#x200B;**[!UICONTROL 用于报表的 Experience Cloud 解决方案]**&#x200B;下拉列表中，单击&#x200B;**[!UICONTROL 为每个活动选择]**。

![](assets/select-per-activity.png)

随即会在&#x200B;**[!UICONTROL 目标和设置]**&#x200B;屏幕中启用&#x200B;**[!UICONTROL 报表源]**&#x200B;下拉列表，以用于创建和编辑活动。

要始终使用[!DNL Analytics]作为报告源，请从[!UICONTROL 管理]的下拉列表中选择&#x200B;**[!UICONTROL Adobe Analytics]**。

## 在使用A4T的自动目标活动中，访客能否在不同访问中的目标体验和受控体验之间切换？

以下情况是正确的，假设visitorId不会因访问之间的访客而发生更改。

如果调整了中活动流量分配百分比，则访客可能会在目标体验和控制体验之间移动。

如果百分比未在中活动调整，则始终会向最初看到控制的访客发送控件。 发送到目标体验的访客始终会发送到目标体验。

* 处于目标流量“桶”中后，如果机器学习模型确定新访问的相关体验不同，则访客可以发送到与访问不同的体验。
* 在分配给流量的控制“存储段”后，访客将始终看到相同的体验，因为体验分配基于访客的visitorId的确定性伪随机哈希。
