---
keywords: google;samesite;cookies;chrome 80;ietf
description: 了解Adobe [!DNL Target] 如何处理随Google Chrome版本80引入的SameSite IETF标准，以及您需要做什么才能遵守这些策略。
title: 如何 [!DNL Target] 处理Google的Samesite Cookie策略？
feature: 隐私和安全
role: Developer
exl-id: 5abd2065-3692-4a6d-9ac9-6d416604c2d2
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '2048'
ht-degree: 7%

---

# Google Chrome SameSite Cookie 策略

默认情况下，谷歌将开始对从Chrome 80开始的用户实施新的Cookie政策，Chrome 80计划于2020年初发布。 本文解释了您需要了解的有关新SameSite Cookie策略的所有信息，[!DNL Adobe Target]如何支持这些策略，以及如何使用[!DNL Target]来符合Google Chrome的新SameSite Cookie策略。

从Chrome 80开始，Web开发人员必须明确指定哪些Cookie可以跨网站工作。 这是谷歌计划为改善网络隐私和安全性而发布的多项声明中的第一个。

鉴于Facebook在隐私和安全方面一直处于热门地位，苹果、谷歌等其他主要公司迅速抓住机会，打造隐私和安全捍卫者的新身份。 苹果率先在今年年初宣布通过ITP 2.1修改其cookie策略，最近又通过ITP 2.2修改。在ITP 2.1中，苹果完全阻止第三方cookie，并只在浏览器上创建cookies七天。 在ITP 2.2中，cookie只保存一天。 谷歌的声明远没有苹果那么激进，但这是朝着同一目标迈出的第一步。 有关Apple策略的详细信息，请参阅[Apple Intelligent Tracking Prevention(ITP)2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)。

## Cookie是什么？它们是如何使用的？

在深入了解谷歌对其cookies策略的更改之前，让我们先了解一下cookies是什么以及它们的使用方式。 简而言之，Cookie是存储在Web浏览器中的用于记住用户属性的小文本文件。

Cookie很重要，因为它们可增强用户浏览Web时的体验。 例如，如果您在电子商务网站上购物，并且向购物车中添加了内容，但并未登录或在该访问中购买，Cookie会记住您的商品并将它们保存在购物车中，供您下次访问。 或者，想象一下，如果您每次访问自己喜爱的社交媒体网站时都被迫重新输入用户名和密码。 Cookies也能解决这一问题，因为它们存储有助于网站识别您身份的信息。 这类Cookie称为第一方Cookie，因为它们是由您访问的网站创建和使用的。

第三方Cookie也存在。 为了更好地理解它们，让我们考虑以下示例：

假设一个名为“朋友”的假设社交媒体公司提供了一个“共享”按钮，其他网站实施该按钮以允许朋友用户在朋友源上共享该网站的内容。 现在，用户在使用“共享”按钮的新闻网站上阅读一篇新闻文章，并点击该文章自动在其“朋友”帐户上发布。

为了实现此目的，加载新闻文章时，浏览器会从`platform.friends.com`中获取“好友共享”按钮。 在此过程中，浏览器会将包含用户登录凭据的Friends Cookies附加到向Friends服务器发出的请求。 这样，好友就可以代表用户在其动态消息中发布新闻文章，而无需用户登录。

使用第三方Cookies即可实现所有这些。 在这种情况下，将在浏览器中为`platform.friends.com`保存第三方Cookie，以便`platform.friends.com`可以代表用户在Friends应用程序中发布帖子。

如果您想象一下，如何在没有第三方Cookie的情况下实现此用例，用户将必须执行大量手动步骤。 首先，用户必须复制指向新闻文章的链接。 其次，用户必须单独登录Friends应用程序。 然后，用户单击“创建帖子”按钮。 然后，用户将复制并粘贴文本字段中的链接，最后单击“发布”。 如您所见，第三方Cookie可大大减少手动步骤对用户体验的帮助。

更一般地，第三方Cookie使数据能够存储在用户的浏览器上，而不需要用户显式访问网站。

## 安全问题

