---
description: mbox3rdPartyId是您公司的访客ID，如您公司忠诚度计划的会员ID。
keywords: mbox;mbox3rdPartyId；配置文件同步；配置文件同步；PCID
seo-description: '有关实时配置文件的信息 '
seo-title: 在Adobe Target中实时同步mbox3rdPartyId的配置文件
solution: Target
title: 为mbox3rdPartyId实时同步配置文件
topic: Standard
uuid: a88353d1-36e8-48b2-9b5e-71ed437c5b99
translation-type: tm+mt
source-git-commit: f54dba622e449fb8dac44cb37ff711419f8eda4b

---


# Real-time profile syncing for mbox3rdPartyId{#real-time-profile-syncing-for-mbox-rdpartyid}

mbox3rdPartyId是您公司的访客ID，如您公司忠诚度计划的会员ID。

访客登录到某个公司的网站后，该公司通常会创建一个 ID，并将其绑定到访客的帐户、会员卡、会员编号，以及该公司的其他适用标识符。

When a visitor accesses a page on which [!DNL Target] is enabled, that visitor is assigned a [!DNL Target] PCID. If the visitor then logs in, and the implementation passes the mbox3rdPartyId to [!DNL Target], [!DNL Target] connects that visitor's mbox3rdPartyId with the [!DNL Target] PCID.

每三到五分钟，更新内容就会与数据库同步一次。访客注销时，合并数据将替换与mbox3rdPartyId关联的先前数据，从而创建该访客操作的更完整记录。 如果两个ID中都存在相同的属性，例如，PCID有category=hats，而mbox3rdPartyId有category=skis，或者如果访客在登录前看到体验A，但体验B存储在mbox3rdPartyId中——存储在mbox3rdPartyId中的属性覆盖PCID中的属性。 如果访客在登录之前处于一个活动或体验中，但mbox3rdPartyId中存储了其他活动和体验，则登录后该访客会被放置到mbox3rdPartyId活动和体验中。

| PCID（未登录） | mbox3rdPartyId（已登录） | 合并并保存到mbox3rdPartyId |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| 活动 1，体验 A | 活动 1，体验 B | 活动 1，体验 B |
| 活动 1 |  | 活动 1 |

访客注销时，将会保留合并后的配置文件。

>[!NOTE]
>
>[!DNL Adobe Analytics] 在 [!DNL Adobe Experience Cloud][!DNL Target] ID(MID)发生更改（例如，访客更改设备）时，将不跟踪目标，即使配置文件可能基于mbox3rdPartyId进行合并，但仍包含活动信息。 对于使用相同 MID 进行标识的访客（使用相同设备访问该页面的访客），[!DNL Analytics for Target] (A4T) 应按预期工作。

## 注意事项 {#considerations}

如果您的页面包含多个mbox并且只有一些使用3rdPartyID，则Target对于每个访客请求没有单独的访客资料／上下文。 第3rdPartyID上下文优先于PCID上下文。 只要一个mbox通过3rdPartyId，它的上下文就足以优先于PCID。

例如，假设访客在登录前访问页面并查看体验。 全局mbox不使用3rdPartyID。 登录后，访客将看到三个子mbox的体验之一，其中一些使用3rdPartyID。 访客访问网站上的各个页面，然后使用“返回”按钮返回登录前访问的主页，并查看不同的体验。 在此方案中，全局mbox未通过3rdPartyID，但一个或多个子mbox已通过。 3rdPartyID优先于PCID。
