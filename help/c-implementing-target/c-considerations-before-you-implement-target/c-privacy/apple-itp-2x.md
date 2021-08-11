---
keywords: Apple;ITP；智能防跟踪；Experience Cloud ID;ECID;ITP
description: 了解Adobe [!DNL Target] 以及Apple智能防跟踪(ITP)计划（旨在保护Safari用户隐私）的影响。
title: ' [!DNL Target] 如何处理Apple ITP支持？'
feature: 隐私和安全
role: Developer
exl-id: 05a62be5-ccfb-4d5c-b511-35023b95e567
source-git-commit: 898a18cbd9c6f499f9e7b74078575bc149c9a292
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 38%

---

# Apple 智能防跟踪 (ITP) 2.x

智能防跟踪 (ITP) 是 Apple 推出的一项旨在保护 Safari 用户隐私的举措。第一版 ITP 于 2017 年发布，主要针对使用第三方 Cookie 的情况。事实上，Apple 完全阻止了第三方 Cookie，这反而给广告技术公司和营销技术公司造成严重的困扰，因为这些公司通常使用第三方 Cookie 来跟踪访客并收集访客数据。现在，Apple 正在对如何在 Safari 中使用第一方 Cookie 进行限制和约束。

这些版本的 ITP 包含以下限制：

| 版本 | 详细信息 |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | 对使用 `document.cookie` API 放到浏览器中的客户端 Cookie 设置上限，七天到期。<br>发布于 2019 年 2 月 21 日。 |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | 七天到期的上限大幅缩短为一天。<br>发布于 2019 年 4 月 24 日。 |
| [ITP 2.3](https://webkit.org/blog/9521/intelligent-tracking-prevention-2-3/) | 消除了一些解决方法，例如使用localStorage或使用JavaScript `Document.referrer property`。<br>发布于2019年9月23日。<br>Safari 14、macOS Big Sur、Catalina、Mojave、iOS 14和iPadOS 14中发布的ITP的CNAME伪装防御功能。由第三方CNAME隐藏的HTTP响应创建的所有Cookie都将设置为在七天后过期。<br>2020年11月12日宣布。 |

## 作为Adobe[!DNL Target]客户，这对我有何影响？ {#impact}

[!DNL Target] 提供了 JavaScript 库可供您在页面上部署，以便 [!DNL Target] 能够为访客提供实时个性化。有三个Target JavaScript库at.js 1.x和at.js 2.x，它们通过`document.cookie` API将客户端[!DNL Target] Cookie放置在访客的浏览器上。 因此，[!DNL Target] Cookie会受Apple ITP 2.1、2.2和2.3的影响，并将在七天（使用ITP 2.1）和一天（使用ITP 2.2和ITP 2.3）后过期。

Apple ITP 2.x会在以下方面影响[!DNL Target]:

| 影响 | 详细信息 |
| --- | --- |
| 潜在增加独特访客计数 | 由于过期时间窗口分别设置为七天（使用ITP 2.1）和一天（使用ITP 2.2和ITP 2.3），您可能会看到来自Safari浏览器的独特访客数量增加。 如果您的访客在七天(ITP 2.1)或一天（ITP 2.2和ITP 2.3）之后重新访问域，则[!DNL Target]会强制在您的域上放置新的[!DNL Target] Cookie来替换已过期的Cookie。 即便是同一用户，新 [!DNL Target] Cookie 仍会转换为新的独特访客。 |
| 缩短了 [!DNL Target] 活动的回溯期限 | [!DNL Target] 活动的访客配置文件可能会缩短决策的回溯期限。利用 [!DNL Target] Cookie 可识别访客和存储用于个性化的用户配置文件属性。鉴于Safari上的[!DNL Target] Cookie可能在七天(ITP 2.1)或一天（ITP 2.2和2.3）后到期，无法使用与已清除的[!DNL Target] Cookie关联的用户配置文件数据做出决策。 |
| 基于 3rdPartyID 的个人资料脚本 | 由于过期时间窗口分别设置为七天（使用ITP 2.1）和一天（使用ITP 2.2和ITP 2.3），因此基于3rdPartyID Cookie的[配置文件脚本](/help/c-target/c-visitor-profile/profile-parameters.md)将在过期时停止运行。 |
| iOS 设备中的 QA/预览 URL | 由于过期时间窗口分别设置为七天（使用ITP 2.1）和一天（使用ITP 2.2和ITP 2.3），因此[QA/预览URL](/help/c-activities/c-activity-qa/activity-qa.md)将在过期时停止运行，因为URL基于第三方ID Cookie。 |

## 我当前已实施的 [!DNL Target] 是否会受到影响？

如果您除了[!DNL Target] JavaScript库之外，还在使用Experience CloudID(ECID)库，则您的实施将会受到下文所述的影响：[Safari ITP 2.1对Adobe Experience Cloud和Experience Platform客户的影响](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)。
