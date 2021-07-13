---
keywords: google;samesite;cookie;chrome 80;ietf
description: 了解Adobe [!DNL Target] 如何处理随Google Chrome版本80引入的SameSite IETF标准，以及您需要执行哪些操作来遵守这些策略。
title: ' [!DNL Target] 如何处理Google的Samesite Cookie策略？'
feature: 隐私和安全
role: Developer
exl-id: 5abd2065-3692-4a6d-9ac9-6d416604c2d2
source-git-commit: 3c79b2ce70e456275ddf6774a35ae5c36f0ae99d
workflow-type: tm+mt
source-wordcount: '1950'
ht-degree: 7%

---

# Google Chrome SameSite Cookie 策略

Google将开始为从Chrome 80开始的用户默认实施新的Cookie策略，该版本计划于2020年初发布。 本文介绍您需要了解的有关新的SameSite Cookie策略、[!DNL Adobe Target]如何支持这些策略，以及如何使用[!DNL Target]符合Google Chrome的新SameSite Cookie策略的所有信息。

从Chrome 80开始，Web开发人员必须明确指定哪些Cookie可以跨网站运行。 这是谷歌计划为提高网络隐私和安全性而发布的众多公告中的第一个。

鉴于Facebook在隐私和安全方面一直处于热门位置，苹果等其他主要参与者，现在又是谷歌，已经迅速抓住机会，创造新的身份，成为隐私和安全保护的捍卫者。 Apple率先于今年初通过ITP 2.1和最近通过ITP 2.2宣布更改其Cookie政策。在ITP 2.1中，Apple完全阻止第三方Cookie，并仅将浏览器上创建的Cookie保存七天。 在ITP 2.2中，Cookie仅保留一天。 谷歌的声明远没有苹果那么激进，但这是朝着同一目标迈出的第一步。 有关Apple策略的更多信息，请参阅[Apple智能防跟踪(ITP)2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)。

## 什么是Cookie？如何使用它们？

在深入研究Google对其Cookie策略的更改之前，让我们先了解Cookie是什么以及它们的使用方式。 简而言之，Cookie是存储在Web浏览器中用于记住用户属性的小文本文件。

Cookie非常重要，因为它们可增强用户在Web上浏览时的体验。 例如，如果您在电子商务网站上购物，并向购物车中添加商品，但未在该访问中登录或购买，则Cookie会记住您的商品并将它们保存在您的购物车中，以供您下次访问。 或者，想象一下，如果每次访问您喜爱的社交媒体网站时都被迫重新输入您的用户名和密码。 Cookie也可以解决此问题，因为它们存储有助于网站识别您身份的信息。 这类Cookie称为第一方Cookie，因为它们是由您访问的网站创建和使用的。

第三方Cookie也存在。 为了更好地理解它们，我们考虑以下示例：

假设一家名为“好友”的社交媒体公司提供了一个“共享”按钮，其他网站将实施该按钮，以便“好友”用户能够在“好友”动态消息中共享该网站的内容。 现在，用户在使用“共享”按钮的新闻网站上阅读一篇新闻文章，并点击该文章以自动在其“好友”帐户上发布。

为了实现此目的，浏览器在加载新闻文章时会从`platform.friends.com`中获取“好友共享”按钮。 在此过程中，浏览器将包含用户登录凭据的好友Cookie附加到好友服务器的请求中。 这样，好友就可以代表用户在其动态消息中发布新闻文章，而无需用户登录。

使用第三方Cookie可实现上述所有操作。 在这种情况下，第三方Cookie会保存在`platform.friends.com`的浏览器中，以便`platform.friends.com`可以代表用户在朋友应用程序中发布帖子。

如果您想象一下，如何在不使用第三方Cookie的情况下实现此用例，用户将必须执行大量手动步骤。 首先，用户必须复制指向新闻文章的链接。 其次，用户必须单独登录“好友”应用程序。 然后，用户将单击创建帖子按钮。 然后，用户将该链接复制并粘贴到文本字段中，最后单击“帖子”。 如您所见，第三方Cookie可以极大地减少手动步骤对用户体验的影响。

