---
keywords: Implementation;mbox.js non javascript;adbox;redirector;mbox
description: 此信息介绍了如何在非 JavaScript 情景中实施 Target，例如使用 AdBox 或重定向器。
title: 电子邮件：实施 Target
feature: email implementation
subtopic: Getting Started
topic: Standard
uuid: 07abc419-0253-47c6-80b8-0bd0734d2c9d
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 82%

---


# 电子邮件：实施 Target{#email-implement-target}

此信息介绍了如何在非 JavaScript 情景中实施 Target，例如使用 AdBox 或重定向器。

您可以跟踪对广告和其他站外内容的访问次数。您还能识别您站内和站外的同一用户，并根据其全部的网络活动情况展示符合其特点的体验。AdBox 通过使用一个 URL 来进行测试，而无需使用 JavaScript、[!DNL at.js] 或 [!DNL mbox.js]。

AdBox 对于没有 [!DNL at.js] 或 [!DNL mbox.js] 的网站（例如联属网站）非常有用。如果您的活动需要动态创意（例如，您需要在广告中显示已从购物车中放弃的产品），那么您将不能使用 AdBox。

AdBox 广告和重定向器可用于任何类型的活动。下表比较了 Adbox 和重定向器，同时还介绍了二者分别在何时使用：

|  | 用途 | 何时使用 | URL 结构 | 选件类型 | 选件内容 |
|--- |--- |--- |--- |--- |--- |
| AdBox | 向广告返回不同的图像 | 改变广告的内容 | `clientcode&#x200B;.tt.&#x200B;omtrdc&#x200B;.net/&#x200B;m2&#x200B;/&#x200B;clientcode/ubox/&#x200B;image?` | 重定向选件 | 图像 URL |
| 重定向器 | 将访客重新导向另一个网页 | 改变广告的登陆页 | `clientcode&#x200B;.tt.omtrdc.net/&#x200B;m2/clientcode&#x200B;/ubox/page?` | 重定向选件 | 页面 URL |

## 安全最佳实践 {#security}

请注意，使用重定向器，您可能会面临开放重定向漏洞的风险。 为避免第三方未授权使用重定向器链接，我们建议您使用“授权主机”来允许列表默认重定向URL域。 目标使允许列表用主机要允许重定向的域。 有关详细信息，请参 [阅创允许列表建指定已授权向主机中的目标发送mbox调用的主机的程序](/help/administrating-target/hosts.md#allowlist) ( *英文)*。

## 限制 {#section_38F559DCF1324271926608BCD4AB1227}

* 标准 mbox 不存在客户端超时。如果 Target 完全关闭，广告访客将看不到广告内容，甚至也看不到默认内容。
* 使用第三方 Cookie 来跟踪访问次数。如果 PCID 不相同，则默认情况下会将访客的第三方配置文件与任何现有的第一方配置文件合并到一起。
* 要在 AdBox 自身中使用第一方 Cookie，您需要在 URL 中传递 mBox 会话。请咨询您的客服专员以实现此操作。
* 要使用第一方 Cookie 来跟踪广告点击次数，需在 URL 中传递 mbox 会话。请咨询您的客服专员以实现此操作。
* 您必须在 URL 中传递 Mbox 会话才能在同一页面上使用多个 AdBox。请咨询您的客服专员以实现此操作。同一个页面上可能会具有一个 AdBox 和一个重定向器链接（因为重定向器实际上位于另一个页面上）。