---
keywords: Analytics for Target;A4T;Analytics作为报表源；Analytics
description: 了解如何将Analytics用于 [!DNL Target] (A4T)。 通过A4T，可以访问 [!DNL Target] 活动。
title: 如何在A4T中使用报表？
feature: Analytics for Target (A4T)
exl-id: cab5dc5f-166a-468e-8382-ae734684afdd
source-git-commit: 6857ba1a6410d3140a83a052efc50e9dd1776fd9
workflow-type: tm+mt
source-wordcount: '1312'
ht-degree: 45%

---

# A4T 报表

使用 [!DNL Adobe Analytics] 作为报表源 [!DNL Adobe Target] (A4T)允许您访问 [!DNL Analytics] 报告 [!DNL Target] 活动。

您可以在这两处查看活动的报表 [!DNL Analytics] 和 [!DNL Target].

要了解使用 [!DNL Analytics] 表示 [!DNL Target], [访问Adobe Spark Page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## 概述 {#section_035A62D65608423285D8A5A54731E2C5}

两者兼有 [!DNL Analytics] 和 [!DNL Target] 报表测量参加者（参加测试的人员），而不是网站的访客。

每次访客在页面上看到活动内容时， [!DNL Target] 对 [!DNL Analytics]，包括访客查看的活动和体验。 [!DNL Target] 也会调用 [!DNL Analytics] 每次进行转换时。 [!DNL Analytics] 将转化添加为特定的新 [!DNL Analytics] 名为“活动转化”的事件，该事件与 [!DNL Analytics].

当 [!UICONTROL 选择] 操作，然后进行排序 *参加者*，则报表中只会显示在选定时间段内接收参加者的体验。

>[!NOTE]
>
>报告由 [!DNL Target] 延迟4分钟。 对于由A4T提供支持的活动，请在 [!DNL Target] 和 [!DNL Analytics] 报表中，活动最初保存后最长可能需要24小时，才能按体验划分报表数据。 在划分数据之前的这 24 小时内收集到的数据仍然准确，并且会被分配给正确的体验。

## Analytics 中的报表 {#analytics}

在 [!DNL Analytics]，则在启用A4T集成后，会提供多个维度和量度。

### 维度

* [!UICONTROL Analytics for Target]  — 通过集成传入的父ID。 此维度的格式为 `Activity ID:Experience ID:3rd ID`. 以下维度是此维度的分类。
* [!UICONTROL Target 活动]
* [!UICONTROL Target 体验]
* [!UICONTROL Target活动] > [!UICONTROL 体验]
* [!UICONTROL 第3个ID]  — 可以忽略

### 量度

* [!UICONTROL 活动展示次数]  — 匹配 [!UICONTROL 参加者] 数字 [!DNL Target] 报表。
* [!UICONTROL 活动转化]  — 匹配 [!UICONTROL 自定义转化] 数字 [!DNL Target] 报表。

在 [!DNL Analysis Workspace]，则使用 [!UICONTROL Analytics for Target] 分析 [!DNL Target] 具有提升度和置信度的活动和体验。 有关更多信息，请参阅 [Analytics for Target(A4T)面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=zh-Hans) 在 *Analytics工具指南*.

>[!IMPORTANT]
>
>如果 [!UICONTROL Target活动] 报告 [!DNL Analytics] 会列出“未指定”，而不是列出您的活动，而是需要对您配置的帐户进行更新。 请联系客户关怀团队以解决此问题。

有关详细信息和示例，请打开 [Analytics和Target:分析最佳实践](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) 教程，由Adobe Experience League提供。

## 报表 [!DNL Target] {#section_C0D1F17F88374B6690BF904D7B83B42E}

When [!DNL Analytics] 用作报表源，报表位于 [!DNL Target] 显示从 [!DNL Analytics]. 报表与其他报表有些不同 [!DNL Target] 报表：

* 的 [!UICONTROL 受众] 列表显示了可供您使用的受众 [!DNL Analytics] 报表包。
* 的 [!UICONTROL 量度] 列表显示了所有可用的量度 [!DNL Analytics].

   每个量度都可用，包括任何内置的自定义量度或计算量度 [!DNL Analytics].

   任何增加的数字都会在报表中显示为正值，即使不希望增加也是如此。 例如，虽然您希望降低跳出率，但是较高的跳出率会显示为具有最高提升度的入选者。根据报表做出决策时，请留心这些量度及类似量度，并确定您是希望降低还是提高这些量度的数值。

您可以在 [!DNL Target] 活动开始后，或甚至在测试完成后。 您无需事先知晓要衡量的确切内容。

单击以查看完整 [!DNL Analytics] 直接从活动报表页面报告。

## 活动创建 {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

在活动创建期间，您必须在“[!UICONTROL 设置]”页面中指定活动的目标。此目标将作为报表的默认量度并且在量度选择器中始终列为第一个选项。您将无法像设置常规 Target 活动的报表那样选择报表的区段。测试 [!DNL Analytics] 使用 [!DNL Adobe Analytics] 区段而不是 [!DNL Target] 受众。

## 为Analytics for Adobe Target(A4T)执行离线计算 {#section_B34BD016C8274C97AC9564F426B9607E}

您可以使用 [!DNL Target] [完整置信度计算器](/help/main/assets/complete_confidence_calculator.xlsx) Excel文件，但需要在中完成数据导出步骤 [!DNL Analytics].

对于A4T，我们使用 [韦尔奇的T检验](https://en.wikipedia.org/wiki/Welch%27s_t-test)连续变量（而非二进制量度）的{target=_blank}计算。 在 Analytics 中，会始终跟踪访客，并计入所执行的每项操作。因此，如果访客进行了多次购买或多次访问了某个成功量度，则会计入这些额外的点击。这会使量度变为连续变量。要执行Welch的t检验计算，需要“平方和”来计算方差，该方差用在t统计量的分母中。 [A/Bn测试中的统计计算](/help/main/c-reports/statistical-methodology/statistical-calculations.md) 解释所用数学公式的详细信息。 平方和可从 [!DNL Analytics]. 要获取平方和数据，您需要导出样本时间段内要优化的量度在访客级别对应的数值。

例如，如果您优化为每位访客的页面查看次数，那么您将导出一个特定时间段（可能是几天）内每位访客总页面查看次数的样本（您只需要几千个数据点）。 之后，您可以对每个值求平方，然后将总数相加（此处的运算顺序至关重要）。此“平方和”值随后可用在完整置信度计算器中。应在该电子表格的“收入”部分中使用这些值。

**使用 [!DNL Analytics] 数据导出功能执行此操作：**

1. 登录到 [!DNL Adobe Analytics]。
1. 单击&#x200B;**[!UICONTROL 工具]** > **[!UICONTROL Data Warehouse]**。
1. 在 **[!UICONTROL Data Warehouse 请求]**&#x200B;选项卡中，填写相应的字段。

   有关各个字段的更多信息，请参阅 [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html) 中的“Data Warehouse 请求描述”。

   | 字段 | 说明 |
   |--- |--- |
   | 请求名称 | 指定请求的名称。 |
   | 报告日期 | 指定时间段和时间粒度。<br>对于首次请求，最好选择不超过 1 小时或 1 天的数据。请求的时间段越长，Data Warehouse 文件处理的时间也就会越长，因此第一次最好请求较短时间段内的数据，以确保文件返回预期的结果。之后，转到“请求管理器”，复制您的请求，然后在第二次请求中请求更多的数据。此外，如果将粒度切换为“无”以外的任何内容，则文件大小将会急剧增加。<br>![Data Warehouse](/help/main/c-reports/assets/datawarehouse.png) |
   | 可用区段 | 根据需要应用区段。 |
   | 划分 | 选择所需的维度：“标准”维度为开箱即用 (OOTB) 维度，而“自定义”维度包含 eVar 和 prop。如果需要访客ID级别信息，建议您使用“访客ID”，而不是“Experience Cloud访客ID”。<ul><li>访客 ID 是 Analytics 使用的最终 ID。访客 ID 将为 AID（如果客户是旧客户）或 MID（如果客户是新客户，或者清除了自 MC 访客 ID 服务启动以来的 Cookie）。</li><li>仅当客户是新客户，或者清除了自 MC 访客 ID 服务启动以来的 Cookie 时，才会为客户设置 Experience Cloud 访客 ID。</li></ul> |
   | 量度 | 选择所需的量度。“标准”量度为开箱即用量度，而“自定义”量度包含自定义事件。 |
   | 报表预览 | 在计划报表之前查看您的设置。<br>![Data Warehouse 2](/help/main/c-reports/assets/datawarehouse2.png) |
   | 计划提交 | 输入要将文件提交到的电子邮件地址，为文件命名，然后选择[!UICONTROL 立即发送]。<br>注意：可通过[!UICONTROL 高级提交选项]<br>![计划提交](/help/main/c-reports/assets/datawarehouse3.png)下方的 FTP 来提交文件。 |

1. 单击&#x200B;**[!UICONTROL 请求此报表]**。

   根据请求的数据数量，文件提交最多可能需要 72 小时。您可以随时查看请求的进度，方法是单击“[!UICONTROL 工具]”>“[!UICONTROL Data Warehouse]”>“[!UICONTROL 请求管理器]”。

   如果您希望重新请求过去请求的数据，则可以复制 [!UICONTROL 请求管理器] 根据需要。

有关 [!DNL Data Warehouse] 的更多信息，请访问 [!DNL Analytics] 帮助文档中的以下链接：

* [创建 Data Warehouse 请求](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/t-dw-create-request.html)
* [data warehouse最佳实践](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-bp.html)
