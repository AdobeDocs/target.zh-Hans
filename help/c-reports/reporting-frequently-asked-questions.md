---
keywords: troubleshooting;metric discrepancies;FAQ;reports;new visitor;new visitors;returning visitor;returning visitors;return visit;new visit
description: 有关 Adobe Target 报表的常见问题解答列表。
title: Adobe Target 报表常见问题解答
topic: Standard
uuid: 0be40d3f-3274-493d-899b-cb7bb3612baf
translation-type: tm+mt
source-git-commit: 4fcbd120c6c6448b4ff1c8fc43ab296f791f9d83
workflow-type: tm+mt
source-wordcount: '1012'
ht-degree: 33%

---


# 报表常见问题解答{#reporting-faq}

有关 [!DNL Target] 报表的常见问题解答列表。

## 如何计算新访客和退回访客指标？

以下信息说明如何计算新访客和退回访客，并举例说明为何这两个细分的总和并不总是等于访客总数。

**新访客**: 倘符合以下条件之一，则访客会计入新访客分部：

* 这是访客首次访问该网站。
* 这是访客清除cookies后首次访问网站。
* 这是访客自访客用户档案生命周期过期后首次访 [问该网站](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md) 。

**退回访客**: 如果用户之前访问过网站（至少离开30分钟），并使用相同的cookie再次返回到网站，则该访客将包含在“返回访客”区段中。 只要访客在其配置文件生命周期内返回网站，他们便是回访访客。

如果这两个区段应用于活动，则“新访客”区段和“退回访客”区段并不总是占总访客数。

请考虑以下示例，以新访客和退回访客的上述条件为例：

* 访客首次访问网站并计为新访客。
* 在满足退回访客的条件后，访客将返回到该站点，并计为退回访客。

此访客在活动的整体访客计数中计为单个访客，即使在“新访客”和“退回访客”细分中均计算。

新访客和退回访客的计数不一致还取决于您如何配置活动的成 [功指标](/help/c-activities/r-success-metrics/success-metrics.md)。

例如：

许多新访客访问您的站点并有资格获得活动。 该等新访客计入新访客分部。 所有这些访客还记录了对该活动的访问。

一些访客点击了转换量度，该量度配置为“增量计数、释放用户并允许重新入门”。 假设其中一些用户多次点击转换量度，转换量度不会增加。 但是，如果设置该设置，某些用户可能会点击转换量度，然后导航回主页，再次确认活动以记录新访问。

## 为何我的[!UICONTROL 体验定位] (XT) 报表包含控制体验的量度？

XT 活动应始终包含一个控制体验。如果您使用 XT 活动的方式与 [!UICONTROL A/B 测试]活动类似（这是一种相当常见的情况），则控制体验数据将会很有用。如果发现控制体验数据在报表中没有用处，则可以将其忽略。

## [!DNL Target] 中的访问次数为何低于其他 [!DNL Adobe Experience Cloud] 解决方案中的访问次数？{#section_7E626FDB417E41B8B58BBF30FB207409}

[!DNL Target] 所报告的量度数量（例如访问次数）总是低于其他 [!DNL Experience Cloud] 解决方案所报告的数量，原因如下：

* [!DNL Target] 只计入符合活动条件的访客的访问次数。其他解决方案则会计入所有显示页面的访客的访问次数，而不管是哪个活动将访客引至页面。
* 可能会出现不同活动争夺同一个位置的情况（不同的活动不能同时存在于一个位置）。鉴于此原因，访客会在一个网页上看到不同的内容，这便会影响 [!DNL Target] 所报告的量度数量。

## 我的活动报表中为何没有可用的数据？{#section_E4722F6445884130951DF79981C8289B}

如果某个活动的内容已成功交付给用户，但是该活动的报表中没有任何数据，请确保您在报表设置中选择了正确的环境（[主机组](/help/administrating-target/hosts.md)）。

如果您选择了开发环境，您可能会看到以下错误消息：“选定的报表设置没有可用的数据。”

要更改活动报表的环境，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL 活动]**，从列表中单击所需活动，然后单击&#x200B;**[!UICONTROL 报表]**&#x200B;选项卡。
1. 单击齿轮图标以配置报表设置。

   ![A/B 设置对话框](/help/c-reports/c-report-settings/assets/ab_settings_dialog.png)

   >[!NOTE]
   >
   >没有为[!UICONTROL 自动个性化] (AP) 报表提供齿轮图标。

1. 从&#x200B;**[!UICONTROL 环境]**&#x200B;下拉列表中，选择&#x200B;**[!UICONTROL 生产]**。

   如果您选择了开发环境，则可能会没有可用的报表数据。

1. 单击&#x200B;**[!UICONTROL 保存]**。

有关环境的更多信息，请参阅[主机](../administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E)。

## 为什么我的A/B或MVT活动中体验之间的流量分配不均？ {#uneven}

例如，我将流量分割设置为50/50或25/25/25/25，但我发现报告中体验之间的分布差异很大。 在访客中报告数不均的原因有很多可解释的 [!DNL Target] 原因：

* 首次 [!DNL Target] 启动活动时，由于边缘节点架构用于优化体验投放，流量分布可 [!DNL Target] 能不均匀。 最佳实践是让活动有时间收集额外数据，然后分发将正常化。 有关架构和边 [!DNL Adobe Target] 缘节点的更多信息，请 [参阅Adobe目标的工作方式](/help/c-intro/how-target-works.md)。
* 如果您处于 [!DNL Target] 或 [!DNL Analytics] 使用访问量度，请记住，这是一个基于 **[!UICONTROL 访客]**[!DNL Target] 的系统，A/B或MVT测试的流量分配在访客级别。 因此，如果您使用“访问”量度检查活动 **[!UICONTROL 结果]** ，则流量分布可能不均匀，因为某些访客可能有多次访问。 访客是评估活动性能时的标准标准化度量。
* A/B和MVT测试的最佳实践是保持流量分配均匀。 在测试过程中更改体验之间的流量分配（例如从90/10更改为50/50）可能会导致不同体验之间的访客不均。 较低的流量体验可能永远不会“赶上”。
* 如果您遵循上述最佳实践，并且随着时间的推移流量分割不正常化，则应检查以下内容：

   * 您是否在使用最新的at.js库？ 有关当前版本和相关发行说明的详细信息，请 [参阅at.js版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)。

   * 是重定向测试吗？ 页面上触发标记的时间不正确可能会导致流量分割不均匀，尤其是当 [!DNL Analytics] 用作活动的数据源 [!DNL Target] 时。 有关使用Analytics for活动(A4T)纠正重定向目标流量分布不均的详细信息，请参 [阅重定向优惠- A4T常见问题解答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md)。
