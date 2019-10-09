---
description: 有关Adobe Target服务器端交付API、Node.js SDK和Target Recommendations API的信息。
keywords: 服务器端；服务器端；api;sdk;node.js;nodejs;nodejs;recommendations api;api:api
seo-description: 有关Adobe Target服务器端交付API、Node.js SDK和Target Recommendations API的信息。
seo-title: 有关Adobe Target服务器端交付API、Node.js SDK和Target Recommendations API的信息。
solution: Target
title: 服务器端：实施 Target
topic: 推荐
uuid: 21d321c7-3da4-44a2-a04f-1807cc2a893b
translation-type: tm+mt
source-git-commit: 9fa095b910b85f244b626c34cacdf9f4a13a6929

---


# 服务器端：实施 Target{#server-side-implement-target}

有关服 [!DNL Adobe Target] 务器端交付API、Node.js SDK和API的 [!DNL Target Recommendations] 信息。

以下过程会在 [!DNL Target] 的服务器端实施中发生：

1. 客户端设备通过您的服务器请求获取体验。
1. 您的服务器将该请求发送至 [!DNL Target]。
1. [!DNL Target] 将响应发送回服务器。
1. 服务器决定将哪种体验交付到客户端设备以供其呈现。

无需在浏览器中显示体验。 该体验可以通过电子邮件或自助终端、语音助手或其他非视觉体验或基于浏览器的设备显示。 由于您的服务器位于客户端和 [!DNL Target] 之间，因此如果您需要更好地控制体验并提高其安全性，或者您希望在服务器上运行复杂的后端进程，则此类实施是最佳选择。

以下各节提供了有关各种API和NodeJS SDK的更多信息：

## 服务器交付API

Link: [Server Side Delivery APIs](https://developers.adobetarget.com/api/delivery-api/)

`/rest/v1/delivery`

通过交 [!DNL Target] 付API，您可以：

* 跨Web（包括SPA、移动渠道）以及非基于浏览器的IoT设备（如网络电视、报亭或店内数字屏幕）提供体验。
* 从任何可进行HTTP/s调用的服务器端平台或应用程序提供体验。
* 无论访客使用哪些渠道或设备与您的业务互动，都可向访客提供一致的个性化体验。
* 在服务器上的会话中缓存访客体验，以避免多个API调用，从而获得更好的性能。
* 与产品( [!DNL Adobe Experience Cloud] 如、 [!DNL Adobe Analytics](AAM) [!DNL Adobe Audience Manager] 和服务器端)无缝 [!DNL Experience Cloud ID Service] 集成。

## Node.js SDK

链接： [Node.js SDK](https://github.com/adobe/target-nodejs-sdk)

Node.js SDK是一个精良的软件开发工具包，它消除了管理Cookie、会话以及与产品（如、和）集 [!DNL Experience Cloud] 成的复杂 [!DNL Analytics]性 [!DNL Experience Cloud Visitor ID Service]问题 [!DNL Audience Manager]。 在后台，Node.js SDK使用 `/rest/v1/delivery` API。 以下是Node.js SDK中支持的一些显着功能：

* **** 支持预取和通知，允许您通过缓存优化性能：您可以使用Node.js SDK检索体验并在本地缓存到Node.js服务器上，以最大限度地减少对应用程序性能的服务器调 [!DNL Target] 用并优化它们。
* **** 能够检索VEC创建的活动：在服务器端检索VEC创建的活动。 包含VEC创建的活动的响应包含选择器，这些选择器可用于仅预隐藏需要个性化的页面部分。 这有助于优化页面的“第一个内容绘制”量度 [，这是您的企业在](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html)Google PageRank系统中获得高分的重要KPI [](https://en.wikipedia.org/wiki/PageRank) 。

## Target 推荐 API

Link: [Target Recommendations APIs](https://developers.adobetarget.com/api/recommendations)

The Recommendations APIs let you programmatically interact with [!DNL Target] recommendations servers. These APIs can be integrated with a range of application stacks to perform functions that you would typically do via the [!DNL Target] user interface.
