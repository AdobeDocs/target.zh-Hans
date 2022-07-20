---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解 Adobe Target 即将发布的版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: bc4b04ae0be1fade2456eb42ade7ee87c0f14b16
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 37%

---

# Target 发行说明（预发行版本）

本文包含预发行版本信息。发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新日期：2022 年 7 月 20 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target] 平台版本（2022年7月20日）

此版本包含以下功能、增强功能和修复：

| 功能 | 描述 |
| --- | --- |
| 通过支持IPv6(TNT-43364、TNT-44692)，提高了受众评估的准确性并减少了最终用户延迟 | 访客的地理位置现在由IPv6地址（如果可用）来确定，而不是仅由IPv4地址来确定。 交付API还支持IPv6输入参数。 筛选和允许列表支持IPv4和IPv6地址。 此版本中的IPv6支持意味着访客将更准确地包含在受众中（更准确地符合活动资格或包含在筛选标准中）。 它还改善了数据延迟，因为IPv6客户端将直接路由，从而避免了IPv6到IPv4网关的开销。 |
| 修复了A4T客户端有效负载处理问题(TNT-44926) | 通过A4T服务器端集成，如果Adobe Target将请求标识为来自机器人的请求，则不会将有效负载转发到Analytics，并且中未记录任何mod_stats事件 [!DNL Target] 日志。 在此版本中，A4T客户端日志记录已得到增强，因此与A4T有效负载相关的行为与与A4T服务器端的行为相同：被识别为机器人的访客将被排除在 [!DNL Target] 计数/报告。 (请注意，相关问题仅限于使用客户端负载处理的实施；未影响服务器端。 在此版本中，服务器端和客户端负载处理的行为现在都保持一致。) |


## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
