---
keywords: 发行说明;新功能;版本;更新;更新;版本;增强;增强;修复;错误修复;更新
description: 了解 [!DNL Adobe Target]当前版本中包含的新增功能、增强功能和修复，包括SDK、API和JavaScript库。
title: 当前版本中包括什么新功能？
feature: 发行说明
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 29b8bf64b0ce4e7e830d9fff5341849799072dfa
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 58%

---

# Target 发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 Target API、SDK、JavaScript 库 (at.js) 的发行说明和其他平台变更。

>[!IMPORTANT]
>
>**mbox.js 生命周期结束**：从 2021 年 3 月 31 日起，[!DNL Adobe Target] 将不再支持 mbox.js 库。2021 年 3 月 31 日之后，所有从 mbox.js 进行的调用都将失败，并影响您通过提供默认内容而运行 [!DNL Target] 活动的页面。
>
>迁移到新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript库的最新版本，以避免您的网站出现任何潜在问题。 有关详细信息，请参阅[概述：为客户端 Web 实现 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## Target Standard/Premium 21.5.1（2021 年 6 月 7 日） 

此版本包括以下增强功能：

| 功能 | 详细信息 |
| --- | --- |
| ![Premium徽](/help/assets/premium.png) [!DNL Recommendations] [!UICONTROL 章目录] SearchAPI | 通过API以编程方式搜索[!DNL Recommendations]产品和内容目录，以识别符合搜索条件的项目并简化目录管理。<br>**限制和说明**:<ul><li>项目超过2,000,000个的环境不支持通过API进行目录搜索。</li><li>与通过[!DNL Target] UI的目录搜索结果相比，通过API的目录搜索结果更新的速度要快。 [!DNL Target] UI中的目录搜索可能需要额外的时间才能反映最新结果。</li></ul>有关更多信息，请参阅&#x200B;*[!DNL Adobe Target][!DNL Recommendations] API*&#x200B;指南中的[搜索实体](http://developers.adobetarget.com/api/recommendations/#tag/Searching-Entities) 。 |

此版本维护版本包含以下修复。

* 修复了在刷新[!UICONTROL Audiences]页面时，导致默认工作区更改为其他工作区的问题。 (TGT-38871)
* 修复了在[!UICONTROL Administration] > [!UICONTROL Implementation]中有时导致出现错误消息“您的全局mbox可能未同步”的问题。 请尝试重新保存它。”

## ![Adobe Experience Platform Web SDK](/help/assets/platform.png) [!DNL Adobe Experience Platform Web SDK] 版本2.5.0（2021年6月1日）

此版本的[!DNL Platform Web SDK]支持以下功能：

| 功能 | 详细信息 |
| --- | --- |
| 对[!UICONTROL Analytics for Target](A4T)的重定向支持 | 现在，使用[A4T](/help/c-integrating-target-with-mac/a4t/a4t.md)时，Platform Web SDK支持[!DNL Target]重定向。<br>有关更多信息，请参阅 [实施 [!DNL Target] 的Analytics](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)。 |

## at.js版本2.5.0（2021年5月13日）

此版本的 at.js 包括以下增强功能和更改：

* 对 at.js 的[设备上决策](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md)支持。
* 对 Automated Personalization 活动的[预览链接](/help/c-activities/c-activity-qa/activity-qa.md)支持。

此版本还删除了对Microsoft Internet Explorer 10、Internet Explorer 11和所有旧版本的支持。 at.js 2.5.0及更高版本仍支持Microsoft Edge。

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 文档更改、以往的发行说明和 Experience Cloud 发行说明

除了针对每个发行的说明外，以下资源还提供更多其他信息：

| 资源 | 详细信息 |
|--- |--- |
| 文档更改 | 查看这些发行说明中未包括的关于本指南的更新的详细信息。<br>有关更多信息，请参阅[文档更改](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)。 |
| 以前版本的发行说明 | 查看与以前版本的 Target Standard 和 Target Premium 中的新增功能和增强功能相关的信息。<br>有关更多信息，请参阅[以前版本的发行说明](/help/r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 发行说明 | 查看 Adobe Experience Cloud 解决方案的最新发行说明。<br>有关详细信息，请参阅 [Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans)。 |

## 预发行信息 {#section_5D588F0415A2435B851A4D0113ACA3A0}

您可以通过以下资源了解下一个 Target 版本即将包含的功能。

| 资源 | 详细信息 |
|--- |--- |
| Adobe 优先产品更新 | 若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：<br>[](https://www.adobe.com/cn/subscription/priority-product-update.html)https://www.adobe.com/cn/subscription/priority-product-update.html |
| 即将推出的发行说明 | 有关当月 Target 发行版本的信息（包括预发行信息），请参阅 [Target 发行说明 - 预发行](/help/r-release-notes/target-release-notes.md)页面。 |
