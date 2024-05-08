---
keywords: 发行说明;新功能;版本;更新;更新;版本;增强;增强;修复;错误修复;更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 44445f269a69a3ac3e3bc88bab8abf9fc4d51663
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 58%

---

# [!DNL Target]发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的发行说明以及其他平台变更。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## [!DNL Target] 报告 [!DNL Adobe Customer Journey Analytics] （2024年5月8日）

之间的集成 [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/customer-journey-analytics){target=_blank} 和 [!DNL Target] 为您的优化项目提供功能强大的分析和省时的工具。

将 [!DNL Customer Journey Analytics] 用作 [!DNL Target] 的报告源主要有以下好处：

* 营销人员可以随时将 [!DNL Customer Journey Analytics] 成功量度动态应用到 [!DNL Target] 活动报表。在运行活动之前什么都不需要指定。
* 营销人员可以利用 [!DNL Customer Journey Analytics] 功能，例如 [“试验”面板](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation){target=_blank}，以进一步分析其网站个性化。
* 营销人员可以拥有针对以下项的单个报表源： [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/reporting/cja-ajo){target=_blank} 和 [!DNL Target]. 可将这两种个性化产品都连接到 [!DNL Customer Journey Analytics] 以更全面地了解您的 Web 个性化情况。

有关更多信息，请参阅 [Adobe Customer Journey Analytics中的Target报表](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md).

## [!UICONTROL Visual Experience Composer] 帮助程序延期（2024年4月23日）

旧版 [!DNL Target] 可视化体验编辑器助手扩展是使用清单V2创建的。 [!DNL Google] 宣布从2024年6月起，将不再允许使用清单V2创建的扩展。 有关更多信息，请参阅 [[!UICONTROL Visual Experience Composer] 帮助程序扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md).

[!DNL Adobe] 建议客户迁移到较新版本 [可视化编辑帮助程序扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) 尽可能早。

## 更新 `Browser:iPad` 和 `Browser:iPhone` 在 [!UICONTROL Browser] 受众属性（2024年4月30日）

| 更新 | 详细信息 |
|--- |--- |
| [!UICONTROL Browser:iPad] 和 [!UICONTROL Browser:iPhone] 更新于 [浏览器属性](/help/main/c-target/c-audiences/c-target-rules/browser.md) 在创建受众时使用。 | [!DNL Adobe Target] 允许您 [定位多个类别属性中的任意一个](/help/main/c-target/c-audiences/c-target-rules/target-rules.md)，包括使用特定的 [浏览器或浏览器选项](/help/main/c-target/c-audiences/c-target-rules/browser.md) 访客访问您的页面时。<P>从 [!DNL Target] Standard/Premium 24.3.1（2024年3月4日至6日），使用Target UI创建的内置受众，例如 `Browser:iPad` 和 `Browser:iPhone` 将更新以对执行适当的定位 [!DNL iPad] 和 [!DNL iPhone] 使用 `profile.mobile.deviceVendor`， `profile.mobile.isMobilePhone` 和 `profile.mobile.isTablet`.<P>客户无需对此更新执行任何操作。<p><B>重要</b>：供客户对以下内容执行适当的定位 [!DNL iPad] 和 [!DNL iPhone] 在配置文件脚本（和JavaScript区段）中，必须由客户手动进行更改 **2024年4月30日**. 有关必须手动更改的替代设置的示例，请参阅 [更新 [!DNL iPad] 和 [!DNL iPhone] 在 [!UICONTROL Browser] 受众属性](/help/main/c-target/c-audiences/c-target-rules/browser.md#updates). |

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
| [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans){target=_blank} | 查看 Adobe Experience Cloud 解决方案的最新发行说明。 |

## 预发行信息 {#section_5D588F0415A2435B851A4D0113ACA3A0}

您可以通过以下资源了解下一个 Target 版本即将包含的功能。

| 资源 | 详细信息 |
|--- |--- |
| [Adobe 优先产品更新](https://www.adobe.com/cn/subscription/priority-product-update.html){target=_blank} | 提前收到有关 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案的即将发行产品增强功能的通知。 |
| [Target 发行说明 - 预发行版本](/help/main/r-release-notes/target-release-notes.md){target=_blank} | 有关当月的 Target 版本的信息，包括预发行信息。 |
