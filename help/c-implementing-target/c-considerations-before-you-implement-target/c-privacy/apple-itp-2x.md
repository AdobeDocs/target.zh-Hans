---
keywords: apple;ITP；智能跟踪预防；experience cloud id;ecid
description: 了解Adobe [!DNL Target] 以及Apple Intelligent Tracking Prevention(ITP)计划的影响，该计划旨在保护Safari用户的隐私。
title: '如何处理Apple ITP支持？ [!DNL Target] '
feature: 隐私和安全
role: Developer
exl-id: 05a62be5-ccfb-4d5c-b511-35023b95e567
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '912'
ht-degree: 50%

---

# Apple 智能防跟踪 (ITP) 2.x

有关通过Experience CloudID(ECID)库4.3支持Apple ITP 2.x的[!DNL Adobe Target]的信息。

智能防跟踪 (ITP) 是 Apple 推出的一项旨在保护 Safari 用户隐私的举措。第一版 ITP 于 2017 年发布，主要针对使用第三方 Cookie 的情况。事实上，Apple 完全阻止了第三方 Cookie，这反而给广告技术公司和营销技术公司造成严重的困扰，因为这些公司通常使用第三方 Cookie 来跟踪访客并收集访客数据。现在，Apple 正在对如何在 Safari 中使用第一方 Cookie 进行限制和约束。

这些版本的 ITP 包含以下限制：

| 版本 | 详细信息 |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | 对使用 `document.cookie` API 放到浏览器中的客户端 Cookie 设置上限，七天到期。<br>发布于 2019 年 2 月 21 日。 |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | 七天到期的上限大幅缩短为一天。<br>发布于 2019 年 4 月 24 日。 |
| [ITP 2.3](https://webkit.org/blog/9521/intelligent-tracking-prevention-2-3/) | 消除了几种解决方法，如使用localStorage或使用JavaScript `Document.referrer property`。<br>于2019年9月23日发布。 |

## 作为Adobe[!DNL Target]客户，对我有何影响？{#impact}

[!DNL Target] 提供了 JavaScript 库可供您在页面上部署，以便 [!DNL Target] 能够为访客提供实时个性化。有三个 Target JavaScript 库（[at.js 1.x、at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)和[mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md))，通过`document.cookie` API将客户端[!DNL Target] cookie放置在访客的浏览器上。 因此，[!DNL Target] cookies受Apple的ITP 2.x影响，将在七天后（使用ITP 2.1）和一天后（使用ITP 2.2和ITP 2.3）过期。

Apple ITP 2.x在以下方面影响[!DNL Target]:

| 影响 | 详细信息 |
| --- | --- |
| 潜在增加独特访客计数 | 由于过期窗口设置为七天（使用ITP 2.1）和一天（使用ITP 2.2和ITP 2.3），您可能会看到来自Safari浏览器的独特访客增加。 如果您的访客在七天(ITP 2.1)后或一天（ITP 2.2和ITP 2.3）后重新访问您的域，则[!DNL Target]将被迫在您的域上放置新的[!DNL Target] Cookie来代替过期的Cookie。 即便是同一用户，新 [!DNL Target] Cookie 仍会转换为新的独特访客。 |
| 缩短了 [!DNL Target] 活动的回溯期限 | [!DNL Target] 活动的访客配置文件可能会缩短决策的回溯期限。利用 [!DNL Target] Cookie 可识别访客和存储用于个性化的用户配置文件属性。由于[!DNL Target] cookies可在七天后(ITP 2.1)或一天（ITP 2.2和2.3）在Safari上过期，因此无法使用与清除的[!DNL Target] cookie关联的用户用户档案数据进行决策。 |
| 用户档案脚本（基于3rdPartyID） | 由于过期窗口设置为七天（使用ITP 2.1）和一天（使用ITP 2.2和ITP 2.3），基于3rdPartyID cookie的用户档案脚本](/help/c-target/c-visitor-profile/profile-parameters.md)将在过期时停止工作。[ |
| iOS设备中的QA/预览URL | 由于过期窗口设置为七天（使用ITP 2.1）和一天（使用ITP 2.2和ITP 2.3），[QA/预览URL](/help/c-activities/c-activity-qa/activity-qa.md)将在过期时停止工作，因为URL基于第三方ID Cookie。 |

## 我当前已实施的 [!DNL Target] 是否会受到影响？

在 Safari 浏览器中，导航到您拥有 [!DNL Target] JavaScript 库的网站。如果您在CNAME的上下文中看到[!DNL Target] cookie集，如`analytics.company.com`，则ITP 2.x不会影响您。

如果除了 Target JavaScript 库之外，您还在使用 Experience Cloud ID (ECID) 库，则您的实施会受到下文所述的影响：[Safari ITP 2.1 对 Adobe Experience Cloud 和 Experience Platform 客户的影响](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)。

## 如何减轻未来ITP 2.x版本对目标的影响？

要减轻未来ITP 2.x版本对目标的影响，请完成以下任务:

1. 将 Experience Cloud ID (ECID) 库部署到您的页面。

   ECID 库可为 Experience Cloud Core 解决方案启用人员识别框架。通过分配永久和唯一标识符，ECID 库让您能够识别不同 Experience Cloud 解决方案中的相同站点访客及其数据。ECID 库将经常更新，以帮助您减轻 ITP 相关更改对您的实施的影响。

   对于ITP 2.x，[ECID库4.3.0+](https://experienceleague.adobe.com/docs/id-service/using/release-notes/release-notes.html)必须用于缓解。

1. 使用 Adobe CNAME 并注册 Adobe Analytics 托管证书计划。

   安装 ECID 库 4.3.0+ 之后，您可以使用 Adobe Analytics CNAME 和托管证书计划。这项计划允许您免费为第一方 Cookie 实施第一方证书。利用CNAME将帮助[!DNL Target]客户减轻ITP 2.x的影响。

   如果您没有利用CNAME，则可以通过与帐户代表交谈并登记[Adobe管理证书项目](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program)来开始该过程。

在您部署 Target JavaScript 库和 ECID 库 v4.3.0+ 并注册 Adobe 托管证书计划来使用 CNAME 之后，您将获得一个强大且长期的可减轻 ITP 相关更改对您影响的计划。

当整个行业都在努力为消费者创建更加安全的 Web 时，[!DNL Adobe Target] 也不遗余力地为客户提供个性化体验，同时满足甚至超越访客的隐私保护期望。[!DNL Adobe Target] 除了支持苹果 [的ITP 2.x外，](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) 已宣布支持谷歌的SameSite Chrome Policys。

由于政策不断发展以保护我们的消费者，[!DNL Adobe] 也将继续在 [!DNL Target] 中支持这些举措，并将帮助我们的客户提供一流的个性化体验。
