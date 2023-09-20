---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解即将发布的 [!DNL Adobe Target]版本中包括的新功能、增强功能和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 6fa553c7179cd2a6d500bdc53cc77dc01ee906e7
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 95%

---

# [!DNL Target] 发行说明（预发行版本）

本文包含即将发布的 [!DNL Adobe Target] 版本的预发行信息，包括 SDK、API 和 JavaScript 库。

**上次更新日期：2023 年 9 月 18 日**

>[!NOTE]
>
>发布日期、功能及其他信息如有更改，恕不另行通知。
>
>要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target] Standard/Premium 23.9.3（2023 年 9 月 18 日）

此版本包含以下增强和修复：

* 增强了 [!UICONTROL 可视化体验编辑器] (VEC)支持Lightning Web Components (Light DOM)。 (TGT-45422)
* 修复了一个问题，该问题导致应用 VEC 操作的顺序有误。在某些情况下，VEC 异步地应用了某些修改，并且添加对某个元素的额外修改导致了错误（如果在[!UICONTROL 插入]操作后显示该元素）。还修复了在单击锚点链接时现在更新的VEC URL。 (TGT-45983)
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

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
