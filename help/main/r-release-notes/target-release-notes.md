---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解 Adobe Target 即将发布的版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 2c4f5666b65bfc36885aad3907639a309e8c69f2
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 59%

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

>[!NOTE]
>
>由于此后已修复的问题，针对以下项的“优化的A4T指标 [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位]3月8日和9日发行的功能已暂时删除。 经过进一步的内部测试后，该功能将在未来几周内再次发布。

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
