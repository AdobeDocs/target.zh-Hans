---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解 Adobe Target 即将发布的版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 1b737f963fe63770cb04d05f3414ed946548d882
workflow-type: ht
source-wordcount: '455'
ht-degree: 100%

---

# Target 发行说明（预发行版本）

本文包含预发行版本信息。发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新日期：2022 年 10 月 19 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target] Standard/Premium 22.10.3（交错发布：2022 年 10 月 25 日至 27 日）

此版本将按照以下交错发布计划发布：

* **10 月 25 日**：欧洲、中东和非洲 (EMEA) 地区
* **10 月 26 日**：亚太 (APAC) 地区
* **10 月 27 日**：美洲地区

此版本包含以下新功能、增强和修复：

| 功能 | 详细信息 |
| --- | --- |
| [!DNL Recommendations] | 在 [!UICONTROL Analytics for Target] A4T 报表中添加了友好名称。[!DNL Target] 以前仅列出体验 ID。此增强使 [!DNL Adobe Analytics] 和 [!DNL Target] 之间的报表保持一致，并帮助客户简化在 A4T 中构建报表。(TGT-41853) |
| 为[!UICONTROL 自动分配]和[!UICONTROL 自动定位]<br>优化了 A4T 指标（可供某些客户进行测试。将在未来版本中提供给所有客户。） | 请注意以下更改：<ul><li>在[!UICONTROL 自动分配]和[!UICONTROL 自动定位]活动的[!UICONTROL 定位分析] A4T 报表中添加了对二进制和最大化指标的支持</li><li>保留现有活动的行为直至 2023 年 2 月。在此日期之后，将停止活动以强制现有活动迁移到新行为</li><li>从 2023 年 2 月 20 日开始，将不再支持 [!DNL Target] 活动中的 `averagetimespentonsite`、`bouncerate` 和 `entries` 指标。</li></ul> |

* 在 [!DNL Target] UI 中添加了工具提示以帮助客户更高效地在受众生成器中导航并了解如何使用可能不熟悉的功能。(TGT-44139)
* 添加了阻止客户编辑被 [!DNL Target] 禁用的活动（因为它使用不支持的指标）的功能。UI 中的一条消息指示客户重复该活动，然后更新转化指标。

   在此版本中，将为新活动弃用 [!DNL Target] 活动中的 `averagetimespentonsite`、`bouncerate` 和 `entries` 指标。现有活动可继续使用这些指标直至 2023 年 2 月。（TGT-43860、TGT-43861 和 TGT-43650）

* 在 [!DNL Target] UI 中添加了工具提示以帮助客户在创建或编辑使用 A4T 的[!UICONTROL 自动定位]活动时选择优化标准。(TGT-43713)

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |


## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
