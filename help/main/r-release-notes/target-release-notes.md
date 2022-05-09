---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解 Adobe Target 即将发布的版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 41db493ad71a2e0909346f81b897d2b1db631116
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 29%

---

# Target 发行说明（预发行版本）

本文包含预发行版本信息。发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新日期：2022 年 5 月 9 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target Standard/Premium] 22.5.1(错开释放；2022年5月11至13日)

此版本将按照以下分批次计划提供：

* **5月11日**:亚太地区
* **5月12日**:北美洲(NA)地区
* **5月13日**:欧洲、中东和非洲(EMEA)地区

此版本包含以下增强功能和修复：

* 修复了导致JavaScript错误并阻止某些客户访问特定活动详细信息的问题 [!UICONTROL Automated Personalization] (AP)活动。 (TGT-43526)
* 修复了导致某些客户无法向AP活动添加（或编辑）特定选件的问题。 (TGT-43503)
* 修复了 [!DNL Target] 显示以下错误消息的UI:“您的全局mbox可能不同步。 请尝试重新保存它。”此问题是UI问题，不会影响客户的实施。 (TGT-43475)
* 修复了在新建客户之前创建细化和受众时，导致一位客户无法编辑体验级别的活动细化和受众的问题 [!UICONTROL 受众] 已部署UI。 (TGT-43433)
* 修复了允许客户选择重复项的问题 [!DNL Adobe Audience Manager] (AAM)受众。 (TGT-43430)
* 修复了阻止客户在不同工作区中创建重复受众的问题。 (TGT-43423)
* 修复了阻止客户删除在 [!UICONTROL 基于表单的体验编辑器]. (TGT-43315)
* 修复了在单击图像选件并刷新UI后阻止客户访问代码选件的问题。 (TGT-43566)
* 确保 [!DNL Target] 创建使用 [!DNL Analytics for Target] (A4T)仅显示由 [!DNL Adobe Analytics]. (TGT-43294)
* 修复了在编辑、激活和停用配置文件脚本后，对配置文件脚本所做的编辑还原到原始未编辑脚本的问题。 配置文件脚本现在保持其编辑状态。 (TGT-43249)
* 修复了在尝试将受众移动到其他工作区时导致以下错误的问题：“我们无法完成您的请求。 如果问题仍然存在，请联系Adobe客户关怀团队。” (TGT-43212)
* 修复了在克隆单页应用程序(SPA)页面的自定义代码修改时导致错误的错误。 (TGT-43137)
* 修复了在复制体验并编辑促销活动后，导致原始促销活动受到影响的问题。 (TGT-41775)

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要提前通知您即将推出的产品增强功能，请执行以下操作： [!DNL Target] 其他 [!DNL Adobe Experience Cloud] 解决方案，注册 [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
