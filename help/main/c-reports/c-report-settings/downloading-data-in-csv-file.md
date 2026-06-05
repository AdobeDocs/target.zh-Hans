---
keywords: 报表;下载报表;CSV;成功量度;订单详细信息
description: 了解如何以CVS格式从Adobe [!DNL Target] 活动下载数据，以便快速导入到Excel、Access或其他数据分析程序中。
title: 如何以CSV文件下载报表数据？
feature: Reports
exl-id: b4387184-8730-4367-8bc3-52d8fbe2583e
TQID: https://experienceleague.adobe.com/-1FEosKnw-h8hRoK-VTO9VZsi5vIghnMnZp-fUUXo2U
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 737
ht-degree: 35%

---

# 将数据下载到 CSV 文件

以.csv格式下载数据以便快速导入到[!DNL Excel]、[!DNL Access]或其他数据分析程序中。

要将数据下载到 CSV 文件，请执行以下操作：

1. 单击“**[!UICONTROL 活动]**”，然后在列表中单击所需的活动。

   如果您有许多活动，请单击“筛选器”（![筛选器图标](/help/main/assets/icons/Filter.svg)）图标以筛选列表，方法是从[!UICONTROL 类型]、[!UICONTROL 状态]、[!UICONTROL 报告Source]、[!UICONTROL 体验编辑器]、[!UICONTROL 量度类型]和[!UICONTROL 活动Source]下拉列表中选择相应的选项。

1. 单击&#x200B;**[!UICONTROL 报表]**&#x200B;选项卡。
1. 单击&#x200B;**[!UICONTROL 下载]** （![下载图标](/help/main/assets/icons/Download.svg) ）图标，然后选择要下载以供在Excel和其他工具中分析的报表类型。

   * [!UICONTROL 将报表导出到CSV]
   * [!UICONTROL 将订单详细信息导出到 CSV]

## [!UICONTROL 将报表导出到 CSV] {#section_38BD9743EB254453B5F4A0A6F2720CD3}

[!UICONTROL 成功量度]报表显示有关您的成功量度的信息，以及[!DNL Target] UI中不可用的以下量度：

* 转化的平均时间（以小时为单位），从而您可以看到每个访客到达转化点需要花费的平均时间。
* 收入的总和与平方（对于离线统计置信度计算）

数据会一直保存到活动结束为止。

>[!NOTE]
>
>CSV报表仅包含原始数据，而不包含计算量度，如A/B测试中使用的每位访客带来的收入、提升度或置信度。 要计算这些计算量度，请下载[!DNL Target] [完整置信度计算器](/help/main/assets/complete_confidence_calculator.xlsx) Excel文件以输入活动的值，或查看A/Bn测试中的[统计计算](/help/main/c-reports/statistical-methodology/statistical-calculations.md)。

## [!UICONTROL 将订单详细信息导出到 CSV] {#section_96B3F578F91F4CA3AFE38BACA2A0F11E}

[!UICONTROL 订单详细信息]报表显示有关您的订单的信息，包括：

* 订单日期和时间
* 订单金额（如果已插入“下单”mbox）

  [!UICONTROL 订单详细信息]报表仅在您有订单时才有效。

* 订单标记（重复或极端订单）

  如果订单与平均订单值的偏差超过+/- 3个标准偏差，则会将其标记为极端。 此计算使用最后一个月的数据（截至计算的时间点）。 在活动运行一小时，或订单量达到 15 个后（以先到者为准），活动将排除其极端订单。 有关更多信息，请参阅[排除超常订单](/help/main/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA)。

* 产品 ID

  产品ID的总长度以逗号连接，不应超过255个字符，否则ID无法在报表中正确显示。 例如，如果您订单中产品的 ID 是“aa, bb”，则总长度为“aa,bb”= 5。

* 体验

  在[!UICONTROL A/B测试]、[!UICONTROL 体验定位] (XT)和[!UICONTROL 多变量测试] (MVT)活动的[!UICONTROL 订单详细信息]报表中，[!UICONTROL 体验]列包含体验`localId`。 这是产品建议令牌中 `$campaign.recipe.id` 的值输出。

  [!UICONTROL 自动个性化] (AP) 活动没有“[!UICONTROL 体验]”列。 当前[!UICONTROL 算法名称]列已替换为“控制”与“目标”术语，如[!DNL Target]中的其他位置所示。

  这对“[!UICONTROL 推荐]”活动没有任何影响。

>[!NOTE]
>
>* 对于默认环境（主机组），订单报表会包含四周的数据，而对于所有非默认环境，订单报表会包含两周的数据。
>* 设置为“[!UICONTROL 递增计数并将用户保留在活动中]”的收入量度仅记录同一访客发出的第一个订单的详细信息。 所有后续订单都会增加转化计数，但不会将收入添加到RPV/AOV/销售中，并且不会包含在[!UICONTROL 订单详细信息]报表中。

## 最佳实践

* 要记录订单记录，必须传递`orderTotal`参数。
* 通过`ProductPurchasedId` mbox参数传递的值在[!UICONTROL 订单详细信息]报表中列出。
* 最佳做法是包括`orderID`和`orderTotal`。 这会自动忽略重复的订单。

## 注意事项 {#section_49B9590904A645B18E694B4EFFFC1DEF}

以下信息适用于[!UICONTROL 下载]选项：

* 您可以下载[!UICONTROL A/B测试]、[!UICONTROL Automated Personalization]、[!UICONTROL 体验定位]和[!UICONTROL 多变量]活动的两个报表。 您无法下载[!UICONTROL 推荐]活动的[!UICONTROL 成功量度]报告。
* [!UICONTROL 下载]选项不可用于在[!DNL Target]版本15.7.1（2015年7月）之前创建的[!UICONTROL A/B测试]和[!UICONTROL 体验定位]活动。
* 下载的报表中不会记录没有关联数据的体验。
* 在[!DNL Target]报表UI中应用的受众不会传递到下载的报表中。
* 如果活动使用多个指标，则为以 .csv 文件形式下载而生成的报表不一致。 仅根据报告设置生成可下载的报告，并且该报告对于任何其他使用的指标都考虑相同的值。 事实来源始终为 [!DNL Target] UI 中显示的报表。
