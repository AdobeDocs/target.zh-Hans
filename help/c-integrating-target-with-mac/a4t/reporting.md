---
keywords: Analytics for Target;A4T;Analytics 作为报表源
description: 了解如何使用Analytics进行目标(A4T)。 A4T为使用Analytics指标和目标区段的活动受众提供对Analytics报告的访问权。
title: 如何在A4T中使用报告?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 32%

---


# A4T 报表{#a-t-reporting}

使用[!DNL Analytics]作为[!DNL Target](A4T)的报告源，您可以访问[!DNL Target]活动的[!DNL Analytics]报告。

您可以在[!DNL Analytics]和[!DNL Target]中视图活动的报告。

有关使用[!DNL Analytics][!DNL Target]的报告最佳实践，请访问此Adobe Spark页面](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)。[

## 概述 {#section_035A62D65608423285D8A5A54731E2C5}

[!DNL Analytics]和[!DNL Target]都会报告进入者（参加测试的人员），而不是网站的访客。

每次访客看到页面上的活动内容时，[!DNL Target]都会对[!DNL Analytics]进行服务器到服务器的直接调用，包括访客看到的活动和体验。 [!DNL Target] 进行转 [!DNL Analytics] 换时也会进行调用。[!DNL Analytics] 将转换添加为名为“ [!DNL Analytics] 活动转换”的特定新事件，该与由收集的其他数据一起 [!DNL Analytics]跟踪。

当使用[!UICONTROL Select]操作并对&#x200B;*进入者*&#x200B;进行排序时，报表中只显示在选定时间段内接收进入者的体验。

>[!NOTE]
>
>由[!DNL Target]提供支持的报告的延迟为4分钟。 对于由A4T支持的活动，在[!DNL Target]和[!DNL Analytics]报告中，最多可能需要24小时才能保存活动，然后才能按体验划分报告数据。 在划分数据之前的这 24 小时内收集到的数据仍然准确，并且会被分配给正确的体验。

## Analytics 中的报表 {#analytics}

在[!DNL Analytics]中，启用A4T集成后有若干维和度量可用。

### 维度

* [!UICONTROL 目标分析] -通过集成传入的父ID。此维的格式为`Activity ID:Experience ID:3rd ID`。 以下维是此维的分类。
* [!UICONTROL Target 活动]
* [!UICONTROL Target 体验]
* [!UICONTROL 目标活动] >体 [!UICONTROL 验]
* [!UICONTROL 第3个ID]  —— 可忽略

### 量度

* [!UICONTROL 活动印象] -与报  表中的入口 [!DNL Target] 号匹配。
* [!UICONTROL 活动转换] -匹配报 [!UICONTROL 表] 中的自定义转 [!DNL Target] 换编号。

在[!DNL Analysis Workspace]中，使用[!UICONTROL 目标分析]面板以提升和自信的方式分析您的[!DNL Target]活动和体验。 有关详细信息，请参阅&#x200B;*分析工具指南*&#x200B;中的[目标分析(A4T)面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html)。

>[!IMPORTANT]
>
>如果您的[!UICONTROL 目标活动]报告在[!DNL Analytics]列表中为“未指定”，而不是列出您的活动，则需要对您的预配帐户进行更新。 请联系客户关怀团队以解决此问题。

有关详细信息和示例，请打开[分析和目标:分析的最佳实践](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)教程，由Adobe Experience League提供。

## Target 中的报表 {#section_C0D1F17F88374B6690BF904D7B83B42E}

当[!DNL Analytics]用作报告源时，[!DNL Target]中的报告显示从[!DNL Analytics]收集的数据。 报告与其他[!DNL Target]报告有所不同：

* [!UICONTROL 受众]列表显示可用于[!DNL Analytics]报表包的受众。
* [!UICONTROL 度量]列表显示通过[!DNL Analytics]可用的每个度量。

   每个指标都可用，包括[!DNL Analytics]中内置的任何自定义或计算指标。

   请注意，在报表中，任何增大的数字都显示为正值，即使增大的数字实际上并不是所需的结果也是如此。例如，虽然您希望降低跳出率，但是较高的跳出率会显示为具有最高提升度的入选者。根据报表做出决策时，请留心这些量度及类似量度，并确定您是希望降低还是提高这些量度的数值。

在[!DNL Target]活动开始后，甚至在测试完成后，您都可以将度量或受众应用到报告。 您无需事先知晓要衡量的确切内容。

单击直接从视图报告页面活动完整的[!DNL Analytics]报告。

## 活动创建 {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

在活动创建期间，您必须在“[!UICONTROL 设置]”页面中指定活动的目标。此目标将作为报表的默认量度并且在量度选择器中始终列为第一个选项。您将无法像设置常规 Target 活动的报表那样选择报表的区段。使用[!DNL Analytics]的测试使用[!DNL Adobe Analytics]段，而不是[!DNL Target]受众。

## 为目标(A4T){#section_33A97A691F3A45D497DAF57A844388F0}执行Analytics的脱机计算

您可以为 A4T 执行离线计算，但需要在 [!DNL Analytics] 中完成数据导出步骤。

有关更多信息，请参阅[为 Analytics for Target (A4T) 执行离线计算](/help/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B)。
