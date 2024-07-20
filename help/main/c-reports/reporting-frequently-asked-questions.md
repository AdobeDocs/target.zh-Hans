---
keywords: 故障诊断；量度不一致；FAQ；报表；新访客；新访客；回访访客；回访访客；新访问
description: 浏览有关Adobe [!DNL Target] 报表的常见问题和答案的列表。
title: 可在何处找到有关 [!DNL Target] 报告的问题的答案？
feature: Reports
exl-id: 1a345a67-5050-4bd3-858d-99731d2c1dd3
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '1367'
ht-degree: 20%

---

# 报表常见问题解答

有关 [!DNL Adobe Target] 报表的常见问题解答列表。

## 如何计算“新访客”和“回访访客”指标？ {#methodology}

只要新访客在网站上处于活动状态，该访客的首次访问就会持续。
如果用户处于非活动状态30分钟或更长时间，则会重置会话。 重置会话意味着该访客在下次访问时成为回访访客，或者在处于非活动状态30分钟后再次变为活动状态。
如果访客在网站中全天每29分钟移动一次，则该访客将被计为当天的新访客。 会话从未重置，因为访客从未超过30分钟的阈值。

以下信息更详细地说明了如何计算新访客和回访访客。 另外，还包含一些示例，以解释为何这两个区段的总和并不总是与访客总数相加。

### 新访客

如果符合以下条件之一，则将访客包括在“新访客”部分中：

* 这是该访客第一次访问该网站。
* 这是自清除 Cookie 以来该访客第一次访问该网站。
* 这是自[访客配置文件生命周期](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md)过期以来该访客第一次访问该网站。

### 旧访客

如果用户以前访问过该网站，停留了至少 30 分钟，然后带着相同的 Cookie 再次返回该网站，则该访问者被包括在“回访访客”区段中。只要访客在其个人资料生命周期内返回，此访客即为回访访客。

假定您的配置文件生命周期设置为14天（默认）。 如果满足以下条件，则访客将包含在“回访访客”部分中：

* 访客首次访问网站，并被记录为“新访客”。
* 访客离开网站，但六天后返回。

由于配置文件生命周期设置为14天，因此该访客将包含在“回访访客”区段中。 如果该访客在六天内删除了Cookie，则该访客将包含在“新访客”区段中。

### 说明量度计数之间差异的示例

**示例1**：如果将这两个区段应用于活动，则“新访客”区段和“回访访客”区段并非总和访客总数。

请考虑以下示例，并采用上面提到的“新访客”和“回访访客”条件：

* 访客首次访问网站，将被计为新访客。
* 访客在满足回访访客的条件并计为回访访客后返回网站。

即使此访客同时计入“新访客”和“回访访客”区段，该访客仍会在活动的访客总数中计为单个访客。

**示例2**：新访客和回访访客计数之间的差异还取决于您配置活动的[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md)的方式。

例如：

多个新访客访问您的网站并有资格参与活动。 这些新访客将计入新访客区段。 所有这些访客还记录了该活动的访问。

一些访客点击了转化量度，该量度已配置为“递增计数并保持用户处于活动中”。 假设这些用户中的某些用户多次点击转化量度，则转化量度不会增加。 但是，鉴于这种设置，某些用户可能会点击转化量度，然后导航回主页，再次参加活动以记录新的访问。

## 我的[!UICONTROL Experience Targeting] (XT)报表为何包含控制体验的量度？

XT 活动应始终包含一个控制体验。如果您使用XT活动的方式与[!UICONTROL A/B Test]活动类似（这是一种相当常见的情况），则控制体验数据将会很有用。 如果发现控制体验数据在报表中没有用处，则可以将其忽略。

## 为什么[!DNL Target]中的访问次数低于其他[!DNL Adobe Experience Cloud]解决方案中的访问次数？ {#section_7E626FDB417E41B8B58BBF30FB207409}

由于以下几种原因，[!DNL Target]报告的量度数量（例如访问次数）始终低于其他[!DNL Experience Cloud]解决方案中报告的数量：

* [!DNL Target] 只计入符合活动条件的访客的访问次数。其他解决方案则会计入所有显示页面的访客的访问次数，而不管是哪个活动将访客引至页面。
* 可能会出现不同活动争夺同一个位置的情况（不同的活动不能同时存在于一个位置）。鉴于此原因，访客会在一个网页上看到不同的内容，这便会影响 [!DNL Target] 所报告的量度数量。

