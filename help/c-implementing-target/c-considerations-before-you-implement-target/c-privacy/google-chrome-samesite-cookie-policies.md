---
description: 有关从 Google Chrome 版本 76 开始使用的 Target 和 SameSite IETF 标准的信息。
keywords: google;samesite；cookies；rome80；ietf
seo-description: 有关 Google Chrome 版本 80 引入的 Adobe Target 和 SameSite IETF 标准的信息。
seo-title: Adobe Target和Google的SameSite Cookie策略
solution: Target
subtopic: 入门指南
title: Google Chrome SameSite Cookie 策略
topic: Standard
uuid: aaeda1e6-7b2c-4a00-b65d-bfc95ea796b5
translation-type: tm+mt
source-git-commit: df40d69676cea586451e3b64b56ef602da91173f

---


# Google Chrome SameSite Cookie 策略

Google将默认为从Chrome80开始的用户强制实施新的cookie策略，该策略将于2020年初发布。本文解释了您所需了解的有关新SaveSite cookie策略的一切、 [!DNL Adobe Target] 支持这些策略以及如何使用 [!DNL Target] Google Chrome新的SaveSite Cookie策略。

从Chrome80开始，Web开发人员必须明确指定哪些cookie可以跨网站工作。这是Google计划提高Web隐私和安全性的许多声明中的第一个。

鉴于Facebook在隐私和安全性方面一直处于领先地位，其他主要播放器(如Apple和现在的Google)已经利用机会来创建新的隐私和安全支持。Apple通过在今年年初通过ITP2.1和ITP2.2宣布对其cookie策略的更改来捆绑包。在ITP2.1中，Apple完全阻止第三方cookie，并将cookie保留在浏览器中仅七天。在ITP2.2中，cookies仅保留一天。Google的公告几乎不像Apple那样大胆，但它是朝着同一最终目标迈出的第一步。有关Apple策略的更多信息，请参阅 [Apple智能跟踪预防(ITP)2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)。

## 什么是cookies？他们如何使用？

在我们深入了解Google对其cookies策略的更改之前，让我们了解一下Cookie是什么以及如何使用它们。简而言之，cookies是存储在Web浏览器中的小文本文件，用于记住用户属性。

Cookie非常重要，因为他们在浏览Web时增强了用户的体验。例如，如果您在eCommerce网站上购物，但在购物车中添加了一些东西，但在该访问中未登录或购买，则cookies会记住您的物品并保存到您的购物车中以便下一次访问。或者，如果您在每次访问您喜爱的社交媒体网站时强制重新输入用户名和密码，请想象一下。Cookies也可以解决这一问题，因为他们存储可帮助站点识别您身份的信息。这些cookies称为第一方cookie，因为它们是由您访问的网站创建和使用的。

第三方Cookie也存在。为了更好地理解它们，请考虑以下示例：

假设一家名为“朋友”的虚构社交媒体公司提供了其他站点的“共享”按钮，让“朋友”用户能够在“朋友”源上分享该站点的内容。现在，用户在使用“共享”按钮的新闻网站上阅读新闻文章，并单击它以自动在其“朋友”帐户上发帖。

为实现这一目标，浏览器将在加载新闻文章时获取 `platform.friends.com` “朋友共享”按钮。在此过程中，浏览器将包含用户登录凭据的“朋友”cookies附加到“朋友”服务器请求。这允许朋友代表用户在其源中发布新闻文章，而无需登录。

这一切都可以通过使用第三方cookie实现。在这种情况下，第三方cookie保存在浏览器上， `platform.friends.com`以便代表 `platform.friends.com` 用户在“朋友”应用程序中发布帖子。

如果您想象一下如何在没有第三方cookie的情况下实现此用例，则用户必须执行大量手动步骤。首先，用户必须复制指向新闻文章的链接。其次，用户必须单独登录到Friends应用程序。然后，用户单击创建帖子按钮。然后，用户将复制并粘贴文本字段中的链接，最后单击“帖子”。正如您所看到的，第三方cookie极大地帮助用户体验，因为手动步骤可以大大减少。

更一般而言，第三方cookie使得数据存储在用户浏览器上，而不要求用户明确访问网站。

## 安全问题

