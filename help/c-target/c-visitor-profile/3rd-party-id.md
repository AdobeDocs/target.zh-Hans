---
description: mbox3rdPartyID 是您公司的访客 ID，例如您公司的忠诚度计划的会员 ID。
keywords: mbox;mbox3rdPartyID;配置文件同步
seo-description: mbox3rdPartyID 是您公司的访客 ID，例如您公司的忠诚度计划的会员 ID。
seo-title: mbox3rdPartyID 的实时配置文件同步
solution: Target
title: mbox3rdPartyID 的实时配置文件同步
topic: Standard
uuid: a88353d1-36e8-48b2-9b5e-71ed437c5b99
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# mbox3rdPartyID 的实时配置文件同步{#real-time-profile-syncing-for-mbox-rdpartyid}

mbox3rdPartyID 是您公司的访客 ID，例如您公司的忠诚度计划的会员 ID。

访客登录到某个公司的网站后，该公司通常会创建一个 ID，并将其绑定到访客的帐户、会员卡、会员编号，以及该公司的其他适用标识符。

如果访客访问的页面启用了 Target，则会为该访客分配一个 Target PCID。如果该访客随后登录，并且相应实施将 mbox3rdPartyID 传递到 Target，则 Target 会将该访客的 mbox3rdPartyID 与 Target PCID 相关联。

每三到五分钟，更新内容就会与数据库同步一次。访客注销后，合并的数据会替换以前与 mbox3rdPartyID 关联的数据，以便创建该访客操作的更完整记录。如果两个 ID 中存在相同的属性（例如，PCID 具有 category=hats，而 mbox3rdPartyID 具有 category=skis；或者，如果访客在登录之前查看了体验 A，而 mbox3rdPartyID 中存储了体验 B），则存储在 mbox3rdPartyID 中的属性会覆盖 PCID 中的属性。如果访客在登录之前位于某个活动或体验中，而 mbox3rdPartyID 中存储了另一个活动和体验，则该访客在登录后会进入 mbox3rdPartyID 中的活动和体验。

| PCID（未登录） | mbox3rdPartyID（已登录） | 合并且保存至 mbox3rdPartyID 的内容 |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| 活动 1，体验 A | 活动 1，体验 B | 活动 1，体验 B |
| 活动 1 |  | 活动 1 |

访客注销时，将会保留合并后的配置文件。

>[!NOTE]
>
>在 [!DNL Adobe Experience Cloud] ID (MID) 发生更改（例如访客更改设备）时，即便 [!DNL Target] 配置文件可能会根据 mbox3rdPartyID 进行合并，并且仍然具有活动信息，仍将不会跟踪 [!DNL Adobe Analytics] 目标。对于使用相同 MID 进行标识的访客（使用相同设备访问该页面的访客），[!DNL Analytics for Target] (A4T) 应按预期工作。
