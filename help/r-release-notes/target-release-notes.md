---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: 发行说明，提供有关最新或即将发布的DNLAdobe Target版本的功能、增强和修复的信息。
title: Adobe Target预发行说明
feature: null
translation-type: tm+mt
source-git-commit: 531e147d99bbc73414f790d66a3633bd1de8f50f
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 11%

---


# Target 发行说明（预发行版本）{#target-release-notes-prerelease}

本文包含预发行信息。 发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新日期：2021 年 1 月 6 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。这些页面上的信息可能相同，具体取决于发布时间。 括号中的问题编号供 [!DNL Adobe] 内部使用。

>[!IMPORTANT]
>
>**mbox.js终止使用**:2021年3月31日 [!DNL Adobe Target] 将不再支持mbox.js库。2021年3月31日之后，mbox.js发出的所有调用将正常失败，并会通过提供默认内容影响[!DNL Target]活动运行的页面。 我们建议所有客户在此日期之前迁移到新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript库的最新版本，以避免您的站点出现任何潜在问题。
>
>* **Adobe Experience PlatformWeb SDK**:Adobe Experience Platform [!UICONTROL Web ] SDK允许您通过Adobe Experience Edge Network与 [!DNL Experience Cloud] （包括）中 [!DNL Target]的各种服务进行交互。如果选择迁移到[!DNL Adobe Experience Platform Web SDK]，请参阅&#x200B;*Web SDK指南*&#x200B;中的[什么是Adobe Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html)。 有关[!DNL Target]特定信息，请参见[目标概述](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html)。
   >
   >
* **at.js**:与mbox.js相比，at.js JavaScript库具有许多优势。at.js可缩短Web实施的页面加载时间，提高安全性，并为单页应用程序提供更好的实施选项。 如果选择迁移到at.js，请参阅[At.js工作方式](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)和[Adobe Target技能生成器：开发人员聊天，将Adobe Target的mbox.js迁移到at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。
>
>
尽管mbox.js目前受支持（2021年3月31日之前），但自2017年7月起，我们尚未对此库提供功能更新。 通过将所有客户移至[!UICONTROL Adobe Experience PlatformWeb SDK]或at.js，我们的工程师和支持人员将能够为您提供新功能并优惠您期望从Adobe获得的支持。

## Target Standard/Premium 20.10.1（2020 年 10 月 27 日） 

此版本包含以下新增功能：

| 功能 | 详细信息 |
| --- | --- |
| [设备上决策](https://adobetarget-sdks.gitbook.io/docs/on-device-decisioning/introduction-to-on-device-decisioning) | 设备上决策允许营销人员和产品开发人员以接近零的延迟从用户设备内跨渠道交付实验和机器学习驱动的个性化。<br>速度和性能至关重要——在客户洞察和用户满意度方面。<br>通过设备决策，您可以将A/B测试和体验定位(XT)活动类型中的关键个性化和试验说明编译为“优化对象：”JSON对象，这些对象通过CDN加载到客户设备上。由于设备上决策与[!DNL Adobe Experience Cloud]产品本机连接，[!DNL Target]用户可以快速分析并更快地体验迭代。<br>有关详细信息，请参[阅*设备决策](/help/c-implementing-target/c-api-and-sdk-overview/on-device-decisioning.md)。 |

此版本包含以下增强、修复和更改：

* 修复了阻止[!UICONTROL 平均提升置信度间隔]和[!UICONTROL 置信度]在[!UICONTROL Total]行的[!DNL Auto-Target]报告中显示的问题。 正确显示所有个体体验的度量值。 (TGT-37301)
* 修复了从9月15日下午2:30开始影响[!DNL Adobe Target Premium]用户[!UICONTROL 自动目标]报告的问题。(PDT)10月6日上午9点25分。(PDT)。 当查看受影响的转换量度的报告（使用“[!UICONTROL 已查看页面]”或“[!UICONTROL 已单击mbox]”选项进行配置）时，会错误报告转换率。 此时不存在已知的投放问题。 有关如何重新同步和更正报告的信息，请参见&#x200B;*已解决问题**中的*&#x200B;已解决问题&lt;a3/>下的[自动目标报告](/help/r-release-notes/known-issues-resolved-issues.md#at-metrics)。
* 在[!UICONTROL 目录搜索]表中添加了可选的[!UICONTROL 上次更新时间]列和上次更新时间]筛选器。 [!UICONTROL 此增强功能省时省力，因为您不必打开每个项目来查看上次更新的时间，并且您可以按上次更新项目的日期进行筛选。

   ![上次在列和滤镜处更新的插图](/help/r-release-notes/assets/column-and-filter.png)

* 更新旨在帮助使目标UI符合[Web内容辅助功能准则](https://www.w3.org/WAI/standards-guidelines/wcag/) 2.0 A级别和AA成功标准(WCAG 2.0 AA)。 （TGT-34384 和 TGT-24679）
* 改进了内容安全策略(CSP)。 (TGT-37035)
* 介绍了一种将客户端代码指定为使用CNAME的客户参数的方法。 (TNT-38571)
* [!DNL Adobe Experience Cloud] 文档正在移 [!DNL Experience League]至在10月份，所有发行说明、文章、视频和教程都将从当前位于`docs.adobe.com`的位置移动到[!DNL Experience League]。 此移动可确保从单一位置提供所有学习、自助、支持和社区内容。 发生此更改时，您无需执行任何操作，因为所有链接都将重定向到[!DNL Experience League]。 我们将在切换开始时更新发行说明。

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
