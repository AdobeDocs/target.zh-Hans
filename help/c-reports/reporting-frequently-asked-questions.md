---
description: 有关 Target 报表的常见问题解答列表。
keywords: 故障诊断;量度不一致;常见问题解答;报表
seo-description: List of frequently asked questions about reporting in Adobe Target.
seo-title: Adobe Target报告常见问题解答
solution: Target
title: 报表常见问题解答
topic: Standard
uuid: 0be40d3f-3274-493d-899b-cb7bb3612baf
translation-type: tm+mt
source-git-commit: a6f2eceaddf67653b36a1687ba071f7226169516

---


# 报表常见问题解答{#reporting-faq}

有关 [!DNL Target] 报表的常见问题解答列表。

## 我的体验定 [!UICONTROL 位] (XT)报告为何包含控制体验的指标？

XT活动应始终具有控制体验。 如果您使用的XT活动与  A/B测试活动类似，这是相当常见的情况，则控制体验数据很有用。 如果您发现控制体验数据在报告中不有用，则可以忽略该数据。

## Why are the number of visits lower in [!DNL Target] than in other [!DNL Adobe Experience Cloud] solutions? {#section_7E626FDB417E41B8B58BBF30FB207409}

[!DNL Target] 所报告的量度数量（例如访问次数）总是低于其他 [!DNL Experience Cloud] 解决方案所报告的数量，原因如下：

* [!DNL Target] 只计入符合活动条件的访客的访问次数。其他解决方案则会计入所有显示页面的访客的访问次数，而不管是哪个活动将访客引至页面。
* 在某些情况下，不同的活动会争夺同一位置（相互排斥）。 鉴于此原因，访客会在一个网页上看到不同的内容，这便会影响 [!DNL Target] 所报告的量度数量。

## 我的活动报表中为何没有可用的数据？{#section_E4722F6445884130951DF79981C8289B}

If an activity's content was successfully delivered to users but its report contains no data, ensure that you have the correct environment ([host group](/help/administrating-target/hosts.md)) selected in the report's settings.

如果您选择了开发环境，您可能会看到以下错误消息：“选定的报表设置没有可用的数据。”

要更改活动报表的环境，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL 活动]**，从列表中单击所需活动，然后单击&#x200B;**报表]选项卡。[!UICONTROL **
1. 单击齿轮图标以配置报表设置。

   ![“A/B设置”对话框](/help/c-reports/c-report-settings/assets/ab_settings_dialog.png)

   >[!NOTE]
   >
   >The gear icon is not available for [!UICONTROL Automated Personalization] (AP) reports.

1. 从&#x200B;**[!UICONTROL 环境]**&#x200B;下拉列表中，选择&#x200B;**[!UICONTROL 生产]**。

   如果您选择了开发环境，则可能会没有可用的报表数据。

1. 单击&#x200B;**[!UICONTROL 保存]**。

有关环境的更多信息，请参阅[主机](../administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E)。
