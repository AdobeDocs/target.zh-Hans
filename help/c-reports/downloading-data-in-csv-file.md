---
keywords: reports;download reports;csv;success metrics;order details
description: 以。csv格式下载数据，以便使用Adobe目标快速导入Excel、Access或其他数据分析项目。
title: 使用Adobe目标在CSV文件中下载数据
subtopic: Multivariate Test
topic: Standard
uuid: 9ac151e1-45a9-4d46-b23b-e7c9ae518253
translation-type: tm+mt
source-git-commit: ba4c776d93f911c122f36113a99ce4349b3c5524

---


# 将数据下载到 CSV 文件{#downloading-data-in-a-csv-file}

可采用 .csv 格式下载数据，以便快速导入到 Excel、Access 或其他数据分析程序中。

要将数据下载到 CSV 文件，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL 活动]**，然后在列表中单击所需的活动。

   如果您拥有多个活动，可以通过从[!UICONTROL 类型]、[!UICONTROL 状态]、[!UICONTROL 报表源]、[!UICONTROL 体验编辑器]、[!UICONTROL 量度类型]和[!UICONTROL 活动来源]下拉列表中选择相应选项来筛选列表。

1. 单击&#x200B;**[!UICONTROL 报表]**&#x200B;选项卡。
1. 单击“**[!UICONTROL 下载]**”图标，然后选择要下载以供在 Excel 和其他工具中进行分析的报表类型。

   * [!UICONTROL 将报告导出为CSV]
   * [!UICONTROL 将订单详细信息导出到 CSV]
   ![下载选项](/help/c-reports/assets/download-options.png)

## 将报表导出到 CSV {#section_38BD9743EB254453B5F4A0A6F2720CD3}

“成功量度”报表可显示与成功量度有关的信息，以及与 Target UI 中未提供的以下量度有关的信息：

* 转化的平均时间（以小时为单位），从而您可以看到每个访客到达转化点需要花费的平均时间。
* 收入的总和与平方（对于离线统计置信度计算）

数据会一直保存到活动结束为止。

>[!NOTE]
>
>CSV报告仅包括原始数据，不包括用于A/B测试的每访客收入、提升或置信度等计算指标。 To calculate these calculated metrics, download the Target&#39;s [Complete Confidence Calculator](/help/assets/complete_confidence_calculator.xlsx) Excel file to input the activity&#39;s value, or review the [statistical calculations used by Target](/help/assets/statistical-calculations.pdf).

## 将订单详细信息导出到 CSV {#section_96B3F578F91F4CA3AFE38BACA2A0F11E}

“订单详细信息”报表显示有关订单的信息，包括：

* 订单日期和时间
* 订单金额（如果已插入“下单”mbox）

   仅当存在订单时，“订单详细信息”报表才可用。

* 订单标记（重复或极端订单）

   如果某个订单与根据上个月（从当前时间往回算起）的数据计算出来的平均订单值之间的标准偏差超过 +/- 3，则该订单会被视为极端订单。在活动运行一小时，或订单量达到 15 个后（以先到者为准），活动将排除其极端订单。有关更多信息，请参阅[排除超常订单](../c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA)。

* 产品 ID

   以逗号连接的各产品 ID 的总长度不应超过 225 个字符，否则这些 ID 将无法在报表中正常显示。例如，如果您订单中产品的 ID 是“aa, bb”，则总长度为“aa,bb”= 5。

* 体验

   在 [!UICONTROL A/B 测试]、[!UICONTROL 体验定位] (XT) 和[!UICONTROL 多变量测试] (MVT) 活动的“[!UICONTROL 订单详细信息]”报表中，“[!UICONTROL 体验]”列包含体验 `localId`。这是选件令牌中 `$campaign.recipe.id` 的值输出。

   [!UICONTROL 自动个性化] (AP) 活动没有“[!UICONTROL 体验]”列。当前的“[!UICONTROL 算法名称]”列已被替换为“控制”与“目标”术语，这些术语显示在 [!DNL Target] 中的其他位置。

   这对“[!UICONTROL 推荐]”活动没有任何影响。

>[!NOTE]
>
>* 对于默认环境（主机组），订单报表会包含四周的数据，而对于所有非默认环境，订单报表会包含两周的数据。
>* 设置为“递增计数并保持用户处于活动中”的收入量度仅为同一访客的第一个订单记录订单详细信息。所有后续订单虽然将增加转化计数，但不会增加 RPV/AOV/销售额所对应的收入，也不会包含到“订单详细信息”报表中。


## 最佳实践

* 要记录订单详细信息，必须传递 `orderTotal` 参数。
* 通过 `ProductPurchasedId` mbox 参数传递的值会在“订单详细信息”报表中列出。
* 最佳做法是同时包含 `orderID` 和 `orderTotal`。这会自动忽略重复的订单。

## 注意事项 {#section_49B9590904A645B18E694B4EFFFC1DEF}

以下信息适用于“下载”选项：

* 您可以下载A/B测试、自动个性化、体验定位和多变量活动的两种报告。 但是对于“推荐”活动，您无法下载“成功量度”报表。
* “下载”选项不适用于在 Target 版本 15.7.1（2015 年 7 月版）之前创建的 A/B 活动和体验定位活动。
* 下载的报表中不会记录没有关联数据的体验。
* Target 报表 UI 中应用的受众不会传递到下载的报表中。
