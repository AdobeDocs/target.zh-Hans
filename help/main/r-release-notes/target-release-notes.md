---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解 Adobe Target 即将发布的版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: e458793e4d0110d97f3f5124cbe6e54520d3f0e9
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 55%

---

# Target 发行说明（预发行版本）

本文包含预发行版本信息。发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新日期：2023 年 8 月 3 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target] Standard/Premium 22.15.1（2023年3月8日和9日）

将按以下交错的时间表发布此版本：

* **3月8日**：美洲区域
* **3月9日**：欧洲、中东和非洲(EMEA)区域
* **3月9日**：亚太(APAC)区域

此版本包含以下新增功能和增强功能：

| 功能 | 详细信息 |
| --- | --- |
| 优化了A4T指标 [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位] | [!DNL Target] 允许您在使用时，选择基于二项式事件的量度或基于连续事件的量度 [!UICONTROL A4T] 对象 [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位] 活动。<P>请注意支持的量度中的以下更改：<ul><li>[!DNL Target] 保留现有活动的先前行为，直到（日期待定）。 在此日期之后，将停止使用不受支持的指标的活动，以强制现有活动迁移到新行为。</li></ul>有关更多信息，请参阅 [支持的目标量度](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#supported) 在 *自动分配和自动定位活动支持A4T*. |
| [!UICONTROL 自动分配] 使用 [!UICONTROL 目标分析] (A4T) | 新教程：<ul><li>[在中设置A4T报表 [!DNL Analysis Workspace] 对象 [!UICONTROL 自动分配] 活动](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank}</li></ul> |
| [!UICONTROL 自动定位] 使用 [!UICONTROL 目标分析] (A4T) | 新教程：<ul><li>[在中设置A4T报表 [!DNL Analysis Workspace] 对象 [!UICONTROL 自动定位] 活动](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html){target=_blank}</li></ul> |

## at.js 版本 2.10.2（2023 年 3 月 7 日）

* 修复了导致 `trackEvent` 函数始终返回错误。

有关所有 at.js 版本的信息，请参阅 [at.js 版本详细信息](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}。

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |


## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
