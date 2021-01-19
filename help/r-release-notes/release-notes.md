---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: 这些发行说明介绍了每个 Target Standard 和 Target Premium 版本的功能、增强功能、修复信息和已知问题。
title: 'Adobe Target 发行说明（当前版本） '
feature: Release Notes
translation-type: tm+mt
source-git-commit: 2dce7bbe94f20ad6f6732dfc3abceb69058a1f75
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Target 发行说明（当前版本）

这些发行说明介绍了每个 Target Standard 和 Target Premium 版本的功能、增强功能和修复信息。此外，还包含目标API、SDK、JavaScript库(at.js)的发行说明以及其他平台更改（如果适用）。

>[!IMPORTANT]
>
>**mbox.js终止使用**:2021年3月31日 [!DNL Adobe Target] 将不再支持mbox.js库。2021年3月31日之后，mbox.js发出的所有调用将正常失败，并会通过提供默认内容影响[!DNL Target]活动运行的页面。 我们建议所有客户在此日期之前迁移到新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript库的最新版本，以避免您的站点出现任何潜在问题。
>
>* **Adobe Experience PlatformWeb SDK**:Adobe Experience Platform [!UICONTROL Web ] SDK允许您通过Adobe Experience Edge Network与 [!DNL Experience Cloud] （包括）中 [!DNL Target]的各种服务进行交互。如果选择迁移到[!DNL Adobe Experience Platform Web SDK]，请参阅&#x200B;*Web SDK指南*&#x200B;中的[什么是Adobe Experience PlatformWeb SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)。
   >
   >
* **at.js**:与mbox.js相比，at.js JavaScript库具有许多优势。at.js可缩短Web实施的页面加载时间，提高安全性，并为单页应用程序提供更好的实施选项。 如果选择迁移到at.js，请参阅[At.js工作方式](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)和[Adobe Target技能生成器：开发人员聊天，将Adobe Target的mbox.js迁移到at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。
>
>
尽管mbox.js目前受支持（2021年3月31日之前），但自2017年7月起，我们尚未对此库提供功能更新。 通过将所有客户移至[!UICONTROL Adobe Experience PlatformWeb SDK]或at.js，我们的工程师和支持人员将能够为您提供新功能并优惠您期望从Adobe获得的支持。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## Target Standard/Premium 21.1.1（2021 年 1 月 19 日） 

此维护版本包含以下增强、修复和更改。

括号中的问题编号供 [!DNL Adobe] 内部使用。

* 在[!UICONTROL 自动目标]活动中，当使用[!UICONTROL 分析作为报告源](A4T)时，在选择[!DNL Adobe Analytics]度量时添加了警告。 [!UICONTROL 自动定] 位模型经过优化，可与二进制（基于转换）指标结合使用。选择连续指标（如收入）可能会产生次优结果，而[!UICONTROL 个性化洞察]报告可能不准确。 (TGT-38926)
* 在[!UICONTROL 自动目标摘要]报告中为使用A4T的[!UICONTROL 自动目标]活动添加了状态图标。 报表中每个体验旁边的绿色复选标记表示已为该体验生成个性化的机器学习模型。时钟图标表示用于构建模型的流量不足。(TGT-38925)
* 生成使用A4T和[!DNL Analytics]转换度量的[!UICONTROL 自动目标段]和[!UICONTROL 重要属性]活动的报告，其外观与使用[!DNL Target]作为报告源时相同。 (TGT-38931)
* 在[!UICONTROL Recommendations] [!UICONTROL 集合]环境中添加了列表过滤选项。 (TGT-38353)
* 修复了导致在[!UICONTROL Recommendations]集合中显示错误产品计数的问题。 (TGT-39162)
* 向[!UICONTROL Recommendations][!UICONTROL 目录搜索]添加了[!UICONTROL 上次更新]筛选器。 (TGT-38340)
* 修复了[!UICONTROL Recommendations]中的一个问题，该问题导致在更改行业垂直后，[!UICONTROL 创建序列]页面挂起。 (TGT-38160)
* 修复了在启用设备协作且用户从[!DNL Target]作为活动源更改为[!DNL Analytics](A4T)时，无法保存报告的问题。 (TGT-38163)
* 修复了阻止用户从[!UICONTROL Automated Personalization](AP)活动中的优惠删除受众的问题。 (TGT-39058)
* 修复了导致某些客户在[!UICONTROL 受众信息]卡中显示不正确的时间帧(开始和结束日期)的问题。 (TGT-39150)
* 修复了导致某些客户无法在[!UICONTROL 默认工作区]中看到活动列表的问题。 (TGT-38526)

## at.js 2.4.0（2021年1月14日）

此版本的at.js是维护版本，包含以下修复：

* 为用户档案API customerId增加对统一投放/平台ID的支持。
* 修复无效样式标记注入。

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 文档更改、以往的发行说明和 Experience Cloud 发行说明

除了针对每个发行的说明外，以下资源还提供更多其他信息：

| 资源 | 详细信息 |
|--- |--- |
| 文档更改 | 查看可能未包含在这些发行说明中的针对该指南的详细更新信息。<br>有关更多信息，请参阅[文档更改](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)。 |
| 以前版本的发行说明 | 查看与以前版本的 Target Standard 和 Target Premium 中的新增功能和增强功能相关的信息。<br>有关更多信息，请参阅[以前版本的发行说明](/help/r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 发行说明 | 查看 Adobe Experience Cloud 解决方案的最新发行说明。<br>有关详细信息，请参阅 [Experience Cloud发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)。 |

## 预发行信息 {#section_5D588F0415A2435B851A4D0113ACA3A0}

您可以通过以下资源了解下一个 Target 版本即将包含的功能。

| 资源 | 详细信息 |
|--- |--- |
| Adobe 优先产品更新列表 | 若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| 即将推出的发行说明 | 有关当月 Target 发行版本的信息（包括预发行信息），请参阅 [Target 发行说明 - 预发行](/help/r-release-notes/target-release-notes.md)页面。 |
