---
keywords: 发行说明；版本；更新；未来版本；增强；新功能；修复；更新；预发行；抢先体验
description: 了解即将发布的 [!DNL Target]版本中包括的新功能、增强功能和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: cc0bf794e366f304b52db309d4e3a66292d7ea32
workflow-type: tm+mt
source-wordcount: '673'
ht-degree: 20%

---

# [!DNL Target] 发行说明（预发行版本）

本文包含即将发布的 [!DNL Adobe Target] 版本的预发行信息，包括 SDK、API 和 JavaScript 库。

**上次更新日期：2025年8月27日**

>[!NOTE]
>
>* 发布日期、功能及其他信息如有更改，恕不另行通知。本文中的信息会经常更新，尤其是在发布版本之前。
>
>* 要查看有关当前版本的信息，请参阅[Target发行说明](release-notes.md)。
>
>* 括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target Standard/Premium] 25.8.4（2025年9月1日）

此版本包含以下更新和修复：

**[!UICONTROL Activities]**

+++查看详细信息
* **客户无法从[!UICONTROL Activity Overview]**&#x200B;中复制活动或文档名称：以前，客户无法直接从更新后的活动创建流程中的[!UICONTROL Activity Overview]中复制活动或关联优惠/文档的名称。 此限制会影响可用性，尤其是在较小的屏幕上。 客户现在可以轻松地复制活动和文档名称而无需变通办法。 (TGT-51850)
* **在活动创建期间主动摄取应用策划的[!DNL Target]客户数据**：通过启用[!DNL Target]客户的报告、内容和屏幕截图的主动收集，改进了活动创建流程。 此增强功能解决了现有用例中发现的数据缺口，并帮助确保在活动和实验设置期间获得更准确的见解。 (TGT-52415)

+++

**[!UICONTROL Recommendations]**

+++查看详细信息
* **产品列表在[!UICONTROL View Collection]对话框中不可见：**&#x200B;以前，客户在[!UICONTROL Recommendations]选项卡中查看收藏集时无法查看产品列表。 [!UICONTROL View Collection]对话框现在可以正确显示关联的产品，从而提高更新后的推荐UI中的透明度和可用性。 (TGT-50531)
* **修复了[!UICONTROL Product Catalog Search]高级搜索中导致区分大小写筛选的问题**： [!UICONTROL Product Catalog Search]页面中的高级搜索筛选现在正确忽略区分大小写的问题，这与后端和GraphQL服务的行为一致。 此更新确保无论文本大小写如何，都能为客户提供一致而准确的建议结果。 (TGT-53585)

+++

**[!UICONTROL Reports]**

+++查看详细信息
* **由于无效受众名称错误，无法为桌面受众加载报告**：客户在活动创建过程中尝试查看一个受众的报告时遇到了GraphQL错误。 系统返回“无效受众名称：XXXXX”消息，阻止访问报表数据。 现在，桌面版受众的报表可正确加载。 (TGT-53371)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++查看详细信息
* **使用[!UICONTROL Enhanced Experience Composer] (EEC)单击“接受Cookie”失败，因为缺少函数**：客户报告说尝试通过EEC接受Cookie导致控制台错误： `handleclickAcceptAllButton is not defined`。 现在，Cookie接受功能可按预期工作，以确保在更新的UI中创建活动期间获得更流畅的体验。 (TGT-52794)
* **新EEC UI无法加载旧版UI中以前支持的特定页面**：客户报告新EEC无法加载旧版UI中可以访问的某些页面，尽管网站上存在iframe-busting代码。 更新的活动创建流程现在支持加载这些页面，从而恢复活动创建工作流的兼容性。 (TGT-53061)
* **在编辑体验时，VEC显示空白白屏**：来自特定租户的客户报告，在更新的VEC中编辑体验时，VEC屏幕变为空白。 此问题会影响新创建的活动和旧的活动，从而妨碍工作流的连续性。 现在，VEC可正确加载，从而允许客户在不中断的情况下编辑体验。 (TGT-53547)
* **加载某些活动时，VEC崩溃并显示一个空白屏幕**：来自特定租户的客户报告VEC无法加载特定活动。 体验编辑器在“应用初始修改”时仍然卡住，直到崩溃并显示空白屏幕。 控制台错误指示读取未定义的属性失败。 该编辑器现在会在更新的VEC中加载受影响的活动，而不会出现错误。 (TGT-53548)

+++

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明： Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=zh-Hans){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
