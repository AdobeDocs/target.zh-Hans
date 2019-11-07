---
keywords: Analytics for Target;A4T;Analytics 作为报表源
description: 使用 Analytics 作为 Target 报表源 (A4T)，您可以访问 Target 活动的 Analytics 报表。
title: A4T 报表
subtopic: 多变量测试
topic: Standard
uuid: bd3a7fa4-ba45-4ea3-81b6-fc2584831ce4
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# A4T 报表{#a-t-reporting}

使用 Analytics 作为 Target 报表源 (A4T)，您可以访问 Target 活动的 Analytics 报表。

在 Analytics 和 Target Standard/Premium 中，均可以查看活动的报表。

有关使用 Analytics for Target 进行报告的最佳做法，请[访问此 Adobe Spark 页面](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)。

## 概述 {#section_035A62D65608423285D8A5A54731E2C5}

Analytics 报表和 Target 报表衡量的都是参加者（参加测试的人员），而不是网站的访客。

每当访客在页面上看到活动内容时，Target 都会对 Analytics 进行直接的服务器到服务器调用，包括访客看到的活动和体验。在发生转化时，Target 也会调用 Analytics。Analytics 会将转化作为特定的新 Analytics 事件进行添加，该事件名为“活动转化”，会与 Analytics 收集的其他数据一起被跟踪。

如果使用“选择”操作并按“参加者”**&#x200B;排序，那么报表中将仅显示在选定的时间段内有参加者的体验。

>[!NOTE]
>
>由 Target 提供支持的报表会有四分钟的延迟。对于由 A4T 提供支持的活动，在 Target 报表和 Analytics 报表中，活动首次保存后最多可能需要经过 24 小时，才能按体验划分报表数据。在划分数据之前的这 24 小时内收集到的数据仍然准确，并且会被分配给正确的体验。

## Analytics 中的报表 {#section_F6884872DC864AE7913587FAED4CD11C}

在 Analytics 的左侧菜单中，单击 **[!UICONTROL Target]** &gt; **[!UICONTROL Target 活动]**。在 Target 中，活动的报表会自动显示 Analytics 数据、量度和区段。从网站收集数据大约一小时后，数据便会显示在这些报表中。报表中的所有量度、受众和值都来自您在设置活动时选择的报表包。

在 Analytics 中，可使用“目标活动”报表来查看 Target 活动的结果。Test&amp;Target（旧版）报表提供有关旧版 Test&amp;Target 插件样式页面集成的信息，该报表中不包含 Analytics for Target 数据。在“活动”报表中，可查看有关 Target 体验的信息。单击&#x200B;**[!UICONTROL 量度]**，然后选择&#x200B;**目标]量度类型。[!UICONTROL **&#x200B;您的报表有两个可用的量度：

* **活动参加：**&#x200B;匹配 Target 报表中的参加者数量。
* **活动转化：**&#x200B;匹配 Target 报表中的自定义转化数量。

>[!NOTE]
>
>Analytics 中还提供了 Target 提升度和置信度详细信息。有关详细信息，请参 [阅《分析组件指南》中的](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/report-target-lift-confidence.html) “目标提 *升和置信度”*。

>[!IMPORTANT]
>
>如果 Analytics 中的“目标活动”报表列出“未指定”，而没有列出您的活动，则需要更新您的已配置帐户。请联系客户关怀团队以解决此问题。

## Target 中的报表 {#section_C0D1F17F88374B6690BF904D7B83B42E}

在将 Analytics 用作报表源时，Target Standard 中的报表会显示从 Analytics 收集的数据。该报表与其他 Target Standard 报表有些不同。

* “受众”列表显示 Analytics 报表包可用的受众。
* “量度”列表显示可通过 Analytics 使用的每个量度。

   每个量度均可用，包括所有自定义量度或 Analytics 中的内置计算量度。

   请注意，在报表中，任何增大的数字都显示为正值，即使增大的数字实际上并不是所需的结果也是如此。例如，虽然您希望降低跳出率，但是较高的跳出率会显示为具有最高提升度的入选者。根据报表做出决策时，请留心这些量度及类似量度，并确定您是希望降低还是提高这些量度的数值。

您可以在测试开始后，甚至在测试完成后，将量度或受众应用到 Target 中的报表。您无需事先知晓要衡量的确切内容。

单击可直接从活动报表页面查看完整的 Analytics 报表。

## Analysis Workspace 中的报表 {#reports-in-analysis-workspace}

您可以使用 [!DNL Adobe Analysis Workspace] 来深入挖掘和可视化数据，或揭示隐藏在表面下的洞察。

For detailed information and examples, open the [Analytics &amp; Target: Best Practices for Analysis tutorial](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), provided by Adobe Experience League.

## 活动创建 {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

在活动创建期间，您必须在“[!UICONTROL 设置]”页面中指定活动的目标。此目标将作为报表的默认量度并且在量度选择器中始终列为第一个选项。您将无法像设置常规 Target 活动的报表那样选择报表的区段。Analytics 测试使用的是 Adobe Analytics 区段，而不是 Target Standard 受众。

## 为 Analytics for Target (A4T) 执行离线计算{#section_33A97A691F3A45D497DAF57A844388F0}

您可以为 A4T 执行离线计算，但需要在 [!DNL Analytics] 中完成数据导出步骤。

有关更多信息，请参阅[为 Analytics for Target (A4T) 执行离线计算](../../c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B)。
