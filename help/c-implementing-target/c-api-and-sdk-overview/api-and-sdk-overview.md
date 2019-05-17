---
description: 有关 Target 服务器端交付 API、推荐 API 和 NodeJS SDK 的信息。
keywords: 服务器端;API;SDK;NodeJS;Node JS;推荐 API
seo-description: 有关 Target 服务器端交付 API、推荐 API 和 NodeJS SDK 的信息。
seo-title: 服务器端：实施 Target
solution: Target
title: 服务器端：实施 Target
topic: 推荐
uuid: 21d321c7-3da4-44a2-a04f-1807cc2a893b
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 服务器端：实施 Target{#server-side-implement-target}

有关 Target 服务器端交付 API、服务器端批量交付 API、NodeJS SDK、Target 推荐 API 和 Target Classic API（已停用）的信息。

以下章节列出了各种 API 和 NodeJS SDK，并提供了其他信息：

## 服务器端交付 API

链接： [服务器端交付API](https://developers.adobetarget.com/api/#server-side-delivery)

`/rest/v1/mbox`

Adobe Target 允许您的应用程序从任何浏览器、移动设备，甚至其他服务器执行 mbox 调用。服务器端交付 API 专门用于将 Adobe Target 与任何执行 HTTP/HTTPS 调用的服务器端平台集成。

您可以使用 API 将自定义应用程序与 Target 集成。这对于想要为不基于浏览器的 IoT 设备（例如联网电视、网亭或店内数字屏幕）提供定位的组织尤其有用。

此端点只能为普通 mbox 返回选件。您也可以仅为单个 mbox 获取内容。

此 API 会以 RESTful 方式实施现有 mbox 功能。

此 API 不处理 Cookie 或重定向调用。

## 服务器端批量交付 API

链接： [服务器端批量交付API](https://developers.adobetarget.com/api/#server-side-batch-delivery)

`/rest/v2/batchmbox`

批量交付 API 允许您的应用程序在一次调用中为多个 mbox 请求内容。它还具有预取模式，允许移动设备应用程序、服务器等客户端在一个请求中为多个 mbox 获取内容，并将其缓存在本地，然后在用户访问这些 mbox 时通知 Target。

此端点只能为普通 mbox 返回选件。由于您可以为多个 mbox 获取内容，因此为了提高性能，最好使用批处理 mbox API。这样可以使您避免执行多个 HTTP 请求，执行多个 HTTP 请求可能会耗费昂贵成本。

## NodeJS SDK

链接： [NodeJS SDK](https://www.npmjs.com/package/@adobe/target-node-client)

就 SDK 而言，目前我们只有一个 SDK，即 NodeJS SDK。

NodeJS SDK 是 NodeJS 核心 HTTP/HTTPS 模块的瘦包装器。在后台，NodeJS SDK API 使用相同的服务器端交付 API。

以下是相关映射：

* `MarketingCloudClient.getOffer() \*- invokes \*/res/v1/mbox endpoint`
* `MarketingCloudClient.getOffers() \*- invokes \*/res/v2/batchmbox endpoint`

## Target 推荐 API

链接： [Target推荐API](https://developers.adobetarget.com/api/recommendations)

通过推荐 API，您能够以编程方式与 Target 的推荐服务器进行交互。这些 API 可以与一系列应用程序堆栈集成，以执行您通常会通过用户界面执行的功能。

## Target Classic API

Target Classic UI 和 API 已停用。有关转为使用 Target 新版 API 的信息，请参阅[从 Target 旧版 API 迁移到 Adobe I/O](../../c-implementing-target/c-api-and-sdk-overview/target-api-documentation.md#concept_3A31E26C8FAF49598152ACFE088BD4D2)。

>[!NOTE]
>用于创建活动、选件、受众等的创作 API 不支持跨域资源共享 (CORS)。

## 服务器端交付 API 与 NodeJS SDK 之间的差异 {#section_10336B7934F54CE98E35907A4748A4A4}

许多客户不清楚服务器端交付 API 与 NodeJS SDK 之间的差异，尤其是在性能方面的差异。

以下常见问题解答可帮助您确定应使用两者中的哪一个：

**何时应使用“原始”服务器端 API，何时应使用 NodeJS SDK？**

理想情况下，如果您使用 NodeJS 作为后端技术，则 NodeJS SDK 是自然之选。该 SDK 处理许多详细信息，例如 Cookie、标头、有效负荷等。这使您可以专注于应用程序的核心。

**我是否应该使用 NodeJS SDK 来实现任何性能提升？**

遗憾的是，我们没有任何性能指数。但是，一般来说，由于具有 NodeJS 事件驱动架构，NodeJS SDK 应该可提供良好的性能。请注意，大部分时间都花在 Target 后端。NodeJS SDK 执行极少的处理工作。该 SDK 基本上负责打包 Target 请求和解析 Target 响应。
