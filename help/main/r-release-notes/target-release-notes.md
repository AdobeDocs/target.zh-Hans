---
keywords: 发行说明；版本；更新；未来版本；增强；新功能；修复；更新；预发行；抢先体验
description: 了解即将发布的 [!DNL Adobe Target]版本中包括的新功能、增强功能和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: cd25bda52b7a1b916a73ca5e531a7134ba8cef4e
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 42%

---

# [!DNL Target] 发行说明（预发行版本）

本文包含即将发布的 [!DNL Adobe Target] 版本的预发行信息，包括 SDK、API 和 JavaScript 库。

**上次更新日期：2025年4月17日**

>[!NOTE]
>
>发布日期、功能及其他信息如有更改，恕不另行通知。
>
>要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

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
