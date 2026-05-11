---
keywords: 发行说明；新功能；版本；更新；更新；版本；增强；增强；修复；错误修复；更新；当前更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 860dd22fc4ec261a62869cb656d72bd49f2bd91c
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 51%

---

# [!DNL Target]发行说明（当前版本）

浏览[!DNL Adobe Target]中的最新功能、增强功能和修复。 这些发行说明还涵盖了[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js和其他平台组件（如果适用）的更新。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## 您需要了解的时间性更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

对于与[!DNL Adobe Target]和您的实施相关的时效性更新，[!DNL Adobe]通过[!UICONTROL Experience League]提供详细的发行说明和文档。 以下是一些与您的实施相关的关键功能亮点：

### [!DNL Target] UI版本切换弃用

有关详细信息，请参阅[[!DNL Target] UI更新常见问题解答](/help/main/c-intro/updated-ui-faq.md)。

## [!DNL Target Standard/Premium] 26.5.1（2026年5月7日）

**集成**

+++查看详细信息

* Experimentation Accelerator中的&#x200B;**[!DNL Adobe Target]管理。** 添加了对将[!DNL Target]工作区分配给Experimentation Accelerator沙盒的支持，以便团队可以在Experimentation Accelerator中一个位置查看来自[!DNL Adobe Target]的试验。 [了解详情](../c-integrating-target-with-mac/experimentation-accelerator.md)

+++

**活动**

+++查看详细信息

* **[!UICONTROL Graph View]与表和下载不同步。** 修复了以下问题：对于某些日期范围，活动报表在&#x200B;**[!UICONTROL Graph View]**&#x200B;中可能显示缺失或零量度，即使&#x200B;**[!UICONTROL Table View]**&#x200B;并且下载的报表仍显示正确的值。 (TGT-54998)

+++

**[!UICONTROL Audiences]**

+++查看详细信息

* **受众使用情况列表未完全呈现。** 修复了受众详细信息中的&#x200B;**[!UICONTROL Usage]**&#x200B;部分只能显示映射活动的子集的问题，即使其他活动与该受众关联也是如此。 (TGT-55094)

+++

**[!UICONTROL Administration]**

+++查看详细信息

* **对最后一个八位字节IP模糊化的确认更清晰。** 当您在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Implementation]**&#x200B;上将&#x200B;**[!UICONTROL Obfuscate Visitor IP addresses]**&#x200B;更改为&#x200B;**[!UICONTROL Last octet]**&#x200B;时，确认对话框现在会说明[!DNL Target]隐藏访客IP地址的最后八位字节。 (TGT-44821)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++查看详细信息

* 使用增强型体验编辑器(EEC) **空白或不完整的页面。** 修复了在启用&#x200B;**[!UICONTROL Enhanced Experience Composer]**&#x200B;时，[!UICONTROL Visual Experience Composer]无法在编辑器中加载网站的问题。 (TGT-54576)

+++


<!--
* **Blank page or CORS errors with Enhanced Experience Composer.** Fixed an issue where the [!UICONTROL Visual Experience Composer] could fail to load when Enhanced Experience Composer (EEC) was enabled. (TGT-54576)




**[!UICONTROL Visual Experience Composer] (VEC)**

+++See details

* **Click tracking for Experience B.** Fixed an issue where click tracking was not saved for **[!UICONTROL Experience B]** in the [!UICONTROL Visual Experience Composer]. (TGT-54843)

+++
-->

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

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