## 我的活动报表中为何没有可用的数据？ {#section_E4722F6445884130951DF79981C8289B}

如果某个活动的内容成功交付给访客，但是该活动的报表中没有任何数据，您可能会看到以下错误消息：“没有可用于所选报表设置的数据。”

活动报表中缺少数据的原因有几个：

* 您在报表设置中选择的环境不正确
* 您没有任何分配给控制体验的流量

### 您在报表设置中选择的环境不正确：

如果某个活动的内容已成功交付给用户，但是该活动的报表中没有任何数据，请确保您在报表设置中选择了正确的环境（[主机组](/help/main/administrating-target/hosts.md)）。

要更改活动报表的环境，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL Activities]**，从列表中单击所需的活动，然后单击&#x200B;**[!UICONTROL Reports]**&#x200B;选项卡。
1. 单击齿轮图标以配置报表设置。

   ![A/B 设置对话框](/help/main/c-reports/c-report-settings/assets/ab_settings_dialog.png)

1. 从&#x200B;**[!UICONTROL Environment]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL Production]**。

   如果您选择了开发环境，则可能会没有可用的报表数据。

1. 单击 **[!UICONTROL Save]**。

有关环境的更多信息，请参阅[主机](/help/main/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E)。

### 您没有任何分配给控制体验的流量

如果某个活动的内容已成功交付给用户，但其报表中没有任何数据，请确保使用具有流量的体验作为控制体验。

1. 单击&#x200B;**[!UICONTROL Activities]**，从列表中单击所需的活动，然后单击&#x200B;**[!UICONTROL Reports]**&#x200B;选项卡。
1. 单击齿轮图标以配置报表设置。

1. 从&#x200B;**[!UICONTROL Control]**&#x200B;下拉列表中，选择接收流量的体验。

1. 单击 **[!UICONTROL Save]**。

>[!NOTE]
>
>有关如何更新[!UICONTROL Automated Personalization] (AP)活动并将控制体验更改为接收流量的体验的详细信息，请参阅[选择Automated Personalization或自动定位活动的控制](/help/main/c-activities/t-automated-personalization/experience-as-control.md)。


## 为什么我的A/B或MVT活动中在各个体验之间的流量分摊不均匀？ {#uneven}

例如，我将流量拆分设置为50/50或25/25/25/25/25，但我发现，在报表中的体验之间分布差异很大。 [!DNL Target]报表中的访客计数不均衡有几个可以解释的原因：

* 首次启动[!DNL Target]活动时，由于[!DNL Target]用于优化体验交付的边缘节点架构，流量分配可能不均匀。 最佳实践为活动留出一段时间以收集更多数据，并且分布会正常化。 有关[!DNL Adobe Target]架构和Edge节点的更多信息，请参阅[Adobe Target的工作方式](/help/main/c-intro/how-target-works.md)。
* 如果您在[!DNL Target]或[!DNL Analytics]中并且使用&#x200B;**[!UICONTROL Visits]**&#x200B;指标，请记住[!DNL Target]是基于访客的系统，A/B或MVT测试的流量分配是在访客级别分配的。 因此，如果您使用&#x200B;**[!UICONTROL Visits]**&#x200B;量度检查活动结果，则流量分配可能会显示不均匀，因为某些访客可能有多次访问。 访客是评估活动绩效时的标准标准化量度。
* A/B和MVT测试的最佳实践是保持流量拆分均匀。 在测试期间更改体验之间的流量分配（例如，从90/10更改为50/50）可能会导致体验之间的访客数不均衡。 较低的流量体验可能永远不会“赶上”。
* 如果您遵循上述最佳实践，并且流量分摊不会随时间而正常化，则您应该检查以下各项：

   * 您是否在使用最新的at.js库？ 有关当前版本和相关发行说明的详细信息，请参阅[at.js版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank}。

   * 是否为重定向测试？ 在页面上触发的标记定时不正确可能会导致不均衡的流量拆分，尤其是在使用[!DNL Analytics]作为[!DNL Target]活动的数据源时。 有关使用Analytics for Target (A4T)纠正重定向活动上流量分配不均衡的详细信息，请参阅[重定向选件 — A4T常见问题解答](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md)。
