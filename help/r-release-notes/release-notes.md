---
keywords: 发行说明;新功能;版本;更新;更新;版本;增强;增强;修复;错误修复;更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解 [!DNL Adobe Target]当前版本中包含的新增功能、增强功能和修复。
title: 当前版本中包含哪些新增功能？
feature: 发行说明
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 8d8584bc5ea1d4ec7295c43238675d906fd37325
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 58%

---

# Target 发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，Target API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js和其他平台更改的发行说明（如果适用）也包含在内。

>[!IMPORTANT]
>
>**mbox.js 生命周期结束**：从 2021 年 3 月 31 日起，[!DNL Adobe Target] 将不再支持 mbox.js 库。2021 年 3 月 31 日之后，所有从 mbox.js 进行的调用都将失败，并影响您通过提供默认内容而运行 [!DNL Target] 活动的页面。
>
>请迁移到新 [!DNL Adobe Experience Platform Web SDK] 或 at.js JavaScript 库的最新版本，以避免您的网站出现任何潜在问题。有关更多信息，请参阅[概述：为客户端 Web 实现 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## at.js 2.6.1（2021年8月16日）

* 修复了使用设备上决策时“没有可用于混合模式的缓存项目”的错误。

## [!DNL Target] node.js SDK 2.2.0（2021年8月11日）

* 添加了SDK遥测数据收集
* 自动交付API客户端openapi代码生成

有关此版本和以前版本的更多信息，请参阅Github上[Target node.js SDK文档](https://github.com/adobe/target-nodejs-sdk)中的[更改日志](https://github.com/adobe/target-nodejs-sdk/blob/main/CHANGELOG.md) 。

## [!DNL Target Standard/Premium] 21.8.1（确定日期）

>[!NOTE]
>
>[!DNL Target Standard/Premium] 21.8.1版本已延迟。 版本21.8.1将在未来几天内发布，而不是在2021年8月4日发布。 更多详细信息（如果可用）。

此维护版本包含许多后端增强功能，包括以下面向客户的更改：

* 修复了导致在[!UICONTROL 基于表单的体验编辑器]中创建的[!UICONTROL 自动个性化]活动的报表引用报表中已删除的选件的问题。 此问题导致显示以下错误消息：“检索此报表的数据时遇到问题。 如果问题仍然存在，请联系Adobe客户关怀。” (TGT-41028)

## [!DNL Target Delivery API] （2021年8月3日）

此版本包含以下增强功能：

* mbox参数限制已增加到100个参数。 以前的限制是50个参数。 (TNT-41717)
* `categoryId`的限制已增加到256个字符。 以前的限制为128个字符。
* 向交付API中添加了以下[!DNL Adobe Audience Manager](AAM)详细信息：

   * AAM UUID:用于唯一标识用户的内部AAM ID。
   * dataPartnerId:数据合作伙伴的ID。
   * dataPartnerUserId:数据合作伙伴提供的用户ID。

   以前，交付API仅包含`dcsLocationHint`和`blob`。 (TNT-41644)

## at.js 2.6.0（2021 年 7 月 27 日）

* 每当 at.js 设置 `secureOnly` 设为 `true` 时，都向 Cookie 添加了安全属性。
* 现在可以在使用 `triggerView()` 时使用响应令牌。
* 修复了与 `CONTENT_RENDERING_NO_OFFERS` 事件相关的问题。现在，每当 [!DNL Target] 没有返回内容时，就会正确触发此事件。
* 使用 `prefetch` 请求时，正确返回了 [!DNL Anlytics for Target] (A4T) 单击指标详细信息。
* UUID 生成功能不再使用 `Math.random()`，而是依赖于 `window.crypto`。
* 在每次网络调用时都会正确延长 `sessionId` Cookie 到期日。
* [!UICONTROL 单页面应用程序] (SPA) 视图缓存初始化现在可以被正确处理并遵循 `viewsEnable` 设置。

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | 有关平台Web SDK每个版本中的更改的详细信息。 |
| [at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 文档更改、以往的发行说明和 Experience Cloud 发行说明

除了针对每个发行的说明外，以下资源还提供更多其他信息：

| 资源 | 详细信息 |
|--- |--- |
| 文档更改 | 查看这些发行说明中未包括的关于本指南的更新的详细信息。<br>有关更多信息，请参阅[文档更改](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)。 |
| 以前版本的发行说明 | 查看与以前版本的 Target Standard 和 Target Premium 中的新增功能和增强功能相关的信息。<br>有关更多信息，请参阅[以前版本的发行说明](/help/r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 发行说明 | 查看 Adobe Experience Cloud 解决方案的最新发行说明。<br>有关更多信息，请参阅 [Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans)。 |

## 预发行信息 {#section_5D588F0415A2435B851A4D0113ACA3A0}

您可以通过以下资源了解下一个 Target 版本即将包含的功能。

| 资源 | 详细信息 |
|--- |--- |
| Adobe 优先产品更新 | 若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：<br>[](https://www.adobe.com/cn/subscription/priority-product-update.html)https://www.adobe.com/cn/subscription/priority-product-update.html |
| 即将推出的发行说明 | 有关当月 Target 发行版本的信息（包括预发行信息），请参阅 [Target 发行说明 - 预发行](/help/r-release-notes/target-release-notes.md)页面。 |
