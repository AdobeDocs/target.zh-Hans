---
keywords: Analytics 跟踪服务器;A4T;Analytics 区段;报表包;数据不正确;孤立;SDID;VisitorAPI.js;mboxMCSDID;虚拟;未指定
description: 本主题介绍了在使用 Analytics 作为 Target 报表源 (A4T) 时遇到的一些常见问题。
title: Analytics 与 Target 集成 (A4T) 故障诊断
subtopic: 多变量测试
topic: Standard
uuid: a5aa3be5-68a2-4f12-8226-f32a76136bbd
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Analytics 与 Target 集成 (A4T) 故障诊断{#troubleshoot-the-analytics-and-target-integration-a-t}

本主题介绍了在使用 Analytics 作为 Target 报表源 (A4T) 时遇到的一些常见问题。

## 活动在 Analytics 中未显示数据，反而列为“未指定”。{#unspecified}

发生这种情况的原因有多种，包括：

* [!DNL Target] 中的分类未完全处理。

   在第一次保存之后，分类通常需要 24 到 72 小时才能对报表进行分类。

* 报表包中未包含任何数据，但 [!DNL Target] 尝试了对点击进行分类。在发生首次点击之前，[!DNL Target] 将一直无法对数据进行分类。

   请确保报表包中至少有一次点击。

* 从 [!DNL Target] 向 [!DNL Analytics] 的分类调用失败。

   [请联系客户关怀团队](../../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)，以获取帮助。

>[!NOTE]
>
>有时，数据原先可在报表中正常显示，但随后又重新列为“未指定”，这是因为添加了未完成分类的新活动。请记住，在第一次保存之后，通常需要 24 到 72 小时才能对报表进行分类。
>
>列为“未指定”时，不会丢失任何数据。运行分类后，数据会正确分配到相应的活动或体验。

## 启动 A4T 后，我的 Analytics 数据显示夸大的访问或访客计数。 {#section_4BE374E573D44FB7918611699B74F58E}

有关更多信息，请参阅[在 A4T 中最大限度地减少夸大的访问和访客计数](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

## 预计收入提升量度显示的数据不正确。{#section_35D766E5E4D347C39E15D08AA883FBB0}

Analytics 中不会提供提升度和置信度详细信息。但是，Target 报表中会提供这些信息。

## 活动未显示在 Analytics 报表中。 {#section_F7001EB4670F4B3497CC7DA60BBDA6D5}

A4T 活动要求指定 Analytics 跟踪服务器。请参阅[使用 Analytics 跟踪服务器](../../../c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)，以确保您的 Analytics 跟踪服务器设置正确。

>[!NOTE]
>
>如果您使用 Adobe Analytics 作为活动的报表源，并且使用的是 mbox.js 版本 61（或更高版本）或者 at.js 版本 0.9.1（或更高版本），则无需在活动创建期间指定跟踪服务器。mbox.js 或 at.js 库会自动将跟踪服务器值发送到 [!DNL Target]。在活动创建期间，您可以将“[!UICONTROL 目标和设置]”页面上的“[!UICONTROL 跟踪服务器]”字段留空。

## 我的 Analytics 区段未显示在 Target 中。 {#section_DEE87F1557834F448E99381D3D02EEEF}

开始创建 A4T 活动之前，请确保您拥有适当的权限。

* 您必须属于 Adobe Analytics 中的“Web 服务访问”组，才能将 Analytics 用作 Target 报表源。
* 您必须是一个或多个拥有 Analytics 和 Target 访问权限的 Experience Cloud 组的成员。
* 确认左侧导航的“营销应用程序”部分中显示了 Analytics 和 Target。

## 跳出率、跳出次数和退出次数量度在报表中显示为正值。 {#section_B5C3D56EF0344407AE67ABEB93037F5A}

这是一个已知问题。

虽然这些量度为负值，但是 Target 报表中显示的提升度似乎表示这些量度为正值。例如，虽然您希望降低跳出率，但是较高的跳出率会显示为具有最高提升度的入选者。根据报表做出决策时，请留心这些量度及类似量度，并确定您是希望降低还是提高这些量度的数值。

## 未显示我需要的报表包。 {#section_BD8F956E41D6475B98B7BF0C74CC387C}

Target Standard/Premium 中显示的报表包列表列出的是已将 Analytics 配置为 Target 报表源的报表包。因此，这意味着您可能看不到自己拥有的所有报表包。如果您未看到要查找的报表包，您应该联系客户关怀团队，以将其启用。

## 报表中显示的数据比预期的要少。 {#section_75002584FA63456D8D9086172925DD8D}

请检查您的实施，特别是要检查访客符合体验条件的页面，并确保 [!DNL Target] 和 [!DNL Analytics] 调用中的补充数据 ID 相匹配。在 [!DNL Target] 调用中，补充数据 ID 包含在 `mboxMCSDID` 参数中。在 [!DNL Analytics] 调用中，补充数据 ID 包含在 `sdid` 参数中。

如果 [!DNL Target] 调用中没有补充数据 ID，请确认 [!DNL VisitorAPI.js] 文件是否在 [!DNL at.js] 或 [!DNL mbox.js] 之前加载。如果 [!DNL Analytics] 调用中没有补充数据 ID，请确认 [!DNL Target] 调用是否在 [!DNL Analytics] 调用之前触发。

有关更多信息，请参阅 [Analytics for Target 实施](../../../c-integrating-target-with-mac/a4t/a4timplementation.md#concept_CE78750AC2A4487D8ACD9369B3EAC85A)或联系[客户关怀团队](../../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。