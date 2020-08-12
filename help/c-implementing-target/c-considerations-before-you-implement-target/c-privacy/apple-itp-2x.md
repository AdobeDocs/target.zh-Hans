---
keywords: apple;ITP;intelligent tracking prevention
description: 有关Adobe Target通过Experience CloudID(ECID)库4.3支持Apple ITP 2.x的信息。
title: Adobe Target 与 Apple ITP 支持
feature: null
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '887'
ht-degree: 52%

---


# Apple 智能防跟踪 (ITP) 2.x

智能防跟踪 (ITP) 是 Apple 推出的一项旨在保护 Safari 用户隐私的举措。第一版 ITP 于 2017 年发布，主要针对使用第三方 Cookie 的情况。事实上，Apple 完全阻止了第三方 Cookie，这反而给广告技术公司和营销技术公司造成严重的困扰，因为这些公司通常使用第三方 Cookie 来跟踪访客并收集访客数据。现在，Apple 正在对如何在 Safari 中使用第一方 Cookie 进行限制和约束。

这些版本的 ITP 包含以下限制：

| 版本 | 详细信息 |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | 对使用 `document.cookie` API 放到浏览器中的客户端 Cookie 设置上限，七天到期。<br>发布于 2019 年 2 月 21 日。 |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | 七天到期的上限大幅缩短为一天。<br>发布于 2019 年 4 月 24 日。 |
| [ITP 2.3](https://webkit.org/blog/9521/intelligent-tracking-prevention-2-3/) | 消除了几种解决办法，如使用localStorage或使用JavaScript `Document.referrer property`。<br>发布于2019年9月23日。 |

## What is the impact to me as an Adobe Target customer? {#impact}

[!DNL Target] 提供了 JavaScript 库可供您在页面上部署，以便 [!DNL Target] 能够为访客提供实时个性化。有三个 Target JavaScript 库（[at.js 1.x, at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md), and [mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)) that place client-side [!DNL Target] cookies on your visitors&#39; browsers via the `document.cookie` API. As a result, [!DNL Target] cookies are impacted by Apple’s ITP 2.x and will expire after seven days (with ITP 2.1) and after one day (with ITP 2.2 and ITP 2.3).

Apple ITP 2.x在以 [!DNL Target] 下方面影响：

| 影响 | 详细信息 |
| --- | --- |
| 潜在增加独特访客计数 | 由于过期窗口设置为七天（使用ITP 2.1）和一天（使用ITP 2.2和ITP 2.3），您可能会看到来自Safari浏览器的独特访客数量增加。 If your visitors revisit your domain after seven days (ITP 2.1) or one day (ITP 2.2 and ITP 2.3), [!DNL Target] is forced to place a new [!DNL Target] cookie on your domain in place of the expired cookie. 即便是同一用户，新 [!DNL Target] Cookie 仍会转换为新的独特访客。 |
| 缩短了 [!DNL Target] 活动的回溯期限 | [!DNL Target] 活动的访客配置文件可能会缩短决策的回溯期限。利用 [!DNL Target] Cookie 可识别访客和存储用于个性化的用户配置文件属性。Given that [!DNL Target] cookies can be expired on Safari after seven days (ITP 2.1) or one day (ITP 2.2 and 2.3), the user profile data that was tied to the purged [!DNL Target] cookie cannot be used for decisioning. |
| 用户档案基于3rdPartyID的脚本 | 由于过期窗口设置为七天（使用ITP 2.1）和一天（使用ITP 2.2和ITP 2.3），基于第 [三方](/help/c-target/c-visitor-profile/profile-parameters.md) ID cookie的用户档案脚本将在过期时停止工作。 |
| iOS设备中的QA/预览URL | 由于过期窗口设置为七天（使用ITP 2.1）和一天（使用ITP 2.2和ITP 2.3）, [QA/预览URL](/help/c-activities/c-activity-qa/activity-qa.md) 将在过期时停止工作，因为URL基于第三方ID cookie。 |

## 我当前已实施的 [!DNL Target] 是否会受到影响？

在 Safari 浏览器中，导航到您拥有 [!DNL Target] JavaScript 库的网站。If you see a [!DNL Target] cookie set in the context of a CNAME, such as `analytics.company.com`, then you are not impacted by ITP 2.x.

如果除了 Target JavaScript 库之外，您还在使用 Experience Cloud ID (ECID) 库，则您的实施会受到下文所述的影响：[Safari ITP 2.1 对 Adobe Experience Cloud 和 Experience Platform 客户的影响](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)。

## 如何减轻未来ITP 2.x版本对目标的影响？

要减轻未来ITP 2.x版本对目标的影响，请完成以下任务:

1. 将 Experience Cloud ID (ECID) 库部署到您的页面。

   ECID 库可为 Experience Cloud Core 解决方案启用人员识别框架。通过分配永久和唯一标识符，ECID 库让您能够识别不同 Experience Cloud 解决方案中的相同站点访客及其数据。ECID 库将经常更新，以帮助您减轻 ITP 相关更改对您的实施的影响。

   对于ITP 2.x, [必须使用ECID库4.](https://docs.adobe.com/content/help/en/id-service/using/release-notes/release-notes.html) 3.0+进行缓解。

1. 使用 Adobe CNAME 并注册 Adobe Analytics 托管证书计划。

   安装 ECID 库 4.3.0+ 之后，您可以使用 Adobe Analytics CNAME 和托管证书计划。这项计划允许您免费为第一方 Cookie 实施第一方证书。Leveraging CNAME will help [!DNL Target] customers mitigate the impact of ITP 2.x.

   If you are not leveraging CNAME, you can start the process by talking with your account representative and enrolling in the [Adobe Managed Certificate Program](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program).

在您部署 Target JavaScript 库和 ECID 库 v4.3.0+ 并注册 Adobe 托管证书计划来使用 CNAME 之后，您将获得一个强大且长期的可减轻 ITP 相关更改对您影响的计划。

当整个行业都在努力为消费者创建更加安全的 Web 时，[!DNL Adobe Target] 也不遗余力地为客户提供个性化体验，同时满足甚至超越访客的隐私保护期望。[!DNL Adobe Target] 除了支持Apple的 [ITP 2.x外](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) ，还已宣布支持Google的SameSite Chrome策略。

由于政策不断发展以保护我们的消费者，[!DNL Adobe] 也将继续在 [!DNL Target] 中支持这些举措，并将帮助我们的客户提供一流的个性化体验。
