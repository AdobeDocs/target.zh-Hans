---
keywords: 发行说明;新功能;版本;更新;更新;版本;增强;增强;修复;错误修复;更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: a03975f8f14db3cb8be0850130aab8d34c4c7fc0
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 47%

---

# Target 发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外， [!DNL Target] API、SDK、 [!DNL Adobe Experience Platform Web SDK]、 at.js和其他平台更改（如果适用）也包含在内。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## Target平台版本（2022年4月13日）

此版本包含以下更新：

* 修复了在使用配置文件脚本捕获IP地址的最后八位字节时，确保正确进行模糊处理的问题。 (TNT-44076)

## [!DNL Target Standard/Premium] 22.3.1（错开发行，日期待定）

此版本包含以下更改和增强功能：

* 修复了在编辑、激活和停用配置文件脚本后，对配置文件脚本所做的编辑还原到原始未编辑脚本的问题。 配置文件脚本现在保持其编辑状态。 (TGT-43249)
* 修复了导致 [!DNL Target] 在移动活动中使用的具有“草稿”状态的受众时使用UI:“我们无法完成您的请求。 如果问题仍然存在，请联系Adobe客户关怀。” (TGT-43212)
* 修复了导致 [!UICONTROL 包括] 和 [!UICONTROL 排除] 用于编辑活动时禁用组合受众的选项。 (TGT-43422)
* 修复了某些客户在编辑活动时无法看到可用受众列表的问题。 (TGT-43404)
* 修复了导致某些客户无法从“[!UICONTROL 要从中排除的IP [!DNL Target] 报告数据]&quot;列表 [!UICONTROL 管理] > [!UICONTROL 报表]. (TGT-43384)
* 修复了在受众标准中无法使用负数的问题，该负数会检查任何变量是否“大于”、“大于或等于”、“小于”或“小于或等于”。 (TGT-43367)
* 修复了阻止客户查看 [!UICONTROL 受众详细信息] 卡片。 (TGT-43303)
* 修复了导致 [!DNL Target] UI或新 [!UICONTROL 受众] UI为某些客户过早超时。 （TGT-42590 和 TGT-43273）

## [!DNL Target] 平台版本（3月30日）

此版本包含以下增强功能：

* 对于使用Analytics作为报表源(A4T)并在客户端处理事件的活动，点击跟踪量度将在交付API请求中包含分析有效负载。 (TNT-43073)

## [!DNL Target Standard] 受众刷新（3月28日）

此版本包含以下更新：

* 新 [!UICONTROL 受众] 将为所有用户启用UI [!DNL Target Standard] 客户。

## Target Standard/Premium客户工程修复（2022年3月22日）

此维护版本包含以下增强功能：

* 添加了返回 [!DNL Analytics] 有效负载数据 `prefetch` 视图和 `pageLoad` 使用 [!UICONTROL 交付API] 活动 [!UICONTROL 将Analytics作为报表源] (A4T)。 (TNT-43198)
* 更新了机器人过滤用户代理列表，以允许使用在日本常用的浏览器类型。 (TNT-43867)

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh_Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

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
| 即将推出的发行说明 | 有关当月 Target 发行版本的信息（包括预发行信息），请参阅 [Target 发行说明 - 预发行](/help/main/r-release-notes/target-release-notes.md)页面。 |
