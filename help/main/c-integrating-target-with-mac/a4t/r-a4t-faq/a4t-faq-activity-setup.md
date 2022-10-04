---
keywords: FAQ;常见问题解答;Analytics for Target;A4T;活动设置
description: 查找有关使用Analytics for [!DNL Target] (A4T)。 A4T允许您将Analytics报表用于 [!DNL Target] 活动。
title: 在哪里可以找到有关A4T活动设置的常见问题解答？
feature: Analytics for Target (A4T)
exl-id: 8a8cdbb9-89f6-4e4a-a53e-8f33adab4d61
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 20%

---

# 活动设置 - A4T 常见问题解答

本主题包含有关活动设置和使用的常见问题解答 [!DNL Analytics] 作为报表源 [!DNL Target] (A4T)。

## 哪些活动类型支持将 Analytics 作为报表源 (A4T)？ {#section_5E4F58CD25A5424E869E6FE0803968EF}

有关完整列表，请参阅[将 Adobe Analytics 作为 Adobe Target 报表源 (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) 中的“支持的活动类型”。

## 在配置目标量度时，为何无法访问高级设置？

对于使用 [!DNL Analytics] 作为报表源(A4T)，目标量度使用[!UICONTROL 递增计数并保持用户处于活动中]&quot;和&quot;[!UICONTROL 每次展示时]“ ”设置。 这些设置包括 *not* 可配置。

有关更多信息，请参阅“配置目标量度时，为何无法访问高级设置选项？” in [量度定义 — A4T常见问题解答](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

## 我刚刚创建了一个活动。但是为何看不到任何数据？ {#section_9F8092BE4225442896F926540292F221}

创建活动后， [!DNL Target] 将分类文件发送到 [!DNL Analytics]. 尽管 [!DNL Analytics] 捕获和处理数据时，在更新分类文件之前不会在报表中显示该信息。 此过程最长可能需要24小时。 如果 48 小时后您还没有看到数据，请[联系客户关怀团队](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。或者，如果您知道自己启动了活动，则可以事前几天创建活动，并在保存活动时发送分类。 这样一来，数据在活动启动时就会显示在报表中。请注意，在中处理数据需要45-90分钟 [!DNL Analytics].

## 在创建活动时，为何无法选择Analytics作为报表源？ {#section_9F4F69C3085F4C2480AF439127EB27CD}

您可以更改 [!UICONTROL 报表设置] 选项 [!UICONTROL 管理].

1. 在 [!DNL Target]，单击 **[!UICONTROL 管理]**.
1. 在&#x200B;**[!UICONTROL 用于报表的 Experience Cloud 解决方案]**&#x200B;下拉列表中，单击&#x200B;**[!UICONTROL 为每个活动选择]**。

![按活动选择图像](assets/select-per-activity.png)

随即会在&#x200B;**[!UICONTROL 目标和设置]**&#x200B;屏幕中启用&#x200B;**[!UICONTROL 报表源]**&#x200B;下拉列表，以用于创建和编辑活动。

始终使用 [!DNL Analytics] 作为报表源，请选择 **[!UICONTROL Adobe Analytics]** 从 [!UICONTROL 管理].

## 在使用A4T的自动定位活动中，访客能否在不同访问中的目标体验和受控体验之间进行切换？

如果访客的visitorId在两次访问之间没有发生更改，则情况如下。

如果在活动期间调整了流量分配百分比，则访客可能会在目标体验和控制体验之间移动。

如果在活动期间未调整百分比，则最初看到控制的访客始终会被发送到控制。 发送到定位体验的访客始终会发送到定位体验。

* 在流量的目标“存储段”中后，如果机器学习模型确定不同的体验与新访问相关，则可以将访客发送到与访问不同的体验。
* 在分配到流量的控制“存储段”后，访客将始终看到相同的体验，因为体验分配基于访客visitorId的确定性伪随机哈希。


## 我能否使用二项式 [!DNL Analytics] 量度中应用了区段作为 [!UICONTROL 自动分配] 活动？ {#binomial}

不能使用 [!DNL Analytics] 量度中应用了区段作为 [!UICONTROL 自动分配] 活动。 作为解决方法，您可以定义一个实现相同目标的自定义事件，并将其用作优化目标量度。