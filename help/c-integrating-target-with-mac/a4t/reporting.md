---
keywords: Analytics for Target;A4T;Analytics 作为报表源
description: 了解如何使用Analytics进行目标(A4T)。 A4T提供对使用Analytics量度和受众区段的目标活动的Analytics报表的访问。
title: 如何在A4T中使用报告?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 4abf975095c5e29eea42d67119a426a3922d8d79
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 30%

---


# A4T 报表{#a-t-reporting}

使用[!DNL Adobe Analytics]作为[!DNL Adobe Target](A4T)的报告源，您可以访问[!DNL Target]活动的[!DNL Analytics]报表。

您可以在[!DNL Analytics]和[!DNL Target]中视图活动的报告。

有关使用[!DNL Analytics][!DNL Target]的报告最佳实践，请访问此Adobe Spark Page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)。[

## 概述 {#section_035A62D65608423285D8A5A54731E2C5}

[!DNL Analytics]和[!DNL Target]报告均衡量进入者（参加测试的人员），而不是网站的访客。

每次访客在页面上看到活动内容时，[!DNL Target]都会对[!DNL Analytics]进行服务器到服务器的直接调用，包括访客看到的活动和体验。 [!DNL Target] 进行 [!DNL Analytics] 转换时也会调用。[!DNL Analytics] 将转换添加为名为“事件转 [!DNL Analytics] 换”的特定新活动，该与由收集的其他数据一起跟 [!DNL Analytics]踪。

当使用[!UICONTROL Select]操作并对&#x200B;*进入者*&#x200B;排序时，报表中只显示在选定时间段内接收进入者的体验。

>[!NOTE]
>
>由[!DNL Target]提供支持的报告的延迟为4分钟。 对于由A4T提供支持的活动，在[!DNL Target]和[!DNL Analytics]报告中，最初保存活动后最多可能需要24小时，然后才能按体验划分报表数据。 在划分数据之前的这 24 小时内收集到的数据仍然准确，并且会被分配给正确的体验。

## Analytics 中的报表 {#analytics}

在[!DNL Analytics]中，启用A4T集成后有若干维度和量度可用。

### 维度

* [!UICONTROL 目标分析]  — 通过集成传入的父ID。此维的格式为`Activity ID:Experience ID:3rd ID`。 以下维度是此维度的分类。
* [!UICONTROL Target 活动]
* [!UICONTROL Target 体验]
* [!UICONTROL 目标活动] >体 [!UICONTROL 验]
* [!UICONTROL 第3个ID]  — 可忽略

### 量度

* [!UICONTROL 活动印象]  — 与报  表中的入口 [!DNL Target] 号匹配。
* [!UICONTROL 活动转换]  — 匹配报 [!UICONTROL 表] 中的自定转 [!DNL Target] 换号。

在[!DNL Analysis Workspace]中，使用[!UICONTROL “Analytics for 目标]”面板，以提升和自信的方式分析您的[!DNL Target]活动和体验。 有关详细信息，请参阅&#x200B;*分析工具指南*&#x200B;中的[目标分析(A4T)面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html)。

>[!IMPORTANT]
>
>如果您的[!UICONTROL 目标活动]报告在[!DNL Analytics]列表“未指定”中，而不是列出您的活动，则需要对您的预配帐户进行更新。 请联系客户关怀团队以解决此问题。

有关详细信息和示例，请打开[分析和目标:分析](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)教程的最佳实践，由Adobe Experience League提供。

## Target 中的报表 {#section_C0D1F17F88374B6690BF904D7B83B42E}

当[!DNL Analytics]用作报告源时，[!DNL Target]中的报表显示从[!DNL Analytics]收集的数据。 该报告与其他[!DNL Target]报告有所不同：

* [!UICONTROL 受众]列表显示[!DNL Analytics]报表包可用的受众。
* [!UICONTROL 量度]列表显示通过[!DNL Analytics]可用的每个量度。

   每个量度都可用，包括[!DNL Analytics]中内置的任何自定义或计算量度。

   任何增加的数字都会在报表中显示为正数，即使不希望增加也是如此。 例如，虽然您希望降低跳出率，但是较高的跳出率会显示为具有最高提升度的入选者。根据报表做出决策时，请留心这些量度及类似量度，并确定您是希望降低还是提高这些量度的数值。

在活动启动后，甚至在测试完成后，您都可以将量度或受众应用到[!DNL Target]中的报表。 您无需事先知晓要衡量的确切内容。

单击可直接从视图报告页面活动完整的[!DNL Analytics]报告。

## 活动创建 {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

在活动创建期间，您必须在“[!UICONTROL 设置]”页面中指定活动的目标。此目标将作为报表的默认量度并且在量度选择器中始终列为第一个选项。您将无法像设置常规 Target 活动的报表那样选择报表的区段。[!DNL Analytics]的测试使用[!DNL Adobe Analytics]段，而不是[!DNL Target]受众。

## 为目标(A4T){#section_33A97A691F3A45D497DAF57A844388F0}的Analytics执行脱机计算

您可以为 A4T 执行离线计算，但需要在 [!DNL Analytics] 中完成数据导出步骤。

有关更多信息，请参阅[为 Analytics for Target (A4T) 执行离线计算](/help/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B)。