尽管Cookie可增强用户体验和强大广告功能，但它们也可能引入诸如跨站点请求伪造(CSRF)攻击等安全漏洞。 例如，如果用户登录银行网站以支付信用卡账单并离开该网站而不注销，然后浏览到同一会话中的恶意网站，则可能发生CSRF攻击。 恶意网站可能包含向银行网站发出请求的代码，这些请求在页面加载时执行。 由于用户仍然被验证到银行站点，因此会话Cookie可用于启动CSRF攻击以从用户的银行帐户启动资金转移事件。 这是因为，每次访问站点时，HTTP请求中都会附加所有Cookie。 由于这些安全问题，谷歌现在正试图缓解这些问题。

## [!DNL Target]如何使用cookies?

尽管如此，让我们看看[!DNL Target]如何使用cookies。 要首先使用[!DNL Target]，您需要在站点上安装[!DNL Target] JavaScript库。 这使您能够在访问您网站的用户的浏览器上放置第一方Cookie。 当用户与您的网站交互时，您可以通过JavaScript库将用户的行为和兴趣数据传递到[!DNL Target]。 [!DNL Target] JavaScript库使用第一方Cookie提取有关要映射到用户行为和兴趣数据的用户的标识信息。 然后，[!DNL Target]会使用此数据来支持您的个性化活动。

目标还（有时）使用第三方Cookie。 如果您拥有多个生活在不同域上的网站，并且希望跟踪这些网站中的用户旅程，则可以通过利用跨域跟踪来使用第三方Cookie。 通过在[!DNL Target] JavaScript库中启用跨域跟踪，您的帐户将使用第三方Cookie进行开始。 当用户从一个域跳到另一个域时，浏览器与[!DNL Target]的后端服务器通信，在此过程中，将创建第三方Cookie并放置在用户的浏览器上。 通过用户浏览器上的第三方Cookie，[!DNL Target]可以为单个用户在不同域之间提供一致的体验。

## 谷歌新的Cookie菜谱

为了在跨站点发送Cookie时提供保护，以便保护用户，Google计划添加对称为SameSite的IETF标准的支持，该标准要求Web开发人员使用Set-Cookie头中的SameSite属性组件管理Cookie。

可以将三个不同的值传递到 SameSite 属性：Strict、Lax 或 None。

| 值 | 描述 |
| --- | --- |
| Strict | 只有在访问最初设置的域时，才可访问具有此设置的 Cookie。换言之，Strict 会完全阻止跨站点使用 Cookie。这种选择最适合银行等需要高安全性的应用。 |
| Lax | 具有此设置的Cookie仅在同一站点请求或具有非幂等HTTP请求的顶级导航上发送，如`HTTP GET`。 因此，如果第三方可以使用Cookie，但附加了安全优势，可保护用户免受CSRF攻击的侵害，则将使用此选项。 |
| None | 使用此设置的Cookie将像Cookie当前的工作方式一样工作。 |

请牢记上述，Chrome 80为用户引入了两个独立设置：&quot;SameSite by default cookies&quot;和&quot;Cookies without SameSite必须安全。&quot; 这些设置将在Chrome 80中默认启用。

