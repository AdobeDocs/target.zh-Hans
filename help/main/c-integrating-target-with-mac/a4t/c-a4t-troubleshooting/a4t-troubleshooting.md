---
keywords: Analytics 跟踪服务器;A4T;Analytics 区段;报表包;数据不正确;孤立;SDID;VisitorAPI.js;mboxMCSDID;虚拟;未指定
description: 探索客户在使用Analytics for [!DNL Target] (A4T)。
title: 如何对Analytics和 [!DNL Target] 集成(A4T)
feature: Analytics for Target (A4T)
exl-id: 7d155cbe-e799-43b5-afc2-1aea43f432ba
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 39%

---

# Analytics和 [!DNL Target] 集成(A4T)

本主题介绍在使用 [!DNL Adobe Analytics] 作为报表源 [!DNL Adobe Target] (A4T)。

## 活动在 Analytics 中未显示数据，反而列为“未指定”。 {#unspecified}

数据显示为“未指定”的原因有以下几点：

* [!DNL Target] 中的分类未完全处理。

   在首次保存后，分类通常需要24到72小时才能对报表进行分类。

* 报表包中未包含任何数据，但 [!DNL Target] 尝试了对点击进行分类。在发生首次点击之前，[!DNL Target] 将一直无法对数据进行分类。

   请确保报表包中至少有一次点击。

* 从 [!DNL Target] 向 [!DNL Analytics] 的分类调用失败。

   [请联系客户关怀团队](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)，以获取帮助。

如果您按“Analytics for Target”维度划分“未指定”行，并且该行不包含活动ID，则意味着所有内容均已正确分类。 如果活动ID列在此处，则它将用作分类问题的指示。

>[!NOTE]
>
>有时，数据会在报表中正确显示，但随后会还原为“未指定”，因为添加了未完成分类的新活动。 请记住，在首次保存后，通常需要24到72小时才能对报表进行分类。
>
>列为“未指定”时，不会丢失任何数据。运行分类后，数据会正确分配到相应的活动或体验。

## A4T活动报表包含一行，其中包含许多“未指定”事件。 {#added_unspecified_events}

可能存在“[!UICONTROL 未指定]“事件”行，具体取决于用于显示数据的量度。

通常，如果您在报表中选择的公用量度不是 [!DNL Target] — 特定(例如， [!UICONTROL 页面查看次数], [!UICONTROL 访问次数], [!UICONTROL 独特访客]，等等)。 在本例中， [!UICONTROL &quot;未指定&quot;] 行包含所有 [!UICONTROL 页面查看次数], [!UICONTROL 访问次数]和 [!UICONTROL 独特访客] 与 [!DNL Target] 活动。

那行没有 [!DNL Target] — 关联信息（例如，无访客、访问次数或展示次数）。 有关更多信息，请参阅 [报表中的“未指定”、“无”、“其他”和“未知”](https://experienceleague.adobe.com/docs/analytics/technotes/unspecified.html?lang=en) 在 *Analytics技术说明*.

如果您选择 [!DNL Target]报表中的特定量度， [!UICONTROL &quot;未指定&quot;] 行不显示。 要避免在报表中包含该变量，唯一的方法是设置 [!DNL Target] 对从该页面发送的每个请求都调用，这种情况不常见，也不是必需的。

## 启动 A4T 后，我的 Analytics 数据显示夸大的访问或访客计数。 {#section_4BE374E573D44FB7918611699B74F58E}

有关更多信息，请参阅[在 A4T 中最大限度地减少夸大的访问和访客计数](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

## 预计收入提升量度显示的数据不正确。 {#section_35D766E5E4D347C39E15D08AA883FBB0}

Analytics 中不会提供提升度和置信度详细信息。但是，Target 报表中会提供这些信息。

## 活动未显示在 Analytics 报表中。 {#section_F7001EB4670F4B3497CC7DA60BBDA6D5}

A4T 活动要求指定 Analytics 跟踪服务器。请参阅 [使用Analytics跟踪服务器](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) 以确保Analytics跟踪服务器设置正确。

>[!NOTE]
>
>如果您使用的是at.js版本0.9.1（或更高版本），则在活动创建期间无需指定跟踪服务器。 at.js库会自动将跟踪服务器值发送到 [!DNL Target]. 在活动创建期间，您可以将“[!UICONTROL 目标和设置]”页面上的“[!UICONTROL 跟踪服务器]”字段留空。

## 我的 Analytics 区段未显示在 Target 中。 {#section_DEE87F1557834F448E99381D3D02EEEF}

开始创建 A4T 活动之前，请确保您拥有适当的权限。

* 属于Adobe Analytics中的“Web服务访问”组，可以将Analytics用作Target报表源
* 是一个或多个有权访问Analytics和Target的Experience Cloud组的成员。
* 确认左侧导航的“营销应用程序”部分中显示了 Analytics 和 Target。

## 跳出率、跳出次数和退出次数量度在报表中显示为正值。 {#section_B5C3D56EF0344407AE67ABEB93037F5A}

在报表中显示为正值的量度是一个已知问题。

虽然这些量度为负值，但是 Target 报表中显示的提升度似乎表示这些量度为正值。例如，虽然您希望降低跳出率，但是较高的跳出率会显示为具有最高提升度的入选者。根据报表做出决策时，请留心这些量度及类似量度，并确定您是希望降低还是提高这些量度的数值。

## 不显示我需要的报表包。 {#section_BD8F956E41D6475B98B7BF0C74CC387C}

显示在 [!DNL Target Standard/Premium] 是为 [!DNL Analytics] 作为报表源 [!DNL Target] (A4T)。 您可能看不到每个拥有的报表包。

如果您使用多个报表源，则报表包必须位于 [!DNL Target] 也是。 如果报表包不在默认报表源中，则不会显示报表包。

如果您仍未看到要查找的报表包，请联系 [客户关怀](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) 启用它。

## 报表中显示的数据比预期的要少。 {#section_75002584FA63456D8D9086172925DD8D}

请检查您的实施，特别是要检查访客符合体验条件的页面，并确保 [!DNL Target] 和 [!DNL Analytics] 调用中的补充数据 ID 相匹配。

* **at.js 1.x**:在 [!DNL Target] 调用中，补充ID包含在 `mboxMCSDID` 参数。 在 [!DNL Analytics] 调用中，补充数据 ID 包含在 `sdid` 参数中。
* **at.js 2.x**:在 [!DNL Target] 调用时，补充ID将在HTTP标头中返回，作为 `experienceCloud.analytics.supplementalDataId`. 在 [!DNL Analytics] 调用中，补充数据 ID 包含在 `sdid` 参数中。

检查补充ID的最简单方法是使用Adobe Experience Platform Debugger。

如果尚未安装调试器，请参阅 [Adobe Experience Platform Debugger简介](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html).

![调试程序](/help/main/c-integrating-target-with-mac/a4t/assets/debugger.png)

如果 [!DNL Target] 呼叫，确认 [!DNL VisitorAPI.js] 文件加载之前 [!DNL at.js]. 如果 [!DNL Analytics] 调用中没有补充数据 ID，请确认 [!DNL Target] 调用是否在 [!DNL Analytics] 调用之前触发。

有关更多信息，请参阅 [Analytics for Target 实施](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#concept_CE78750AC2A4487D8ACD9369B3EAC85A)或联系[客户关怀团队](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。
