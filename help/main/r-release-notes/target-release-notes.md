---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解 Adobe Target 即将发布的版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: fa6324606b32f265084615fd1c13ce6c49921b48
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 55%

---

# Target 发行说明（预发行版本）

本文包含预发行版本信息。发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新时间：2022 年 6 月 30 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target Standard/Premium] 22.6.2（2022 年 6 月 30 日）

此版本包含以下功能、增强功能和修复：

| 功能 | 描述 |
| --- | ---  |
| 产品内通知 | 获取以下相关的产品内通知：<ul><li>**活动**:批准或停用活动时（手动或达到活动开始或结束日期时），所有活动类型的通知。 通知包含带有活动概述页面链接的活动名称。</li><li>**配置文件脚本** 手动或Target激活或停用配置文件脚本时的通知。</li><li>**Recommendations信息源**:手动或由Target激活或停用Recommendations馈送时的通知。 当Recommendations馈送失败时，也会发送通知。</li></ul> 默认情况下，产品管理员、发布者和批准者会收到通知。 通知可在Experience Cloud首选项中进行配置。<br>有关详细信息，请参阅 [通知和公告](/help/main/c-intro/understand-the-target-ui.md#notifications-announcements). |
| *Adobe Target开发人员指南* | 的 *Adobe Target开发人员指南* 合并所有 [!DNL Target] 开发人员内容。 本指南包含有关实施的信息 [!DNL Target] 和 [!DNL Recommendations], [!DNL Target] SDK和 [!DNL Target] API。<br>有关更多信息，请参阅 [Adobe Target开发人员指南](https://developer.adobe.com/target/){target=_blank}。 |

* 具有[!UICONTROL 编辑者]角色的用户无法再编辑直播活动中的受众。(TGT-43582)
* 如果客户试图将感叹号 (！) 作为受众名称的第一个字符（例如 !London）来保存受众，则会显示警告消息。(TGT-43643)
* 修复了导致某些客户的受众定义详细信息卡指示已结束活动仍处于活动状态的问题。(TGT-43527)

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
