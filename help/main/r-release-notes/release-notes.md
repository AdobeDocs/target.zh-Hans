---
keywords: 发行说明；新功能；版本；更新；更新；版本；增强；增强；修复；错误修复；更新；当前更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 62d33419f2cbad93d99b29cef58e99f4d84a98f6
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 47%

---

# [!DNL Target]发行说明（当前版本）

浏览[!DNL Adobe Target]中的最新功能、增强功能和修复。 这些发行说明还涵盖了[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js和其他平台组件（如果适用）的更新。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## 您需要了解的时间性更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

对于与[!DNL Adobe Target]和您的实施相关的时效性更新，[!DNL Adobe]通过[!UICONTROL Experience League]提供详细的发行说明和文档。 以下是一些与您的实施相关的关键功能亮点：

### [!DNL Target] UI版本切换弃用

有关详细信息，请参阅[[!DNL Target] UI更新常见问题解答](/help/main/c-intro/updated-ui-faq.md)。

## [!DNL Target Standard/Premium] 26.3.2（2026年3月10日）

**活动**

+++查看详细信息

* **体验中的直接优惠更改未保存。**&#x200B;此修复了无法保存对活动体验中的直接优惠所做的修改的问题。 以前，当用户打开直接选件、做出更改并保存它时，更改似乎在开始时反映出来，但在重新打开选件时丢失。 此修复程序可确保正确保存对直接选件所做的更改，并在重新打开选件时保留这些更改。 (TGT-54653)

+++

**实施**

+++查看详细信息

* 在“实施”屏幕上&#x200B;**添加闪烁管理切换开关。**&#x200B;已向[!UICONTROL Implementation]屏幕添加新的切换开关以控制启用闪烁管理设置。 此切换允许管理员直接从“实施”屏幕配置闪烁管理。 (TGT-52247)

+++

**概述**

+++查看详细信息

* **在概述页面中显示受众和体验的全名。**&#x200B;此增强功能会更新[!UICONTROL Overview]页面以显示受众和体验的全名。 以前，长名称会被截断并且无法完全显示，因此需要用户通过三次单击来选择所有文本，以查看完整名称。 此更新可确保完整受众和体验名称可见，从而使用户更容易识别和审查活动配置。 (TGT-53323)

+++


## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=zh-Hans){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

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
