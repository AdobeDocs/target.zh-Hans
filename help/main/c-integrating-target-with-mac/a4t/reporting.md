---
keywords: analytics for target；a4t；Analytics作为报表源；Analytics
description: 了解如何将Analytics用于 [!DNL Target] (A4T)。 通过A4T可访问Analytics报表 [!DNL Target] 使用Analytics量度和受众区段的活动。
title: 如何在A4T中使用报表？
feature: Analytics for Target (A4T)
exl-id: cab5dc5f-166a-468e-8382-ae734684afdd
source-git-commit: 6857ba1a6410d3140a83a052efc50e9dd1776fd9
workflow-type: tm+mt
source-wordcount: '1310'
ht-degree: 45%

---

# A4T 报表

使用 [!DNL Adobe Analytics] 作为的报表源 [!DNL Adobe Target] (A4T)让您能够访问 [!DNL Analytics] 您的报表 [!DNL Target] 活动。

您可以在中和报表中查看活动的报表 [!DNL Analytics] 和 [!DNL Target].

要了解报告最佳实践，请使用 [!DNL Analytics] 对象 [!DNL Target]， [访问此Adobe Spark Page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## 概述 {#section_035A62D65608423285D8A5A54731E2C5}

两者 [!DNL Analytics] 和 [!DNL Target] 报表衡量参加测试的人员，而不是网站的访客。

每次访客在页面上看到活动内容时， [!DNL Target] 对进行直接服务器到服务器调用 [!DNL Analytics]，包括访客看到的活动和体验。 [!DNL Target] 也调用 [!DNL Analytics] 每次进行转换时。 [!DNL Analytics] 将转化添加为特定新内容 [!DNL Analytics] 名为“活动转化”的事件，与收集的其他数据一起进行跟踪 [!DNL Analytics].

当 [!UICONTROL 选择] 操作已使用，并且您排序为 *参加者*，则报表中只会显示选定时间段内收到参加者的体验。

>[!NOTE]
>
>由提供支持的报表 [!DNL Target] 会延迟四分钟。 对于由A4T支持的活动，在 [!DNL Target] 和 [!DNL Analytics] 在报表中，可能在最初保存活动后长达24小时，之后才能按体验细分报表数据。 在划分数据之前的这 24 小时内收集到的数据仍然准确，并且会被分配给正确的体验。

## Analytics 中的报表 {#analytics}

In [!DNL Analytics]中，在启用A4T集成之后，提供了多个维度和量度。

### 维度

* [!UICONTROL 目标分析]  — 通过集成传入的父ID。 此维度的格式为 `Activity ID:Experience ID:3rd ID`. 以下维度是此维度的分类。
* [!UICONTROL Target 活动]
* [!UICONTROL Target 体验]
* [!UICONTROL Target活动] > [!UICONTROL 体验]
* [!UICONTROL 第三个ID]  — 可以忽略

### 量度

* [!UICONTROL 活动展示次数]  — 匹配 [!UICONTROL 参加者] 中的数字 [!DNL Target] 报告。
* [!UICONTROL 活动转化]  — 匹配 [!UICONTROL 自定义转化] 中的数字 [!DNL Target] 报告。

In [!DNL Analysis Workspace]，使用 [!UICONTROL 目标分析] 用于分析您的 [!DNL Target] 提升度和置信度高的活动和体验。 有关更多信息，请参阅 [Analytics for Target (A4T)面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=zh-Hans) 在 *Analytics工具指南*.

>[!IMPORTANT]
>
>如果您的 [!UICONTROL Target活动] 报告位置 [!DNL Analytics] 列出“未指定”而不是列出您的活动，需要更新您的已设置帐户。 请联系客户关怀团队以解决此问题。

有关详细信息和示例，请打开 [Analytics和Target：分析最佳实践](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) 教程，由Adobe Experience League提供。

## 报告位置 [!DNL Target] {#section_C0D1F17F88374B6690BF904D7B83B42E}

时间 [!DNL Analytics] 用作报表源，报表 [!DNL Target] 显示从以下位置收集的数据： [!DNL Analytics]. 此报告与其他报告略有不同 [!DNL Target] 报告：

* 此 [!UICONTROL 受众] 列表显示了您可用的受众 [!DNL Analytics] 报表包。
* 此 [!UICONTROL 量度] 列表显示了所有可用的量度，通过 [!DNL Analytics].

   每个量度都是可用的，包括内置的任何自定义或计算量度 [!DNL Analytics].

   任何增加的数字在报表中显示为正数，即使不希望增加。 例如，虽然您希望降低跳出率，但是较高的跳出率会显示为具有最高提升度的入选者。根据报表做出决策时，请留心这些量度及类似量度，并确定您是希望降低还是提高这些量度的数值。

您可以在中将量度或受众应用于报表 [!DNL Target] 活动开始之后，甚至测试完成之后。 您无需事先知晓要衡量的确切内容。

单击以查看完整的 [!DNL Analytics] 直接从“活动报告”页面报告。

## 活动创建 {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

在活动创建期间，您必须在“[!UICONTROL 设置]”页面中指定活动的目标。此目标将作为报表的默认量度并且在量度选择器中始终列为第一个选项。您将无法像设置常规 Target 活动的报表那样选择报表的区段。测试 [!DNL Analytics] 用途 [!DNL Adobe Analytics] 区段，而不是 [!DNL Target] 受众。

## 为Analytics for Adobe Target (A4T)执行离线计算 {#section_B34BD016C8274C97AC9564F426B9607E}

您可以使用对A4T的置信度和置信区间执行离线计算 [!DNL Target] [完全置信度计算器](/help/main/assets/complete_confidence_calculator.xlsx) Excel文件，但需要在中完成数据导出步骤 [!DNL Analytics].

对于A4T，我们使用 [韦尔奇t检验](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} 连续变量的计算（而不是二进制量度）。 在 Analytics 中，会始终跟踪访客，并计入所执行的每项操作。因此，如果访客进行了多次购买或多次访问了某个成功量度，则会计入这些额外的点击。这会使量度变为连续变量。要执行Welch的t检验计算，需要“平方和”来计算方差，方差用作t统计量的分母。 [A/Bn测试中的统计计算](/help/main/c-reports/statistical-methodology/statistical-calculations.md) 说明使用的数学公式的详细信息。 平方和可以从 [!DNL Analytics]. 要获取平方和数据，您需要导出样本时间段内要优化的量度在访客级别对应的数值。

例如，如果您针对每位访客的页面查看次数进行优化，则可以导出一个样本，即在指定的时间段内（可能几天）每位访客的页面查看总次数（只需几千个数据点）。 之后，您可以对每个值求平方，然后将总数相加（此处的运算顺序至关重要）。此“平方和”值随后可用在完整置信度计算器中。应在该电子表格的“收入”部分中使用这些值。

**使用 [!DNL Analytics] 数据导出功能执行此操作：**

1. 登录到 [!DNL Adobe Analytics]。
1. 单击&#x200B;**[!UICONTROL 工具]** > **[!UICONTROL Data Warehouse]**。
1. 在 **[!UICONTROL Data Warehouse 请求]**&#x200B;选项卡中，填写相应的字段。

   有关各个字段的更多信息，请参阅 [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html) 中的“Data Warehouse 请求描述”。

   | 字段 | 说明 |
   |--- |--- |
   | 请求名称 | 指定请求的名称。 |
   | 报告日期 | 指定时间段和时间粒度。<br>对于首次请求，最好选择不超过 1 小时或 1 天的数据。请求的时间段越长，Data Warehouse 文件处理的时间也就会越长，因此第一次最好请求较短时间段内的数据，以确保文件返回预期的结果。之后，转到“请求管理器”，复制您的请求，然后在第二次请求中请求更多的数据。此外，如果将粒度切换为“无”以外的任何粒度，文件大小都将急剧增加。<br>![Data Warehouse](/help/main/c-reports/assets/datawarehouse.png) |
   | 可用区段 | 根据需要应用区段。 |
   | 划分 | 选择所需的维度：“标准”维度为开箱即用 (OOTB) 维度，而“自定义”维度包含 eVar 和 prop。如果需要访客ID级别信息，建议您使用“访客ID”，而不是“Experience Cloud访客ID”。<ul><li>访客 ID 是 Analytics 使用的最终 ID。访客 ID 将为 AID（如果客户是旧客户）或 MID（如果客户是新客户，或者清除了自 MC 访客 ID 服务启动以来的 Cookie）。</li><li>仅当客户是新客户，或者清除了自 MC 访客 ID 服务启动以来的 Cookie 时，才会为客户设置 Experience Cloud 访客 ID。</li></ul> |
   | 量度 | 选择所需的量度。“标准”量度为开箱即用量度，而“自定义”量度包含自定义事件。 |
   | 报表预览 | 在计划报表之前查看您的设置。<br>![Data Warehouse 2](/help/main/c-reports/assets/datawarehouse2.png) |
   | 计划提交 | 输入要将文件提交到的电子邮件地址，为文件命名，然后选择[!UICONTROL 立即发送]。<br>注意：可通过[!UICONTROL 高级提交选项]<br>![计划提交](/help/main/c-reports/assets/datawarehouse3.png)下方的 FTP 来提交文件。 |

1. 单击&#x200B;**[!UICONTROL 请求此报表]**。

   根据请求的数据数量，文件提交最多可能需要 72 小时。您可以随时查看请求的进度，方法是单击“[!UICONTROL 工具]”>“[!UICONTROL Data Warehouse]”>“[!UICONTROL 请求管理器]”。

   如果您希望重新请求您过去请求的数据，则可以从 [!UICONTROL 请求管理器] 根据需要。

有关 [!DNL Data Warehouse] 的更多信息，请访问 [!DNL Analytics] 帮助文档中的以下链接：

* [创建 Data Warehouse 请求](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/t-dw-create-request.html)
* [data warehouse最佳实践](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-bp.html)