尽管cookies增强了用户体验和强大的广告功能，但它们还引入了跨站点请求伪造(CSRF)攻击等安全漏洞。例如，如果用户登录到银行站点以支付信用卡账单并离开站点而不注销，然后在同一会话中浏览到恶意站点，则可能发生CSRF攻击。恶意站点可能包括向在加载页面时执行的银行站点发出请求的代码。由于用户仍可对银行站点进行身份验证，因此会话cookie可用于启动CSRF攻击，以从用户的银行帐户启动资金传输事件。这是因为每次访问站点时，都会在HTTP请求中附加所有Cookie。由于存在这些安全问题，Google现在正在尝试缓解它们。

## Target如何使用cookies？

通过所有这些说明，我们来看看 [!DNL Target] 如何使用cookies。为了供您首先使用 [!DNL Target] ，您需要在您的站点上安装 [!DNL Target] JavaScript库。这使您能够在访问站点的用户的浏览器上放置第一方cookie。当用户与您的网站交互时，您可以通过JavaScript库将用户的行为和 [!DNL Target] 兴趣数据传递给您。[!DNL Target] JavaScript库使用第一方cookie提取有关用户的标识信息以映射到用户的行为和兴趣数据。然后，此数据被 [!DNL Target] 用来支持您的个性化活动。

Target还(有时)使用第三方cookie。如果您拥有多个在不同域上实时访问的网站，并且希望跟踪跨这些网站的用户旅程，则可以利用跨域跟踪来使用第三方cookie。通过在 [!DNL Target] JavaScript库中启用跨域跟踪，您的帐户将开始使用第三方cookie。当用户从一个域跳转到另一个域时，浏览器与后端 [!DNL Target]服务器通信，在此过程中，创建第三方cookie并放在用户的浏览器上。通过用户浏览器上的第三方Cookie， [!DNL Target] 能够为单个用户提供跨不同域的一致体验。

## Google的新cookie食谱

要在跨站点发送cookies时提供保护，以便用户受保护，Google计划为称为saveSite的IEETF标准添加支持，这需要Web开发人员使用Set-Cookie标题中的sameSite属性组件来管理cookies。

可以将三个不同的值传递到 SameSite 属性：Strict、Lax 或 None。

| 值 | 描述 |
| --- | --- |
| Strict | 只有在访问最初设置的域时，才可访问具有此设置的 Cookie。换言之，Strict 会完全阻止跨站点使用 Cookie。此选项最适合需要高安全性(如银行)的应用程序。 |
| Lax | Cookies with this setting are sent only on same-site requests or top-level navigation with non-idempotent HTTP requests, like `HTTP GET`. 因此，如果第三方可使用Cookie，但又增加了安全益处，保护用户免受CSRF攻击侵害，则将使用此选项。 |
| None | 使用此设置的Cookies的工作方式与Cookies目前的工作方式相同。 |

请记住，Chrome80为用户引入了两个独立设置：“默认cookie的SaveSite”和“不带SaveSite的Cookie必须安全”。默认情况下，Chrome80中将启用这些设置。

