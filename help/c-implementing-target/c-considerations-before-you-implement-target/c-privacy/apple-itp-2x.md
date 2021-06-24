---
keywords: Apple;ITP；智能防跟踪；Experience Cloud ID;ECID
description: 了解Adobe [!DNL Target] 以及Apple智能防跟踪(ITP)计划（旨在保护Safari用户隐私）的影响。
title: ' [!DNL Target] 如何处理Apple ITP支持？'
feature: 隐私和安全
role: Developer
exl-id: 05a62be5-ccfb-4d5c-b511-35023b95e567
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '910'
ht-degree: 52%

---

# Apple 智能防跟踪 (ITP) 2.x

有关[!DNL Adobe Target]通过Experience CloudID(ECID)库4.3支持Apple ITP 2.x的信息。

智能防跟踪 (ITP) 是 Apple 推出的一项旨在保护 Safari 用户隐私的举措。第一版 ITP 于 2017 年发布，主要针对使用第三方 Cookie 的情况。事实上，Apple 完全阻止了第三方 Cookie，这反而给广告技术公司和营销技术公司造成严重的困扰，因为这些公司通常使用第三方 Cookie 来跟踪访客并收集访客数据。现在，Apple 正在对如何在 Safari 中使用第一方 Cookie 进行限制和约束。

这些版本的 ITP 包含以下限制：

| 版本 | 详细信息 |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | 对使用 `document.cookie` API 放到浏览器中的客户端 Cookie 设置上限，七天到期。<br>发布于 2019 年 2 月 21 日。 |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | 七天到期的上限大幅缩短为一天。<br>发布于 2019 年 4 月 24 日。 |
| [ITP 2.3](https://webkit.org/blog/9521/intelligent-tracking-prevention-2-3/) | 消除了一些解决方法，例如使用localStorage或使用JavaScript `Document.referrer property`。<br>发布于2019年9月23日。 |

## 作为Adobe[!DNL Target]客户，这对我有何影响？ {#impact}

[!DNL Target] 提供了 JavaScript 库可供您在页面上部署，以便 [!DNL Target] 能够为访客提供实时个性化。有三个Target JavaScript库at.js 1.x和at.js 2.x，它们通过`document.cookie` API将客户端[!DNL Target] Cookie放置在访客的浏览器上。 因此，[!DNL Target] Cookie会受Apple ITP 2.x的影响，并将在七天（使用ITP 2.1）和一天（使用ITP 2.2和ITP 2.3）后过期。

Apple ITP 2.x会在以下方面影响[!DNL Target]:

| 影响 | 详细信息 |
| --- | --- |
| 潜在增加独特访客计数 | 由于过期时间窗口分别设置为七天（使用ITP 2.1）和一天（使用ITP 2.2和ITP 2.3），您可能会看到来自Safari浏览器的独特访客数量增加。 如果您的访客在七天(ITP 2.1)或一天（ITP 2.2和ITP 2.3）之后重新访问域，则[!DNL Target]会强制在您的域上放置新的[!DNL Target] Cookie来替换已过期的Cookie。 即便是同一用户，新 [!DNL Target] Cookie 仍会转换为新的独特访客。 |
| 缩短了 [!DNL Target] 活动的回溯期限 | [!DNL Target] 活动的访客配置文件可能会缩短决策的回溯期限。利用 [!DNL Target] Cookie 可识别访客和存储用于个性化的用户配置文件属性。鉴于Safari上的[!DNL Target] Cookie可能在七天(ITP 2.1)或一天（ITP 2.2和2.3）后到期，无法使用与已清除的[!DNL Target] Cookie关联的用户配置文件数据做出决策。 |
| 基于 3rdPartyID 的个人资料脚本 | 由于过期时间窗口分别设置为七天（使用ITP 2.1）和一天（使用ITP 2.2和ITP 2.3），因此基于3rdPartyID Cookie的[配置文件脚本](/help/c-target/c-visitor-profile/profile-parameters.md)将在过期时停止运行。 |
| iOS 设备中的 QA/预览 URL | 由于过期时间窗口分别设置为七天（使用ITP 2.1）和一天（使用ITP 2.2和ITP 2.3），因此[QA/预览URL](/help/c-activities/c-activity-qa/activity-qa.md)将在过期时停止运行，因为URL基于第三方ID Cookie。 |

## 我当前已实施的 [!DNL Target] 是否会受到影响？

在 Safari 浏览器中，导航到您拥有 [!DNL Target] JavaScript 库的网站。如果您在CNAME的上下文中看到已设置[!DNL Target] Cookie（如`analytics.company.com`），则不受ITP 2.x的影响。

如果除了 Target JavaScript 库之外，您还在使用 Experience Cloud ID (ECID) 库，则您的实施会受到下文所述的影响：[Safari ITP 2.1 对 Adobe Experience Cloud 和 Experience Platform 客户的影响](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)。

## 如何减轻未来ITP 2.x版本对Target的影响？

要减轻未来ITP 2.x版本对Target的影响，请完成以下任务：

1. 将 Experience Cloud ID (ECID) 库部署到您的页面。

   ECID 库可为 Experience Cloud Core 解决方案启用人员识别框架。通过分配永久和唯一标识符，ECID 库让您能够识别不同 Experience Cloud 解决方案中的相同站点访客及其数据。ECID 库将经常更新，以帮助您减轻 ITP 相关更改对您的实施的影响。

   对于ITP 2.x，必须使用[ECID库4.3.0+](https://experienceleague.adobe.com/docs/id-service/using/release-notes/release-notes.html?lang=zh-Hans)来减轻影响。

1. 使用 Adobe CNAME 并注册 Adobe Analytics 托管证书计划。

   安装 ECID 库 4.3.0+ 之后，您可以使用 Adobe Analytics CNAME 和托管证书计划。这项计划允许您免费为第一方 Cookie 实施第一方证书。使用CNAME将帮助[!DNL Target]客户减轻ITP 2.x的影响。

   如果您没有使用CNAME，则可以通过与您的客户代表沟通并注册[Adobe托管证书计划](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program)来开始该过程。

在您部署 Target JavaScript 库和 ECID 库 v4.3.0+ 并注册 Adobe 托管证书计划来使用 CNAME 之后，您将获得一个强大且长期的可减轻 ITP 相关更改对您影响的计划。

当整个行业都在努力为消费者创建更加安全的 Web 时，[!DNL Adobe Target] 也不遗余力地为客户提供个性化体验，同时满足甚至超越访客的隐私保护期望。[!DNL Adobe Target] 除了支持Apple ITP 2. [x之外，已](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) 经宣布还支持Google SameSite Chrome政策。

由于政策不断发展以保护我们的消费者，[!DNL Adobe] 也将继续在 [!DNL Target] 中支持这些举措，并将帮助我们的客户提供一流的个性化体验。
