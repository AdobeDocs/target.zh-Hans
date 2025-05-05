---
keywords: 发行说明；新功能；版本；更新；更新；版本；增强；增强；修复；错误修复；更新、当前更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 579ebd9bebd3faa724f0d1d542f4d23766adefe3
workflow-type: tm+mt
source-wordcount: '1677'
ht-degree: 24%

---

# [!DNL Target]发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的发行说明以及其他平台变更。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## [!DNL Target Standard/Premium] 25.4.5（2025年4月25日）

此版本包含以下修复和更新：

* 修复了导致[!UICONTROL Activity]设置页面和[!UICONTROL Reporting]概述页面之间的受众列表不一致的问题。 (TGT-52203)
* 修复了由于无效的用户输入错误而阻止向活动添加新页面的问题。 (TGT-52263)
* 修复了在选项保持不变时导致`OptionLocalIDs`错误递增的问题。 (TGT-52187)
* 修复了在选项保持不变时导致`location`和`OptionLocalIDs`错误递增的问题。 (TGT-52188)
* 修复了导致活动[!UICONTROL Overview]页面上的位置不正确的问题。 (TGT-52182)
* 修复了针对无效位置未显示无效选择器警告的问题。 (TGT-52110)
* 修复了一个问题，以便下载的报表文件正确显示报表UI中存在的数据。 (TGT-52068)
* 修复了一个问题，以便在添加页面交付规则后批量操作不会失败。 (TGT-52097)
* 修复了导致[!DNL Target]从网站URL中修剪所有查询参数的问题。 (TGT-52100)
* 解决了阻止客户在旧版和更新的[!DNL Target] UI中创建活动的控制台错误。 (TGT-52181)
* 修复了阻止客户添加新页面，从而导致无效用户输入错误的问题。 (TGT-52258)
* 修复了在添加其他页面然后导航回[!UICONTROL Experiences]选项卡后导致修改消失的问题。 (TGT-52264)
* 修复了阻止客户更改[!UICONTROL Experience Targeting] (XT)活动中的受众的问题。 (TGT-52191)
* 修复了由于不支持的UI规则而阻止编辑XT活动的错误。 (TGT-52273)
* 修复了更新的[!UICONTROL Visual Experience Composer] (VEC)中的问题，该问题导致痕迹导航不始终显示在编辑器底部，从而难以准确地选择元素。 (TGT-52169)
* 修复了[!UICONTROL Audience]下拉列表因分页而无法显示所有受众的问题。 (TGT-52204)
* 修复了在[!UICONTROL Automated Personalization] (AP)活动中添加新选件时导致用户输入消息无效的问题。 (TGT-52210)
* 修复了以下问题：[!UICONTROL Analytics for Target] (A4T)被错误地选为报表源，即使客户无权访问A4T。 (TGT-52226)
* 修复了阻止使用[!UICONTROL View a Page] URL量度保存活动的问题。 (TGT-52260)
* 修复了一个问题，该问题阻止客户在活动中创建优惠时选择工作区。 (TGT-52289)
* 修复了阻止客户在所有工作区中创建活动的问题。 (Tgt-52218)
* 修复了在切换到另一个体验时，某个体验中的修改无法正确显示的问题。 (TGT-52184)
* 修复了在打开活动时[!DNL Target] UI中错误显示默认选件的问题。 (TGT-52198)

## Target权限更新（2025年4月22日）

此未来更新增强了组织对[!DNL Target]实例配置的控制，防止了可能影响不同测试和个性化团队之间活动交付的意外更新。

自2025年4月22日起，仅[!UICONTROL Product]和[!UICONTROL Solutions]管理员能够更新[!UICONTROL Administration]部分中的设置，无论他们在[!DNL Target]工作区中的角色如何。 没有此权限的用户将具有[!UICONTROL Administration]部分的只读访问权限。

有关详细信息，请参阅[管理Target](/help/main/administrating-target/start-target.md)。

## [!DNL Target Standard/Premium] 25.4.4（2025年4月17日）

此版本包含以下修复和更新：