![SaveSite对话框](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

* **默认Cookie SaveSite**：设置后，所有未指定saveSite属性的cookie将自动强制使用 `SameSite = Lax`。
* **不带SameSite的Cookie必须安全**：设置时，不带sameSite属性或 `SameSite = None` 需要Secure的cookies。在此上下文中，安全是指所有浏览器请求都必须遵循 HTTPS 协议。不符合此要求的 Cookie 将被拒绝。所有网站都应使用HTTPS来满足此要求。

## Target 遵循 Google 安全最佳实践

在Adobe，我们始终希望支持业界最新的安全和隐私最佳实践。We are happy to announce that [!DNL Target] supports the new security and privacy settings introduced by Google.

对于“按默认cookies站点站点” [!DNL Target] 设置，您将继续提供个性化，而不会受到您的任何影响和干预。[!DNL Target] 会使用第一方 Cookie，并在 Google Chrome 应用标记 `SameSite = Lax` 时继续正常运行。

对于“没有SaveSite的Cookie必须安全”选项，如果您不选择在中 [!DNL Target]加入跨域跟踪功能，则中 [!DNL Target] 的第一方cookie将继续有效。

However, when you opt-in to use cross-domain tracking to leverage [!DNL Target] across multiple domains, Chrome requires `SameSite = None` and Secure flags to be used for third-party cookies. 这意味着您必须确保站点使用HTTPS协议。中 [!DNL Target] 的客户端库将自动使用HTTPS协议并将 `SameSite = None` 和安全标记附加到中 [!DNL Target] 的第三方Cookie以确保所有活动继续提供。

## 您需要执行哪些操作？

要了解 [!DNL Target] 如何继续为Google Chrome80+用户工作，请参阅下表，其中将显示以下列：

* **目标JavaScript库**：如果您使用的是. js，请访问. js1。*x* 还是 at.js 2.*x* 在您的网站上。
* **默认cookies= Enabled SaveSite**：如果您的用户启用了“by default cookies”，则它对您有何影响，并且您需要为继续工作提供 [!DNL Target] 任何功能。
* **不带SaveSite的Cookie必须为secure= Enabled**：如果您的用户有“不带SaveSite的Cookies”启用，它会对您有何影响，它会对您 [!DNL Target] 有所影响。

| Target JavaScript库 | 默认为 Cookie 设置 SameSite = 已启用 | 不具有 SameSite 的 Cookie 必须是安全的 = 已启用 |
| --- | --- | --- |
| mbox. js with第一方cookie。 | 不受影响。 | 如果您未使用跨域跟踪，则无影响。 |
| mbox. js，启用跨域跟踪。 | 不受影响。 | 必须为站点启用HTTPS协议。<br>[!DNL Target] 使用第三方cookie跟踪用户，Google需要第三方Cookie拥有 `SameSite = None` 和安全标记。安全标志要求您的站点必须使用HTTPS协议。 |
| at.js 1.*x*&#x200B;使用第一方cookie。 | 不受影响。 | 如果您未使用跨域跟踪，则无影响。 |
| at.js 1.*x*&#x200B;启用跨域跟踪。 | 不受影响。 | 必须为站点启用HTTPS协议。<br>[!DNL Target] 使用第三方cookie跟踪用户，Google需要第三方Cookie拥有 `SameSite = None` 和安全标记。安全标志要求您的站点必须使用HTTPS协议。 |
| at.js 2.*x* | 不受影响。 | 不受影响。 |

## Target需要做什么？

因此，我们需要在我们的平台中做些什么来帮助您遵守新的Google Chrome80+ SAmeSite cookie策略？

| Target JavaScript库 | 默认为 Cookie 设置 SameSite = 已启用 | 不具有 SameSite 的 Cookie 必须是安全的 = 已启用 |
| --- | --- | --- |
| mbox. js with第一方cookie。 | 不受影响。 | 如果您未使用跨域跟踪，则无影响。 |
| mbox. js，启用跨域跟踪。 | 不受影响。 | [!DNL Target] 当调用服务器时，将标记添加 `SameSite = None` 到 [!DNL Target] 第三方cookie。 |
| at.js 1.*x*&#x200B;使用第一方cookie。 | 不受影响。 | 如果您未使用跨域跟踪，则无影响。 |
| at.js 1.*x*&#x200B;启用跨域跟踪。 | 不受影响。 | at.js 1.*x*&#x200B;启用跨域跟踪。 |
| at.js 2.*x* | 不受影响。 | 不受影响。 |

## 如果您不切换到使用HTTPS协议，会产生什么影响？

仅当您使用mbox. js或. js中 [!DNL Target] 的跨域跟踪功能时，才会影响您的用例。*x* 不支持跨域跟踪。如果不切换到Google的要求，您将看到不同域中的独特访客激增，因为Google将丢弃我们使用的第三方cookie。由于第三方cookie将被丢弃，当 [!DNL Target] 用户从一个域导航到另一个域时，将无法为该用户提供一致的个性化体验。第三方cookie主要用于识别单个用户在您拥有的域之间导航。

## 结论

随着行业竞相为消费者创建更加安全的Web， [!DNL Adobe] 我们绝对致力于帮助客户以确保最终用户安全和隐私的方式提供个性化体验。您只需遵循上述最佳做法，充分利用Google [!DNL Target] Chrome新的SaveSite Cookie策略。
