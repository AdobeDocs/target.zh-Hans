---
keywords: analytics for target；a4t；Analytics作为报表源；Analytics
description: 了解如何使用Analytics for [!DNL Target] (A4T)。 通过A4T，可以访问使用Analytics量度和受众区段的 [!DNL Target] 活动的Analytics报表。
title: 如何在A4T中使用报表？
feature: Analytics for Target (A4T)
exl-id: cab5dc5f-166a-468e-8382-ae734684afdd
source-git-commit: 6857ba1a6410d3140a83a052efc50e9dd1776fd9
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 39%

---

# A4T 报表

使用[!DNL Adobe Analytics]作为[!DNL Adobe Target] (A4T)的报告源，可让您访问[!DNL Target]活动的[!DNL Analytics]报告。

您可以在[!DNL Analytics]和[!DNL Target]中查看活动报告。

有关[!DNL Target]使用[!DNL Analytics]的报表最佳实践，[请访问此Adobe Spark Page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)。

## 概述 {#section_035A62D65608423285D8A5A54731E2C5}

[!DNL Analytics]和[!DNL Target]均报告度量值参加者（进入测试的人员），而不是网站的访客。

每次访客在页面上看到活动内容时，[!DNL Target]都会直接对[!DNL Analytics]进行服务器到服务器调用，包括访客看到的活动和体验。 每次进行转换时，[!DNL Target]还会调用[!DNL Analytics]。 [!DNL Analytics]将转化添加为名为“活动转化”的特定新[!DNL Analytics]事件，该事件将与[!DNL Analytics]收集的其他数据一起进行跟踪。

如果使用[!UICONTROL Select]操作并且您对&#x200B;*参加者*&#x200B;进行排序，则报告中只会显示选定时间段内接收参加者的体验。

>[!NOTE]
>
>由[!DNL Target]提供支持的报表有四分钟的延迟。 对于由A4T提供支持的活动，在[!DNL Target]和[!DNL Analytics]报表中，可能需要长达24小时才能在最初保存活动之后将报表数据按体验细分。 在划分数据之前的这 24 小时内收集到的数据仍然准确，并且会被分配给正确的体验。

## Analytics 中的报表 {#analytics}

在[!DNL Analytics]中，启用A4T集成后提供了多个维度和量度。

### 维度

* [!UICONTROL Analytics for Target] — 通过集成传入的父ID。 此维度的格式为`Activity ID:Experience ID:3rd ID`。 以下维度是此维度的分类。
* [!UICONTROL Target Activities]
* [!UICONTROL Target Experiences]
* [!UICONTROL Target Activity] > [!UICONTROL Experience]
* [!UICONTROL 3rd ID] — 可以忽略

### 量度

* [!UICONTROL Activity Impressions] — 与[!DNL Target]报告中的[!UICONTROL Entrants]编号匹配。
* [!UICONTROL Activity Conversions] — 与[!DNL Target]报告中的[!UICONTROL Custom Conversions]编号匹配。

在[!DNL Analysis Workspace]中，使用[!UICONTROL Analytics for Target]面板以提升度和置信度分析您的[!DNL Target]活动和体验。 有关详细信息，请参阅&#x200B;*Analytics工具指南*&#x200B;中的[Analytics for Target (A4T)面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=zh-Hans)。

>[!IMPORTANT]
>
>如果您在[!DNL Analytics]中的[!UICONTROL Target Activities]报表列出了“未指定”而不是您的活动，则需要更新您的设置帐户。 请联系客户关怀团队以解决此问题。

有关详细信息和示例，请打开由Adobe Experience League提供的[Analytics &amp; Target：分析最佳实践](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)教程。

## [!DNL Target]中的报告 {#section_C0D1F17F88374B6690BF904D7B83B42E}

使用[!DNL Analytics]作为报表源时，[!DNL Target]中的报表显示从[!DNL Analytics]收集的数据。 此报表与其他[!DNL Target]报表略有不同：

* [!UICONTROL Audiences]列表显示了您的[!DNL Analytics]报表包可用的受众。
* [!UICONTROL Metric]列表显示通过[!DNL Analytics]可用的每个量度。

  每个量度都可用，包括[!DNL Analytics]中内置的任何自定义或计算量度。

  任何增加的数字在报表中都显示为正数，即使不需要增加时也是如此。 例如，虽然您希望降低跳出率，但是较高的跳出率会显示为具有最高提升度的入选者。根据报表做出决策时，请留心这些量度及类似量度，并确定您是希望降低还是提高这些量度的数值。

在活动开始后，甚至测试完成后，您都可以在[!DNL Target]中将量度或受众应用于报表。 您无需事先知晓要衡量的确切内容。

单击可直接从活动报告页面查看完整的[!DNL Analytics]报告。

## 活动创建 {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

