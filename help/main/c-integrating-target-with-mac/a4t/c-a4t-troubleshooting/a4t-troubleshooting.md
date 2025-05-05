---
keywords: Analytics 跟踪服务器;A4T;Analytics 区段;报表包;数据不正确;孤立;SDID;VisitorAPI.js;mboxMCSDID;虚拟;未指定
description: 探讨客户在使用 Analytics for [!DNL Target] (A4T) 时遇到的常见问题。
title: 如何为 Analytics 与 [!DNL Target] 集成 (A4T) 排除故障
feature: Analytics for Target (A4T)
exl-id: 7d155cbe-e799-43b5-afc2-1aea43f432ba
source-git-commit: 0be54d82e25eb919102f6098c1b1db76ab291675
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 88%

---

# 为 Analytics 与 [!DNL Target] Target 集成 (A4T) 排除故障

本主题涵盖了在使用 [!DNL Adobe Analytics] 作为 [!DNL Adobe Target] (A4T) 的报表源时会遇到的一些常见问题。

## 活动在 Analytics 中未显示数据，反而列为“未指定”。 {#unspecified}

有多个原因会可能导致数据显示为“未指定”：

* [!DNL Target] 中的分类未完全处理。

  在首次保存后，分类通常需要 24 到 72 个小时来分类报表。

* 报表包中未包含任何数据，但 [!DNL Target] 尝试了对点击进行分类。在发生首次点击之前，[!DNL Target] 将一直无法对数据进行分类。

  请确保报表包中至少有一次点击。

* 从 [!DNL Target] 向 [!DNL Analytics] 的分类调用失败。

  [请联系客户关怀团队](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)，以获取帮助。

如果您按照“Analytics for Target”维度细分“未指定”行并且它不包含活动 ID，这意味着所有内容均已正确分类。如果其中列出了活动 ID，则它起到指示有分类问题的作用。

>[!NOTE]
>
>有时候数据在报表中正确显示，然后转换为“未指定”，因为添加的新活动没有完成分类。请记住，在首次保存后，分类通常需要 24 到 72 个小时来分类报表。
>
>列为“未指定”时，不会丢失任何数据。运行分类后，数据会正确分配到相应的活动或体验。

## A4T 活动报表中的一行具有许多“未指定”事件。 {#added_unspecified_events}

报表中可能会显示“[!UICONTROL Unspecified]”事件行，具体取决于您用于显示数据的指标。

通常，如果您在报表中选择了并非特定于[!DNL Target]的常见量度（例如，[!UICONTROL Page Views]、[!UICONTROL Visits]、[!UICONTROL Unique Visitors]等），则会显示此行。 在这种情况下，[!UICONTROL "Unspecified"]行包括未与[!DNL Target]活动关联的所有[!UICONTROL Page Views]、[!UICONTROL Visits]和[!UICONTROL Unique Visitors]。

该行不会具有任何与 [!DNL Target] 关联的信息（例如，无访客、访问次数或展示数）。有关更多信息，请参阅 *Analytics 技术说明*&#x200B;的[报表中的“未指定”、“无”、“其他”和“未知”](https://experienceleague.adobe.com/docs/analytics/technotes/unspecified.html?lang=zh-Hans)。

如果您在报表中选择特定于[!DNL Target]的指标，则不会显示该[!UICONTROL "Unspecified"]行。 避免报表中出现这一情况的唯一方法是在从该页面发送的每个请求上设置 [!DNL Target] 调用，这既不常见，也非必要。

## 预计收入提升指标显示的数据不正确。 {#section_35D766E5E4D347C39E15D08AA883FBB0}

Analytics 中不会提供提升度和置信度详细信息。但是，Target 报表中会提供这些信息。

## 活动未显示在 Analytics 报表中。 {#section_F7001EB4670F4B3497CC7DA60BBDA6D5}

A4T 活动要求指定 Analytics 跟踪服务器。请参阅[使用Analytics跟踪服务器](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)，以确保您的Analytics跟踪服务器设置正确。

>[!NOTE]
>
>如果您使用 at.js 版本 0.9.1（或更高版本），则在活动创建期间无需指定跟踪服务器。at.js 库自动将跟踪服务器值发送到 [!DNL Target]。在活动创建期间，您可以将[!UICONTROL Goals & Settings]页面上的[!UICONTROL Tracking Server]字段留空。

## 我的 Analytics 区段未显示在 Target 中。 {#section_DEE87F1557834F448E99381D3D02EEEF}

开始创建 A4T 活动之前，请确保您拥有适当的权限。

* 属于 Adobe Analytics 中的 Web 服务访问组才能够使用 Analytics 作为 Target 的报表源
* 成为一个或多个可以访问 Analytics 和 Target 的 Experience Cloud 组的成员。
* 确认左侧导航的“营销应用程序”部分中显示了 Analytics 和 Target。

## 跳出率、跳出次数和退出次数量度在报表中显示为正值。 {#section_B5C3D56EF0344407AE67ABEB93037F5A}

这些指标在报表中显示为正值是已知问题。

虽然这些量度为负值，但是 Target 报表中显示的提升度似乎表示这些量度为正值。例如，虽然您希望降低跳出率，但是较高的跳出率会显示为具有最高提升度的入选者。根据报表做出决策时，请留心这些量度及类似量度，并确定您是希望降低还是提高这些量度的数值。

## 我需要的报表套件未显示。 {#section_BD8F956E41D6475B98B7BF0C74CC387C}

[!DNL Target Standard/Premium] 中显示的报表套件列表是已经为 [!DNL Analytics] 配置作为 [!DNL Target] 报表源 (A4T) 的报表套件列表。您可能不会看到自己具有的所有报表套件。

如果您使用多个报表源，则报表套件也必须位于在 [!DNL Target] 中设置的默认报表源中。如果报表套件不在默认报表源中，报表套件不会显示。

如果您仍未看到所查找的报表套件，请联系[客户关怀](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)以启用它。

## 报表中显示的数据比预期的要少。 {#section_75002584FA63456D8D9086172925DD8D}

请检查您的实施，特别是要检查访客符合体验条件的页面，并确保 [!DNL Target] 和 [!DNL Analytics] 调用中的补充数据 ID 相匹配。

* **at.js 1.x**：在 [!DNL Target] 调用中，补充数据 ID 包含在 `mboxMCSDID` 参数中。在 [!DNL Analytics] 调用中，补充数据 ID 包含在 `sdid` 参数中。
* **at.js 2.x**：在 [!DNL Target] 调用中，补充数据 ID 在 HTTP 标头中作为 `experienceCloud.analytics.supplementalDataId` 的值返回。在 [!DNL Analytics] 调用中，补充数据 ID 包含在 `sdid` 参数中。

检查补充数据 ID 的最简单方法是使用 Adobe Experience Platform Debugger。

如果您未安装调试程序，请参阅 [Adobe Experience Platform Debugger 简介](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html?lang=zh-Hans)。

![调试程序](/help/main/c-integrating-target-with-mac/a4t/assets/debugger.png)

如果 [!DNL Target] 调用中没有补充数据 ID，请确认 [!DNL VisitorAPI.js] 文件已在 [!DNL at.js] 之前加载。如果 [!DNL Analytics] 调用中没有补充数据 ID，请确认 [!DNL Target] 调用是否在 [!DNL Analytics] 调用之前触发。

有关更多信息，请参阅 [Analytics for Target 实施](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#concept_CE78750AC2A4487D8ACD9369B3EAC85A)或联系[客户关怀团队](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。
