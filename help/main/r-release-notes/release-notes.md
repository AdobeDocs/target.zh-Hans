---
keywords: 发行说明;新功能;版本;更新;更新;版本;增强;增强;修复;错误修复;更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 6bef27637c06f39ffc0e755f19e8a0870ec749e5
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 90%

---

# Target 发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的发行说明以及其他平台变更。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## [!DNL Target] Standard/Premium 22.9.1（交错发布：2022 年 9 月 13 日至 15 日）

此版本将按照以下交错发布计划发布：

* **9 月 13 日**：欧洲、中东和非洲 (EMEA) 区域
* **9 月 14 日**：美洲区域
* **9 月 15 日**：亚太 (APAC) 区域

此版本包含以下增强功能和修复：

* 在下载 at.js 2.10.0（及更高版本）时添加了 [!UICONTROL Cross-Domain] 选项以允许或禁用设置第三方 cookie. (TGT-43674)
* 更新了 [!DNL Target] UI，用于通知客户是否导入 [!DNL Recommendations] 馈送失败。 (TGT-35811)
* 修复了导致 [!UICONTROL Decision Offers] 在 [!UICONTROL Visual Experience Composer] (VEC) 中无法正常工作的问题。 (TGT-43866)
* 修复了在创建 [!UICONTROL Multivariate Testing] (MVT) 活动时选择[!UICONTROL 单击了一个元素]转换目标时导致显示错误消息的问题。 (TGT-43842)
* 修复了导致[!UICONTROL 印象]列无法显示在下载的 [!UICONTROL Automated Personalization] (AP) 活动的 CSV 报告文件中的问题。 (TGT-43780)
* 修复了在使用[!UICONTROL 基于表单的体验生成器]时，客户在复制体验后无法编辑 HTML/JSON 优惠的问题。 (TGT-43633)
* 修复了阻止客户将 [!UICONTROL A/B Test] 活动从非默认工作区复制到另一个非默认工作区的问题。 (TGT-41910)
* 修复了确保客户能够正确显示 [!DNL Recommendations] 对象（设计、标准、收藏集等） [!UICONTROL A/B测试] 和 [!UICONTROL 体验定位] (XT)活动，该活动包含推荐，同时还会删除不再使用的标准对象 [!DNL Target] UI和 [!DNL Recommendations] 后端。 (TGT-42331)
* 修复了在获取参数时导致 [!DNL Target]UI 中出现网络超时警报的问题。(TGT-43737)
* 进行了 UI 更新，以确保键盘可以进行某些拖放操作。(TGT-42969)
* 进行了 UI 更新，以确保文本字符串正确本地化。

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
| Adobe Experience Cloud 发行说明 | 查看 Adobe Experience Cloud 解决方案的最新发行说明。<br>有关更多信息，请参阅 [Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)。 |

## 预发行信息 {#section_5D588F0415A2435B851A4D0113ACA3A0}

您可以通过以下资源了解下一个 Target 版本即将包含的功能。

| 资源 | 详细信息 |
|--- |--- |
| Adobe 优先产品更新 | 若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：<br>[](https://www.adobe.com/cn/subscription/priority-product-update.html)https://www.adobe.com/cn/subscription/priority-product-update.html |
| 即将推出的发行说明 | 有关当月 Target 发行版本的信息（包括预发行信息），请参阅 [Target 发行说明 — 预发行](/help/main/r-release-notes/target-release-notes.md)页面。 |
