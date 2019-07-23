---
description: 有关通过Experience Cloud ID(ECID)库4.3对Apple的ITP2.1和ITP2.2支持的信息。
keywords: Apple；ITP；智能跟踪预防
seo-description: 有关通过Experience Cloud ID(ECID)库4.3对Apple的ITP2.1和ITP2.2提供Adobe Target支持的信息。
seo-title: Adobe Target和Apple ITP支持
solution: Target
subtopic: 入门指南
title: Apple IDP2.x
topic: Standard
translation-type: tm+mt
source-git-commit: 71419ee6053eeb86ab6595cfba2f05d8506e05b3

---


# Apple智能跟踪预防(ITP)2.x

智能跟踪预防(ITP)是Apple保护Safari用户隐私的举措。ITP的第一个版本是2017年，它目标是使用第三方cookie。事实上，Apple被阻止的第三方cookies完全为广告技术和科技公司造成了严重头疼，因为第三方Cookie通常用于跟踪访客和收集访客数据。现在，Apple开始对Safari中使用第一方Cookie的方式施加限制和限制。

这些版本的ITP包括以下限制：

| 版本 | 详细信息 |
| --- | --- |
| [ITP2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | Capped client-side cookies that are placed on the browser using the `document.cookie` API to a seven-day expiry.<br>发布于2019年月21日。 |
| [ITP2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | 大幅缩短了七天的到期上限。<br>发布时间：2019年月24日。 |

## 作为Adobe Target客户，对我有何影响？

[!DNL Target] 提供JavaScript库，以便在页面上部署 [!DNL Target] ，从而为访客提供实时个性化。There are three Target JavaScript libraries ([at.js 1.*x*&#x200B;和at. js2。*x*](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)和 [mbox. js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md))通过API将客户端 [!DNL Target] Cookie放置到访客浏览器 `document.cookie` 上。[!DNL Target] 因此，cookies受Apple的ITP2.1和2.2影响，将在七天后(借助ITP2.1)和一天后(使用ITP2.2)过期。

Apple ITP 2.1 and 2.1 impact [!DNL Target] in the following areas:

| 影响 | 详细信息 |
| --- | --- |
| 独特访客计数的潜在增加 | 由于过期窗口设置为七天(使用ITP2.1)和一天(借助ITP2.2)，您可能会看到来自Safari浏览器的独特访客数量增加。If your visitors revisit your domain after seven days (ITP 2.1) or one day (ITP 2.2), [!DNL Target] is forced to place a new [!DNL Target] cookie on your domain in place of the expired cookie. The new [!DNL Target] cookie translates to a new unique visitor even though the user is the same. |
| Decreased lookback periods for [!DNL Target] activities | [!DNL Target] 针对活动的访客配置文件的决策期限可能较缩短。[!DNL Target] 利用cookies识别访客并存储用户个人资料属性以供个性化。Given that [!DNL Target] cookies can be expired on Safari after seven days (ITP 2.1) or one day (ITP 2.2), the user profile data that was tied to the purged [!DNL Target] cookie cannot be used for decisioning. |

## Is my current implementation of [!DNL Target] impacted?

In a Safari browser, navigate to your website on which you have a [!DNL Target] JavaScript library. If you see a [!DNL Target] cookie set in the context of a CNAME, such as `analytics.company.com`, then you are not impacted by ITP 2.1 or 2.2.

If you are using the Experience Cloud ID (ECID) library in addition to the Target JavaScript library, your implementation will be impacted in the ways listed in this article: [Safari ITP 2.1 Impact on Adobe Experience Cloud and Experience Platform Customers](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac).

## How can I mitigate the impact of ITP 2.1, ITP 2.2, and future ITP releases to [!DNL Target]?

To mitigate the impact of ITP 2.1, ITP 2.2, and future ITP releases to [!DNL Target], complete the following tasks:

1. 将Experience Cloud ID(EID)库部署到您的页面。

   EID库支持Experience Cloud核心解决方案的人员识别框架。EID库允许您通过分配永久和唯一标识符，在不同的Experience Cloud解决方案中识别相同的站点访客及其数据。将经常更新ECID库以帮助您减轻影响实施的任何与ITP相关的更改。

   For ITP 2.1 and ITP 2.2, [ECID library 4.3.0+](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) must be utilized for mitigation.

1. 使用Adobe的CNAME和注册Adobe Analytics的Managed Certificate Program。

   安装ECID库4.3.0+之后，您可以利用Adobe Analytics的CNAME和Managed Certificate Program。此计划允许您免费为第一方Cookie实施一个第三方证书。Leveraging CNAME will help [!DNL Target] customers mitigate the impact of ITP 2.1 and ITP 2.2.

   If you are not leveraging CNAME, you can start the process by talking with your account representative and enrolling in the [Adobe Managed Certificate Program](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html).

在您将Target JavaScript库与ECID库v4.3.0+一起部署并加入Adobe Managed Certificate Program以利用CNAME后，您将拥有一个强大的长期缓解计划，用于与ITP相关的更改。

As the industry makes strides to create a more secure web for consumers, [!DNL Adobe Target] is absolutely committed to delivering personalized experiences while meeting and exceeding the privacy expectations of visitors. [!DNL Adobe Target] 除了支持Apple的ITP2.1和ITP2.2之外，已经宣布支持 [Google的saveSite Chrome策略](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) 。

As policies continue to evolve to protect our consumers, [!DNL Adobe] will also continue to support these initiatives in [!DNL Target], while helping our customers provide the best-in-class personalized experiences.
