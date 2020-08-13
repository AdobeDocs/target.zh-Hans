---
keywords: at.js;api;release;updates;apis;sdks;server side;serverside;server-side;api;delivery api
description: 与Adobe Target服务器端API相关的发行说明。
title: 与Adobe Target服务器端API相关的发行说明。
feature: release notes
topic: Standard
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 0%

---


# 发行说明-目标服务器端API

与Adobe Target服务器 [端API相关的发行说明](https://developers.adobetarget.com/api/delivery-api/)。

## V1/投放（2019年10月9日）

已发布全新的投放API端点。

* New [documentation](https://developers.adobetarget.com/api/delivery-api/) is available.
* 一个端点，用于检索一个或多个mbox的体验。
* 通过API检索VEC创建的活动。

   包含VEC创建的活动的响应包含选择器，这些选择器可用于仅预隐藏需要个性化的页面部分。 这有助于优化页面的“第一 [个内容绘制”量度](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html)，这是企业在Google PageRank系统中获得高分的重要 [KPI](https://en.wikipedia.org/wiki/PageRank) 。

* 支持称为视图的全新对象，该对象用 [于单页应用程序](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md) (SPA)和 [移动应用](/help/c-target-mobile-app/target-mobile-app.md)。
* 支持预取视图和mbox，以通过缓存优化性能。
* 支持发送预取视图和mbox的通知。

>[!IMPORTANT]
>
>仍可 [以访问旧版/v1/mbox和/v2/batchmbox](https://developers.adobetarget.com/api/legacy-api/index.html) API文档。 但是，新功能将在新的投放API中开发，并且不会后移到传统API。
