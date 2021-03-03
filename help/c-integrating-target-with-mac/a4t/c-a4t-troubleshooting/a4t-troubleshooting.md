---
keywords: Analytics 跟踪服务器;A4T;Analytics 区段;报表包;数据不正确;孤立;SDID;VisitorAPI.js;mboxMCSDID;虚拟;未指定
description: 浏览客户在使用Analytics for 目标(A4T)时遇到的常见问题。
title: 如何对Analytics和目标集成(A4T)进行疑难解答
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: f48c54eb12a416312c3ceb6c1b36c3fc43496e78
workflow-type: tm+mt
source-wordcount: '1003'
ht-degree: 42%

---


# Analytics 与 Target 集成 (A4T) 故障诊断

本主题涵盖使用[!DNL Adobe Analytics]作为[!DNL Adobe Target](A4T)的报告源时遇到的一些常见问题。

## 活动在 Analytics 中未显示数据，反而列为“未指定”。{#unspecified}

数据显示为“未指定”的原因有几个：

* [!DNL Target] 中的分类未完全处理。

   分类通常需要24至72小时，才能在第一次保存后对报表进行分类。

* 报表包中未包含任何数据，但 [!DNL Target] 尝试了对点击进行分类。在发生首次点击之前，[!DNL Target] 将一直无法对数据进行分类。

   请确保报表包中至少有一次点击。

* 从 [!DNL Target] 向 [!DNL Analytics] 的分类调用失败。

   [请联系客户关怀团队](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)，以获取帮助。

如果按“Analytics for 目标”维划分“未指定”行，且它不包含活动ID，则表示所有内容均已正确分类。 如果活动ID列在此处，则它将作为分类问题的指示。

>[!NOTE]
>
>有时，数据会在报表中正确显示，但随后会还原为“未指定”，因为添加了尚未完成分类的新活动。 请记住，对报表进行分类通常需要24到72小时。
>
>列为“未指定”时，不会丢失任何数据。运行分类后，数据会正确分配到相应的活动或体验。

## A4T活动报表包含具有许多“未指定”事件的行。{#added_unspecified_events}

报表中可能显示“[!UICONTROL 未指定]”事件行，具体取决于用于显示数据的量度。

通常，如果您在报表中选择了非特定于[!DNL Target]的公用量度(例如，[!UICONTROL 页面视图]、[!UICONTROL 访问]、[!UICONTROL 唯一访客]等)，则此行会显示。 在这种情况下，[!UICONTROL &quot;Unspecified&quot;]行包括所有未与[!DNL Target]视图关联的[!UICONTROL 页面访客]、[!UICONTROL 访问]和[!UICONTROL 唯一活动]。

该行没有任何与[!DNL Target]相关的信息(例如，没有访客、访问或展示次数)。 有关详细信息，请参阅&#x200B;*分析技术说明*&#x200B;中报告](https://experienceleague.adobe.com/docs/analytics/technotes/unspecified.html?lang=en)中的[“未指定”、“无”、“其他”和“未知”。

如果在报表中选择[!DNL Target]特定量度，则不显示[!UICONTROL &quot;未指定&quot;]行。 要避免报表中出现此问题，唯一的方法是对从该页面发送的每个请求设置[!DNL Target]调用，这并不常见，也不必要。

## 启动 A4T 后，我的 Analytics 数据显示夸大的访问或访客计数。{#section_4BE374E573D44FB7918611699B74F58E}

有关更多信息，请参阅[在 A4T 中最大限度地减少夸大的访问和访客计数](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

## 预计收入提升量度显示的数据不正确。{#section_35D766E5E4D347C39E15D08AA883FBB0}

Analytics 中不会提供提升度和置信度详细信息。但是，Target 报表中会提供这些信息。

## 活动未显示在 Analytics 报表中。 {#section_F7001EB4670F4B3497CC7DA60BBDA6D5}

A4T 活动要求指定 Analytics 跟踪服务器。请参阅  [使用Analytics跟踪](/help/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) 服务器来确保正确设置Analytics跟踪服务器。

>[!NOTE]
>
>如果您使用mbox.js版本61（或更高版本）或at.js版本0.9.1（或更高版本），则在创建活动时无需指定跟踪服务器。 mbox.js 或 at.js 库会自动将跟踪服务器值发送到 [!DNL Target]。在活动创建期间，您可以将“[!UICONTROL 目标和设置]”页面上的“[!UICONTROL 跟踪服务器]”字段留空。

## 我的 Analytics 区段未显示在 Target 中。  {#section_DEE87F1557834F448E99381D3D02EEEF}

开始创建 A4T 活动之前，请确保您拥有适当的权限。

* 属于Adobe Analytics中的Web服务访问组，可以将Analytics用作目标的报告源
* 成为有权访问Analytics和目标的一个或多个Experience Cloud组的成员。
* 确认左侧导航的“营销应用程序”部分中显示了 Analytics 和 Target。

## 跳出率、跳出次数和退出次数量度在报表中显示为正值。  {#section_B5C3D56EF0344407AE67ABEB93037F5A}

在报表中显示为正面的量度是已知问题。

虽然这些量度为负值，但是 Target 报表中显示的提升度似乎表示这些量度为正值。例如，虽然您希望降低跳出率，但是较高的跳出率会显示为具有最高提升度的入选者。根据报表做出决策时，请留心这些量度及类似量度，并确定您是希望降低还是提高这些量度的数值。

## 我需要的报表包不显示。{#section_BD8F956E41D6475B98B7BF0C74CC387C}

[!DNL Target Standard/Premium]中显示的报表包列表是已配置[!DNL Analytics]为[!DNL Target](A4T)报告源的报表包的列表。 您可能看不到每个报表包。

如果您使用多个报告源，则报表包还必须位于[!DNL Target]中设置的默认报告源中。 如果报表包不在默认报告源中，则不显示报表包。

如果仍未看到要查找的报表包，请联系[客户关怀](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)以启用它。

## 报表中显示的数据比预期的要少。{#section_75002584FA63456D8D9086172925DD8D}

请检查您的实施，特别是要检查访客符合体验条件的页面，并确保 [!DNL Target] 和 [!DNL Analytics] 调用中的补充数据 ID 相匹配。

* **at.js 1.x**:在调 [!DNL Target] 用中，补充ID包含在参 `mboxMCSDID` 数中。在 [!DNL Analytics] 调用中，补充数据 ID 包含在 `sdid` 参数中。
* **at.js 2.x**:在调 [!DNL Target] 用中，补充ID在HTTP头中返回，作为值 `experienceCloud.analytics.supplementalDataId`。在 [!DNL Analytics] 调用中，补充数据 ID 包含在 `sdid` 参数中。

检查补充ID的最简单方法是使用Adobe Experience Platform调试器。

如果尚未安装调试器，请参阅[Adobe Experience Platform调试器简介](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html)。

![调试程序](/help/c-integrating-target-with-mac/a4t/assets/debugger.png)

如果 [!DNL Target] 调用中没有补充数据 ID，请确认 [!DNL VisitorAPI.js] 文件是否在 [!DNL at.js] 或 [!DNL mbox.js] 之前加载。如果 [!DNL Analytics] 调用中没有补充数据 ID，请确认 [!DNL Target] 调用是否在 [!DNL Analytics] 调用之前触发。

有关更多信息，请参阅 [Analytics for Target 实施](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#concept_CE78750AC2A4487D8ACD9369B3EAC85A)或联系[客户关怀团队](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。
