---
keywords: mbox;mbox3rdPartyId;配置文件同步;PCID
description: 了解如何使用mbox3rdPartyId，它是您组织的访客ID，如会员ID或您组织的忠诚度计划。
title: 如何对mbox3rdPartyId使用实时配置文件同步？
feature: Audiences
exl-id: ed409225-fa35-49da-87d1-1770221f2ae0
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 18%

---

# mbox3rdPartyId 的实时配置文件同步

[!DNL Adobe Target]中的`mbox3rdPartyId`是您公司的访客ID，例如您公司的忠诚度计划的会员ID。

访客登录到某个公司的网站后，该公司通常会创建一个 ID，并将其绑定到访客的帐户、会员卡、会员编号，以及该公司的其他适用标识符。

如果访客访问的页面启用了 [!DNL Target]，则会为该访客分配一个 [!DNL Target] PCID。如果该访客随后登录，并且实施将`mbox3rdPartyId`传递到[!DNL Target]，则[!DNL Target]会将该访客的`mbox3rdPartyId`与[!DNL Target] PCID相关联。

更新每5-10分钟与配置文件存储同步一次。 当访客的会话结束时，合并的数据将替换以前与`mbox3rdPartyId`关联的数据，从而创建该访客操作的完整记录。 如果两个ID中存在相同的属性 — 例如，PCID具有category=hats，而`mbox3rdPartyId`具有category=skis；或者，如果访客在登录之前查看了体验A，但体验B存储在`mbox3rdPartyId`中，则存储在`mbox3rdPartyId`中的属性会覆盖PCID中的属性。 如果访客在登录之前位于某个活动或体验中，但`mbox3rdPartyId`中存储了另一个活动和体验，则在登录后，该访客将被放入`mbox3rdPartyId`活动和体验中。

| PCID（未登录） | mbox3rdPartyId（已登录） | 合并且保存至 mbox3rdPartyId 的内容 |
|---|---|---|
| category=hats | category=skis | category=skis |
|   | store=94103 | store=94103 |
| 活动 1，体验 A | 活动 1，体验 B | 活动 1，体验 B |
| 活动 1 |  | 活动 1 |

访客注销时，将会保留合并后的配置文件。

>[!NOTE]
>
>如果要区分经过身份验证（已登录）的用户与未经身份验证的用户，请使用[!DNL Adobe Experience Cloud Identity Service] (ECID)而不是mbox3rdPartyID。 当用户与mbox3rdPartyID关联后，即使注销后它仍与该用户关联。

>[!NOTE]
>
>在[!DNL Adobe Experience Cloud] ID (ECID)发生更改（例如访客更改设备）时，即使[!DNL Target]配置文件可能会根据mbox3rdPartyId进行合并，并且仍然具有活动信息，仍将不会跟踪[!DNL Adobe Analytics]目标。 对于使用相同ECID进行标识的访客（使用同一设备访问页面的访客），[!DNL Analytics for Target] (A4T)应按预期工作。

## 注意事项 {#considerations}

* 如果您的页面包含多个mbox且只有一些使用`3rdPartyID`，则[!DNL Target]不会为每个访客请求提供单独的访客配置文件/上下文。 `3rdPartyID`上下文优先于PCID上下文。 一个mbox足以传递`3rdPartyId`，因为其上下文优先于PCID。

  例如，假设访客在登录之前访问页面并看到某个体验。 全局mbox不使用`3rdPartyID`。 登录后，访客看到三个具有子mbox的体验之一，其中一些使用`3rdPartyID`。 访客访问网站上的各种页面，然后使用“返回”按钮返回到登录前访问的主页，并将看到一个不同的体验。在此方案中，全局mbox未传递`3rdPartyID`，但有一个或多个子mbox传递。 `3rdPartyID`优先于PCID。

* 您可以使用两种方法将访客的客户ID发送到[!DNL Target]：

   1. 使用`mbox3rdPartyId`/`thirdPartyId`。

      * 当您使用`targetPageParams`或`targetPageParamsAll`时，`mbox3rdPartyId`是参数名称
      * `thirdPartyId`是您直接在投放API有效载荷中设置的参数名称。
      * 您只能在此参数中发送一个值。

   1. 使用ECID服务的`setCustomerId`/`customerIds`函数。

      * `setCustomerId`是一个您可以在客户端（浏览器）实施中使用的函数，前提是页面上有VisitorAPI.js。
      * `customerIds`是您在投放API有效载荷中直接设置它时使用的参数名称，通常在服务器端或IOT（物联网）实施中完成。
      * 与`mbox3rdPartyId`/`thirdPartyId`不同，您可以在此方法中将多个ID作为列表发送，但由于[!DNL Target]仅支持每个TnT ID一个客户ID，因此它使用具有已知别名（在客户属性UI中配置的别名）的列表中的第一个ID。

  如果[!DNL Target]是您唯一的[!DNL Adobe Experience Cloud]解决方案并且您不想使用客户属性，则可以使用`mbox3rdPartyId`/`thirdPartyId`。 对于所有其他情况，我们建议您使用`setCustomerId`/`customerIds`来发送客户ID。

  >[!IMPORTANT]
  >
  > 为单个访客交替使用上述两种方法可能会导致未经身份验证和经过身份验证的[!DNL Target]配置文件不正确的配置文件合并。
  >
  >Adobe不建议同时使用`mbox3rdPartyId`/`thirdPartyId`和`setCustomerID`/`customerIds`。
  >
  >如果必须交替使用这两种方法，请确保`setCustomerID`/`customerIds`使用的列表中的第一个ID是`thirdPartyId`/`mbox3rdPartyId`使用的ID，反之亦然。

