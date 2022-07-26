---
keywords: 疑难解答；量度差异；FAQ；报表；新访客；新访客；回访访客；回访访客；回访访客；回访；新访问
description: 浏览有关Adobe的常见问题解答和答案列表 [!DNL Target] 报表。
title: 在哪里可以找到有关 [!DNL Target] 报告？
feature: Reports
exl-id: 1a345a67-5050-4bd3-858d-99731d2c1dd3
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '1227'
ht-degree: 32%

---

# 报表常见问题解答

有关 [!DNL Adobe Target] 报表的常见问题解答列表。

## 如何计算“新访客”和“回访访客”指标？ {#methodology}

只要新访客在网站上处于活动状态，新访客的首次访问就会持续。
如果用户处于非活动状态30分钟或更长时间，则会重置会话。 重置会话意味着该访客在下次访问时成为回访访客，或在处于不活动状态30分钟后再次变为活动访客。
如果访客在整天内每29分钟在网站周围移动一次，则该访客将被计为当天的新访客。 会话从未重置，因为访客从未超过30分钟的阈值。

以下信息更详细地说明了如何计算新访客和旧访客。 此外，还包含一些示例来解释为什么这两个区段的总和并不总是等于访客总数。

### 新访客

如果符合以下条件之一，则将访客包括在“新访客”部分中：

* 这是该访客第一次访问该网站。
* 这是自清除 Cookie 以来该访客第一次访问该网站。
* 这是自[访客个人资料生命周期](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md)到期以来该访客第一次访问该网站。

### 旧访客

如果用户以前访问过该网站，停留了至少 30 分钟，然后带着相同的 Cookie 再次返回该网站，则该访问者被包括在“回访访客”区段中。只要访客在其个人资料生命周期内返回，此访客即为回访访客。

假定配置文件生命周期设置为14天（默认）。 如果满足以下条件，则“回访访客”区段中会包含访客：

* 访客首次访问网站并记录为新访客。
* 访客离开网站，但六天后返回。

由于配置文件生命周期设置为14天，因此该访客包含在“回访访客”区段中。 如果访客在该六天内删除了Cookie，则该访客将包含在“新访客”区段中。

### 解释量度计数之间差异的示例

**示例1**:如果将这两个区段应用于活动，则“新访客”区段和“回访访客”区段并不总是总计访客数。

请考虑以下示例，以上是“新访客”和“回访访客”的条件：

* 访客首次访问网站并计为新访客。
* 在满足回访访客的条件后，该访客返回网站，并计为回访访客。

此访客在活动的整体访客计数中将计为单个访客，即使同时计入新访客和回访访客区段也是如此。

**示例2**:“新访客”和“回访访客”计数之间的差异还取决于您如何配置活动 [成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md).

例如：

有数位新访客访问了您的网站，并符合活动条件。 这些新访客将计入新访客区段。 所有这些访客还记录了对该活动的访问。

某些访客点击了转化量度，该量度配置为“递增计数并保持用户处于活动中”。 假设其中某些用户多次点击转化量度，则转化量度不会增加。 但是，鉴于此设置，某些用户可能会点击转化量度，然后导航回主页，从而再次符合活动条件以记录新访问。

## 为何我的[!UICONTROL 体验定位] (XT) 报表包含控制体验的量度？

XT 活动应始终包含一个控制体验。如果您使用 XT 活动的方式与 [!UICONTROL A/B 测试]活动类似（这是一种相当常见的情况），则控制体验数据将会很有用。如果发现控制体验数据在报表中没有用处，则可以将其忽略。

## [!DNL Target] 中的访问次数为何低于其他 [!DNL Adobe Experience Cloud] 解决方案中的访问次数？ {#section_7E626FDB417E41B8B58BBF30FB207409}

量度数量，例如由 [!DNL Target] 总是低于其他 [!DNL Experience Cloud] 解决方案有以下几个原因：

* [!DNL Target] 只计入符合活动条件的访客的访问次数。其他解决方案则会计入所有显示页面的访客的访问次数，而不管是哪个活动将访客引至页面。
* 可能会出现不同活动争夺同一个位置的情况（不同的活动不能同时存在于一个位置）。鉴于此原因，访客会在一个网页上看到不同的内容，这便会影响 [!DNL Target] 所报告的量度数量。

## 我的活动报表中为何没有可用的数据？ {#section_E4722F6445884130951DF79981C8289B}

如果某个活动的内容已成功交付给用户，但是该活动的报表中没有任何数据，请确保您在报表设置中选择了正确的环境（[主机组](/help/main/administrating-target/hosts.md)）。

如果您选择了开发环境，您可能会看到以下错误消息：“选定的报表设置没有可用的数据。”

要更改活动报表的环境，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL 活动]**，从列表中单击所需活动，然后单击&#x200B;**[!UICONTROL 报表]**&#x200B;选项卡。
1. 单击齿轮图标以配置报表设置。

   ![A/B 设置对话框](/help/main/c-reports/c-report-settings/assets/ab_settings_dialog.png)

   >[!NOTE]
   >
   >没有为[!UICONTROL 自动个性化] (AP) 报表提供齿轮图标。

1. 从&#x200B;**[!UICONTROL 环境]**&#x200B;下拉列表中，选择&#x200B;**[!UICONTROL 生产]**。

   如果您选择了开发环境，则可能会没有可用的报表数据。

1. 单击&#x200B;**[!UICONTROL 保存]**。

有关环境的更多信息，请参阅[主机](/help/main/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E)。

## 为什么我的A/B或MVT活动中的体验之间的流量分配不均？ {#uneven}

例如，我将流量拆分设置为50/50或25/25/25/25，但我在报表中看到的体验之间的分配存在很大差异。 中访客计数不均的原因有几个可解释的原因 [!DNL Target] 报告：

* 当 [!DNL Target] 活动首次启动时，流量分配可能会不均衡，因为边缘节点架构 [!DNL Target] 用于优化体验交付。 最佳做法是为活动留出一些时间来收集更多数据，并且分发将恢复正常。 有关 [!DNL Adobe Target] 架构和边缘节点，请参阅 [Adobe Target的工作原理](/help/main/c-intro/how-target-works.md).
* 如果您在 [!DNL Target] 或 [!DNL Analytics] 而且你使用 **[!UICONTROL 访问次数]** 量度，记住 [!DNL Target] 是基于访客的系统，A/B或MVT测试的流量分配是在访客级别分配的。 因此，如果您使用 **[!UICONTROL 访问次数]** 量度时，流量分布可能会显示不均匀，因为某些访客可能多次访问。 访客是评估活动性能时的标准标准化量度。
* A/B和MVT测试的最佳实践是保持流量分配均匀。 在测试期间更改体验之间的流量分配(例如从90/10到50/50)可能会导致不同体验之间的访客数不均衡。 流量体验越低，可能永远无法“赶上”。
* 如果您遵循上述最佳实践，并且流量拆分在一段时间内没有正常化，则应检查以下内容：

   * 您是否在使用最新的at.js库？ 有关当前版本和相关发行说明的更多信息，请参阅 [at.js版本详细信息](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank}。

   * 它是重定向测试吗？ 在页面上触发的标记时间不正确可能会导致不均衡的流量分配，尤其是在使用 [!DNL Analytics] 作为 [!DNL Target] 活动。 有关使用Analytics for Target(A4T)解决重定向活动中流量分配不均的详细信息，请参阅 [重定向选件 — A4T常见问题解答](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md).
