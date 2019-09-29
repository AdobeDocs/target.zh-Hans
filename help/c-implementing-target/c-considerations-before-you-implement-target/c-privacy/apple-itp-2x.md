---
description: 有关通过Experience Cloud ID(ECID)库4.3实现Apple ITP 2.1和ITP 2.2的Target支持的信息。
keywords: apple;ITP;intelligent tracking prevention
seo-description: 通过Experience Cloud ID(ECID)库4.3了解Adobe Target对Apple ITP 2.1和ITP 2.2的支持信息。
seo-title: Adobe Target and Apple ITP support
solution: Target
subtopic: 入门指南
title: Apple ITP 2.x
topic: Standard
translation-type: tm+mt
source-git-commit: 8dc94ca1ed48366e6b3ac7a75b03c214f1db71d9

---


# Apple Intelligent Tracking Prevention (ITP) 2.x

Intelligent Tracking Prevention(ITP)是Apple保护Safari用户隐私的举措。 The first release of ITP, which was in 2017, targeted the usage of third-party cookies. In fact, Apple blocked third-party cookies entirety, which in turn, caused a severe headache for ad tech and mar tech companies because third-party cookies are generally used for tracking visitors and collecting visitor data. Now, Apple is on the move to place limitations and restrictions on how first-party cookies are used within Safari.

这些版本的ITP包含以下限制：

| 版本 | 详细信息 |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | 使用API放置到浏览器上的客户端Cookie `document.cookie` 有上限，到期七天。<br>发布于2019年2月21日。 |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | 将七天期限的上限大幅削减为一天。<br>发布于2019年4月24日。 |

## 作为Adobe target客户，对我有何影响？

[!DNL Target] 提供JavaScript库，供您在页面上部署， [!DNL Target] 以便为访客提供实时个性化。 有三个Target javaScript库([at.js 1.*x*&#x200B;和at.js 2。*x*](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)和 [mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md))，它们通过 [!DNL Target] API将客户端Cookie放置到访客的浏览器 `document.cookie` 上。 因此， [!DNL Target] cookie受Apple的ITP 2.1和2.2影响，将在七天后（使用ITP 2.1）和一天后（使用ITP 2.2）过期。

Apple ITP 2.1和2.1在以下 [!DNL Target] 方面有影响：

| 影响 | 详细信息 |
| --- | --- |
| 唯一访客计数的潜在增加 | 由于过期窗口设置为七天（使用ITP 2.1）和一天（使用ITP 2.2），您可能会看到来自Safari浏览器的独特访客数量增加。 如果访客在七天(ITP 2.1)或一天(ITP 2.2)后重新访问您的域，则 [!DNL Target] 将强制在您的域上放置新 [!DNL Target] Cookie来代替过期的Cookie。 新的 [!DNL Target] Cookie将转换为新的唯一访客，即使用户相同。 |
| 活动的回顾时间缩 [!DNL Target] 短 | 活动的访客 [!DNL Target] 资料可能会缩短决策回顾期。 [!DNL Target] cookies用于标识访客和存储用户配置文件属性以进行个性化。 由于 [!DNL Target] Cookies可在七天(ITP 2.1)或一天(ITP 2.2)后在Safari上过期，因此无法使用与清除的 [!DNL Target] Cookie关联的用户配置文件数据进行决策。 |

## 我的当前实施是否受 [!DNL Target] 影响？

在Safari浏览器中，导航到您拥有JavaScript库的 [!DNL Target] 网站。 如果您在CNAME [!DNL Target] 的上下文中看到设置的Cookie，例如 `analytics.company.com`，则您不会受到ITP 2.1或2.2的影响。

如果您除了使用Target javaScript库之外还使用Experience Cloud ID(ECID)库，则您的实施将受本文中列出的方式的影响： [Safari ITP 2.1对Adobe Experience cloud和Experience platform客户的影响](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)。

## 如何减轻ITP 2.1、ITP 2.2和未来ITP版本对的影响 [!DNL Target]?

要减轻ITP 2.1、ITP 2.2和未来ITP版本对以下任务的影 [!DNL Target]响，请执行以下任务：

1. 将Experience Cloud ID(ECID)库部署到您的页面。

   ECID库支持Experience Cloud核心解决方案的人员识别框架。 The ECID library allows you to identify same site visitors and their data in different Experience Cloud solutions by assigning persistent and unique identifiers. The ECID library will be updated frequently to help you mitigate any ITP-related changes that impact your implementation.

   For ITP 2.1 and ITP 2.2, ECID library 4.3.0+ must be utilized for mitigation.[](https://docs.adobe.com/content/help/en/id-service/using/release-notes/release-notes.html)

1. Use Adobe’s CNAME and Enroll in Adobe Analytics' Managed Certificate Program.

   After installing the ECID library 4.3.0+, you can leverage Adobe Analytics' CNAME and Managed Certificate Program. This program lets you implement a first-party certificate for first-party cookies at no charge. Leveraging CNAME will help  customers mitigate the impact of ITP 2.1 and ITP 2.2.[!DNL Target]

   If you are not leveraging CNAME, you can start the process by talking with your account representative and enrolling in the Adobe Managed Certificate Program.[](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program)

After you deploy a Target JavaScript library in conjunction with the ECID library v4.3.0+ and enroll in the Adobe Managed Certificate Program to leverage CNAME, you will have a robust and long-term mitigation plan for ITP-related changes.

As the industry makes strides to create a more secure web for consumers, [!DNL Adobe Target] is absolutely committed to delivering personalized experiences while meeting and exceeding the privacy expectations of visitors. [!DNL Adobe Target] has already announced support for Google’s SameSite Chrome Policies in addition to support for Apple’s ITP 2.1 and ITP 2.2.[](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md)

随着政策不断演变以保护我们的消费者， [!DNL Adobe] 我们还将继续支持这些举措 [!DNL Target]，同时帮助客户提供一流的个性化体验。
