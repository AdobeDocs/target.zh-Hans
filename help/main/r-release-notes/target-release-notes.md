---
keywords: 发行说明；版本；更新；未来版本；增强；新功能；修复；更新；预发行；抢先体验
description: 了解即将发布的 [!DNL Adobe Target]版本中包括的新功能、增强功能和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 36f269331d992f621d71fc085c85f3a7ad5bdfa6
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 24%

---

# [!DNL Target] 发行说明（预发行版本）

本文包含即将发布的 [!DNL Adobe Target] 版本的预发行信息，包括 SDK、API 和 JavaScript 库。

**上次更新日期：2025年3月30日**

>[!NOTE]
>
>发布日期、功能及其他信息如有更改，恕不另行通知。
>
>要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target Standard/Premium] 25.3.8（2025年3月28日）

此版本包含以下修复和更新：

* 解决了导致[!UICONTROL Activities]页面加载缓慢的问题。 (TGT-51151)

## [!DNL Target Standard/Premium] 25.3.7（2025年3月26日）

此版本包含以下修复和更新：

* 解决了在修改后删除页面时阻止保存多页面活动的问题。 (TGT-51988)
* 解决了编辑活动时发生的错误： `default message [Invalid optionLocalIds: xx]]`。 (TGT-51985)
* 解决了向活动添加新修改时删除现有修改的问题。 (TGT-51981)
* 解决了在活动创建或编辑期间将受众替换为“[!UICONTROL All visitors]”导致“不允许存在重复的受众”错误的问题。 (TGT-51978)
* 解决了在保存[!UICONTROL A/B Test]活动时导致“用户输入无效”错误的问题。 (TGT-51976)
* 解决了导致计算量度无法在[!UICONTROL Goals & Settings]页面上正确显示的问题。 (TGT-51975)
* 解决了阻止在`pageviews`量度的[!DNL Analytics]配置中匹配`companyName`和`reportSuite`的问题。 (TGT-51965)
* 解决了在活动中切换体验时删除修改的问题。 (TGT-51945)
* 解决了删除页面受众时也删除[!UICONTROL ClickTrack]选择器的问题。 (TGT-51935)
* 解决了在打开活动[!UICONTROL Overview]页面后使其不可编辑的问题。 (TGT-51931)
* 解决了在活动创建期间导致出现`[Unused optionLocalIds: 0]]`错误的问题。 (TGT-51920)
* 解决了删除文本样式更改后某些更改无法正确翻译的问题。 (TGT-51876)
* 解决了阻止目标受众在[!UICONTROL Form-Based Experience Composer]中正确更新的问题。 (TGT-51845)
* 解决了[!UICONTROL Visual Experience Composer]中的URL在活动导航期间未正确更新的问题。 (TGT-51832)
* 解决了导致选件无法在[!UICONTROL Offers] UI中显示的问题，尽管在创建活动和添加选件时显示正确。 (TGT-51805)
* 解决了在无法交付个性化或目标内容时，某些活动缺少用于显示默认内容的回退屏幕的问题。 (TGT-51638)
* 解决了导致实时优惠和某些文件夹无法在[!UICONTROL Offers] UI中正确显示的问题。 (TGT-51628)
* 解决了导致某些URL字符串和goURL无法正确本地化的问题。 (TGT-35741)
* 修复了导致无法在[!DNL Target] UI中正确本地化角色（[!UICONTROL Approver]、[!UICONTROL Editor]和[!UICONTROL Observer]）的问题。 (TGT-29925)

## [!DNL Target Standard/Premium] 25.3.6（2025年3月14日）

此版本包含以下修复和更新：

