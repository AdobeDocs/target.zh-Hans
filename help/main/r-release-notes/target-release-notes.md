---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解 Adobe Target 即将发布的版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 62b0c6ca313ab5990b5e0bc6d33e913fd0bdd5ef
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 92%

---

# Target 发行说明（预发行版本）

本文包含预发行版本信息。发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新日期：2023 年 1 月 26 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target] Standard/Premium 22.13.3（2023 年 1 月 25 日至 26 日）

此版本将按照以下交错发布计划发布：

* **1月25日**:欧洲、中东和非洲(EMEA)地区
* **1月25日**:亚太地区
* **1月26日**:美洲地区

此版本包含以下新功能、增强和修复：

| 功能 | 详细信息 |
| --- | --- |
| [JSON选件](/help/main/c-experiences/c-manage-content/create-json-offer.md) 在Automated Personalization支持(AP) | 使用基于表单的体验编辑器在 [!UICONTROL Automated Personalization] (AP) 活动中添加了对 JSON 选件的支持。(TGT-41460) |
| [AEM 体验片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) | 添加了区分导出到 [!DNL Target] 的 [!DNL Adobe Experience Manager] 片段 (AEM XF) 类型的功能。[!DNL Target] 现在允许您按“HTML XF”和“JSON XF”过滤和搜索，而不是“体验片段”选项。(TGT-44132) |

* 修复了在 [!UICONTROL A/B 测试]和 [!UICONTROL Experience Targeting] (XT) 活动中导致“500 错误”的问题，并包含建议。当 [!DNL Target] 无法从 [!DNL Target] UI 和 [!DNL Recommendations] 后端正确删除不再使用的条件对象时，会导致此问题。(TGT-44383)
* 从 [!UICONTROL Offer Level] 报告中为 [!UICONTROL Automated Personalization] 活动显示的优惠名称中删除了位置。此更改使报告更具可读性。(TGT-44294)
* 从 [!DNL Target] UI 中的 AP 和[!UICONTROL 自动目标][!UICONTROL 个性化洞察]和[!UICONTROL 重要属性]报告中删除了 45 天和 90 天日历选项。由于使用模式和为了提高性能，已弃用这些日期范围。UI 已更新，以反映当前允许的范围：15 天、30 天和 60 天。(TGT-39357)
* 禁用了在活动上线后更改[!UICONTROL 目标和设置]页面上的[!UICONTROL 与优化目标相同]设置的功能。(TGT-43923)
* 修复了从 [!DNL Target Standard] 升级到 [!DNL Target Premium] 时导致 [!DNL Target] 后端默认工作区出现问题的情况。（TGT-44081 和 TGT-44306）
* 进行了更改以允许 [!DNL Analytics] 包含点字符“”的报表包。 在他们的名字中 [!DNL Target] 用于创建的UI [!DNL Analytics] 分类信息源。
* 更改了[!UICONTROL 实施]页面（[!UICONTROL 管理]>[!UICONTROL 实施]）上“设备上决策的实现方法”的链接，使其指向说明如何为所有受支持的 SDK（Node.js、Java、.NET 和 Python）使用设备上决策的页面。有关更多信息，请参阅 [Target SDK 快速入门](https://developer.adobe.com/target/implement/server-side/sdk-guides/getting-started/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}。
* 修复了使用 [!DNL Scene7] 和 [!DNL Target] 时导致文件上传问题的情况。
* 通过使用内部可用性审计的结果，增强了 [!DNL Target] UI 对残障人士提供的可访问性。这些增强的辅助功能包括访问以前无法通过键盘访问的功能、替代文本增强功能、缩放 UI 部分以提高可用性的能力、改进键盘焦点等等。(TGT-42759)
* 对整个 [!DNL Target] UI 进行了各种本地化修复。

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |


## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
