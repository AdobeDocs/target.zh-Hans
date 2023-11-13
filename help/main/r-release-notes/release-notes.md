---
keywords: 发行说明;新功能;版本;更新;更新;版本;增强;增强;修复;错误修复;更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: d2aac088d5f1ae60a4b0e7ac1fff9960e2959130
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 82%

---

# [!DNL Target]发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的发行说明以及其他平台变更。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## [!DNL Target]标准/高级 23.11.1（2023 年 11 月 13 日和 14 日）

此版本计划在以下天数内发布：

* **11 月 13 日**：亚太 (APAC) 区域
* **11 月 14 日**：美洲区域
* **11 月 14 日**：欧洲、中东和非洲 (EMEA) 区域

此版本包含以下增强和修复：

* 增强了 [活动QA](/help/main/c-activities/c-activity-qa/activity-qa.md) 要支持的功能 [不允许重复的选件](/help/main/c-activities/t-automated-personalization/managing-exclusions.md) 中的体验 [!UICONTROL Automated Personalization] 活动。 (TGT-46627)
* 在 [!DNL Target] UI 中添加了一个工具提示，以帮助客户理解如果没有为控制体验分配流量，为什么活动报告中可能会没有可用的数据。工具提示中包含有关更多信息的链接：[为什么我的活动报告没有可用数据？](/help/main/c-reports/reporting-frequently-asked-questions.md#section_E4722F6445884130951DF79981C8289B)。(TGT-46610)
* 修复了一些客户的活动无法在[!UICONTROL 活动] 页面上正确显示的问题。(TGT-46830)
* 修复了以下影响使用的活动的问题 [[!UICONTROL 目标分析]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)作为报表源：
   * 修复了阻止某些客户查看报表数据的问题。 (TGT-46557)
   * 修复了有时会导致 [!UICONTROL 在Analytics中查看] 活动报告页面上的链接无法正常运行。 (TGT-46731)
   * 修复了阻止数据访问的问题。 [!UICONTROL 提升] 和 [!UICONTROL 置信度] 以正确显示在 [!DNL Target] UI。 （TGT-46592、TGT-46554 和 TGT-46586）

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

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