更一般地说，第三方Cookie使数据存储在用户的浏览器上，而无需用户明确访问网站。

## 安全问题

尽管Cookie可增强用户体验和强大广告功能，但它们也可能会引入诸如跨站点请求伪造(CSRF)攻击等安全漏洞。 例如，如果用户登录银行网站支付信用卡账单，然后离开网站而不注销，然后浏览到同一会话中的恶意网站，则可能会发生CSRF攻击。 恶意网站可能包含向银行网站发出请求的代码，该银行网站在页面加载时执行。 由于用户仍然已通过银行网站的身份验证，因此会话Cookie可用于启动CSRF攻击，以从用户的银行帐户发起资金转移事件。 这是因为每当您访问网站时，所有Cookie都会在HTTP请求中附加。 由于这些安全问题，谷歌现在正在尝试缓解这些问题。

## [!DNL Target]如何使用Cookie?

尽管如此，让我们看看[!DNL Target]如何使用Cookie。 首先，要使用[!DNL Target]，您需要在网站上安装[!DNL Target] JavaScript库。 这样，您就可以在访问您网站的用户的浏览器上放置第一方Cookie。 当用户与您的网站交互时，您可以通过JavaScript库将用户的行为和兴趣数据传递到[!DNL Target]。 [!DNL Target] JavaScript库使用第一方Cookie提取有关要映射到用户行为和兴趣数据的用户的标识信息。 然后，[!DNL Target]会使用此数据来支持您的个性化活动。

Target还（有时）使用第三方Cookie。 如果您拥有多个位于不同域的网站，并且希望跟踪这些网站中的用户历程，则可以利用跨域跟踪来使用第三方Cookie。 通过在[!DNL Target] JavaScript库中启用跨域跟踪，您的帐户将开始使用第三方Cookie。 当用户从一个域跳到另一个域时，浏览器会与[!DNL Target]的后端服务器进行通信，在此过程中，会创建第三方Cookie并将其放置在用户的浏览器上。 通过用户浏览器上的第三方Cookie，[!DNL Target]能够为单个用户跨不同域提供一致的体验。

## 谷歌新Cookie方法

为了在跨站点发送Cookie时提供安全保护以保护用户，Google计划添加对名为SameSite的IETF标准的支持，该标准要求Web开发人员在Set-Cookie标头中使用SameSite属性组件管理Cookie。

可以将三个不同的值传递到 SameSite 属性：Strict、Lax 或 None。

| 值 | 描述 |
| --- | --- |
| Strict | 只有在访问最初设置的域时，才可访问具有此设置的 Cookie。换言之，Strict 会完全阻止跨站点使用 Cookie。此选项最适用于需要高安全性的应用程序，如银行。 |
| Lax | 具有此设置的Cookie仅在同一站点请求或具有非幂等HTTP请求（如`HTTP GET`）的顶级导航上发送。 因此，如果Cookie可供第三方使用，则将使用此选项，此选项可提供附加的安全性，保护用户免受CSRF攻击。 |
| None | 具有此设置的Cookie的工作方式与当今Cookie的工作方式相同。 |

请记住，Chrome 80为用户引入了两个独立设置：&quot;默认为Cookie设置SameSite&quot;和&quot;不具有SameSite的Cookie必须是安全的。&quot; 这些设置将在Chrome 80中默认启用。

