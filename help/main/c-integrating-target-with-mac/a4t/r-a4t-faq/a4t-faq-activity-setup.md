---
keywords: FAQ;常见问题解答;Analytics for Target;A4T;活动设置
description: 查找有关在将Analytics用于时进行活动设置的问题答案 [!DNL Target] (A4T)。 A4T允许您将Analytics报表用于 [!DNL Target] 活动。
title: 可在何处找到有关A4T活动设置的常见问题解答？
feature: Analytics for Target (A4T)
exl-id: 8a8cdbb9-89f6-4e4a-a53e-8f33adab4d61
source-git-commit: 981cff428d9e8849b9bbcbf7bef389dad0fbb32a
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 10%

---

# 活动设置 - A4T 常见问题解答

本主题包含有关活动设置和使用的常见问题解答 [!DNL Analytics] 作为的报表源 [!DNL Target] (A4T)。

## 支持哪些活动类型 [!DNL Analytics] 作为报表源(A4T)？ {#section_5E4F58CD25A5424E869E6FE0803968EF}

+++有关完整列表，请参阅中的“支持的活动类型” [将Adobe Analytics作为Adobe Target报表源(A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE).

+++

## 使用A4T报表时，能否将同一活动名称用于来自不同工作区的两个活动？

+++回答

不要将相同的活动名称用于两个独立的活动 [工作区](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) 使用A4T报表的客户。

虽然在使用时，此函数受支持 [!DNL Target] 作为报表源，在使用时，不支持为两个活动使用相同的活动名称 [!UICONTROL 目标分析] 作为报表源。

+++

## 在配置目标量度时，为何无法访问高级设置？

+++使用回答活动 [!DNL Analytics] 作为报表源(A4T)，目标量度使用&quot;[!UICONTROL 增量计数并保持用户处于活动中]”和“[!UICONTROL 每次展示时]”设置。 这些设置包括 *非* 可配置。

有关更多信息，请参阅配置目标指标时为何无法访问高级设置选项？ 在 [量度定义 — A4T常见问题解答](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

+++

## 我刚刚创建了一个活动。但是为何看不到任何数据？ {#section_9F8092BE4225442896F926540292F221}


+++答案在创建活动时， [!DNL Target] 将分类文件发送到 [!DNL Analytics]. 尽管 [!DNL Analytics] 正在捕获和处理数据，在分类文件更新之前不会显示在报表中。 完成此过程可能需要24到72小时。 如果您在72小时后仍未看到数据， [联系客户关怀团队](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C). 或者，如果您知道自己启动了一个活动，则可以提前几天创建该活动，并在保存该活动时发送分类。 这样一来，数据在活动启动时就会显示在报表中。请注意，在中处理数据需要45-90分钟 [!DNL Analytics].

+++

## 在创建活动时，为何无法选择Analytics作为报表源？ {#section_9F4F69C3085F4C2480AF439127EB27CD}

+++回答：您可以更改您的 [!UICONTROL 报表设置] 中的选项 [!UICONTROL 管理].

1. 在 [!DNL Target]，单击 **[!UICONTROL 管理]**.
1. 在&#x200B;**[!UICONTROL 用于报表的 Experience Cloud 解决方案]**&#x200B;下拉列表中，单击&#x200B;**[!UICONTROL 为每个活动选择]**。

![为每个活动选择图像](assets/select-per-activity.png)

随即会在&#x200B;**[!UICONTROL 目标和设置]**&#x200B;屏幕中启用&#x200B;**[!UICONTROL 报表源]**&#x200B;下拉列表，以用于创建和编辑活动。

要始终使用 [!DNL Analytics] 作为报表源，选择 **[!UICONTROL Adobe Analytics]** 从的下拉列表中 [!UICONTROL 管理].

+++

## 在使用A4T的自动定位活动中，访客能否在不同的访问中切换针对性体验与对照体验？

+++回答假设访客的visitorId在两次访问之间不会发生更改，则符合以下情况。

如果在活动中调整了流量分配百分比，则访客可能会在目标体验和控制体验之间切换。

如果在活动期间未调整百分比，则最初看到控制的访客始终会发送给控制。 被发送到目标体验的访客始终会被发送到目标体验。

* 进入流量的“存储桶”后，如果机器学习模型确定不同的体验与新访问相关，则访客可能会从访问被发送到不同的体验。
* 在分配给流量的控制“存储桶”后，访客将始终看到相同的体验，因为体验分配基于访客ID的确定性伪随机哈希。

+++

## 我可以使用二项式吗 [!DNL Analytics] 量度，其中将区段用作中的优化目标 [!UICONTROL 自动分配] 活动？ {#binomial}

+++回答您不能使用 [!DNL Analytics] 量度，其中将区段用作中的优化目标 [!UICONTROL 自动分配] 活动。 作为解决方法，您可以定义一个实现相同目标的自定义事件，并将其用作优化目标量度。

+++