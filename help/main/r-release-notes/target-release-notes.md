---
keywords: 发行说明；版本；更新；未来版本；增强；新功能；修复；更新；预发行；抢先体验
description: 了解即将发布的 [!DNL Adobe Target]版本中包括的新功能、增强功能和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 2e3191da2ac21f51fa6e08af615659db1ccdd2d9
workflow-type: tm+mt
source-wordcount: '744'
ht-degree: 27%

---

# [!DNL Target] 发行说明（预发行版本）

本文包含即将发布的 [!DNL Adobe Target] 版本的预发行信息，包括 SDK、API 和 JavaScript 库。

**上次更新日期：2025年4月10日**

>[!NOTE]
>
>发布日期、功能及其他信息如有更改，恕不另行通知。
>
>要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target Standard/Premium] 25.4.3（2025年4月10日）

此版本包含以下修复和更新：

* 修复了阻止客户打开某些[!UICONTROL Experience Targeting] (XT)活动的受众信息弹出窗口的错误。 (TGT-52049)
* 修复了阻止客户在默认工作区中插入[!UICONTROL Experience Fragment]的问题。 (TGT-52073)
* 修复了选件显示为“找不到内容”并且未在[!UICONTROL Automated Personalization] (AP)活动的[!UICONTROL Offers]页面上显示的问题。 (TGT-52150)
* 添加了在活动中允许重复受众的功能。 (TGT-51200)
* 修复了在编辑后XT活动的[!UICONTROL Goals & Settings]页面上显示错误的mbox名称的问题。 (TGT-52026)
* 修复了`defaultContent`尽管不在`experiences/optionLocations`中，却显示在选项中的问题。 (TGT-52036)
* 修复了一个问题，以确保未将空字符串转换为null值。 (TGT-52037)
* 修复了要求客户在编辑[!UICONTROL Goals & Settings]页面上的[!UICONTROL Reporting Settings]中重新配置[!UICONTROL Optimization Goal]的问题。 (TGT-52071)
* 修复了没有页面交付规则的活动在[!UICONTROL Overview]页面上显示多个规则的问题。 (TGT-52084)
* 为尝试保存包含基本多语言平面以外的字符（如表情符号）的选件的用户添加了错误消息。 (TGT-52105)
* 修复了打开活动时触发错误消息“此活动使用一个或多个在源中删除的受众”的问题。 (TGT-52120)
* 修复了在编辑期间更新的[!UICONTROL Visual Experience Composer] (VEC)中未显示ClickTrack量度的问题。 (TGT-52152)
* 修复了将查询参数作为活动位置的URL未在活动的[!UICONTROL Overview]页面上显示查询参数的问题。 (TGT-51635)
* 修复了导致整个体验URL无法在[!UICONTROL Visual Experience Composer] (VEC)的[!UICONTROL Browse mode]中显示的问题。 (TGT-52101)
* 修复了编辑活动导致页面交付在URL末尾添加“/”使其无效的问题。 (TGT-52114)
* 修复了[!UICONTROL Form-Based Experience Composer]中的[!UICONTROL Activity QA]链接被错误地重定向到[!DNL Adobe Experience Cloud]主页的问题。 (TGT-52055)
* 修复了在保存并重新打开后未保留添加到[!UICONTROL A/B Test]活动中的其他页面的问题。 (TGT-51994)
* 修复了阻止客户删除内联样式部分中的样式的问题。 (TGT-52070)
* 类似于旧版UI，已恢复对[!UICONTROL Activity QA]对话框中的[受众定义卡片](/help/main/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780)的访问。 (TGT-52056)
* 更新后的UI未保存未经修改的页面或受众。 如果客户向活动添加新页面或受众，但没有对它们进行更改，则[!DNL Target]会在保存时丢弃未修改的受众。 已在相关位置添加了通知，以告知用户此行为。 (TGT-52104)

## [!DNL Target Standard/Premium] 25.4.4（2025年4月15日）

此版本包含以下修复和更新：

* 添加了错误消息，以指导用户解决活动中的重复选项。 (TGT-51927)
* 修复了在删除具有重定向选件的页面或体验时未删除ClickTrack选择器的问题。 (TGT-51952)
* 修复了[!DNL Target]在活动URL中无法正确检测“#”字符的问题。 (TGT-52093)
* 修复了在[!UICONTROL Automated Personalization] (AP)活动中编辑选件级别定位时受众定义不可见的问题。 (TGT-52148)
* 修复了在UI中反转受众细化和活动定位受众的问题。 (TGT-52158)

## Target权限更新（2025年4月22日）

此未来更新增强了组织对[!DNL Target]实例配置的控制，防止了可能影响不同测试和个性化团队之间活动交付的意外更新。

自2025年4月22日起，仅[!UICONTROL Product]和[!UICONTROL Solutions]管理员能够更新[!UICONTROL Administration]部分中的设置，无论他们在[!DNL Target]工作区中的角色如何。 没有此权限的用户将具有[!UICONTROL Administration]部分的只读访问权限。

有关详细信息，请参阅[管理Target](/help/main/administrating-target/start-target.md)。

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
