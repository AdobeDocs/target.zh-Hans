---
keywords: mbox;mbox3rdPartyId;配置文件同步;PCID
description: '有关实时配置文件的信息 '
title: Adobe Target 中 mbox3rdPartyId 的实时配置文件同步
topic: Standard
uuid: a88353d1-36e8-48b2-9b5e-71ed437c5b99
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# mbox3rdPartyId 的实时配置文件同步{#real-time-profile-syncing-for-mbox-rdpartyid}

mbox3rdPartyId 是您公司的访客 ID，例如您公司的忠诚度计划的会员 ID。

访客登录到某个公司的网站后，该公司通常会创建一个 ID，并将其绑定到访客的帐户、会员卡、会员编号，以及该公司的其他适用标识符。

如果访客访问的页面启用了 [!DNL Target]，则会为该访客分配一个 [!DNL Target] PCID。如果该访客随后登录，并且相应实施将 mbox3rdPartyId 传递到 [!DNL Target]，则 [!DNL Target] 会将该访客的 mbox3rdPartyId 与 [!DNL Target] PCID 相关联。

每三到五分钟，更新内容就会与数据库同步一次。访客注销后，合并的数据会替换以前与 mbox3rdPartyId 关联的数据，以便创建该访客操作的更完整记录。如果两个 ID 中存在相同的属性（例如，PCID 具有 category=hats，而 mbox3rdPartyId 具有 category=skis；或者，如果访客在登录之前查看了体验 A，而 mbox3rdPartyId 中存储了体验 B），则存储在 mbox3rdPartyId 中的属性会覆盖 PCID 中的属性。如果访客在登录之前位于某个活动或体验中，而 mbox3rdPartyId 中存储了另一个活动和体验，则该访客在登录后会进入 mbox3rdPartyId 中的活动和体验。

| PCID（未登录） | mbox3rdPartyId（已登录） | 合并且保存至 mbox3rdPartyId 的内容 |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| 活动 1，体验 A | 活动 1，体验 B | 活动 1，体验 B |
| 活动 1 |  | 活动 1 |

访客注销时，将会保留合并后的配置文件。

>[!NOTE]
>
>如果要区分已验证（已登录）的用户与非已验证的用户，请使用Adobe Experience Cloud Identity Service(ECID)而不是mbox3rdPartyID。 在用户与mbox3rdPartyID关联后，即使在注销后，该用户仍与该用户关联。

>[!NOTE]
>
>[!DNL Adobe Analytics] 在 [!DNL Adobe Experience Cloud][!DNL Target] ID(EDID)更改（例如，访客更改设备）时，不会跟踪目标，即使配置文件可能基于mbox3rdPartyId进行合并，但仍包含活动信息。 For visitors identified with the same EDID (those who access the page with the same device), [!DNL Analytics for Target] (A4T) should work as expected.

## 注意事项 {#considerations}

如果您的页面包含多个 mbox 并且只有部分 mbox 使用 3rdPartyID，则 Target 将不会对每个访客请求提供单独的访客配置文件/上下文。3rdPartyID 上下文优先于 PCID 上下文。一个 mbox 足以传递 3rdPartyId，因为其上下文优先于 PCID。

例如，假定某位访客在登录之前访问页面并看到某个体验。全局 mbox 没有使用 3rdPartyID。登录后，访客将看到三个使用子 mbox 体验的其中一个，其中一些 mbox 使用 3rdPartyID。访客访问网站上的各种页面，然后使用“返回”按钮返回到登录前访问的主页，并将看到一个不同的体验。在此情景中，全局 mbox 并未传递 3rdPartyID，但一个或多个子 mbox 传递了 3rdPartyID。3rdPartyID 优先于 PCID。
