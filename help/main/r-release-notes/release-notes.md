---
keywords: 发行说明;新功能;版本;更新;更新;版本;增强;增强;修复;错误修复;更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: e458793e4d0110d97f3f5124cbe6e54520d3f0e9
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 68%

---

# [!DNL Target]发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的发行说明以及其他平台变更。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## [!DNL Target] Standard/Premium 22.15.1（2023年3月8日和9日）

将按以下交错的时间表发布此版本：

* **3月8日**：美洲区域
* **3月9日**：欧洲、中东和非洲(EMEA)区域
* **3月9日**：亚太(APAC)区域

此版本包含以下新增功能和增强功能：

| 功能 | 详细信息 |
| --- | --- |
| 优化了A4T指标 [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位] | [!DNL Target] 允许您在使用时，选择基于二项式事件的量度或基于连续事件的量度 [!UICONTROL A4T] 对象 [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位] 活动。<P>请注意支持的量度中的以下时效性更改：<ul><li>[!DNL Target] 保留现有活动先前的行为，直到2023年9月9日。 在此日期之后，将停止使用不受支持的指标的活动，以强制现有活动迁移到新行为。</li></ul>有关更多信息，请参阅 [支持的目标量度](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#supported) 在 *自动分配和自动定位活动支持A4T*. |
| [!UICONTROL 自动分配] 使用 [!UICONTROL 目标分析] (A4T) | 新教程：<ul><li>[在中设置A4T报表 [!DNL Analysis Workspace] 对象 [!UICONTROL 自动分配] 活动](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank}</li></ul> |
| [!UICONTROL 自动定位] 使用 [!UICONTROL 目标分析] (A4T) | 新教程：<ul><li>[在中设置A4T报表 [!DNL Analysis Workspace] 对象 [!UICONTROL 自动定位] 活动](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html){target=_blank}</li></ul> |

## at.js 版本 2.10.2（2023 年 3 月 7 日）

* 修复了导致 `trackEvent` 函数始终返回错误。

有关所有 at.js 版本的信息，请参阅 [at.js 版本详细信息](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}。

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 文档更改、以往的发行说明和 Experience Cloud 发行说明

除了针对每个发行的说明外，以下资源还提供更多其他信息：

| 资源 | 详细信息 |
|--- |--- |
| 文档更改 | 查看这些发行说明中未包括的关于本指南的更新的详细信息。<br>有关更多信息，请参阅[文档更改](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)。 |
| 以前版本的发行说明 | 查看与以前版本的 Target Standard 和 Target Premium 中的新增功能和增强功能相关的信息。<br>有关更多信息，请参阅[以前版本的发行说明](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 发行说明 | 查看 Adobe Experience Cloud 解决方案的最新发行说明。<br>有关更多信息，请参阅 [Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans)。 |

## 预发行信息 {#section_5D588F0415A2435B851A4D0113ACA3A0}

您可以通过以下资源了解下一个 Target 版本即将包含的功能。

| 资源 | 详细信息 |
|--- |--- |
| Adobe 优先产品更新 | 若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：<br>[](https://www.adobe.com/cn/subscription/priority-product-update.html)https://www.adobe.com/cn/subscription/priority-product-update.html |
| 即将推出的发行说明 | 有关当月 Target 发行版本的信息（包括预发行信息），请参阅 [Target 发行说明 — 预发行](/help/main/r-release-notes/target-release-notes.md)页面。 |
