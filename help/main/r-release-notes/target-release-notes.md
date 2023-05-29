---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解即将发布的 [!DNL Adobe Target]版本中包括的新功能、增强功能和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: ecdb94a679e033d3ec030513fd66c9eea039195b
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 100%

---

# [!DNL Target] 发行说明（预发行版本）

本文包含即将发布的 [!DNL Adobe Target] 版本的预发行信息，包括 SDK、API 和 JavaScript 库。

**上次更新日期：2023 年 5 月 24 日**

>[!NOTE]
>
>发布日期、功能及其他信息如有更改，恕不另行通知。
>
>要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target] Standard/Premium 23.5.2（2023 年 5 月 31 日）

此版本包含以下增强功能和修复：

* 修复了导致在生成配置文件 API 授权令牌时显示空白页面的问题。(TGT-45387)
* 修复了如果图像名称包含 GB 18030 个字符，阻止在[!UICONTROL 创建设计]面板中显示该图像的问题。(TGT-44614)
* 修复了导致反映在分析过程中 [!UICONTROL Auto Personalization] 活动停滞的问题。(TGT-44820)
* 修复了一个问题，该问题导致对于某些客户的默认工作区，在 Target UI 中不显示任何活动。(TGT-45286)
* 更新了“不允许重复”标志的行为。更新了被排除的重复优惠标志，以便可重复优惠（如果优惠为默认内容优惠（对于 API v3、v4））并可重复选项（如果选项引用默认内容优惠且未定义模板）。(TNT-46617)
* 修复了一个问题，在该问题中，将一个查询参数添加到 URL，导致无法加载在可视化体验编辑器 (VEC) 中加载该页面。(TGT-44873)
* 修复了一个问题，在该问题中，体验中的文本/HTML 中有一些字符转义不当。(TGT-44600)

## [!DNL Target] Standard/Premium 23.5.3（日期待定）

此版本包含以下增强功能：

| 功能 | 详细信息 |
|--- |--- |
| [!UICONTROL Automated Personalization] 活动的 [!UICONTROL QA 模式] | [!DNL Adobe Target] [!UICONTROL QA 模式]现在取代[!UICONTROL 预览链接]功能，可供 [!UICONTROL Automated Personalization] 活动使用。<P>有关更多信息，请参阅[活动 QA](/help/main/c-activities/c-activity-qa/activity-qa.md)。。 |
| 与 [!DNL Target] 共享的 Real-Time CDP 配置文件属性 | Real-Time CDP 配置文件属性可以共享给 [!DNL Target]，用于 HTML 选件和 JSON 选件。<P>有关更多信息，请参阅 [与  [!DNL Target]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#rtcdp-profile-attributes) 共享 Real-Time CDP 配置文件属性。 |

* 不允许在 [!UICONTROL Automated Personalization] 活动中[管理排除项](/help/main/c-activities/t-automated-personalization/managing-exclusions.md#concept_4EF78013F80E48EFA024AE0274C9F037)的同时使用重复功能，从而增强了性能（包括缩短了加载时间）。

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
