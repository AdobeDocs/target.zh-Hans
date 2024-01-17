---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解即将发布的 [!DNL Adobe Target]版本中包括的新功能、增强功能和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: b76a0541b181ee5ebe88f2d11f5556c6c7b91126
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 49%

---

# [!DNL Target] 发行说明（预发行版本）

本文包含即将发布的 [!DNL Adobe Target] 版本的预发行信息，包括 SDK、API 和 JavaScript 库。

**上次更新日期： 2024年1月16日**

>[!NOTE]
>
>发布日期、功能及其他信息如有更改，恕不另行通知。
>
>要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## 从“浏览器”受众属性弃用iPad和iPhone （2024年4月30日）

| 弃用 | 详细信息 |
|--- |--- |
| [!DNL iPad] 和 [!DNL iPhone] 将被弃用 [浏览器属性](/help/main/c-target/c-audiences/c-target-rules/browser.md) 在创建受众时使用。<p>弃用日期：<P>2024年4月30日 | [!DNL Adobe Target] 允许您 [定位多个类别属性中的任意一个](/help/main/c-target/c-audiences/c-target-rules/target-rules.md)，包括使用特定的 [浏览器或浏览器选项](/help/main/c-target/c-audiences/c-target-rules/browser.md) 访客访问您的页面时。<P><B>从2024年4月30日开始，iPad和iPhone将从以下可用中删除： [!UICONTROL 浏览器] 为受众创建类别时，键入/下拉列表。</b><P>如果您的受众使用 [!UICONTROL 浏览器] 特性，您必须在2024年4月30日之前更改这些设置，以确保这些受众继续按预期工作。<P>以后应使用以下设置：<ul><li>[!UICONTROL 移动设备] > [!UICONTROL 是平板电脑]<P>![手机就是平板电脑](/help/main/r-release-notes/assets/is-tablet.png)</li><li>[!UICONTROL 移动设备] > [!UICONTROL 设备营销名称] [!UICONTROL 匹配] [!DNL iPad]<P>![iPad](/help/main/r-release-notes/assets/ipad.png)</li><li>[!UICONTROL 移动设备] > [!UICONTROL 设备营销名称] [!UICONTROL 匹配] [!DNL iPhone]<p>![iPhone](/help/main/r-release-notes/assets/iphone.png)</li></ul> |

## [!DNL Target] Standard/Premium 24.1.1（2024年1月22日、 23日和25日）

此版本计划在接下来的几天发布：

* **1 月 22 日**：欧洲、中东和非洲 (EMEA) 地区
* **1 月 23 日**：亚太 (APAC) 地区
* **1 月 25 日**：美洲区域

此版本包含以下增强和修复：

* 修复了导致报表日期间隔无法正常工作的问题。 (TGT-47396)
* 修复了一个问题，该问题导致在 [!UICONTROL 所有活动] 客户使用以下方式激活或停用活动后的页面 [!UICONTROL 更多操作] 图标。 (TGT-47367)
* 修复了导致出现错误的问题 [!UICONTROL 重要属性] 报告不显示给一个客户。 (TGT-47272)
* 修复了一个问题，该问题导致在一个客户尝试启用“需要身份验证”时显示“有效负载无效”消息。 (TGT-47195)
* 更新了 [!DNL Target] UI。

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
