---
keywords: google;samesite;cookies;chrome 80;ietf
description: 有关 Google Chrome 版本 80 引入的 Adobe Target 和 SameSite IETF 标准的信息。
title: Adobe Target和谷歌的SameSite Cookie政策
feature: privacy and security
subtopic: Getting Started
topic: Standard
uuid: aaeda1e6-7b2c-4a00-b65d-bfc95ea796b5
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '2033'
ht-degree: 8%

---


# Google Chrome SameSite Cookie 策略

谷歌将开始默认为从Chrome 80开始的用户实施新的cookie策略，该策略计划于2020年初发布。 本文解释了您需要了解的有关新的SameSite [!DNL Adobe Target] Cookie策略、如何支持这些策略以及如何 [!DNL Target] 使用来遵守Google Chrome的新的SameSite Cookie策略。

从Chrome 80开始，Web开发人员必须明确指定哪些cookie可以跨网站工作。 这是谷歌计划为改善网络隐私和安全性而发布的多项声明中的第一项。

鉴于Facebook在隐私和安全方面一直处于热门地位，苹果等其他主要企业也迅速抓住机会，打造新身份，成为隐私和安全捍卫者。 苹果率先在今年年初通过ITP 2.1宣布对其cookie策略做出更改，最近又通过ITP 2.2宣布修改。在ITP 2.1中，苹果完全阻止第三方cookie，并在浏览器上创建cookies仅七天。 在ITP 2.2中，cookie只保存一天。 谷歌的声明远没有苹果那么激进，但这是朝着同样的最终目标迈出的第一步。 有关Apple策略的详细信息，请参 [阅Apple Intelligent Tracking Prevention(ITP)2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)。

## 什么是cookie，它们的使用方式？

在深入了解Google对其cookies策略的更改之前，让我们先了解cookies是什么以及它们的使用方式。 简而言之，Cookie是存储在Web浏览器中的用于记住用户属性的小文本文件。

Cookies很重要，因为当用户浏览Web时，它们可以增强用户的体验。 例如，如果您在电子商务网站上购物并向购物车中添加内容，但不登录或在该访问中购买，cookie会记住您的商品并将它们保存在购物车中，供您下次访问。 或者，想象一下，如果您每次访问自己喜爱的社交媒体网站时都被迫重新输入用户名和密码。 Cookies也可以解决此问题，因为它们存储可帮助网站识别您身份的信息。 这些类型的cookies称为第一方cookies，因为它们是由您访问的网站创建和使用的。

第三方Cookie也存在。 为了更好地理解它们，我们来考虑以下示例：

假设一个名为“朋友”的社交媒体公司提供了一个“共享”按钮，其他网站实施该按钮后，“朋友”用户便可在“朋友”源上共享该网站的内容。 现在，用户在使用“共享”按钮的新闻网站上阅读一篇新闻文章，并单击它以自动发布到其好友帐户。

为了实现此目的，加载新闻文章时，浏览器会 `platform.friends.com` 从中获取“好友共享”按钮。 在此过程中，浏览器将包含用户登录凭据的好友cookie附加到好友服务器的请求中。 这样，好友就可以代表用户在其源中发布新闻文章，而无需用户登录。

这一切都可以通过使用第三方cookies实现。 在这种情况下，第三方cookie会保存在浏览器 `platform.friends.com`中， `platform.friends.com` 以便代表用户在朋友应用程序中发布。

如果您想象一下，如何在没有第三方cookies的情况下实现此用例，用户将必须执行大量手动步骤。 首先，用户必须复制指向新闻文章的链接。 其次，用户必须单独登录Friends应用程序。 然后，用户单击“创建帖子”按钮。 然后，用户将复制并粘贴文本字段中的链接，最后单击“发布”。 正如您所看到的，第三方Cookie可以大大减少手动步骤，从而极大地帮助用户体验。

更一般地说，第三方Cookie使数据能够存储在用户的浏览器中，而无需该用户显式访问网站。

## 安全问题

