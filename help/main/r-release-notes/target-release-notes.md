---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解 Adobe Target 即将发布的版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: bc4b04ae0be1fade2456eb42ade7ee87c0f14b16
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Target 发行说明（预发行版本）

本文包含预发行版本信息。发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新日期：2022 年 7 月 20 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target] Platform 版本（2022 年 7 月 20 日）

此版本包含以下功能、增强和修复：

| 功能 | 描述 |
| --- | --- |
| 通过 IPv6 支持 (TNT-43364、TNT-44692) 提高受众评估准确性并减少最终用户延迟 | 访客的地理位置现在由 IPv6 地址（如果可用）决定，而不仅仅是 IPv4 地址决定。 投放 API 还支持 IPv6 输入参数。 过滤和允许列表同时支持 IPv4 和 IPv6 地址。 本版本中的 IPv6 支持意味着访客将更准确地包括在受众中（更准确地符合活动资格或筛选标准）。 它还改善了数据延迟，因为 IPv6 客户端将直接路由，避免了 IPv6 到 IPv4 网关的开销。 |
| 修复了 A4T 客户端有效负载处理问题 (TNT-44926) | 通过 A4T 服务器端集成，如果 Adobe Target 识别来自机器人的请求，则不会将有效负载转发给 Analytics，并且 [!DNL Target] 日志中没有记录 mod_stats 事件。 通过此版本，A4T 客户端记录功能得到了增强，因此 A4T 有效负载的行为与 A4T 服务器端相同：被识别为机器人的访客不计入 [!DNL Target] 计数/报告。 （注意，问题仅限于使用客户端有效负载处理的实施；服务器端没有受到影响。 有了这个版本，服务器端和客户端有效负载处理的行为现在都是一致的。） |


## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