* 添加了错误消息，以指导用户解决活动中的重复选项。 (TGT-51927)
* 修复了在删除具有重定向选件的页面或体验时未删除`ClickTrack`选择器的问题。 (TGT-51952)
* 修复了允许空`ClickTrack`选择器导致的问题。 [!DNL Target]现在要求选择器字段不能为空。 (TGT-52107)
* 修复了错误地允许具有重复名称的量度的问题。 指标现在需要唯一名称。 (TGT-52201)
* 修复了在[!UICONTROL Automated Personalization] (AP)活动中编辑选件级别定位时受众定义不可见的问题。 (TGT-52148)
* 修复了阻止具有[!UICONTROL Editor]权限的客户保存活动的问题。 (TGT-52227)
* 当选项保持不变时，`OptionLocalIDs`不再错误地增加。 (TGT-52139)
* 修复了在尝试创建活动时导致“无效的`optionLocalIds`”消息的问题。 (TGT-52154)
* 为活动定义的`OptionLocalIDs`与用于定义体验的之间的差异已修复。 (TGT-52215)
* 修复了在尝试创建A/B活动时导致验证失败的问题。 (TGT-51923)

## [!DNL Target Standard/Premium] 25.4.3（2025年4月11日）

此版本包含以下修复和更新：

* 修复了阻止客户打开某些[!UICONTROL Experience Targeting] (XT)活动的受众信息弹出窗口的错误。 (TGT-52049)
* 修复了在[!UICONTROL Visual Experience Composer] (VEC)中进行更改后，受众设置恢复为“[!UICONTROL All Visitors]”的问题。 (TGT-52132)
* 修复了未针对特定活动显示受众细化的问题(TGT-52057)
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

## [!DNL Target Standard/Premium] 25.4.1（2025年4月2日）

此版本包含以下修复和更新：

* 修复了导致体验受众从活动中消失的问题。 (TGT-52003)
* 修复了在投放期间导致出现意外元素的问题。 (TGT-52011)
* 修复了阻止客户在Ove[!UICONTROL r]视图页面的定位图形中以及活动编辑期间查看受众的问题。 (TGT-52050)
* 修复了一个问题，该问题阻止客户在[!UICONTROL Experience Targeting] (XT)活动中按优先级重新排序体验。 (TGT-52054)
* 修复了在撤消文本样式更改时导致呈现不正确的问题。 (TGT-51876)
* 修复了在修改重定向选件时，[!DNL Target]还会删除与该选件关联的所有[!UICONTROL ClickTrack]选择器的问题。 (TGT-51936)
* 修复了在取消[!UICONTROL ClickTrack]时导致[!DNL Target]错误保存选择器的问题。 (TGT-51937)
* 修复了在未进行任何更改的情况下打开和关闭[!UICONTROL Goals & Settings]页面上的mbox选取器后触发无效名称错误的问题。 (TGT-51983)
* 修复了阻止编辑在旧版[!DNL Target] UI中创建的临时优惠的问题。 (TGT-51984)
* 修复了阻止编辑具有包含自定义代码的临时选件的活动的问题。 (TGT-51995)
* 修复了在编辑组合受众定义时导致排除规则显示为包含规则的问题。 (TGT-51999)
* 修复了在体验编辑期间阻止自定义代码正确显示的问题。 (TGT-52005)
* 修复了[!UICONTROL Insert Before]选项无法用于在导航栏之前插入内容的问题。 (TGT-52031)
* 修复了导致无法在报告中正确突出显示默认体验的问题。 (TGT-51716)
* 修复了在创建活动时触发`default message [Invalid optionLocalIds: xx]]`消息的问题。 (TGT-52038)

## at.js版本2.11.8（2025年3月31日）

* 解决了字符串后缀验证中CodeQL识别的漏洞，以防止在调整大小和移动操作期间出现边缘情况。 (TNT-51516)

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=zh-Hans){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 文档更改、以往的发行说明和 Experience Cloud 发行说明

除了针对每个发行的说明外，以下资源还提供更多其他信息：

| 资源 | 详细信息 |
|--- |--- |
| [文档更改](/help/main/r-release-notes/doc-change.md) | 查看这些发行说明中未包括的关于本指南的更新的详细信息。 |
| [以前版本的发行说明](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 | 查看与以前版本的 Target Standard 和 Target Premium 中的新增功能和增强功能相关的信息。 |
| [Adobe Experience Cloud发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans){target=_blank} | 查看 Adobe Experience Cloud 解决方案的最新发行说明。 |

## 预发行信息 {#section_5D588F0415A2435B851A4D0113ACA3A0}

您可以通过以下资源了解下一个 Target 版本即将包含的功能。

| 资源 | 详细信息 |
|--- |--- |
| [Adobe 优先产品更新](https://www.adobe.com/cn/subscription/priority-product-update.html){target=_blank} | 提前收到有关 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案的即将发行产品增强功能的通知。 |
| [Target 发行说明 - 预发行版本](/help/main/r-release-notes/target-release-notes.md){target=_blank} | 有关当月的 Target 版本的信息，包括预发行信息。 |