虽然cookies增强了用户体验和强大广告功能，但它们也可能引入诸如跨站点请求伪造(CSRF)攻击等安全漏洞。 例如，如果用户登录银行站点以支付信用卡账单并离开该站点而不注销，然后浏览到同一会话中的恶意站点，则可能发生CSRF攻击。 恶意站点可能包含向银行站点发出请求的代码，该请求在页面加载时执行。 由于用户仍然通过银行站点的身份验证，会话cookie可用于启动CSRF攻击以从用户的银行帐户发起资金转移事件。 这是因为，每次访问站点时，HTTP请求中都会附加所有Cookie。 由于这些安全问题，谷歌现在正在试图缓解这些问题。

## 目标如何使用cookies?

尽管如此，让我们看看如何使 [!DNL Target] 用cookies。 要首先使用 [!DNL Target] ，您需要在站点上 [!DNL Target] 安装JavaScript库。 这使您能够在访问您网站的用户的浏览器上放置第一方cookie。 当用户与您的网站交互时，您可以通过JavaScript库将用户的行为和兴 [!DNL Target] 趣数据传递给用户。 JavaScript [!DNL Target] 库使用第一方Cookie提取有关用户的标识信息以映射到用户的行为和兴趣数据。 然后，这些数据被用 [!DNL Target] 于支持您的个性化活动。

目标还（有时）使用第三方cookie。 如果您拥有多个位于不同域的网站，并且希望跟踪这些网站中的用户旅程，则可以通过利用跨域跟踪来使用第三方Cookie。 通过在JavaScript库中启用跨域 [!DNL Target] 跟踪，您的帐户将使用第三方Cookie进行开始。 当用户从一个域跳到另一个域时，浏览器会与其后端服务器进行通信 [!DNL Target]，在此过程中，会创建第三方cookie并将其放置在用户的浏览器上。 通过用户浏览器上的第三方cookie, [!DNL Target] 可以为单个用户跨不同域提供一致的体验。

## 谷歌新Cookie秘方

为了在跨站点发送cookie时提供保护，以便保护用户，Google计划添加对称为SameSite的IETF标准的支持，该标准要求Web开发人员使用Set-Cookie头中的SameSite属性组件管理cookie。

可以将三个不同的值传递到 SameSite 属性：Strict、Lax 或 None。

| 值 | 描述 |
| --- | --- |
| Strict | 只有在访问最初设置的域时，才可访问具有此设置的 Cookie。换言之，Strict 会完全阻止跨站点使用 Cookie。这种选择最适用于需要高安全性的应用，如银行。 |
| Lax | Cookies with this setting are sent only on same-site requests or top-level navigation with non-idempotent HTTP requests, like `HTTP GET`. 因此，如果第三方可以使用cookie，但增加了安全优势，保护用户免受CSRF攻击的侵害，则将使用此选项。 |
| None | 使用此设置的Cookie将像Cookie当前工作的方式一样工作。 |

请牢记以上几点，Chrome 80为用户引入了两个独立设置：“默认情况下，SameSite cookies”和“无SameSite的Cookies必须安全。” 这些设置将在Chrome 80中默认启用。

