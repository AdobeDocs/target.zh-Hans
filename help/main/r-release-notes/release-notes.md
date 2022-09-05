---
keywords: 发行说明;新功能;版本;更新;更新;版本;增强;增强;修复;错误修复;更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: e0e12caec1cf9db713d56983f3697d80bea72015
workflow-type: ht
source-wordcount: '977'
ht-degree: 100%

---

# Target 发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的发行说明以及其他平台变更。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## [!DNL Target Standard/Premium] 22.8.1（2022 年 8 月 17 至 18 日，交错发行）

此维护版本包括后端和本地化修复。

## [!DNL Target] Platform 版本（2022 年 7 月 20 日）

此版本包含以下功能、增强和修复：

| 功能 | 描述 |
| --- | --- |
| 通过 IPv6 支持 (TNT-43364、TNT-44692) 提高受众评估准确性并减少最终用户延迟 | 访客的地理位置现在由 IPv6 地址（如果可用）决定，而不仅仅是 IPv4 地址决定。 投放 API 还支持 IPv6 输入参数。 过滤和允许列表同时支持 IPv4 和 IPv6 地址。 本版本中的 IPv6 支持意味着访客将更准确地包括在受众中（更准确地符合活动资格或筛选标准）。 它还改善了数据延迟，因为 IPv6 客户端将直接路由，避免了 IPv6 到 IPv4 网关的开销。 |
| 修复了 A4T 客户端有效负载处理问题 (TNT-44926) | 通过 A4T 服务器端集成，如果 Adobe Target 识别来自机器人的请求，则不会将有效负载转发给 Analytics，并且 [!DNL Target] 日志中没有记录 mod_stats 事件。 通过此版本，A4T 客户端记录功能得到了增强，因此 A4T 有效负载的行为与 A4T 服务器端相同：被识别为机器人的访客不计入 [!DNL Target] 计数/报告。 （注意，问题仅限于使用客户端有效负载处理的实施；服务器端没有受到影响。 有了这个版本，服务器端和客户端有效负载处理的行为现在都是一致的。） |

## [!DNL Target Standard/Premium] 22.6.2（2022 年 6 月 30 日）

此版本包含以下功能、增强和修复：

| 功能 | 描述 |
| --- | ---  |
| 产品内通知 | 获取以下相关的产品内通知：<ul><li>**活动**:批准或停用活动时（手动或达到活动开始或结束日期时），所有活动类型的通知。 通知包含带有活动概述页面链接的活动名称。</li><li>**配置文件脚本** 手动或Target激活或停用配置文件脚本时的通知。</li><li>**Recommendations信息源**:手动或由Target激活或停用Recommendations馈送时的通知。 当Recommendations馈送失败时，也会发送通知。</li></ul> 默认情况下，产品管理员、发布者和批准者会收到通知。 通知可在Experience Cloud首选项中进行配置。<br>有关详细信息，请参阅 [通知和公告](/help/main/c-intro/understand-the-target-ui.md#notifications-announcements). |
| *Adobe Target 开发人员指南* | *Adobe Target 开发人员指南* 便于合并所有 [!DNL Target] 开发人员内容。 [!DNL Target][!DNL Recommendations][!DNL Target][!DNL Target]<br>有关更多信息，请参阅 [Adobe Target 开发人员指南](https://developer.adobe.com/target/){target=_blank}。 |

* 具有[!UICONTROL 编辑者]角色的用户无法再编辑直播活动中的受众。(TGT-43582)
* 如果客户试图将感叹号 (！) 作为受众名称的第一个字符（例如 !London）来保存受众，则会显示警告消息。(TGT-43643)
* 修复了导致某些客户的受众定义详细信息卡指示已结束活动仍处于活动状态的问题。(TGT-43527)

## [!DNL Target Standard/Premium] 22.6.1（2022 年 6 月 7 日至 9 日，交错发行）

此版本将按照以下交错发布计划发布：

* **6 月 7 日**：亚太 (APAC) 地区
* **6 月 8 日**：美洲地区
* **6 月 9 日**：欧洲、中东和非洲 (EMEA) 地区

此版本包含以下增强功能和修复：

* 对新的[!UICONTROL 受众]页面进行了增强，以防止过去存储受众的旧数据库与直接从后端检索信息的新架构之间出现不一致的状态。(TGT-43552)
* 修复了由于 Target UI 创建“空”容器而导致某些客户无法保存合并受众的问题。 (TGT-43588)

## Target 平台版本（2022 年 5 月 25 日）

此版本包含以下增强功能和修复：

* 添加了[用户代理客户端提示](https://developer.adobe.com/target/implement/client-side/atjs/user-agent-and-client-hints/){target=_blank}支持功能。
* 修复了一个问题，在[!UICONTROL 体验定位] (XT) 活动中呈现[!UICONTROL 优惠决策]时，该问题间歇性地导致超时。(TNT-44611)

## at.js 版本 2.9.0（2022 年 5 月 27 日）

* 添加了[用户代理客户端提示](https://developer.adobe.com/target/implement/client-side/atjs/user-agent-and-client-hints/){target=_blank}支持功能。
* 修复了同一页面上的多个 mbox 请求具有不同印象 ID 的错误。

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 文档更改、以往的发行说明和 Experience Cloud 发行说明

除了针对每个发行的说明外，以下资源还提供更多其他信息：

| 资源 | 详细信息 |
|--- |--- |
| 文档更改 | 查看这些发行说明中未包括的关于本指南的更新的详细信息。<br>有关更多信息，请参阅[文档更改](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)。 |
| 以前版本的发行说明 | 查看与以前版本的 Target Standard 和 Target Premium 中的新增功能和增强功能相关的信息。<br>有关更多信息，请参阅[以前版本的发行说明](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 发行说明 | 查看 Adobe Experience Cloud 解决方案的最新发行说明。<br>有关更多信息，请参阅 [Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)。 |

## 预发行信息 {#section_5D588F0415A2435B851A4D0113ACA3A0}

您可以通过以下资源了解下一个 Target 版本即将包含的功能。

| 资源 | 详细信息 |
|--- |--- |
| Adobe 优先产品更新 | 若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：<br>[](https://www.adobe.com/cn/subscription/priority-product-update.html)https://www.adobe.com/cn/subscription/priority-product-update.html |
| 即将推出的发行说明 | 有关当月 Target 发行版本的信息（包括预发行信息），请参阅 [Target 发行说明 — 预发行](/help/main/r-release-notes/target-release-notes.md)页面。 |
