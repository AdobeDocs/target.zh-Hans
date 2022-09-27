---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解 Adobe Target 即将发布的版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 07d71ccf934a1c638c37285372c3ec3199ec2000
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 32%

---

# Target 发行说明（预发行版本）

本文包含预发行版本信息。发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新日期：2022 年 7 月 9 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target] Standard/Premium 22.10.1（错开发行，2022年10月4日至6日）

此版本将按照以下交错发布计划发布：

* **10月4日**:欧洲、中东和非洲(EMEA)地区
* **10月5日**:亚太地区
* **10月6日**:美洲地区

此版本包含以下新增功能、增强功能和修复：

| 功能 | 详细信息 |
| --- | --- |
| 新建 [!UICONTROL 可视化体验编辑器] 适用于Google Chrome的扩展 | 新 [!DNL Adobe Target] [!UICONTROL 可视化体验编辑器] (VEC)Chrome扩展可在Chrome网上应用店中获取。<br>自2023年1月起， [!DNL Target] VEC助手扩展将停止在Google Chrome中工作，因为Google不允许使用清单V2的扩展。 下载新扩展以继续在 [!DNL Target] 从新年开始。 |
| 针对 [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位]<br>（确切的发行日期待定。） | 请注意以下更改：<ul><li>在 [!UICONTROL Analytics for Target] 适用于的A4T报表 [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位] 活动</li><li>删除了 [!UICONTROL 自动定位] 活动</li><li>保留现有活动的行为，直到2023年2月20日。 在此日期之后，将停止活动以强制现有活动迁移到新行为</li><li>自2023年2月20日起，支持 `averagetimespentonsite`, `bouncerate`和 `entries` 量度 [!DNL Target] 活动将被弃用。</li></ul> |

* 修复了受众规则信息无法在 [!UICONTROL 受众细化] 信息窗口。 (TGT-43917)
* 改进了 [!DNL Target] 加载接近 [建议的定位规则限制](/help/main/r-troubleshooting-target/target-limits.md#targeting-rules). (TGT-43675)
* 修复了导致某些组件无法在 [!UICONTROL 修改] 面板 [!UICONTROL 体验] 从 [!UICONTROL 撰写] to [!UICONTROL 浏览] 模式。 (TGT-43300)
* 修复了阻止某些客户存档的问题 [!UICONTROL A/B测试] 使用 [!UICONTROL 自动定位]. (TGT-40978)
* 添加了在单个报表组中的多个位置自动使用单个选件的功能。 (TGT-43974)
* 在 [!UICONTROL 选件] 列表。 (TGT-43121)
* 修复了允许客户插入JSON的问题 [!UICONTROL 体验片段] 选件。 JSON选件只能使用 [!UICONTROL 基于表单的体验] 编辑器。 (TGT-43846)

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
