---
keywords: Analytics for Target;A4T;Analytics作为报表源；Analytics
description: 了解如何将Analytics用于 [!DNL Target] (A4T)。 通过A4T，可以访问 [!DNL Target] 活动。
title: 如何在A4T中使用报表？
feature: Analytics for Target (A4T)
exl-id: cab5dc5f-166a-468e-8382-ae734684afdd
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 29%

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

## 为Analytics for Adobe Target(A4T)执行离线计算 {#section_33A97A691F3A45D497DAF57A844388F0}

您可以为 A4T 执行离线计算，但需要在 [!DNL Analytics] 中完成数据导出步骤。

有关更多信息，请参阅[为 Analytics for Target (A4T) 执行离线计算](/help/main/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B)。
