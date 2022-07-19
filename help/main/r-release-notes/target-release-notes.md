---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解 Adobe Target 即将发布的版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: a5d2c07105b1d0fac6115fe507537be6a36799e9
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 31%

---

# Target 发行说明（预发行版本）

本文包含预发行版本信息。发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新日期：2022 年 7 月 19 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target Standard/Premium] 22.7.1（2022年7月20日）

此版本包含以下功能、增强功能和修复：

| 功能 | 描述 |
| --- | --- |
| 通过IPv6支持，提高了受众评估的准确性和最终用户延迟 | 访客的地理位置现在由IPv6地址（如果可用）来确定，而不是仅由IPv4地址来确定。 交付API还支持IPv6输入参数。 筛选和允许列表支持IPv4和IPv6地址。 此版本中的此IPv6支持意味着访客将更准确地包含在受众中（更准确地符合活动条件或包含在筛选标准中）。 它还改善了数据延迟，因为IPv6客户端将直接路由，从而避免了IPv6到IPv4网关的开销。 |
| A4T客户端负载处理增强功能 | 通过A4T服务器端集成，如果Adobe Target将请求标识为来自机器人的请求，则不会将有效负载转发到Analytics，并且中未记录任何mod_stats事件 [!DNL Target] 日志。 在此版本之前，A4T客户端集成会将有效负载转发到 [!DNL Analytics]，即使当它被标识为机器人流量时也是如此。 服务器端与客户端之间的这种不一致会导致差异，因为后者的A4T报表包含机器人流量。 此外，机器人流量不一定被识别或标记，这意味着无法消除其他流量中的机器人流量的歧义或将其删除。 即使客户自己确实考虑了机器人流量，它也不一定匹配 [!DNL Target] 已识别并排除为机器人流量，从而导致拆分差异或其他问题。 在此版本中，A4T客户端日志记录已得到增强，因此与A4T有效负载相关的行为与与A4T服务器端的行为相同：被识别为机器人的访客将被排除在 [!DNL Target] 计数/报告，适用于服务器端和客户端实施。 |


## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
