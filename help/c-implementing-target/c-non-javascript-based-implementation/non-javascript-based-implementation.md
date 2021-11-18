---
keywords: 实施；at.js非javascript;Adbox；重定向器；mbox
description: 了解如何实施Adobe [!DNL Target] 在非JavaScript情景中，例如使用AdBox或重定向器。
title: 如何实施 [!DNL Target] 电子邮件？
feature: Implement Email
role: Developer
exl-id: 3287cf3d-3ed4-471f-aa06-25bb12e23ead
source-git-commit: bef2b493e8964f468d4f766c932a96d32e994a03
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 78%

---

# 电子邮件：实施 Target

此信息介绍了如何在非 JavaScript 情景中实施 Target，例如使用 AdBox 或重定向器。

您可以跟踪对广告和其他站外内容的访问次数。您还能识别您站内和站外的同一用户，并根据其全部的网络活动情况展示符合其特点的体验。AdBox通过使用单个URL进行测试，而无需使用JavaScript或 [!DNL at.js].

AdBox对于没有 [!DNL at.js]，如附属活动。 如果您的活动需要动态创意（例如，您需要在广告中显示已从购物车中放弃的产品），那么您将不能使用 AdBox。

AdBox 广告和重定向器可用于任何类型的活动。下表比较了 Adbox 和重定向器，同时还介绍了二者分别在何时使用：

|  | 用途 | 何时使用 | URL 结构 | 选件类型 | 选件内容 |
|--- |--- |--- |--- |--- |--- |
| AdBox | 向广告返回不同的图像 | 改变广告的内容 | `clientcode&#x200B;.tt.&#x200B;omtrdc&#x200B;.net/&#x200B;m2&#x200B;/&#x200B;clientcode/ubox/&#x200B;image?` | 重定向选件 | 图像 URL |
| 重定向器 | 将访客重新导向另一个网页 | 改变广告的登陆页 | `clientcode&#x200B;.tt.omtrdc.net/&#x200B;m2/clientcode&#x200B;/ubox/page?` | 重定向选件 | 页面 URL |

## 安全最佳实践 {#security}

请注意，使用重定向器，您可能会面临打开重定向漏洞的风险。 为避免第三方未经授权使用重定向器链接，我们建议您使用“已授权的主机”来允许列表默认的重定向URL域。 Target 使用主机将您要允许重定向到的域列入允许列表。有关详细信息，请在“主机”**&#x200B;中参阅[创建允许列表，其中指定有权将 mbox 调用发送到 Target 的主机](/help/administrating-target/hosts.md#allowlist)。

## 限制 {#section_38F559DCF1324271926608BCD4AB1227}

* 标准 mbox 不存在客户端超时。如果 Target 完全关闭，广告访客将看不到广告内容，甚至也看不到默认内容。
* 使用第三方 Cookie 来跟踪访问次数。如果 PCID 不相同，则默认情况下会将访客的第三方配置文件与任何现有的第一方配置文件合并到一起。
* 要在 AdBox 自身中使用第一方 Cookie，您需要在 URL 中传递 mBox 会话。请咨询您的客服专员以实现此操作。
* 要使用第一方 Cookie 来跟踪广告点击次数，需在 URL 中传递 mbox 会话。请咨询您的客服专员以实现此操作。
* 您必须在 URL 中传递 Mbox 会话才能在同一页面上使用多个 AdBox。请咨询您的客服专员以实现此操作。同一个页面上可能会具有一个 AdBox 和一个重定向器链接（因为重定向器实际上位于另一个页面上）。
