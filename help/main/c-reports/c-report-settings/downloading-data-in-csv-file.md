---
keywords: 报表;下载报表;CSV;成功量度;订单详细信息
description: 了解如何以CVS格式从Adobe [!DNL Target] 活动下载数据，以便快速导入到Excel、Access或其他数据分析程序中。
title: 如何以CSV文件下载报表数据？
feature: Reports
exl-id: b4387184-8730-4367-8bc3-52d8fbe2583e
source-git-commit: fc1dcc2b6de1248c35191c1ecd7b36aeb891fd3f
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 37%

---

# 将数据下载到 CSV 文件

可采用 .csv 格式下载数据，以便快速导入到 Excel、Access 或其他数据分析程序中。

要将数据下载到 CSV 文件，请执行以下操作：

1. 单击 **[!UICONTROL Activities]**，然后在列表中单击所需的活动。

   如果您有许多活动，可以通过从[!UICONTROL Type]、[!UICONTROL Status]、[!UICONTROL Reporting Source]、[!UICONTROL Experience Composer]、[!UICONTROL Metrics Type]和[!UICONTROL Activity Source]下拉列表中选择相应选项来筛选列表。

1. 单击&#x200B;**[!UICONTROL Reports]**&#x200B;选项卡。
1. 单击&#x200B;**[!UICONTROL Download]**&#x200B;图标，然后选择要下载以供在Excel和其他工具中分析的报表类型。

   * [!UICONTROL Export Reports to CSV]
   * [!UICONTROL Export Order Details to CSV]

   ![下载选项](/help/main/c-reports/assets/download-options.png)

## [!UICONTROL Export Report to CSV] {#section_38BD9743EB254453B5F4A0A6F2720CD3}

[!UICONTROL Success Metrics]报表显示有关成功量度的信息，以及[!DNL Target] UI中不可用的以下量度：

* 转化的平均时间（以小时为单位），从而您可以看到每个访客到达转化点需要花费的平均时间。
* 收入的总和与平方（对于离线统计置信度计算）

数据会一直保存到活动结束为止。

>[!NOTE]
>
>CSV报表仅包含原始数据，而不包含计算量度，如A/B测试中使用的每位访客带来的收入、提升度或置信度。 要计算这些计算量度，请下载[!DNL Target] [完整置信度计算器](/help/main/assets/complete_confidence_calculator.xlsx) Excel文件以输入活动的值，或查看A/Bn测试中的[统计计算](/help/main/c-reports/statistical-methodology/statistical-calculations.md)。

## [!UICONTROL Export Order Details to CSV] {#section_96B3F578F91F4CA3AFE38BACA2A0F11E}

[!UICONTROL Order Details]报表显示有关您的订单的信息，包括：

* 订单日期和时间
* 订单金额（如果已插入“下单”mbox）

  [!UICONTROL Order Details]报表仅在您有订单时才有效。

* 订单标记（重复或极端订单）

  如果订单与平均订单值的偏差超过+/- 3个标准偏差，则会将其标记为极端。 此计算使用最后一个月的数据（截至计算的时间点）。 在活动运行一小时，或订单量达到 15 个后（以先到者为准），活动将排除其极端订单。有关更多信息，请参阅[排除超常订单](/help/main/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA)。

* 产品 ID

  产品ID的总长度以逗号连接，不应超过255个字符，否则ID无法在报表中正确显示。 例如，如果您订单中产品的 ID 是“aa, bb”，则总长度为“aa,bb”= 5。

* 体验

  在[!UICONTROL A/B Test]、[!UICONTROL Experience Targeting] (XT)和[!UICONTROL Multivariate Test] (MVT)活动的[!UICONTROL Order Details]报表中，[!UICONTROL Experience]列包含体验`localId`。 这是选件令牌中 `$campaign.recipe.id` 的值输出。

  [!UICONTROL Automated Personalization] (AP)活动没有[!UICONTROL Experience]列。 当前[!UICONTROL Algorithm Name]列已替换为“控制”与“目标”术语，如[!DNL Target]中的其他位置所示。

  对[!UICONTROL Recommendations]活动没有影响。

>[!NOTE]
>
>* 对于默认环境（主机组），订单报表会包含四周的数据，而对于所有非默认环境，订单报表会包含两周的数据。
>* 设置为“[!UICONTROL Increment count and keep the user in the activity]”的收入量度仅记录同一访客首次订购的详细信息。 所有后续订单都会增加转化计数，但不会将收入添加到RPV/AOV/销售中，并且不会包含在[!UICONTROL Order Details]报表中。

## 最佳实践

* 要记录订单记录，必须传递`orderTotal`参数。
* 通过`ProductPurchasedId` mbox参数传递的值在[!UICONTROL Order Details]报表中列出。
* 最佳做法是包括`orderID`和`orderTotal`。 这会自动忽略重复的订单。

## 注意事项 {#section_49B9590904A645B18E694B4EFFFC1DEF}

以下信息适用于[!UICONTROL Download]选项：

* 您可以下载[!UICONTROL A/B Test]、[!UICONTROL Automated Personalization]、[!UICONTROL Experience Targeting]和[!UICONTROL Multivariate]活动的报告。 您无法下载[!UICONTROL Recommendations]活动的[!UICONTROL Success Metrics]报告。
* [!UICONTROL Download]选项不适用于[!DNL Target]版本15.7.1（2015年7月）之前创建的[!UICONTROL A/B Test]和[!UICONTROL Experience Targeting]活动。
* 下载的报表中不会记录没有关联数据的体验。
* 在[!DNL Target]报表UI中应用的受众不会传递到下载的报表中。
* 如果活动使用多个指标，则为以 .csv 文件形式下载而生成的报表不一致。仅根据报告设置生成可下载的报告，并且该报告对于任何其他使用的指标都考虑相同的值。 事实来源始终为 [!DNL Target] UI 中显示的报表。
