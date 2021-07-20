---
keywords: 发行说明;新功能;版本;更新;更新;版本;增强;增强;修复;错误修复;更新
description: 了解 [!DNL Adobe Target]当前版本中包含的新增功能、增强功能和修复，包括SDK、API和JavaScript库。
title: 当前版本中包括什么新功能？
feature: 发行说明
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 21c7675085bf5dc06bf9b1b38a82b2be4d4b0f76
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 54%

---

# Target 发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 Target API、SDK、JavaScript 库 (at.js) 的发行说明和其他平台变更。

>[!IMPORTANT]
>
>**mbox.js 生命周期结束**：从 2021 年 3 月 31 日起，[!DNL Adobe Target] 将不再支持 mbox.js 库。2021 年 3 月 31 日之后，所有从 mbox.js 进行的调用都将失败，并影响您通过提供默认内容而运行 [!DNL Target] 活动的页面。
>
>迁移到新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript库的最新版本，以避免您的网站出现任何潜在问题。 有关详细信息，请参阅[概述：为客户端 Web 实现 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## at.js 2.6.0（2021年7月16日）

* 每当at.js设置`secureOnly`设置为`true`时，都向Cookie添加了安全属性。
* 现在，使用`triggerView()`时，可使用响应令牌。
* 修复了与`CONTENT_RENDERING_NO_OFFERS`事件相关的问题。 现在，当没有从[!DNL Target]返回内容时，可正确触发此事件。
* [!DNL Anlytics for Target] (A4T)使用请求时，可正确返回点击量度详细 `prefetch` 信息。
* UUID生成不再使用`Math.random()`，而是依赖于`window.crypto`。
* 在每次网络调用中，`sessionId` Cookie到期正确延长。
* [!UICONTROL 单页应用程序](SPA)视图缓存初始化现已得到正确处理，并遵循`viewsEnable`设置。

## [!DNL Target Standard/Premium] 21.6.1（2021年6月30日）

此版本包含以下新增功能和增强功能。括号中的问题编号供 [!DNL Adobe] 内部使用。

| 功能 | 详细信息 |
| --- | --- |
| Analytics for Target (A4T) | 现在，在使用[!DNL Analytics]作为报表源(A4T)的活动中，单击[!UICONTROL Reports]页面上的“[!UICONTROL 在Analytics中查看]”链接，即会打开[!DNL Analysis Workspace]。 以前，链接会打开[!DNL Analytics]报表。 (TGT-36959) |

## Python SDK 1.0.0（2021年6月16日）

新的[!DNL Adobe Target]具有设备上决策功能的Python SDK现已推出。 此最新添加内容可增强服务器端SDK的[!DNL Target]包。 这些SDK可帮助您与[!DNL Target]集成，并加快使用所选语言实现价值的速度。 由于市场正在向无Cookie的世界转变，在这个世界中，第一方数据很有价值，因此服务器端集成正成为一种热门选择。 Target SDK提供市场上最流行的编程语言(Python、Java、JavaScript、C# / .Net)。

有关更多信息，请参阅[Adobe Target SDK指南](https://adobetarget-sdks.gitbook.io/docs/)中的[Python SDK文档](https://adobetarget-sdks.gitbook.io/docs/sdk-reference-guides/python-sdk)。

## ![Adobe Experience Platform Web SDK](/help/assets/platform.png) [!DNL Adobe Experience Platform Web SDK] 版本2.5.0（2021年6月1日）

此版本的[!DNL Platform Web SDK]支持以下功能：

| 功能 | 详细信息 |
| --- | --- |
| 对[!UICONTROL Analytics for Target](A4T)的重定向支持 | 现在，使用[A4T](/help/c-integrating-target-with-mac/a4t/a4t.md)时，Platform Web SDK支持[!DNL Target]重定向。<br>有关更多信息，请参阅 [实施 [!DNL Target] 的Analytics](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)。 |

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
