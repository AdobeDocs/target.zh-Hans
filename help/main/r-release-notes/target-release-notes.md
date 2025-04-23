---
keywords: 发行说明；版本；更新；未来版本；增强；新功能；修复；更新；预发行；抢先体验
description: 了解即将发布的 [!DNL Adobe Target]版本中包括的新功能、增强功能和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: ad82d108adc6f5c76b2104f40fb0bb2c66e98a2b
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 33%

---

# [!DNL Target] 发行说明（预发行版本）

本文包含即将发布的 [!DNL Adobe Target] 版本的预发行信息，包括 SDK、API 和 JavaScript 库。

**上次更新日期：2025年4月23日**

>[!NOTE]
>
>发布日期、功能及其他信息如有更改，恕不另行通知。
>
>要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target Standard/Premium] 25.4.5（2025年4月24日）

此版本包含以下修复和更新：

* 修复了在激活[!DNL Recommendations]活动后，客户网站上未显示推荐的问题。 (TGT-52164)
* 当选项保持不变时，`OptionLocalIDs`不再错误地增加。 (TGT-52187)
* 现在，下载的报表文件可正确显示报表UI中存在的数据。 (TGT-52068)
* 添加页面交付规则后，批处理操作不再失败。 (TGT-52097)
* 修复了导致[!DNL Target]从网站URL中修剪所有查询参数的问题。 (TGT-52100)
* 解决了阻止客户在旧版和更新后的Target UI中创建活动的控制台错误。 (TGT-52181)
* 修复了阻止客户添加新页面，从而导致无效用户输入错误的问题。 (TGT-52258)
* 修复了在添加其他页面然后导航回[!UICONTROL Experiences]选项卡后导致修改消失的问题。 (TGT-52264)
* 修复了阻止客户更改[!UICONTROL Experience Targeting] (XT)活动中的受众的问题。 (TGT-52191)
* 修复了由于不支持的UI规则而阻止编辑XT活动的错误。 (TGT-52273)
* 修复了活动修改无法显示在[!DNL Target] UI中的问题，尽管已成功地将其交付到网页。 (TGT-52192)
* 修复了更新的[!UICONTROL Visual Experience Composer] (VEC)中的问题，该问题导致痕迹导航不始终显示在编辑器底部，从而难以准确地选择元素。 (TGT-51169)
* 修复了[!UICONTROL Audience]下拉列表因分页而无法显示所有受众的问题。 (TGT-52204)
* 修复了在[!UICONTROL Automated Personalization] (AP)活动中添加新选件时导致用户输入消息无效的问题。 (TGT-52210)
* 修复了以下问题：[!UICONTROL Analytics for Target] (A4T)被错误地选为报表源，即使客户无权访问A4T。 (TGT-52226)
* 修复了阻止使用[!UICONTROL View a Page] URL量度保存活动的问题。 (TGT-52260)
* 修复了一个问题，该问题阻止客户在活动中创建优惠时选择工作区。 (TGT-52289)
* 修复了在切换到另一个体验时，某个体验中的修改无法正确显示的问题。 (TGT-52184)
* 修复了在打开活动后[!DNL Target] UI中错误显示默认选件的问题。 (TGT-52198)

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