![“相同”对话框](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

* **默认情况下，SameSite**:设置后，所有未指定SameSite属性的Cookie都将自动强制使用 `SameSite = Lax`。
* **没有SameSite的Cookie必须安全**:设置后，没有SameSite属性或具有Secure属 `SameSite = None` 性的Cookie需要是安全的。在此上下文中，安全是指所有浏览器请求都必须遵循 HTTPS 协议。不符合此要求的 Cookie 将被拒绝。所有网站都应使用HTTPS来满足此要求。

## Target 遵循 Google 安全最佳实践

在Adobe方面，我们始终希望支持业界有关安全性和隐私的最新最佳实践。 我们很高兴地宣布[!DNL Target]支持Google引入的新安全性和隐私设置。

对于“SameSite by default cookies”设置，[!DNL Target]将继续提供个性化，而不会受到任何影响和干预。 [!DNL Target] 会使用第一方 Cookie，并在 Google Chrome 应用标记 `SameSite = Lax` 时继续正常运行。

对于“无SameSite的Cookie必须安全”选项，如果您不选择[!DNL Target]中的跨域跟踪功能，则[!DNL Target]中的第一方Cookie将继续工作。

但是，当您选择使用跨域跟踪来跨多个域利用[!DNL Target]时，Chrome要求使用`SameSite = None`和安全标志来用于第三方Cookie。 这意味着您必须确保您的站点使用HTTPS协议。 [!DNL Target]中的客户端库将自动使用HTTPS协议，并将`SameSite = None`和安全标志附加到[!DNL Target]中的第三方Cookie，以确保所有活动继续传送。

## 您需要执行哪些操作？

要了解让[!DNL Target]继续适用于Google Chrome 80+用户，您需要做什么，请查阅下表，其中将显示以下列：

* **目标 JavaScript库**:如果您使用mbox.js，at.js 1。*x* 还是 at.js 2.*让您* 的站点更加轻松。
* **默认情况下，SameSite cookies =已启用**:如果您的用户启用了“SameSite by default cookies”，它会对您产生什么影响，您还需要做什么才能 [!DNL Target] 继续工作。
* **没有SameSite的Cookie必须是安全的=已启用**:如果您的用户启用了“必须安全”的“无SameSite的Cookie”，它会对您产生什么影响，您还需要做什么才能 [!DNL Target] 继续工作。

| 目标 JavaScript库 | 默认为 Cookie 设置 SameSite = 已启用 | 不具有 SameSite 的 Cookie 必须是安全的 = 已启用 |
| --- | --- | --- |
| mbox.js（仅包含第一方cookie）。 | 没有影响。 | 如果您未使用跨域跟踪，则不会受到影响。 |
| 已启用跨域跟踪的mbox.js。 | 没有影响。 | 您必须为站点启用HTTPS协议。<br>[!DNL Target] 使用第三方cookie来跟踪用户，而Google要求第三方cookie具有和安 `SameSite = None` 全标志。安全标志要求您的站点必须使用HTTPS协议。 |
| at.js 1.*x* 第一方cookie。 | 没有影响。 | 如果您未使用跨域跟踪，则不会受到影响。 |
| at.js 1.*x* 启用跨域跟踪。 | 没有影响。 | 您必须为站点启用HTTPS协议。<br>[!DNL Target] 使用第三方cookie来跟踪用户，而Google要求第三方cookie具有和安 `SameSite = None` 全标志。安全标志要求您的站点必须使用HTTPS协议。 |
| at.js 2.*x* | 没有影响。 | 没有影响。 |

## [!DNL Target]需要做什么？

那么，我们需要在我们的平台中做什么来帮助您遵守新的Google Chrome 80+ SameSite cookie策略？

| 目标 JavaScript库 | 默认为 Cookie 设置 SameSite = 已启用 | 不具有 SameSite 的 Cookie 必须是安全的 = 已启用 |
| --- | --- | --- |
| mbox.js（仅包含第一方cookie）。 | 没有影响。 | 如果您未使用跨域跟踪，则不会受到影响。 |
| 已启用跨域跟踪的mbox.js。 | 没有影响。 | [!DNL Target] 在 `SameSite = None` 调用服务器时向第三方Cookie添加和 [!DNL Target] 安全标志。 |
| at.js 1.*x* 第一方cookie。 | 没有影响。 | 如果您未使用跨域跟踪，则不会受到影响。 |
| at.js 1.*x* 启用跨域跟踪。 | 没有影响。 | at.js 1.*x* 启用跨域跟踪。 |
| at.js 2.*x* | 没有影响。 | 没有影响。 |

## 如果您不转而使用HTTPS协议，会产生什么影响？

影响您的唯一用例是，如果您使用[!DNL Target]中的跨域跟踪功能（通过mbox.js或at.js 1）。*x* 中不再对跨域跟踪提供开箱即用支持。如果不转向HTTPS（这是Google的要求），您会看到域内独特访客的激增，因为Google会丢弃我们使用的第三方Cookie。 由于将丢弃第三方Cookie，当用户从一个域导航到另一个域时， [!DNL Target]将无法为该用户提供一致的个性化体验。 第三方Cookie主要用于标识在您拥有的域之间导航的单个用户。

## 结论

随着行业在为消费者创建更安全的Web方面取得长足进展，[!DNL Adobe]绝对致力于帮助客户以确保最终用户安全和隐私的方式提供个性化体验。 您只需遵循上述最佳实践并利用[!DNL Target]符合Google Chrome的新SameSite Cookie策略。
