---
keywords: 发行说明；版本；更新；未来版本；增强；新功能；修复；更新；预发行；抢先体验
description: 了解即将发布的 [!DNL Adobe Target]版本中包括的新功能、增强功能和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 203c0ca94b198ee7ce8379731d31d32b27cb8a0d
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 30%

---

# [!DNL Target] 发行说明（预发行版本）

本文包含即将发布的 [!DNL Adobe Target] 版本的预发行信息，包括 SDK、API 和 JavaScript 库。

**上次更新日期：2025年4月2日**

>[!NOTE]
>
>发布日期、功能及其他信息如有更改，恕不另行通知。
>
>要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## Target权限更新（2025年4月22日）

此未来更新增强了组织对[!DNL Target]实例配置的控制，防止了可能影响不同测试和个性化团队之间活动交付的意外更新。

自2025年4月22日起，仅[!UICONTROL Product]和[!UICONTROL Solutions]管理员能够更新[!UICONTROL Administration]部分中的设置，无论他们在[!DNL Target]工作区中的角色如何。 没有此权限的用户将具有[!UICONTROL Administration]部分的只读访问权限。

有关详细信息，请参阅[管理Target](/help/main/administrating-target/start-target.md)。

## [!DNL Target Standard/Premium] 25.4.3（2025年4月10日）

此版本包含以下修复和更新：

* 修复了[!UICONTROL Form-Based Experience Composer]中的[!UICONTROL Activity QA]链接被错误地重定向到[!DNL Adobe Experience Cloud]主页的问题。 (TGT-52055)
* 添加了错误消息，以指导用户解决活动中的重复选项。 (TGT-51927)

## [!DNL Target Standard/Premium] 25.4.2（2025年4月8日）

此版本包含以下修复和更新：

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

<!-- 
## [!DNL Target Standard/Premium] 24.10.2 (October 21, 2024)

This release contains the following fixes:

* Fixed an issue that prevented [!UICONTROL Recommendations] activities from loading in [!UICONTROL Compose] and [!UICONTROL Browse] modes. (TGT-50709)
* Fixed an issue with the new [[!DNL Google Chrome] [!UICONTROL Visual Editing Helper] extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) that caused a redirect from the [!UICONTROL Visual Experience Composer] (VEC) to the [!UICONTROL Activities Library] after clicking Cancel. Before this fix, customers needed to refresh the [!UICONTROL Activities Library] before being able to create new activities. (TGT-49980)-->

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
