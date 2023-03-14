---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解 Adobe Target 即将发布的版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 8cdf362d9e45153b26bca5a45ed59ef557adc016
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Target 发行说明（预发行版本）

本文包含预发行版本信息。发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新日期：2023 年 14 月 3 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target] Standard/Premium 22.15.1（2023 年 3 月 8 日和 9 日）

将按以下交错的时间表发布此版本：

* **3 月 8 日**：美洲地区
* **3 月 9 日**：欧洲、中东和非洲 (EMEA) 地区
* **3 月 9 日**：亚太 (APAC) 地区

此版本包含以下新功能、增强和修复：

| 功能 | 详细信息 |
| --- | --- |
| 为[!UICONTROL 自动分配]和[!UICONTROL 自动定位]优化了 A4T 指标 | 通过 [!DNL Target]，可在使用 [!UICONTROL A4T] 进行[!UICONTROL 自动分配]和[!UICONTROL 自动定位]活动时，根据二项式事件或连续事件选择指标。<P>请注意，在支持的指标中发生了以下变化：<ul><li>[!DNL Target] 保留现有活动以前的行为直至（待定日期）。在此日期之后，将不再继续执行使用不支持的指标的活动，以强制现有活动采用新行为。</li></ul>有关更多信息，请参阅&#x200B;*自动分配和自动定位活动支持 A4T* 中的[支持的目标指标](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#supported)。 |
| 使用 [!UICONTROL Analytics for Target (A4T)] 进行的[!UICONTROL 自动分配] | 新的教程：<ul><li>[在  [!DNL Analysis Workspace]  中为[!UICONTROL 自动分配]活动设置 A4T 报表](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank}</li></ul> |
| 使用 [!UICONTROL Analytics for Target (A4T)] 进行的[!UICONTROL 自动定位] | 新的教程：<ul><li>[在  [!DNL Analysis Workspace]  中为[!UICONTROL 自动定位]活动设置 A4T 报表](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html){target=_blank}</li></ul> |

此版本包含以下修复：

* 更新了自定义Web组件创作 [!UICONTROL 可视化体验编辑器] (VEC)：

   * 通过改进创作过程修复了VEC中的影子DOM元素选择，因此不依赖于 [!DNL Target] 创作影子根目录时的实施类型。 现在，在VEC中选择影子DOM元素应该适用于任何网站。
   * 修复了导致无法在VEC中使用DOM加载HTML元素#Shadow问题。 (TGT-35801)
   * 修复了使用ShadowDOM的SPA网站的VEC问题。 (TGT-43169)
   * 修复了优化目标“单击了某个元素”的问题，该问题未能正确识别ShadowDOM中的CSS选择器。

>[!NOTE]
>
>要确保交付在VEC中创作的更改，请确保您使用的是 [!DNL Target] SDK ([at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} or [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html){target=_blank} (alloy.js))，版本高于2.8。

**已知问题**：使用时对影子根元素进行点击跟踪 [!DNL Adobe Experience Platform Web SDK] 无法正常工作。 (TNT-47012)

## at.js 版本 2.10.2（2023 年 3 月 7 日）

* 修复了导致 `trackEvent` 函数始终返回错误的问题。

有关所有 at.js 版本的信息，请参阅 [at.js 版本详细信息](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}。

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |


## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
