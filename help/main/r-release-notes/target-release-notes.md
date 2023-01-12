---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解 Adobe Target 即将发布的版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 02105c00a856e755ef2fd0bb41620fd35ed609d2
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 52%

---

# Target 发行说明（预发行版本）

本文包含预发行版本信息。发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新日期：2023 年 1 月 4 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target] Standard/Premium 22.13.3（2023 年 1 月 25 日至 26 日）

此版本包含以下新功能、增强和修复：

* 使用基于表单的体验编辑器在 [!UICONTROL Automated Personalization] (AP) 活动中添加了对 JSON 选件的支持。(TGT-41460)
* 已实施 [QA模式](/help/main/c-activities/c-activity-qa/activity-qa.md) （在AP活动中）。
* 中的体验名称 [!DNL Recommendations] 活动现在以友好名称显示，以便客户能够更好地将 [!DNL Adobe Analytics] 在 [!DNL Target] UI。 (TGT-41853)
* 修复了导致 [!UICONTROL A/B测试] 和 [!UICONTROL 体验定位] (XT)包含推荐的活动。 此问题是在 [!DNL Target] 未能从 [!DNL Target] UI和 [!DNL Recommendations] 后端。 (TGT-44383)
* 从 [!UICONTROL 选件级别] 报表 [!UICONTROL Automated Personalization] 活动。 此更改使报表更易读。 (TGT-44294)
* 已重命名“[!UICONTROL 体验片段]“ ”选项 [!UICONTROL 可视化体验编辑器] (VEC)工作流。 该选项现为“[!UICONTROL HTML XF]”。(TGT-44132)
* 添加了在选件信息工具提示中查看体验片段选件元数据的功能。(TGT-43838)
* 从 [!DNL Target] UI 中的 AP 和[!UICONTROL 自动目标][!UICONTROL 个性化洞察]和[!UICONTROL 重要属性]报告中删除了 45 天和 90 天日历选项。由于使用模式和为了提高性能，已弃用这些日期范围。UI 已更新，以反映当前允许的范围：15 天、30 天和 60 天。(TGT-39357)
* 不允许更改 [!UICONTROL 与优化目标相同] 设置 [!UICONTROL 目标和设置] 页面。 (TGT-43923)
* 修复了导致 [!DNL Target] 从升级 [!DNL Target Standard] to [!DNL Target Premium]. （TGT-44081 和 TGT-44306）
* 更改了 [!UICONTROL 实施] 页面([!UICONTROL 管理] > [!UICONTROL 实施])，以阅读“使用设备决策实施方法”，指向该页面，该页面说明如何对所有受支持的SDK使用设备决策：Node.js、Java、.NET和Python。 有关更多信息，请参阅 [Target SDK快速入门](https://developer.adobe.com/target/implement/server-side/sdk-guides/getting-started/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.
* 修复了在使用 [!DNL Scene7] 和 [!DNL Target].
* 增强了 [!DNL Target] 使用内部可用性审核结果为残障人士提供UI。 这些辅助功能增强功能包括：访问以前无法通过键盘访问的功能、替换文本增强功能、缩放UI部分以使用的功能、改进键盘焦点等。   (TGT-42759)
* 在 [!DNL Target] UI。

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |


## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
