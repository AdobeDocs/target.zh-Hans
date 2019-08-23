---
description: mbox3rdPartyId是贵公司的访客ID，如贵公司忠诚度计划的会员ID。
keywords: mbox；mbox3rdPartyId；配置文件同步；个人资料同步；PCID
seo-description: '实时配置文件的相关信息 '
seo-title: Adobe Target中的mbox3 rdPartyId实时配置文件同步
solution: Target
title: mbox3 rdPartyId的实时配置文件同步
topic: Standard
uuid: a88353d1-36e8-48b2-9b5e-71ed437c5b99
translation-type: tm+mt
source-git-commit: f54dba622e449fb8dac44cb37ff711419f8eda4b

---


# Real-time profile syncing for mbox3rdPartyId{#real-time-profile-syncing-for-mbox-rdpartyid}

mbox3rdPartyId是贵公司的访客ID，如贵公司忠诚度计划的会员ID。

访客登录到某个公司的网站后，该公司通常会创建一个 ID，并将其绑定到访客的帐户、会员卡、会员编号，以及该公司的其他适用标识符。

When a visitor accesses a page on which [!DNL Target] is enabled, that visitor is assigned a [!DNL Target] PCID. If the visitor then logs in, and the implementation passes the mbox3rdPartyId to [!DNL Target], [!DNL Target] connects that visitor's mbox3rdPartyId with the [!DNL Target] PCID.

每三到五分钟，更新内容就会与数据库同步一次。访客注销时，合并的数据替换与mbox3rdPartyId关联的先前数据，从而创建一个更完整的访客操作记录。如果两个ID中存在相同的属性—例如，PCID有catories= hats，mbox3rdPartyId有category= ski，或者如果访客在登录之前看到体验A，则体验B存储在mbox3rdPartyId中。—mbox3rdPartyId中存储的属性会覆盖PCID中的属性。如果访客在登录前处于某个活动或体验中，但在mbox3rdPartyId中登录后，该访客将存储在mbox3rdPartyId中，该ID被放置到mbox3rdPartyID活动和体验中。

| PCID（未登录） | mbox3rdPartyId(loged in) | 合并并保存到mbox3rdPartyId |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| 活动 1，体验 A | 活动 1，体验 B | 活动 1，体验 B |
| 活动 1 |  | 活动 1 |

访客注销时，将会保留合并后的配置文件。

>[!NOTE]
>
>[!DNL Adobe Analytics] 如果 [!DNL Adobe Experience Cloud] ID(MID)更改(例如，访客可以根据mbox3rdPartyId合并 [!DNL Target] 配置文件)，但仍有活动信息，则不会跟踪目标。对于使用相同 MID 进行标识的访客（使用相同设备访问该页面的访客），[!DNL Analytics for Target] (A4T) 应按预期工作。

## 注意事项 {#considerations}

如果您的页面包含多个mbox并且只使用3rdPartyId，则Target没有每个访客请求的单独访客配置文件/上下文。3rdPartyId上下文优先于PCID上下文。一个mbox足以传递3rdPartyId以使其上下文优先于PCID。

例如，假定访客在登录之前访问页面并查看体验。全局mbox不使用3rdPartyId。登录后，访客将看到三种使用子mbox的体验，其中某些是使用3rdPartyId的。访客访问网站上的各种页面，然后使用“返回”按钮返回到访问前访问的主页，并查看不同的体验。在此方案中，全局mbox未传递3rdPartyId，但一个或多个子mbox。3rdPartyId优先于PCID。
