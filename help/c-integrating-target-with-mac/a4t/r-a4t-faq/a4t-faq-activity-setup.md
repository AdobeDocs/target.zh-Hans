---
keywords: FAQ;常见问题解答;Analytics for Target;A4T;活动设置
description: 查找有关使用Analytics for [!DNL Target] (A4T). A4T lets you use Analytics reporting for [!DNL Target] 活动时活动设置的问题解答。
title: 在哪里可以找到有关A4T活动设置的常见问题解答？
feature: Analytics for Target (A4T)
exl-id: 8a8cdbb9-89f6-4e4a-a53e-8f33adab4d61
source-git-commit: 15ca5e92af5ebc66caa52ffc1dc04e1fbcbb2ed3
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 20%

---

# 活动设置 - A4T 常见问题解答

本主题包含有关活动设置和使用[!DNL Analytics]作为[!DNL Target](A4T)报表源的常见问题解答。

## 哪些活动类型支持将 Analytics 作为报表源 (A4T)？ {#section_5E4F58CD25A5424E869E6FE0803968EF}

有关完整列表，请参阅[将 Adobe Analytics 作为 Adobe Target 报表源 (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) 中的“支持的活动类型”。

## 在配置目标量度时，为何无法访问高级设置？

对于使用[!DNL Analytics]作为报表源(A4T)的活动，目标量度使用“[!UICONTROL 递增计数并保持活动中的用户]”和“[!UICONTROL 每次展示时]”设置。 这些设置可配置为&#x200B;*不*。

有关更多信息，请参阅“配置目标量度时，为何无法访问高级设置选项？” 在[量度定义 — A4T常见问题解答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md)中。

## 我刚刚创建了一个活动。但是为何看不到任何数据？ {#section_9F8092BE4225442896F926540292F221}

创建活动后，[!DNL Target]会向[!DNL Analytics]发送分类文件。 尽管[!DNL Analytics]正在捕获和处理数据，但在更新分类文件之前，不会在报表中显示该数据。 此过程最长可能需要24小时。 如果 48 小时后您还没有看到数据，请[联系客户关怀团队](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。或者，如果您知道自己启动了活动，则可以事前几天创建活动，并在保存活动时发送分类。 这样一来，数据在活动启动时就会显示在报表中。请注意，在[!DNL Analytics]中处理数据需要45-90分钟。

## 在创建活动时，为何无法选择Analytics作为报表源？ {#section_9F4F69C3085F4C2480AF439127EB27CD}

您可以在[!UICONTROL Administration]中更改[!UICONTROL Reporting Settings]选项。

1. 在[!DNL Target]中，单击&#x200B;**[!UICONTROL 管理]**。
1. 在&#x200B;**[!UICONTROL 用于报表的 Experience Cloud 解决方案]**&#x200B;下拉列表中，单击&#x200B;**[!UICONTROL 为每个活动选择]**。

![](assets/select-per-activity.png)

随即会在&#x200B;**[!UICONTROL 目标和设置]**&#x200B;屏幕中启用&#x200B;**[!UICONTROL 报表源]**&#x200B;下拉列表，以用于创建和编辑活动。

要始终使用[!DNL Analytics]作为报表源，请从[!UICONTROL Administration]的下拉列表中选择&#x200B;**[!UICONTROL Adobe Analytics]**。

## 在使用A4T的自动定位活动中，访客能否在不同访问中的目标体验和受控体验之间进行切换？

如果访客的visitorId在两次访问之间没有发生更改，则情况如下。

如果在活动期间调整了流量分配百分比，则访客可能会在目标体验和控制体验之间移动。

如果在活动期间未调整百分比，则最初看到控制的访客始终会被发送到控制。 发送到定位体验的访客始终会发送到定位体验。

* 在流量的目标“存储段”中后，如果机器学习模型确定不同的体验与新访问相关，则可以将访客发送到与访问不同的体验。
* 在分配到流量的控制“存储段”后，访客将始终看到相同的体验，因为体验分配基于访客visitorId的确定性伪随机哈希。


## 我能否在[!UICONTROL 自动分配]活动中将区段应用为优化目标的二项式[!DNL Analytics]量度？ {#binomial}

您不能在[!UICONTROL 自动分配]活动中将区段应用为优化目标的[!DNL Analytics]量度。 作为解决方法，您可以定义一个实现相同目标的自定义事件，并将其用作优化目标量度。