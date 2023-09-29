---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解即将发布的 [!DNL Adobe Target]版本中包括的新功能、增强功能和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 2e15709ac2a34a96dbc632c71f400c2575d74cf4
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 75%

---

# [!DNL Target] 发行说明（预发行版本）

本文包含即将发布的 [!DNL Adobe Target] 版本的预发行信息，包括 SDK、API 和 JavaScript 库。

**上次更新日期：2023 年 9 月 29 日**

>[!NOTE]
>
>发布日期、功能及其他信息如有更改，恕不另行通知。
>
>要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target] Standard/Premium 23.9.4（2023年10月2日至4日）

将按以下交错的时间表发布此版本：

* **10 月 2 日**：欧洲、中东和非洲 (EMEA) 地区
* **10 月 3 日**：美洲地区
* **10 月 4 日**：亚太 (APAC) 地区

此版本包含以下增强和修复：

| 功能 | 详细信息 |
| --- | --- |
| [!UICONTROL 活动] UI刷新<P>和<P>[!UICONTROL 信息源] UI刷新 | 作为 [!DNL Adobe Target] 团队为改善的用户体验而不断努力的成果 [!DNL Target] 用户时，此版本会刷新 [!UICONTROL 活动] 和 [!DNL Recommendations] [!UICONTROL 信息源] 中的页面 [!DNL Target] UI。 此更新统一并标准化了以前不一致的设计模式，同时添加了新的增强功能。<P>有关详细信息，请参阅 [活动](/help/main/c-activities/activities.md) 和 [信息源](/help/main/c-recommendations/c-products/feeds.md). |
| [!DNL Recommendations] 实现模式 | 此 *使用at.js的Recommendations实施模式* 文章可帮助您了解和创建 [!DNL Adobe Target Recommendations] 在使用at.js JavaScript库时实施。<P>有关Target模式的一般信息，请参阅 [实施模式概述](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/pattern-overview.html){target=_blank} 在 *Adobe Target开发人员指南*.<P>新的Recommendations实施模式由以下文章组成：<ul><li>[使用at.js的Recommendations实施模式概述](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/recs-implementation-pattern-atjs.html){target=_blank}</li><ul><li>[初始化SDK](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/initialize-sdk.html){target=_blank}</li><li>[配置数据收集](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/data-collection.html){target=_blank}</li><li>[渲染体验](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/render-experiences.html?lang=en){target=_blank}</li><li>[通知 [!DNL Target]](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/notify-target.html?lang=en){target=_blank}</li></ul></ul> |

* 已添加 [!UICONTROL 可视化体验编辑器] (VEC)增强了动态框架。 (TGT-44064)
* 修复了导致在 `getViewInAnalyticsId` 请求不正确更新。 此修复帮助重新计算 [!DNL Analytics] 日期范围和量度报表设置发生更改时报告中的链接。 (TGT-46246)

## [!DNL Target] Standard/Premium 23.9.3（2023 年 9 月 18 日）

此版本包含以下增强和修复：

* 增强了[!UICONTROL 视觉体验编辑器] (VEC) 以支持 Lightning Web 组件 (Light DOM)。(TGT-45422)
* 修复了一个问题，该问题导致应用 VEC 操作的顺序有误。在某些情况下，VEC 异步地应用了某些修改，并且添加对某个元素的额外修改导致了错误（如果在[!UICONTROL 插入]操作后显示该元素）。还修复了现在单击锚点链接时更新的 VEC URL。(TGT-45983)
* 修复了有关 VEC [!UICONTROL 叠加]功能的问题，此功能现在支持 Shadow DOM 中的元素。（TGT-45202 和 TGT-45262）
* 修复了一个问题，在 VEC 中打开单页面应用程序 (SPA) 页面，然后转到[!UICONTROL 浏览]模式时，该问题导致“后退”和“前进”箭头无法正常工作。(TGT-45956)
* 修复了导致某些网页无法在 VEC 中加载的问题。(TGT-45983)

## [!DNL Target] Standard/Premium 23.9.2（2023 年 9 月 12 日至 14 日）

将按以下交错的时间表发布此版本：

* **9 月 12 日**：美洲地区
* **9 月 13 日**：亚太 (APAC) 地区
* **9 月 14 日**：欧洲、中东和非洲 (EMEA) 地区

此版本包含以下增强和修复：

* 将 [!DNL Analytics] API 改为新的 [!DNL Analytics] API 2.0 版本。(TGT-45345)
* 修复了影响某些客户的 [!UICONTROL Automated Personalization] (AP) 活动的问题，包括及时同步 [!DNL Target] 后端上的活动以及在预览链接中投放预期的体验。(TGT-46202)

## [!DNL Target] Standard/Premium 23.9.1（2023 年 9 月 6 日至 11 日）

将按以下交错的时间表发布此版本：

* **9 月 6 日**：美洲地区
* **9 月 7 日**：欧洲、中东和非洲 (EMEA) 地区
* **9 月 11 日**：亚太 (APAC) 地区

此版本包含以下增强和修复：

* 修复了一个问题，该问题导致将 [!UICONTROL Analytics for Target] (A4T) 用作报告源的[!UICONTROL 自动分配]活动在 [!DNL Target] UI 和 [!DNL Adobe Analytics] UI 中的报告数据不一致。(TGT-46112)
* 将 PUT 调用目标投放 API 的超时延长到 15 秒以免发生超时错误。(TGT-46091)
* 修复了一个问题，在浏览单页面应用程序 (SPA) 网站时，该问题阻止一致地更新 URL。(TGT-45417)

## [!DNL Target] Standard/Premium 23.5.2（日期待定）

此版本包含以下增强和修复：

* 已为 [!DNL Adobe Analytics] 量度启用优化标准选择。
* 已启用使用 Sling 作业的外部受众同步。
* 已修复不支持名称中包含点字符的 SC 报表包的问题。
* 已启用可让客户删除和编辑内置受众的功能。

## [!DNL Target] Standard/Premium 23.5.3（日期待定）

此版本包含以下增强功能：

| 功能 | 详细信息 |
|--- |--- |
| [!UICONTROL Automated Personalization] 活动的 [!UICONTROL QA 模式] | [!DNL Adobe Target] [!UICONTROL QA 模式]现在取代[!UICONTROL 预览链接]功能，可供 [!UICONTROL Automated Personalization] 活动使用。<P>有关更多信息，请参阅[活动 QA](/help/main/c-activities/c-activity-qa/activity-qa.md)。。 |

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
