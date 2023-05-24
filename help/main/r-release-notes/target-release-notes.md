---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解即将发布的 [!DNL Adobe Target]版本中包括的新功能、增强功能和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: ecdb94a679e033d3ec030513fd66c9eea039195b
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 72%

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
* 修复了在图像名称包含 GB 18030 个字符时组织图像在[!UICONTROL 创建设计]面板中显示的问题。(TGT-44614)
* 修复了导致[!UICONTROL 自动个性化]活动的报告在分析过程中冻结的问题。(TGT-44820)
* 修复了导致某些客户的默认工作区的Target UI中不显示任何活动的问题。 (TGT-45286)
* 更新了“不允许重复项”标记的行为。 排除的重复选件标记已更新，如果重复选件是默认内容选件（适用于API v3、v4），则允许重复选件；如果选项引用默认内容选件且未定义模板，则允许重复选项。 (TNT-46617)
* 修复了向URL添加查询参数导致页面无法在可视化体验编辑器(VEC)中加载的问题。 (TGT-44873)
* 修复了体验中的文本/HTML中某些字符被错误转义的问题。 (TGT-44600)

## [!DNL Target]Standard/Premium 23.5.3（日期待定）

此版本包含以下增强功能：

| 功能 | 详细信息 |
|--- |--- |
| [!UICONTROL Automated Personalization] 活动的[!UICONTROL 质检模式] | [!DNL Adobe Target][!UICONTROL 质检模式]现在可用于 [!UICONTROL Automated Personalization] 活动，以更换[!UICONTROL 预览链接]功能。<P>有关更多信息，请参阅[活动 QA](/help/main/c-activities/c-activity-qa/activity-qa.md)。。 |
| 与 [!DNL Target] 共享的 Real-Time CDP 配置文件属性 | Real-Time CDP 配置文件属性可以共享给 [!DNL Target]，用于 HTML 选件和 JSON 选件。<P>有关更多信息，请参阅 [与  [!DNL Target]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#rtcdp-profile-attributes) 共享 Real-Time CDP 配置文件属性。 |

* 性能增强，不允许重复项功能（包括减少加载时间），同时 [管理排除项](/help/main/c-activities/t-automated-personalization/managing-exclusions.md#concept_4EF78013F80E48EFA024AE0274C9F037) 在 [!UICONTROL Automated Personalization] 活动。

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