![“SameSite”对话框](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

* **默认为Cookie设置SameSite**:设置后，所有未指定SameSite属性的Cookie将自动强制使用 `SameSite = Lax`。
* **不具有SameSite的Cookie必须是安全的**:设置后，不具有SameSite属性或具有的Cookie `SameSite = None` 需要是安全的。在此上下文中，安全是指所有浏览器请求都必须遵循 HTTPS 协议。不符合此要求的 Cookie 将被拒绝。所有网站都应使用HTTPS来满足此要求。

## Target 遵循 Google 安全最佳实践

Adobe时，我们始终希望支持业界在安全和隐私方面的最新最佳实践。 我们很高兴地宣布[!DNL Target]支持Google引入的新安全和隐私设置。

对于“默认为Cookie设置SameSite”设置，[!DNL Target]将继续提供个性化，而不会受到您的任何影响和干预。 [!DNL Target] 会使用第一方 Cookie，并在 Google Chrome 应用标记 `SameSite = Lax` 时继续正常运行。

对于“不具有SameSite的Cookie必须是安全的”选项，如果您未选择加入[!DNL Target]中的跨域跟踪功能，则[!DNL Target]中的第一方Cookie将继续工作。

但是，如果您选择使用跨域跟踪在多个域中利用[!DNL Target]，则Chrome需要`SameSite = None`和用于第三方Cookie的安全标记。 这意味着您必须确保您的站点使用HTTPS协议。 [!DNL Target]中的客户端库将自动使用HTTPS协议，并将`SameSite = None`和安全标记附加到[!DNL Target]中的第三方Cookie，以确保继续交付所有活动。

## 您需要执行哪些操作？

要了解您需要执行哪些操作来使[!DNL Target]继续适用于Google Chrome 80及更高版本的用户，请参阅下表，您将看到其中的以下列：

* **Target JavaScript库**:如果您使用的是at.js 1.** xor at.js 2.** 访问您的网站。
* **默认为Cookie设置SameSite =已启用**:如果您的用户启用了“默认为Cookie设置SameSite”，那么这对您有何影响，您需要执行哪些操作才 [!DNL Target] 能继续工作。
* **不具有SameSite的Cookie必须是安全的=已启用**:如果您的用户启用了“不具有SameSite的Cookie必须是安全的”，那么这对您有何影响，您需要执行哪些操作才能继 [!DNL Target] 续工作。

| Target JavaScript库 | 默认为 Cookie 设置 SameSite = 已启用 | 不具有 SameSite 的 Cookie 必须是安全的 = 已启用 |
| --- | --- | --- |
| at.js 1.*x* 使用第一方Cookie。 | 没有影响。 | 如果您没有使用跨域跟踪，则不会受到影响。 |
| at.js 1.*x* 启用跨域跟踪。 | 没有影响。 | 您必须为站点启用HTTPS协议。<br>[!DNL Target] 使用第三方Cookie来跟踪用户，而Google要求第三方Cookie具有和安 `SameSite = None` 全标记。安全标记要求您的站点必须使用HTTPS协议。 |
| at.js 2.*x* | 没有影响。 | 没有影响。 |

## [!DNL Target]需要执行哪些操作？

那么，我们需要在我们的平台中执行哪些操作来帮助您遵守新的Google Chrome 80及更高版本SameSite Cookie策略？

| Target JavaScript库 | 默认为 Cookie 设置 SameSite = 已启用 | 不具有 SameSite 的 Cookie 必须是安全的 = 已启用 |
| --- | --- | --- |
| at.js 1.*x* 使用第一方Cookie。 | 没有影响。 | 如果您没有使用跨域跟踪，则不会受到影响。 |
| at.js 1.*x* 启用跨域跟踪。 | 没有影响。 | at.js 1.*x* 启用跨域跟踪。 |
| at.js 2.*x* | 没有影响。 | 没有影响。 |

## 如果您不使用HTTPS协议迁移到，会产生什么影响？

影响您的唯一用例是，如果您使用[!DNL Target]中的跨域跟踪功能，但使用的是at.js 1.*x* 中不再对跨域跟踪提供开箱即用支持。如果不迁移到HTTPS（这是Google的一项要求），您将看到跨域的独特访客数量会激增，因为Google会丢弃我们使用的第三方Cookie。 而且，由于将删除第三方Cookie，因此当用户从一个域导航到另一个域时，[!DNL Target]将无法为该用户提供一致的个性化体验。 第三方Cookie主要用于识别在您拥有的域中导航的单个用户。

## 结论

当整个行业都在努力为消费者创建更加安全的Web时，[!DNL Adobe]将不遗余力地帮助客户以确保最终用户安全和隐私的方式提供个性化体验。 您只需遵循上述最佳实践并利用[!DNL Target]遵守Google Chrome的新SameSite Cookie策略即可。
