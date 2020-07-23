---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: 这些发行说明介绍了每个 Target Standard 和 Target Premium 版本的功能、增强功能、修复信息和已知问题。
title: 'Adobe Target 发行说明（当前版本） '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: b9a445d1b9e0b4b06b10370c6fefd570380d48f7
workflow-type: tm+mt
source-wordcount: '904'
ht-degree: 30%

---


# Target 发行说明（当前版本）{#target-release-notes-current}

这些发行说明介绍了每个 Target Standard 和 Target Premium 版本的功能、增强功能和修复信息。此外，还包含目标API、SDK、JavaScript库(at.js)的发行说明以及其他平台更改（如果适用）。

>[!IMPORTANT]
>
>* **Adobe再次在Gartner个性化引擎魔力象限报告中被评为领导者**: 在Gartner 2020年个性化引擎魔力象限报告中，Adobe再次被评为行业领袖。 Gartner个性化引擎魔力象限评估了属于两个类别的15个供应商： 愿景和执行能力的完整性。 [在Adobe博客上阅读相关信息](https://theblog.adobe.com/adobe-again-named-leader-in-gartner-magic-quadrant-for-personalization-engines/)。
   >
   >
* **mbox.js弃用**: 2020年8月30日，Adobe Target将不再支持mbox.js库。 2020年8月30日之后，mbox.js发出的所有调用将正常失败，并会通过提供默认内容影响目标活动运行的页面。 我们建议所有客户在此日期之前迁移到at.js库的最新版本，以避免您的站点出现任何潜在问题。 有关详细信息，请 [参阅At.js工作方式](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) 和 [Adobe Target技能生成器： 开发人员聊天，将Adobe Target的mbox.js迁移到at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。
   >
   >   
   尽管目前支持mbox.js，但自2017年7月起，我们便未对此库提供功能更新。 较新的at.js比mbox.js具有许多优势。 at.js可缩短Web实施的页面加载时间，提高安全性，并为单页应用程序提供更好的实施选项。
   >
   >   
   通过将所有客户转移到at.js，我们的工程师和支持人员将能够为您提供新功能并优惠您期望从Adobe获得的支持。
   >
   >
* **目标通知**: 有关即将进行的目标的信息，请参阅事件公告页，包括目标技能生成器会话、开发人员聊天、网络研讨会和目标咖啡休息会话。 有关详细信息，请参阅 [目标公告](/help/r-release-notes/target-announcements.md)。


括号中的问题编号供 [!DNL Adobe] 内部使用。

## at.js 2.3.2（2020年7月24日）

此版本的at.js是维护版本，包括以下修复：

* 修复了脚本或代码向窗口或文档添加默认属性时的错误。

## Target Standard/Premium 20.7.1（2020 年 7 月 27 日） 

此版本包含以下更改：

### [!UICONTROL 管理] 部分UI刷新

我们正在逐步重写整个 [!DNL Target] UI，使用新的技术堆栈，以便能够优惠改进的性能、减少发布新功能时所需的维护时间以及改善整个产品的用户体验。 刷新的第一个部分是 [!UICONTROL Setup] （设置）部分，它已更名为 [!UICONTROL Administration]（管理）

作为此刷新的一部分，您将能够使用“管理”部分中的页面轻松执行 [!UICONTROL 许多] 操作，如：

* 从“实施”选项卡(“管理”>“ [!UICONTROL 实施] ”)下&#x200B;**[!UICONTROL 载最新]** 的at.js **[!UICONTROL 文件]**。
* 自定义您的at.js设置，并可轻松查看更改(“**[!UICONTROL 管理]** ”> **[!UICONTROL “实]**&#x200B;施”)。
* 修改增强的报告设置，如默认货币和时区、要从报告中排除的IP等。 (**[!UICONTROL 管理]** > **[!UICONTROL 报告]**)
* 出于隐私原因模糊处理访客IP **[!UICONTROL 地址]** (“管 **[!UICONTROL 理”]**>“实施”)
* 在AdobeAdmin Console（“管理”>“用户”）中管理每个工作区的用户及其角色的现&#x200B;**[!UICONTROL 有视图]** ，之 **[!UICONTROL 前再进]**&#x200B;行列表。
* 搜索并过滤“管理”部分中 [!UICONTROL 的所有] 表。

有关详细信息，请参 [阅管理目标概述](/help/administrating-target/administrating-target.md)。

### 增强功能、修复和变更

此版本包含以下增强、修复和更改：

* 修复了在刷新后无法保留站点首选项的问题。 (TGT-37239)
* 修复了“在后插 [!UICONTROL 入”] >“图 [!UICONTROL 像”无法正常使用] 可缩放矢量图形(SVG)图像的问题。 (TGT-37242)
* 修复了具有“发布者”角 [!UICONTROL 色的用户] ，该问题导致无法删除草稿活动。 (TGT-37358)
* 修复了在选择“我的所有工作区”时阻止 [!UICONTROL 用户编辑活动] 的问题。 (TGT-37276)

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明-目标服务器端API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | 与Adobe Target的服务器端API相关的发行说明。 |
| [发行说明-目标Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | 与Adobe Target的Node.js SDK相关的发行说明。 |
| [发行说明-目标Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | 与Adobe Target的Java SDK相关的发行说明。 |
| [at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 有关Adobe Targetat.js JavaScript库各版本中更改的详细信息。 |
| [mbox.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | 此页面显示对 mbox.js 的每个版本所做的更改。<br>请注意，mbox.js库不再在开发中。 所有客户都应该从 mbox.js 迁移到 at.js。 |

## 文档更改、以往的发行说明和 Experience Cloud 发行说明 {#section_1BC5F5208DA548E9B4344A0836E4B943}

除了针对每个发行的说明外，以下资源还提供更多其他信息：

| 资源 | 详细信息 |
|--- |--- |
| 文档更改 | 查看可能未包含在这些发行说明中的针对该指南的详细更新信息。<br>有关更多信息，请参阅[文档更改](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)。 |
| 以前版本的发行说明 | 查看与以前版本的 Target Standard 和 Target Premium 中的新增功能和增强功能相关的信息。<br>有关更多信息，请参阅[以前版本的发行说明](../r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 发行说明 | 查看 Adobe Experience Cloud 解决方案的最新发行说明。<br>有关详细信息，请参阅 [Experience Cloud发行说明](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)。 |

## 预发行信息 {#section_5D588F0415A2435B851A4D0113ACA3A0}

您可以通过以下资源了解下一个 Target 版本即将包含的功能。

| 资源 | 详细信息 |
|--- |--- |
| Adobe 优先产品更新列表 | 若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| 即将推出的发行说明 | 有关当月 Target 发行版本的信息（包括预发行信息），请参阅 [Target 发行说明 - 预发行](/help/r-release-notes/target-release-notes.md)页面。 |
