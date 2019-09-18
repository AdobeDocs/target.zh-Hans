---
description: 有关通过Experience Cloud ID(ECID)库4.3实现Apple ITP 2.1和ITP 2.2的Target支持的信息。
keywords: apple;ITP；智能跟踪防范
seo-description: 通过Experience Cloud ID(ECID)库4.3了解Adobe Target对Apple ITP 2.1和ITP 2.2的支持信息。
seo-title: Adobe Target和Apple ITP支持
solution: Target
subtopic: 入门指南
title: Apple ITP 2.x
topic: Standard
translation-type: tm+mt
source-git-commit: 8dc94ca1ed48366e6b3ac7a75b03c214f1db71d9

---


# Apple Intelligent Tracking Prevention(ITP)2.x

Intelligent Tracking Prevention(ITP)是Apple保护Safari用户隐私的举措。 2017年发布的ITP第一个版本针对第三方cookie的使用。 事实上，Apple阻止了第三方Cookie的整体，这反过来又给广告科技和科技公司带来了严重的麻烦，因为第三方Cookie通常用于跟踪访客和收集访客数据。 现在，Apple正在对在Safari中使用第一方Cookie的方式设置限制和限制。

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

   ECID库支持Experience Cloud核心解决方案的人员识别框架。 ECID库允许您通过分配永久和唯一标识符来识别不同Experience cloud解决方案中的同一站点访客及其数据。 ECID库将经常更新，以帮助您减轻影响实施的任何与ITP相关的更改。

   对于ITP 2.1和ITP 2.2, [ECID库4.3.0+必须用于缓解](https://docs.adobe.com/content/help/en/id-service/using/release-notes/release-notes.html) 。

1. 使用Adobe的CNAME并登记Adobe Analytics的托管证书计划。

   安装ECID库4.3.0+后，您可以利用Adobe Analytics的CNAME和托管证书程序。 此程序允许您免费为第一方Cookie实施第一方证书。 利用CNAME将帮 [!DNL Target] 助客户减轻ITP 2.1和ITP 2.2的影响。

   如果您没有利用CNAME，则可以通过与客户代表交谈并登记 [Adobe托管证书计划来开始该过程](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program)。

在将Target javaScript库与ECID库v4.3.0+一起部署并注册Adobe托管证书计划以利用CNAME后，您将拥有一个强大且长期的缓解计划来缓解与ITP相关的更改。

As the industry makes strides to create a more secure web for consumers, [!DNL Adobe Target] is absolutely committed to delivering personalized experiences while meeting and exceeding the privacy expectations of visitors. [!DNL Adobe Target] 除了支持 [Apple的ITP 2.1和ITP 2.2外，还已宣布支持Google的SameSite Chrome策略](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) 。

随着政策不断演变以保护我们的消费者， [!DNL Adobe] 我们还将继续支持这些举措 [!DNL Target]，同时帮助客户提供一流的个性化体验。
