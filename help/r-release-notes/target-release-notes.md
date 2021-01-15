---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease
description: 发行说明，提供有关最新或即将发布的DNLAdobe Target版本的功能、增强和修复的信息。
title: Adobe Target预发行说明
feature: Release Notes
translation-type: tm+mt
source-git-commit: a85a5c10c31fb0d7eb00c21ff03b2012d044de45
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 20%

---


# Target 发行说明（预发行版本）

本文包含预发行信息。 发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新日期：2021 年 1 月 14 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。这些页面上的信息可能相同，具体取决于发布时间。 括号中的问题编号供 [!DNL Adobe] 内部使用。

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

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
