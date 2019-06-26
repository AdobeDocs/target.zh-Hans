---
description: 有关Target和SaveSite IETF标准的信息，从Google Chrome76版本开始。
keywords: Google；samesite
seo-description: 有关Adobe Target和随Google Chrome版本76引入的SaveSite IETF标准的信息。
seo-title: Adobe Target和SaveSite Cookie策略
solution: Target
subtopic: 入门指南
title: Google Chrome SameSite Cookie策略
topic: Standard
uuid: aaeda1e6-7b2c-4a00-b65d-bfc95ea796b5
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Google Chrome SameSite Cookie策略

Google最近宣布从Chrome76(对于2019年月30日发行)开始，开发人员必须明确指定哪些cookie可以跨网站工作以及哪些cookie可以跟踪用户。

## SameSite概述

为了在跨站点发送cookies时提供保护，以便用户受到保护，Google增加了对Google Chrome76(及更高版本)中称为“SaveSite”的IEETF标准的支持。SameSite requires web developers to manage cookies with the SameSite attribute component in the `Set-Cookie` header.

可以将三个不同的值传递到sameSite属性中：Strict、lax或None。

| 值 | 描述 |
| --- | --- |
| Strict | 只有在访问最初设置此设置的域时，才可以访问此设置。换言之，Strict完全阻止cookie跨站点使用。此选项最适合需要高安全性(如银行)的应用程序。 |
| Lax | Cookies with this setting are sent only on same-site requests or top-level navigation with non-idempotent HTTP requests, such as `HTTP GET`. Therefore, this option should be used if the cookie can be used by third-parties, but with an added security benefit that protects users from being victimized by [CSRF](https://en.wikipedia.org/wiki/Cross-site_request_forgery) (Cross-Site Request Forgery) attacks. |
| 无 | 使用此设置的Cookies的工作方式与Cookies目前工作相同。 |

请记住，Chrome76(及更高版本)引入了两个设置：“默认cookie的SaveSite”和“不带SaveSite的Cookie必须安全”。用户可以启用设置或同时启用这两个设置。

| 设置 | 描述 |
| --- | --- |
| SaveSite by default cookies | When set, all cookies that don&#39;t specify the SameSite attribute are automatically forced with `SameSite = Lax`. |
| 不带SameSite的Cookie必须安全 | When set, cookies without the SameSite attribute or with `SameSite = None`, must be Secure. 此上下文中的安全意味着所有浏览器请求必须遵循HTTPS协议。不符合此要求的Cookies被拒绝。 |

![SaveSite设置页面](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

## Target遵循Google的安全最佳做法

通过Target，我们希望通过始终支持业界最新的安全最佳实践来确保您获得成功。我们很高兴地宣布Target支持Google Chrome76中引入的新安全设置。

当访客开启“默认cookies设置”时，Target继续提供个性化，而不会影响您的任何影响。Target uses first-party cookies and will continue to function properly as the flag `SameSite = Lax` is applied by Google Chrome.

当访客启用“不带SaveSite的Cookie必须是安全的”时，您不会选择加入Target的跨域跟踪功能，Target的第一方Cookie将继续有效。However, when you opt-in to using cross-domain tracking to leverage Target across multiple domains, Google Chrome 76 (and later) requires `SameSite = None` and `Secure` flags to be used for third-party cookies. 这意味着您必须确保站点使用HTTPS协议。Target&#39;s client-side libraries automatically use the HTTPS protocol and, in addition to that, attach the `SameSite = None` and `Secure` flags to Target’s third-party cookie to ensure all activities continue to deliver.

## 您需要做什么？

查看下表，了解如何让Target继续为Google Chrome76+用户工作。

表包含以下列：

* **目标客户端库**：无论您使用的是mbox. js，at. js1。*x*或at. js2。*站点上的x以及* Google Chrome设置对您的影响
* **默认cookies= Enabled SaveSite**：如果您的访客在Chrome76+上启用了“saveSite by default cookies”，则它会对您有何影响，并且您需要执行任何操作才能让Target继续工作
* **不带SaveSite的Cookie必须为secure= Enabled**：如果您的访客拥有Chrome76+上启用的“不带SaveSite的Cookie”，它会对您产生何种影响，并且您需要执行任何操作才能让Target继续工作
* **Adobe Target的跨域跟踪=已启用**：如果您的访客启用了“by default cookies”启用的“Same Site”和“cookies with saveSite”，则Chrome76+上启用了“Target”，并且您正在使用Target进行跨域跟踪，它会对您有何影响，并且您是否有必要让Target继续工作

| 目标客户端库 | saveSite by default cookies= Enabled | 没有SaveSite的Cookie必须为secure= Enabled | Adobe Target的跨域跟踪=已启用 |
| --- | --- | --- | --- |
| mbox.js | 没有影响，因为mbox. js使用第一方cookie | 没有影响，因为客户没有使用跨域跟踪 | 客户必须为其站点启用HTTPS协议。<br>Target使用第三方cookie跟踪用户，Google需要第三方Cookie， `SameSite = None` 并让站点使用HTTPS协议。 |
| at.js 1.*x* | 没有影响，因为在. js1。*x* 使用第一方cookie | 没有影响，因为客户没有使用跨域跟踪 | 客户必须为其站点启用HTTPS协议。<br>Target使用第三方Cookie跟踪用户，Google需要第三方Cookie， `SameSite = None` 并且站点使用HTTPS协议 |
| at.js 2.*x* | 没有影响，因为在. js2。*x* 使用第一方cookie | 没有影响，因为客户没有使用跨域跟踪 | 在. js中不支持跨域跟踪。*x* 并且因此，对客户没有影响 |

## Adobe需要做什么？

| 目标客户端库 | saveSite by default cookies= Enabled | 没有SaveSite的Cookie必须为secure= Enabled | Adobe Target的跨域跟踪=已启用 |
| --- | --- | --- | --- |
| mbox.js | 没有影响，因为mbox. js使用第一方cookie | 没有影响，因为客户没有使用跨域跟踪 | Target adds `SameSite = None` and `Secure` flag to third-party cookie when the Target backend is called. |
| at.js 1.*x* | 没有影响，因为在. js1。*x* 使用第一方cookie | 没有影响，因为客户没有使用跨域跟踪 | Target adds `SameSite = None` and `Secure` flag to third-party cookie when the Target backend is called. |
| at.js 2.*x* | 没有影响，因为在. js2。*x* 使用第一方cookie | 没有影响，因为客户没有使用跨域跟踪 | 在. js中不支持跨域跟踪。*x* |

## 结论

随着行业努力为消费者创建更加安全的Web，Target绝对致力于在会议期间提供个性化体验并超越访客的隐私期望。