* 解决了当多次使用同一[!UICONTROL ClickTrack]选择器时启用了[!UICONTROL Click Tracking]的[!UICONTROL Visual Experience Composer] (VEC)活动中的“用户输入无效”错误。 (TGT-51921)
* 修复了具有共享位置(例如，HEAD选择器)和相同选件的VEC活动中的“用户输入无效”错误。 (TGT-51879)
* 修复了导致体验修改在受众之间共享的问题。 (TGT-51815)
* 解决了创建活动时由于区段ID冲突导致的验证错误。 [!DNL Target]检测到使用匿名区段的现有活动时出现错误。 (TGT-51784)
* 解决了阻止[!DNL Target]在受众中保存带有排除规则的活动的问题。 (TGT-51581)
* 解决了阻止客户在无法访问默认工作区的情况下创建、删除或移动文件夹的问题。 (TGT-51499)
* 解决了在检索[!DNL Analytics]指标列表时导致GET请求失败的问题。 (TGT-51106)

## [!DNL Target Standard/Premium] 25.3.5（2025年3月11日）

此版本包含以下修复和更新：

* 解决了阻止用户更改[!UICONTROL Modifications]面板中选件的问题。 (TGT-51800)
* 解决了在体验和受众的左侧面板（包括在[!UICONTROL ClickTrack]模式下）中错误显示操作的问题。 (TGT-51895)
* 解决了[!UICONTROL ClickTrack]选择器未应用于正确受众页面的问题。 (TGT-51871)

## [!DNL Target Standard/Premium] 25.3.4（2025年3月7日）

此版本包含以下修复和更新：

* 解决了仅活动受众在[!UICONTROL Audiences]面板中不可见，导致无法编辑或重用的问题。 (TGT-51860)
* 修复了阻止[!DNL Target Standard]客户使用[!UICONTROL Analytics for Target] (A4T)报表创建活动的问题。 (TGT-51854)
* 修复了在批量创建和编辑操作期间从有效负载中排除本地ID计数器的问题。 (TGT-51867)

## [!DNL Target Standard/Premium] 25.3.2（2025年3月6日）

此版本包含以下修复和更新：

* 修复了复制仅包含活动受众的活动时无法创建新活动，从而错误地使用原始活动的受众的问题。 (TGT-51855)
* 修复了阻止编辑具有仅限该活动的受众的[!UICONTROL Experience Targeting] (XT)活动的问题。 (TGT-51846)
* 修复了[!UICONTROL Visual Experience Composer] (VEC)在首次编辑时无法正确将修改应用于体验的问题。 (TGT-51843)
* 修复了单击VEC中的某些元素时触发“ID”错误的问题。 (TGT-51814)
* 在活动创建期间更新了VEC中的错误处理。 (TGT-51759)
* 修复了在保存活动时，[!UICONTROL Modifications]面板中缺少视图导致“无效用户输入”错误的问题。 (TGT-51827)
* 修复了阻止创建推荐标准的问题。 (TGT-51834)
* 在重定向到其他URL之前添加了确认消息。 (TGT-51703)
* 修复了选件和文件夹中的GraphQL集成测试问题。 (TGT-51839)

## [!DNL Target Standard/Premium] 25.3.1（2025年3月3日）

此版本包含以下修复和更新：

* 组合受众可以包括子组，每个子组包含多个受众。 此版本修复了导致子组受众无法在[!UICONTROL Rules]对话框中显示的问题。 (TGT-51813)
* 解决了在打开旧版活动时，某些体验受众被替换为[!UICONTROL All Visitors]的问题。 (TGT-51812)
* 解决了阻止编辑仅具有活动受众的活动的问题。 (TGT-51807)
* 解决了阻止在更新的[!DNL Target] UI中编辑页面标题修改的问题。 (TGT-51797)
* 解决了在复制体验、删除其他体验然后尝试保存活动时发生的空错误。 (TGT-51796)
* 解决了在创建活动的[!UICONTROL Targeting]步骤期间，受众信息面板中无法显示受众排除规则的问题。 (TGT-51579)
* 更新了韩语本地化的错误消息。 （TGT-51701 和 TGT-51699）

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