![“同一站点”对话框](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

* **默认情况下，SameSite** cookie:设置后，所有未指定SameSite属性的cookie将自动强制使用 `SameSite = Lax`。
* **没有SameSite的Cookie必须安全**:设置后，没有SameSite属性或具有安全 `SameSite = None` 性的Cookie需要。 在此上下文中，安全是指所有浏览器请求都必须遵循 HTTPS 协议。不符合此要求的 Cookie 将被拒绝。所有网站都应使用HTTPS来满足此要求。

## Target 遵循 Google 安全最佳实践

在Adobe，我们始终希望支持业界最新的安全和隐私最佳实践。 We are happy to announce that [!DNL Target] supports the new security and privacy settings introduced by Google.

对于“SameSite by default cookies”设置，将继 [!DNL Target] 续提供个性化，而不受您影响和干预。 [!DNL Target] 会使用第一方 Cookie，并在 Google Chrome 应用标记 `SameSite = Lax` 时继续正常运行。

对于“无SameSite的Cookie必须是安全的”选项，如果您不选择加入中的跨域跟踪功能， [!DNL Target]则中的第一方Cookie [!DNL Target] 将继续工作。

However, when you opt-in to use cross-domain tracking to leverage [!DNL Target] across multiple domains, Chrome requires `SameSite = None` and Secure flags to be used for third-party cookies. 这意味着您必须确保您的站点使用HTTPS协议。 中的客户端库 [!DNL Target] 将自动使用HTTPS协议，并将 `SameSite = None` 和安全标志附加到第三方Cookie中， [!DNL Target] 以确保所有活动继续提供。

## 您需要执行哪些操作？

要了解继续为Google Chrome 80 [!DNL Target] +用户工作需要做什么，请查阅下表，其中将显示以下列：

* **目标JavaScript库**:如果您使用mbox.js,at.js 1。*x* 还是 at.js 2.*x* 。
* **默认情况下，SameSite cookies =已启用**:如果您的用户启用了“默认为SameSite cookies”，它会对您产生何种影响，您还需要做什么才能 [!DNL Target] 继续工作。
* **没有SameSite的Cookie必须是安全的=已启用**:如果您的用户启用了“必须安全地使用SameSite的Cookie”，它会对您产生何种影响，您还需要做什么才能 [!DNL Target] 继续工作。

| 目标JavaScript库 | 默认为 Cookie 设置 SameSite = 已启用 | 不具有 SameSite 的 Cookie 必须是安全的 = 已启用 |
| --- | --- | --- |
| mbox.js（仅包含第一方cookie）。 | 没有影响。 | 如果不使用跨域跟踪，则不会产生任何影响。 |
| 已启用跨域跟踪的mbox.js。 | 没有影响。 | 必须为站点启用HTTPS协议。<br>[!DNL Target] 使用第三方cookie来跟踪用户，而Google需要第三方cookie来具有和安 `SameSite = None` 全标志。 安全标志要求您的站点必须使用HTTPS协议。 |
| at.js 1.*x* 第一方cookie。 | 没有影响。 | 如果不使用跨域跟踪，则不会产生任何影响。 |
| at.js 1.*x* 启用跨域跟踪。 | 没有影响。 | 必须为站点启用HTTPS协议。<br>[!DNL Target] 使用第三方cookie来跟踪用户，而Google需要第三方cookie来具有和安 `SameSite = None` 全标志。 安全标志要求您的站点必须使用HTTPS协议。 |
| at.js 2.*x* | 没有影响。 | 没有影响。 |

## 目标需要做什么？

那么，我们需要在我们的平台中做什么来帮助您遵守新的Google Chrome 80+ SameSite cookie策略？

| 目标JavaScript库 | 默认为 Cookie 设置 SameSite = 已启用 | 不具有 SameSite 的 Cookie 必须是安全的 = 已启用 |
| --- | --- | --- |
| mbox.js（仅包含第一方cookie）。 | 没有影响。 | 如果不使用跨域跟踪，则不会产生任何影响。 |
| 已启用跨域跟踪的mbox.js。 | 没有影响。 | [!DNL Target] 在 `SameSite = None` 调用服务器时向第三方cookie添加安全 [!DNL Target] 标志。 |
| at.js 1.*x* 第一方cookie。 | 没有影响。 | 如果不使用跨域跟踪，则不会产生任何影响。 |
| at.js 1.*x* 启用跨域跟踪。 | 没有影响。 | at.js 1.*x* 启用跨域跟踪。 |
| at.js 2.*x* | 没有影响。 | 没有影响。 |

## 如果不转而使用HTTPS协议，会产生什么影响？

影响您的唯一用例是，如果您使用的跨域跟踪功能是 [!DNL Target] 通过mbox.js或at.js 1的。*x* 中不再对跨域跟踪提供开箱即用支持。如果不转向HTTPS（这是Google的要求），您会发现域内的唯一访客会激增，因为Google会丢弃我们使用的第三方Cookie。 由于第三方cookie将被删除，因此当 [!DNL Target] 用户从一个域导航到另一个域时，将无法为该用户提供一致的个性化体验。 第三方cookie主要用于标识在您拥有的域中导航的单个用户。

## 结论

随着行业在为消费者创建更加安全的Web方面取得长足进展， [!DNL Adobe] 我们始终致力于帮助客户以确保最终用户安全和隐私的方式提供个性化体验。 您只需遵循上述最佳实践，并充分利 [!DNL Target] 用Google Chrome的新SameSite Cookie策略。
