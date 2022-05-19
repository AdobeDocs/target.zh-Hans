---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解 Adobe Target 即将发布的版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 71190b0f6c66d4c448121a330e7c07b6255ae8be
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 100%

---

# Target 发行说明（预发行版本）

本文包含预发行版本信息。发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新日期：2022 年 5 月 9 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target Standard/Premium] 22.5.1（2022 年 5 月 11 日至 13 日，交错发行）

此版本将按照以下交错发行计划发行：

* **5 月 11 日**：亚太 (APAC) 地区
* **5 月 12 日**：北美 (NA) 地区
* **5 月 13 日**：欧洲、中东和非洲 (EMEA) 地区

此版本包含以下增强功能和修复：

* 修复了一个问题，该问题导致 JavaScript 错误并阻止一些客户访问某些 [!UICONTROL Automated Personalization] (AP) 活动的详细信息。 (TGT-43526)
* 修复了一个问题，该问题阻止某些客户在 AP 活动中添加（或编辑）特定优惠的问题。 (TGT-43503)
* 修复了在 [!DNL Target] UI 中显示以下错误消息的问题：“您的全局 mbox 可能不同步。 请尝试重新保存它。”这是一个 UI 问题，不会影响客户的实施。 (TGT-43475)
* 修复了一个问题，如果在部署新的[!UICONTROL 受众] UI 之前创建活动的体验级细化和受众，该问题阻止单个客户编辑这些体验级细化和受众。(TGT-43433)
* 修复了一个问题，该问题允许客户在编辑活动的报告受众时选择重复的 [!DNL Adobe Audience Manager] (AAM) 受众。 (TGT-43430)
* 修复了一个阻止客户在不同工作区创建重复受众的问题。 (TGT-43423)
* 修复了一个问题，该问题阻止客户删除在 [!UICONTROL 基于表单的体验生成器] 创建的活动中享有临时优惠的位置。 (TGT-43315)
* 修复了一个问题，该问题阻止客户在单击图像优惠信息然后刷新 UI 后访问代码优惠信息。 (TGT-43566)
* 修复了一个问题，该问题导致对配置文件脚本的编辑在脚本被编辑、激活然后停用后，恢复为原始的未编辑脚本。 配置文件脚本现在仍处于编辑状态。 (TGT-43249)
* 修复了试图将受众移动到另一个工作区时导致以下错误的问题：“我们无法完成您的请求。 如果问题仍然存在，请联系 Adobe 客户关怀部门。” (TGT-43212)
* 修复了一个问题，该问题导致克隆单页面应用程序 (SPA) 页面的自定义代码修改时出现错误。 (TGT-43137)
* 修复了在复制体验并编辑促销后导致原始促销受到影响的问题。 (TGT-41775)

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
