---
keywords: 发行说明;新功能;版本;更新;更新;版本;增强;增强;修复;错误修复;更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 5d3e5a15a262d29bd1d95af71baae52ed288b33e
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 80%

---

# Target 发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 Target API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的发行说明以及其他平台变更。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## Target Standard/Premium 22.2.1（2022 年 2 月 1 日）

此维护版本包含以下针对新 [!UICONTROL 受众] Target Standard/Premium 22.1.2版本中宣布的UI，该版本将在未来六周内向所有地区的客户推出。 这些修复使在中创建的受众的功能保持一致 [!DNL Adobe Target Standard/Premium].

* 修复了导入受众无法从 [!DNL Adobe Experience Platform], [!DNL Adobe Experience Cloud]和 [!DNL Adobe Target Classic] 分配为报表受众。 (TGT-43140)
* 添加了 [!UICONTROL 删除] 选项 [!UICONTROL 受众] 从中导入受众的列表 [!DNL Adobe Experience Platform], [!DNL Adobe Experience Cloud]和 [!DNL Adobe Target Classic]. 还添加了批量删除功能。 (TGT-42914)

## at.js 版本 2.8.1（2022 年 1 月 28 日）

* 修复了在[!UICONTROL 设备上决策] (ODD) 混合执行模式中 `pageLoad` 无法映射到 target-global-mbox 的问题
* 修复了有关 mbox 请求的分析详细信息的问题。
* 升级了开发依赖关系以修复安全漏洞。

## [!DNL Target Standard/Premium] 22.1.2（2022 年 1 月 26 日）

| 功能 | 详细信息 |
| --- | --- |
| [!DNL Target] 中的 [!DNL Adobe Experience Platform] 受众 | 您现在可以继续使用 [!DNL Target] 中的 [!DNL Adobe Experience Platform] 受众。[!DNL Target] 团队、[!DNL Experience Platform] [!DNL Destinations] 团队和 [!DNL Unified Profile Service] 团队很高兴地宣布推出“同一页面/下一页面个性化”用例。<br>利用在 [!DNL Adobe Experience Platform] 中创建的受众可提供更丰富的客户数据，从而带来更强大的个性化功能。的 [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=zh-Hans){target=_blank}(RTCDP)，内置于 [!DNL Adobe Experience Platform] 帮助公司整合来自多个企业来源的已知和匿名数据，以创建客户配置文件，以便用于在所有渠道和设备上实时提供个性化的客户体验。<br>有关更多信息，请参阅 [使用来自Adobe Experience Platform的受众](/help/c-target/c-audiences/audiences.md#aep) in *创建受众* 和 [同页和下一页个性化用例](https://www.adobe.com/go/destinations-edge-personalization-en){target=_blank} *目标概述* 的双曲余切值。 |
| [!UICONTROL 受众] UI 刷新 | 作为 [!DNL Adobe Target] 团队努力改进的 [!DNL Target] 用户体验的一部分，此版本刷新了 [!DNL Target] UI 中的[!UICONTROL 受众]和[!UICONTROL 个人资料脚本]页面。此更新统一并标准化了以前不一致的设计模式，并添加了新的增强功能，例如：<ul><li>同时选择和删除多个受众的功能</li><li>刷新的[受众生成器设计](/help/c-target/c-audiences/create-audience.md)</li><li>[!UICONTROL 受众]库规则生成器中的排除规则支持</li><li>新的“受众来源”筛选器，可用于更快地发现受众</li><li>会话持久搜索和筛选选项</li><li>为 [!DNL Target Premium] 客户在工作区之间移动受众的功能。</li></ul>有关更多信息，请参阅[受众](/help/c-target/target.md)。<br>**注意**：此功能将在八周后向不同地区的客户推出。 |
| [!UICONTROL 个人资料脚本] UI 刷新 | [!UICONTROL 个人资料脚本]库也已更新，并且包含一个更新后的界面和几项生产力更新：<ul><li>同时选择和删除多个个人资料脚本的功能</li><li>个人资料脚本的新代码编辑器</li><li>代码编辑器中的语法突出显示和错误检查</li><li>通过键盘快捷键自动完成令牌（mbox 或 profile）参数</li></ul>有关更多信息，请参阅[访客个人资料](/help/c-target/c-visitor-profile/visitor-profile.md)。<br>**注意**：此功能将在八周后向不同地区的客户推出。 |

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
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
