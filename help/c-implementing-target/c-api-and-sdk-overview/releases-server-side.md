---
description: 与Adobe Target的服务器端API和SDK相关的发行说明
keywords: at.js;api;release；更新；api;sdks；服务器端；服务器端；服务器端；api；交付api
seo-description: 与Adobe Target的服务器端API相关的发行说明。
seo-title: 与Adobe Target的服务器端API相关的发行说明。
solution: Target
title: 发行说明——目标服务器端API
topic: Standard
translation-type: tm+mt
source-git-commit: 434b103cee15e2e3efdb53febe15c689b5ccd48e

---


# 发行说明——目标服务器端API

与 [Adobe Target服务器端API相关的发行说明](https://developers.adobetarget.com/api/delivery-api/)。

## V1/交付（2019年10月9日）

已发布全新的交付API端点。

* New [documentation](https://developers.adobetarget.com/api/delivery-api/) is available.
* 一个端点，用于检索一个或多个mbox的体验。
* 通过API检索VEC创建的活动。

   包含VEC创建的活动的响应包含选择器，这些选择器可用于仅预隐藏需要个性化的页面部分。 这有助于优化页面的“第一个内容绘制”量度 [，这是您的企业在](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html)Google PageRank系统中获得高分的重要KPI [](https://en.wikipedia.org/wiki/PageRank) 。

* 支持一个称为“视图”的全新对象，该对象用于 [单页应用程序](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md) (SPA)和移 [动应用程序](/help/c-target-mobile-app/target-mobile-app.md)。
* 支持预取视图和mbox，以通过缓存优化性能。
* 支持发送预取视图和mbox的通知。

>[!IMPORTANT]
>
>仍可 [以访问旧版/v1/mbox和/v2/batchmbox API文档](https://developers.adobetarget.com/api/legacy-api/index.html) 。 但是，新功能将在新的交付API中开发，并且不会后移到传统API。
