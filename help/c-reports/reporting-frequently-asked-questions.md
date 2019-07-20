---
description: 有关 Target 报表的常见问题解答列表。
keywords: 故障诊断;量度不一致;常见问题解答;报表
seo-description: 有关 Target 报表的常见问题解答列表。
seo-title: 报表常见问题解答
solution: Target
title: 报表常见问题解答
topic: Standard
uuid: 0be40d3f-3274-493d-899b-cb7bb3612baf
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 报表常见问题解答{#reporting-faq}

有关 Target 报表的常见问题解答列表。

## Target 中的访问次数为何低于其他 Experience Cloud 解决方案中的访问次数？{#section_7E626FDB417E41B8B58BBF30FB207409}

[!DNL Target] 所报告的量度数量（例如访问次数）总是低于其他 [!DNL Experience Cloud] 解决方案所报告的数量，原因如下：

* [!DNL Target] 只计入符合活动条件的访客的访问次数。其他解决方案则会计入所有显示页面的访客的访问次数，而不管是哪个活动将访客引至页面。
* 可能会出现不同活动争夺同一个位置的情况（不同的活动不能同时存在于一个位置）。鉴于此原因，访客会在一个网页上看到不同的内容，这便会影响 [!DNL Target] 所报告的量度数量。

## 我的活动报表中为何没有可用的数据？{#section_E4722F6445884130951DF79981C8289B}

如果某个活动的内容已成功交付给用户，但是该活动的报表中没有任何数据，请确保您在报表设置中选择了正确的环境（主机组）。

如果您选择了开发环境，您可能会看到以下错误消息：“选定的报表设置没有可用的数据。”

要更改活动报表的环境，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL 活动]**，从列表中单击所需活动，然后单击&#x200B;**报表]选项卡。[!UICONTROL **
1. 单击齿轮图标以配置报表设置。

   ![](assets/ab_settings_dialog.png)

   >[!NOTE]
   >
   >没有为自动个性化报表提供齿轮图标。

1. 从&#x200B;**[!UICONTROL 环境]**&#x200B;下拉列表中，选择&#x200B;**[!UICONTROL 生产]**。

   如果您选择了开发环境，则可能会没有可用的报表数据。

1. 单击&#x200B;**[!UICONTROL 保存设置]**。

有关环境的更多信息，请参阅[主机](../administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E)。