在活动创建期间，必须在[!UICONTROL Settings]页面上指定活动的目标。 此目标将作为报表的默认量度并且在量度选择器中始终列为第一个选项。您将无法像设置常规 Target 活动的报表那样选择报表的区段。具有[!DNL Analytics]的测试使用[!DNL Adobe Analytics]区段，而不是[!DNL Target]受众。

## 为Analytics for Adobe Target (A4T)执行离线计算 {#section_B34BD016C8274C97AC9564F426B9607E}

您可以使用[!DNL Target] [完整置信度计算器](/help/main/assets/complete_confidence_calculator.xlsx) Excel文件对A4T的置信度和置信区间执行离线计算，但需要在[!DNL Analytics]中完成数据导出步骤。

对于A4T，我们对连续变量（而不是二进制量度）使用[Welch的t检验](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank}计算。 在 Analytics 中，会始终跟踪访客，并计入所执行的每项操作。因此，如果访客进行了多次购买或多次访问了某个成功量度，则会计入这些额外的点击。这会使量度变为连续变量。要执行韦尔奇的t检验计算，需要“平方和”来计算方差，方差用作t统计量的分母。 [A/Bn测试中的统计计算](/help/main/c-reports/statistical-methodology/statistical-calculations.md)说明了使用的数学公式的详细信息。 可从[!DNL Analytics]检索平方和。 要获取平方和数据，您需要导出样本时间段内要优化的量度在访客级别对应的数值。

例如，如果您正在针对每位访客的页面查看次数进行优化，则可以导出一个样本，其中包含指定时间段内（可能几天）每位访客的页面查看总次数（只需要几千个数据点）。 之后，您可以对每个值求平方，然后将总数相加（此处的运算顺序至关重要）。此“平方和”值随后可用在完整置信度计算器中。应在该电子表格的“收入”部分中使用这些值。

**使用 [!DNL Analytics] 数据导出功能执行此操作：**

1. 登录到 [!DNL Adobe Analytics]。
1. 单击&#x200B;**[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]**。
1. 在&#x200B;**[!UICONTROL Data Warehouse Request]**&#x200B;选项卡上，填写字段。

   有关各个字段的更多信息，请参阅 [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html?lang=zh-Hans) 中的“Data Warehouse 请求描述”。

   | 字段 | 说明 |
   |--- |--- |
   | 请求名称 | 指定请求的名称。 |
   | 报告日期 | 指定时间段和时间粒度。<br>对于首次请求，最好选择不超过 1 小时或 1 天的数据。请求的时间段越长，Data Warehouse 文件处理的时间也就会越长，因此第一次最好请求较短时间段内的数据，以确保文件返回预期的结果。之后，转到“请求管理器”，复制您的请求，然后在第二次请求中请求更多的数据。此外，如果您将粒度切换为“无”以外的任何粒度，则文件大小将急剧增加。<br>![Data Warehouse](/help/main/c-reports/assets/datawarehouse.png) |
   | 可用区段 | 根据需要应用区段。 |
   | 划分 | 选择所需的维度：“标准”维度是现成的(OOTB)，而“自定义”维度包含eVar和prop。 如果需要访客ID级别信息，建议您使用“访客ID”，而不是“Experience Cloud访客ID”。<ul><li>访客 ID 是 Analytics 使用的最终 ID。访客 ID 将为 AID（如果客户是旧客户）或 MID（如果客户是新客户，或者清除了自 MC 访客 ID 服务启动以来的 Cookie）。</li><li>仅当客户是新客户，或者清除了自 MC 访客 ID 服务启动以来的 Cookie 时，才会为客户设置 Experience Cloud 访客 ID。</li></ul> |
   | 量度 | 选择所需的量度。“标准”量度为开箱即用量度，而“自定义”量度包含自定义事件。 |
   | 报表预览 | 在计划报表之前查看您的设置。<br>![Data Warehouse2](/help/main/c-reports/assets/datawarehouse2.png) |
   | 计划提交 | 输入要向其传递文件的电子邮件地址，命名文件，然后选择[!UICONTROL Send Immediately]。<br>注意：可在[!UICONTROL Advanced Delivery Options]<br>![计划提交](/help/main/c-reports/assets/datawarehouse3.png)下通过FTP提交文件。 |

1. 单击 **[!UICONTROL Request this Report]**。

   根据请求的数据数量，文件提交最多可能需要 72 小时。您可以随时通过单击[!UICONTROL Tools] > [!UICONTROL Data Warehouse] > [!UICONTROL Request Manager]来查看请求进度。

   如果您希望重新请求您过去请求的数据，则可以根据需要从[!UICONTROL Request Manager]中复制旧请求。

有关 [!DNL Data Warehouse] 的更多信息，请访问 [!DNL Analytics] 帮助文档中的以下链接：

* [创建Data Warehouse请求](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/t-dw-create-request.html?lang=zh-Hans)
* [Data Warehouse最佳实践](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-bp.html?lang=zh-Hans)
