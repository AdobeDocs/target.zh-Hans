---
keywords: FAQ;常见问题解答;Analytics for Target;A4T;活动设置
description: 查找有关在使用Analytics for [!DNL Target] (A4T)时的活动设置问题的答案。 A4T允许您对 [!DNL Target] 活动使用Analytics报表。
title: 可在何处找到有关A4T活动设置的常见问题解答？
feature: Analytics for Target (A4T)
exl-id: 8a8cdbb9-89f6-4e4a-a53e-8f33adab4d61
source-git-commit: 981cff428d9e8849b9bbcbf7bef389dad0fbb32a
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 6%

---

# 活动设置 - A4T 常见问题解答

本主题包含有关活动设置和使用[!DNL Analytics]作为[!DNL Target] (A4T)的报表源的常见问题解答。

## 哪些活动类型支持将[!DNL Analytics]作为报表源(A4T)？ {#section_5E4F58CD25A5424E869E6FE0803968EF}

+++回答
有关完整列表，请参阅[Adobe Analytics作为适用于Adobe Target (A4T)的Source报表](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)中的“支持的活动类型”。

+++

## 使用A4T报表时，能否将同一活动名称用于来自不同工作区的两个活动？

+++回答

对于来自使用A4T报表的独立[工作区](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)的两个活动，请勿使用相同的活动名称。

尽管将[!DNL Target]用作报表源时支持此功能，但是将[!UICONTROL Analytics for Target]用作报表源时，不支持对两个活动使用相同的活动名称。

+++

## 在配置目标量度时，为何无法访问高级设置？

+++回答
对于使用[!DNL Analytics]作为报表源(A4T)的活动，目标量度使用“[!UICONTROL Increment Count & Keep User in Activity]”和“[!UICONTROL On Every Impression]”设置。 这些设置是&#x200B;*不可配置的*。

有关更多信息，请参阅配置目标指标时为何无法访问高级设置选项？ 在[量度定义中 — A4T常见问题解答](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md)。

+++

## 我刚刚创建了一个活动。但是为何看不到任何数据？ {#section_9F8092BE4225442896F926540292F221}


+++回答
创建活动时，[!DNL Target]向[!DNL Analytics]发送分类文件。 虽然[!DNL Analytics]正在捕获和处理数据，但在更新分类文件之前不会显示在报表中。 完成此过程可能需要24到72小时。 如果您在72小时后仍未看到数据，请[联系客户关怀团队](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。 或者，如果您知道自己启动了一个活动，则可以提前几天创建该活动，并在保存该活动时发送分类。 这样一来，数据在活动启动时就会显示在报表中。请注意，在[!DNL Analytics]中处理数据需要45-90分钟。

+++

## 在创建活动时，为何无法选择Analytics作为报表源？ {#section_9F4F69C3085F4C2480AF439127EB27CD}

+++回答
您可以在[!UICONTROL Administration]中更改[!UICONTROL Reporting Settings]选项。

1. 在[!DNL Target]中，单击&#x200B;**[!UICONTROL Administration]**。
1. 在&#x200B;**[!UICONTROL Experience Cloud solution used for reporting]**&#x200B;下拉列表中，单击&#x200B;**[!UICONTROL Select per Activity]**。

![为每个活动选择图像](assets/select-per-activity.png)

已在&#x200B;**[!UICONTROL Goal & Settings]**&#x200B;屏幕中启用&#x200B;**[!UICONTROL Reporting Source]**&#x200B;下拉列表以创建和编辑活动。

要始终使用[!DNL Analytics]作为报表源，请从[!UICONTROL Administration]的下拉列表中选择&#x200B;**[!UICONTROL Adobe Analytics]**。

+++

## 在使用A4T的自动定位活动中，访客能否在不同的访问中切换针对性体验与对照体验？

+++回答
假设访客在两次访问之间的visitorId不会发生更改，则符合以下情况。

如果在活动中调整了流量分配百分比，则访客可能会在目标体验和控制体验之间切换。

如果在活动期间未调整百分比，则最初看到控制的访客始终会发送给控制。 被发送到目标体验的访客始终会被发送到目标体验。

* 进入流量的“存储桶”后，如果机器学习模型确定不同的体验与新访问相关，则访客可能会从访问被发送到不同的体验。
* 在分配给流量的控制“存储桶”后，访客将始终看到相同的体验，因为体验分配基于访客ID的确定性伪随机哈希。

+++

## 我能否将二项式[!DNL Analytics]量度与作为[!UICONTROL Auto-Allocate]活动中的优化目标的区段结合使用？ {#binomial}

+++回答
您不能将[!DNL Analytics]量度与作为[!UICONTROL Auto-Allocate]活动中的优化目标的区段结合使用。 作为解决方法，您可以定义一个实现相同目标的自定义事件，并将其用作优化目标量度。

+++