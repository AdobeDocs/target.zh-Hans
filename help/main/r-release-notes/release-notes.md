---
keywords: 发行说明；新功能；版本；更新；更新；版本；增强；增强；修复；错误修复；更新；当前更新
description: 了解 [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解 [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复。
short-description: 了解 [!DNL Target] 当前版本中包括的新功能、增强和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
TQID: 'https://experienceleague.adobe.com/-Unx6cVsw3wch2LJgPtvBYPe-10rdpiJ4v9F7tMSP08'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
  - id: c5abb976-5170-45d6-bcac-66d15d10a4d4
    internal-label: Release notes
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 06cdc2613d49e3c71c2d29c6ee1307d39215ac84
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 42%
---
# [!DNL Target]发行说明（当前版本）

浏览[!DNL Adobe Target]中的最新功能、增强功能和修复。 这些发行说明还涵盖了[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js和其他平台组件（如果适用）的更新。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## [!DNL Target Standard/Premium] 26.10.2（2026年10月15日）

**[!UICONTROL 活动]**

+++查看详细信息

* **活动概述**&#x200B;中显示的目标设置不正确。 修复了活动的&#x200B;**[!UICONTROL 概述]**&#x200B;页面中显示的目标设置不正确的问题。 例如，`https://`已添加到页面URL，并且未显示&#x200B;**[!UICONTROL URL包含]**&#x200B;条件，即使实际目标配置正确也是如此。 (TGT-56326)

+++

**[!UICONTROL 推荐]**

+++查看详细信息

* **在实时活动中更新促销活动后显示的备用推荐**。 修复了在实时[!DNL Recommendations]活动中编辑促销活动导致[!DNL Target]创建新促销和推荐单位的问题，即使其定义未发生任何更改也是如此。 (TGT-56369)

+++

**[!UICONTROL 报表]**

+++查看详细信息

* **报告预设在两周后删除**。 修复了用户在大约两周后为活动保存的报表预设会自动删除的问题。 (TGT-56374)

+++

**[!UICONTROL 可视化体验编辑器] (VEC)**

+++查看详细信息

* **Safari支持已添加到[!DNL Adobe Target]**。 [!DNL Safari]浏览器现在支持[!DNL Target]。 请注意，[!DNL Safari]不支持可视化体验编辑器和[!DNL Enhanced Experience Composer]。 因此，[!DNL VEC]中现在会显示一个叠加，以通知用户必须切换到[!DNL Chrome]才能使用编辑器。 (TGT-55853)

+++


## [!DNL Target Standard/Premium] 26.10.1（2026年10月13日）

**[!UICONTROL 目标分析]**

+++查看详细信息

* **A4T报告失败，出现“出现错误”错误**。 修复了使用新添加的报表包的[!DNL A4T]活动在[!DNL Target]报表中显示“出现错误”而不是结果的问题。 单击Analytics中的&#x200B;**[!UICONTROL 查看]**&#x200B;也会显示“不兼容的报表包”消息，其中缺少[!DNL Analytics for Target]分类信息。 (TGT-56389)

+++

**[!UICONTROL 可视化体验编辑器] (VEC)**

+++查看详细信息

* 显示&#x200B;**原始HTML，而不是通过mbox**&#x200B;交付的[!DNL Experience Fragments]的选件名称。 修复了通过mbox传递[!DNL Experience Fragment]时，**[!UICONTROL 修改]**&#x200B;面板显示原始HTML/代码而不是选件名称的问题。 (TGT-56241)

+++

## 您需要了解的时间性更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

对于与[!DNL Adobe Target]和您的实施相关的时效性更新，[!DNL Adobe]通过[!UICONTROL Experience League]提供详细的发行说明和文档。 以下是一些与您的实施相关的关键功能亮点：

### [!DNL Target] UI版本切换弃用

有关详细信息，请参阅[[!DNL Target] UI更新常见问题解答](/help/main/c-intro/updated-ui-faq.md)。

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
