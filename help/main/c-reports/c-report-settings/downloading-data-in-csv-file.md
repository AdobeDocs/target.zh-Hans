---
keywords: 报表;下载报表;CSV;成功量度;订单详细信息
description: 了解如何从Adobe下载数据 [!DNL Target] CVS格式的活动，用于快速导入到Excel、Access或其他数据分析程序中。
title: 如何将报表数据下载为CSV文件？
feature: Reports
exl-id: b4387184-8730-4367-8bc3-52d8fbe2583e
source-git-commit: fc1dcc2b6de1248c35191c1ecd7b36aeb891fd3f
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 54%

---

# 将数据下载到 CSV 文件

可采用 .csv 格式下载数据，以便快速导入到 Excel、Access 或其他数据分析程序中。

要将数据下载到 CSV 文件，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL 活动]**，然后在列表中单击所需的活动。

   如果您拥有多个活动，可以通过从[!UICONTROL 类型]、[!UICONTROL 状态]、[!UICONTROL 报表源]、[!UICONTROL 体验编辑器]、[!UICONTROL 量度类型]和[!UICONTROL 活动来源]下拉列表中选择相应选项来筛选列表。

1. 单击&#x200B;**[!UICONTROL 报表]**&#x200B;选项卡。
1. 单击“**[!UICONTROL 下载]**”图标，然后选择要下载以供在 Excel 和其他工具中进行分析的报表类型。

   * [!UICONTROL 将报表导出到CSV]
   * [!UICONTROL 将订单详细信息导出到 CSV]

   ![下载选项](/help/main/c-reports/assets/download-options.png)

## [!UICONTROL 将报表导出到 CSV] {#section_38BD9743EB254453B5F4A0A6F2720CD3}

此 [!UICONTROL 成功量度] 报表显示有关成功指标的信息，以及以下在中不可用的指标 [!DNL Target] UI：

* 转化的平均时间（以小时为单位），从而您可以看到每个访客到达转化点需要花费的平均时间。
* 收入的总和与平方（对于离线统计置信度计算）

数据会一直保存到活动结束为止。

>[!NOTE]
>
>CSV报表仅包含原始数据，而不包含计算量度，如A/B测试中使用的每位访客带来的收入、提升度或置信度。 要计算这些计算指标，请下载 [!DNL Target] [完全置信度计算器](/help/main/assets/complete_confidence_calculator.xlsx) 用于输入活动值或审阅的Excel文件 [A/Bn测试中的统计计算](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## [!UICONTROL 将订单详细信息导出到 CSV] {#section_96B3F578F91F4CA3AFE38BACA2A0F11E}

此 [!UICONTROL 订单详细信息] 报表显示有关订单的信息，包括：

* 订单日期和时间
* 订单金额（如果已插入“下单”mbox）

   此 [!UICONTROL 订单详细信息] 报表仅在您有订单时才有效。

* 订单标记（重复或极端订单）

   如果订单与平均订单值的偏差超过+/- 3个标准差，则会将其标记为极端。 此计算使用最后一个月的数据（截至计算的时间点）。 在活动运行一小时，或订单量达到 15 个后（以先到者为准），活动将排除其极端订单。有关更多信息，请参阅[排除超常订单](/help/main/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA)。

* 产品 ID

   产品ID的总长度不应超过255个字符，否则这些ID无法在报表中正确显示。 例如，如果您订单中产品的 ID 是“aa, bb”，则总长度为“aa,bb”= 5。

* 体验

   在 [!UICONTROL A/B 测试]、[!UICONTROL 体验定位] (XT) 和[!UICONTROL 多变量测试] (MVT) 活动的“[!UICONTROL 订单详细信息]”报表中，“[!UICONTROL 体验]”列包含体验 `localId`。这是选件令牌中 `$campaign.recipe.id` 的值输出。

   [!UICONTROL 自动个性化] (AP) 活动没有“[!UICONTROL 体验]”列。当前的“[!UICONTROL 算法名称]”列已被替换为“控制”与“目标”术语，这些术语显示在 [!DNL Target] 中的其他位置。

   这对“[!UICONTROL 推荐]”活动没有任何影响。

>[!NOTE]
>
>* 对于默认环境（主机组），订单报表会包含四周的数据，而对于所有非默认环境，订单报表会包含两周的数据。
>* 收入指标设置为&quot;[!UICONTROL 递增计数并保持用户处于活动中]”仅记录同一访客下第一个订单的订单详细信息。 所有后续订单都会增加转化计数，但不会将收入添加到RPV/AOV/销售中，并且不会包含在 [!UICONTROL 订单详细信息] 报告。


## 最佳实践

* 若要记录订单记录，请 `orderTotal` 必须传递参数。
* 通过 `ProductPurchasedId` mbox 参数传递的值会在“订单详细信息”报表中列出。
* 最佳实践是包含 `orderID` 和 `orderTotal`. 这会自动忽略重复的订单。

## 注意事项 {#section_49B9590904A645B18E694B4EFFFC1DEF}

以下信息适用于 [!UICONTROL 下载] 选项：

* 您可以下载以下两个报表： [!UICONTROL A/B测试]， [!UICONTROL Automated Personalization]， [!UICONTROL 体验定位]、和 [!UICONTROL 多变量] 活动。 您无法下载 [!UICONTROL 成功量度] 报告 [!UICONTROL Recommendations] 活动。
* 此 [!UICONTROL 下载] 选项不可用于 [!UICONTROL A/B测试] 和 [!UICONTROL 体验定位] 之前创建的活动 [!DNL Target] 版本15.7.1（2015年7月）。
* 下载的报表中不会记录没有关联数据的体验。
* 中应用的受众 [!DNL Target] 报表UI不会传递到下载的报表。
* 如果活动使用多个指标，则为以 .csv 文件形式下载而生成的报表不一致。仅根据报告设置生成可下载的报表，并且该报表对于任何其他所使用的指标均考虑相同的值。事实来源始终为 [!DNL Target] UI 中显示的报表。
