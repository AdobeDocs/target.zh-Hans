---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解即将发布的 [!DNL Adobe Target]版本中包括的新功能、增强功能和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 8da8daf7da0cfe3e4936cb48b4c594c464708775
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# [!DNL Target] 发行说明（预发行版本）

本文包含即将发布的 [!DNL Adobe Target] 版本的预发行信息，包括 SDK、API 和 JavaScript 库。

**上次更新日期：2023 年 9 月 4 日**

>[!NOTE]
>
>发布日期、功能及其他信息如有更改，恕不另行通知。
>
>要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target] Standard/Premium 23.9.1（2023年9月6日至11日）

将按以下交错的时间表发布此版本：

* **9 月 6 日**：美洲区域
* **9 月 7 日**：欧洲、中东和非洲 (EMEA) 区域
* **9 月 11 日**：亚太 (APAC) 区域

此版本包含以下增强和修复：

* 修复了导致中报表数据不一致的问题 [!DNL Target] UI和 [!DNL Adobe Analytics] 的UI [!UICONTROL 自动分配] 使用的活动 [!UICONTROL 目标分析] (A4T)作为报表源。 (TGT-46112)
* 将Target投放API的PUT调用超时增加到15秒，以避免超时错误。 (TGT-46091)
* 修复了在以下各项之间切换时显示错误报表名称的问题 [!UICONTROL 表格视图] 和 [!UICONTROL 自动化区段] 和 [!UICONTROL 重要属性] 报表。 (TGT-46040)
* 增强了 [!UICONTROL 可视化体验编辑器] (VEC)支持Lightning DOM（Web组件）。 (TGT-45422)
* 修复了导致VEC操作应用顺序不正确的问题。 在某些情况下，VEC异步应用了一些修改，如果某个元素在 [!UICONTROL 插入] 操作。 (TGT-45983)
* 修复了在VEC中打开单页应用程序(SPA)页面，然后转到“浏览”模式时导致“后退”和“前进”箭头无法正常运行的问题。 (TGT-45956)
* 修复了在浏览单页应用程序(SPA)网站时阻止URL一致更新的问题。 (TGT-45417)

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
