---
keywords: mbox;mbox3rdPartyId;配置文件同步;PCID
description: 了解如何使用mbox3rdPartyId（即您组织的访客ID），例如会员ID或您组织的忠诚度计划。
title: 如何对mbox3rdPartyId使用实时配置文件同步？
feature: Audiences
exl-id: ed409225-fa35-49da-87d1-1770221f2ae0
source-git-commit: 211931f4456f5360efb1fbaa4f0bc23f5bfbcfc1
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 21%

---

# mbox3rdPartyId 的实时配置文件同步

的 `mbox3rdPartyId` in [!DNL Adobe Target] 是您公司的访客ID，例如您公司忠诚度计划的会员ID。

访客登录到某个公司的网站后，该公司通常会创建一个 ID，并将其绑定到访客的帐户、会员卡、会员编号，以及该公司的其他适用标识符。

如果访客访问的页面启用了 [!DNL Target]，则会为该访客分配一个 [!DNL Target] PCID。如果访客随后登录，并且实施通过 `mbox3rdPartyId` to [!DNL Target], [!DNL Target] 连接该访客的 `mbox3rdPartyId` 和 [!DNL Target] PCID。

更新每5-10分钟与配置文件存储同步一次。 当访客的会话结束时，合并的数据将替换与 `mbox3rdPartyId`，以创建该访客操作的完整记录。 如果两个ID中存在相同的属性 — 例如，PCID具有category=hats，并且 `mbox3rdPartyId` 具有category=skis，或者如果访客在登录之前查看了体验A，但体验B存储在 `mbox3rdPartyId` — 存储在 `mbox3rdPartyId` 覆盖PCID中的属性。 如果访客在登录之前位于某个活动或体验中，但在 `mbox3rdPartyId`，则登录后，该访客将被置于 `mbox3rdPartyId` 活动和体验。

| PCID（未登录） | mbox3rdPartyId（已登录） | 合并且保存至 mbox3rdPartyId 的内容 |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| 活动 1，体验 A | 活动 1，体验 B | 活动 1，体验 B |
| 活动 1 |  | 活动 1 |

访客注销时，将会保留合并后的配置文件。

>[!NOTE]
>
>如果要区分已验证（已登录）的用户和未验证的用户，请使用 [!DNL Adobe Experience Cloud Identity Service] (ECID)，而不是mbox3rdPartyID。 在用户与mbox3rdPartyID关联后，即使在注销后，它仍会与用户关联。

>[!NOTE]
>
>[!DNL Adobe Analytics] 如果 [!DNL Adobe Experience Cloud] ID(ECID)会更改（例如，访客会更改设备），即使 [!DNL Target] 配置文件可能会根据mbox3rdPartyId进行合并，并且仍然具有活动信息。 对于使用相同ECID标识的访客（使用相同设备访问该页面的访客）， [!DNL Analytics for Target] (A4T)应按预期工作。

## 注意事项 {#considerations}

* 如果您的页面包含多个mbox，并且只有部分用户使用 `3rdPartyID`, [!DNL Target] 每个访客请求没有单独的访客配置文件/上下文。 的 `3rdPartyID` 上下文优先于PCID上下文。 一个mbox就足够通过 `3rdPartyId` 因为其上下文优先于PCID。

   例如，假定访客在登录之前访问了某个页面并看到了某个体验。 全局 mbox 没有使用 `3rdPartyID`. 登录后，访客将看到三个使用子 mbox 体验的其中一个，其中一些 mbox 使用 `3rdPartyID`. 访客访问网站上的各种页面，然后使用“返回”按钮返回到登录前访问的主页，并将看到一个不同的体验。在此方案中，全局mbox未传递 `3rdPartyID`，但一个或多个子mbox执行了此操作。 `3rdPartyID` 优先于PCID。

* 您可以将访客的客户ID发送到 [!DNL Target] 使用两种方法：

   1. 使用 `mbox3rdPartyId`/`thirdPartyId`.

      * `mbox3rdPartyId` 是使用 `targetPageParams` 或 `targetPageParamsAll`
      * `thirdPartyId` 是您在交付API有效负载中直接设置的参数名称。
      * 您只能在此参数中发送一个值。
   1. 使用 `setCustomerId`/`customerIds` 函数。

      * `setCustomerId` 是一个函数，当页面上有VisitorAPI.js时，您可以在客户端（浏览器）实施中使用该函数。
      * `customerIds` 是直接在交付API有效负载中设置参数名称时使用的参数名称，通常在服务器端或IOT（物联网）实施中完成。
      * 不同 `mbox3rdPartyId`/`thirdPartyId`，则您可以在此方法中作为列表发送多个ID，但是因为 [!DNL Target] 每个TnT ID仅支持一个客户ID，它使用列表中的第一个ID和已知别名（在客户属性UI中配置的别名）。

   您可以使用 `mbox3rdPartyId`/`thirdPartyId` if [!DNL Target] 仅 [!DNL Adobe Experience Cloud] 解决方案，则您不希望使用客户属性。 对于所有其他情况，我们建议您使用 `setCustomerId`/`customerIds` 用于发送客户ID。

   >[!IMPORTANT]
   >
   > 对单个访客交替使用上述两种方法可能会导致未验证和已验证的配置文件合并不正确 [!DNL Target] 用户档案。
   >
   >Adobe不建议您同时使用 `mbox3rdPartyId`/`thirdPartyId` 和 `setCustomerID`/`customerIds` 一起。
   >
   >如果必须交替使用这两种方法，请确保 `setCustomerID`/`customerIds` 是使用的 `thirdPartyId`/`mbox3rdPartyId` 反之亦然。

