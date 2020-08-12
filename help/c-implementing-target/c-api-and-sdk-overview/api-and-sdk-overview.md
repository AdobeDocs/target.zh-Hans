---
keywords: server side;server-side;api;sdk;node.js;nodejs;node js;recommendations api;api:apis
description: 有关Adobe Target服务器端投放API、Node.js SDK和目标RecommendationsAPI的信息。
title: 有关Adobe Target服务器端投放API、Node.js SDK和目标RecommendationsAPI的信息。
feature: null
topic: Recommendations
uuid: 21d321c7-3da4-44a2-a04f-1807cc2a893b
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 11%

---


# 服务器端：实施 Target{#server-side-implement-target}

有关服 [!DNL Adobe Target] 务器端投放API、Node.js SDK和API的 [!DNL Target Recommendations] 信息。

以下过程会在 [!DNL Target] 的服务器端实施中发生：

1. 客户端设备通过您的服务器请求获取体验。
1. 您的服务器将该请求发送至 [!DNL Target]。
1. [!DNL Target] 将响应发送回服务器。
1. 您的服务器决定要向客户端设备提供哪些体验以供其呈现。

无需在浏览器中显示体验。 该体验可以通过电子邮件或自助终端、语音助手或其他非视觉体验或基于浏览器的设备显示。 由于您的服务器位于客户端和 [!DNL Target] 之间，因此如果您需要更好地控制体验并提高其安全性，或者您希望在服务器上运行复杂的后端进程，则此类实施是最佳选择。

以下各节提供有关各种API和NodeJS SDK的更多信息：

## 服务器端交付 API

Link: [Server Side Delivery APIs](https://developers.adobetarget.com/api/delivery-api/)

`/rest/v1/delivery`

通过 [!DNL Target] 投放API，您可以：

* 跨Web交付体验，包括SPA、移动渠道以及基于非浏览器的IoT设备，如网络电视、报亭或店内数字屏幕。
* 从任何可进行HTTP/s调用的服务器端平台或应用程序提供体验。
* 向访客提供一致、个性化的体验，无论访客使用何种渠道或设备与您的业务互动。
* 在服务器上的会话中缓存访客体验，以避免多个API调用，从而获得更好的性能。
* 与诸如 [!DNL Adobe Experience Cloud] 、(AAM [!DNL Adobe Analytics])和服 [!DNL Adobe Audience Manager] 务器端的 [!DNL Experience Cloud ID Service] 产品无缝集成。

## Node.js SDK

链接： [Node.js SDK](https://github.com/adobe/target-nodejs-sdk)

Node.js SDK是一款精良的软件开发工具包，可消除管理Cookie、会话以及与产品（如、和） [!DNL Experience Cloud] 集成的复杂 [!DNL Analytics]性 [!DNL Experience Cloud Visitor ID Service][!DNL Audience Manager]问题。 Node.js SDK在后台使用 `/rest/v1/delivery` API。 以下是Node.js SDK支持的一些值得注意的功能：

* **支持预回迁和通知，允许您通过缓存优化性能：** 您可以使用Node.js SDK检索体验并在本地将其缓存到Node.js服务器上，以最大限度地减少对应用程序的服务 [!DNL Target] 器调用并优化性能。
* **能检索VEC创建的活动:** 在服务器端检索VEC创建的活动。 包含VEC创建的活动的响应包含选择器，这些选择器可用于仅预隐藏需要个性化的页面部分。 这有助于优化您页面的“第 [一个内容绘制](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html)”指标，这是您的企业在Google PageRank系统中获得高分的重要 [KPI](https://en.wikipedia.org/wiki/PageRank) 。

## 目标Java SDK

链接： [目标Java SDK](https://github.com/adobe/target-java-sdk)

Java SDK是一款精良的软件开发工具包，它消除了管理Cookie、会话以及与解决方 [!DNL Adobe Experience Cloud] 案（如、和）集 [!DNL Adobe Analytics]成的 [!DNL Experience Cloud Visitor ID Service]复杂性 [!DNL Adobe Audience Manager]。 在幕后，Java SDK使用 `/rest/v1/delivery` API。 以下是Java SDK支持的一些值得注意的功能：

* **支持预回迁和通知，允许您通过缓存优化性能**:您可以使用JavaSDK检索体验并在本地将它们缓存到Java服务器上，以最大限度地减少对应用程序性能的服 [!DNL Target] 务器调用并优化它们。
* **能检索VEC创建的活动**:在服务器端检索VEC创建的活动。 包含VEC创建的活动的响应包含选择器，这些选择器可用于仅预隐藏需要个性化的页面部分。 这有助于优化您页面的“第 [一个内容绘制](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html) ”指标，这是您的企业在Google PageRank系统中获得高分的重要 [KPI](https://en.wikipedia.org/wiki/PageRank) 。

## Target 推荐 API

链接： [目标Recommendations](https://developers.adobetarget.com/api/recommendations) API [和Adobe RecommendationsAPI概述](https://docs.adobe.com/content/help/en/target-learn/recommendations-api-tutorial/recs-api-overview.html)。

The Recommendations APIs let you programmatically interact with [!DNL Target] recommendations servers. These APIs can be integrated with a range of application stacks to perform functions that you would typically do via the [!DNL Target] user interface.
