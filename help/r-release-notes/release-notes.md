---
keywords: 发行说明;新功能;版本;更新;更新;版本;增强;增强;修复;错误修复;更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么新功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 8fe168950effe60ead262c842fe9d89d1e376e57
workflow-type: tm+mt
source-wordcount: '1140'
ht-degree: 96%

---

# Target 发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 Target API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的发行说明以及其他平台变更。

>[!IMPORTANT]
>
>**mbox.js 生命周期结束**：从 2021 年 3 月 31 日起，[!DNL Adobe Target] 将不再支持 mbox.js 库。2021 年 3 月 31 日之后，所有从 mbox.js 进行的调用都将失败，并影响您通过提供默认内容而运行 [!DNL Target] 活动的页面。
>
>请迁移到新 [!DNL Adobe Experience Platform Web SDK] 或 at.js JavaScript 库的最新版本，以避免您的网站出现任何潜在问题。有关更多信息，请参阅[概述：为客户端 Web 实现 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## at.js版本2.8.0（2022年1月7日）

的 [!DNL Target] at.js JavaScript库现在可收集功能使用情况和性能遥测数据。 不会收集个人数据。 通过设置 `telemetryEnabled` 为false `targetGlobalSettings`. 有关更多信息，请参阅 [targetGlobalSettings中已启用遥测](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#telemetry).

## [!DNL Target Standard/Premium] 21.10.5（2021 年 10 月 28 日）

此维护版本包含以下增强功能：

| 功能 | 详细信息 |
| --- | --- |
| 可视化体验编辑器 (VEC) | 添加了对 [Web 组件](https://developer.mozilla.org/en-US/docs/Web/Web_Components)的支持。可以在自定义元素以及自定义元素内部的元素上创建和测试个性化的体验和方案。<br>有关更多信息，请参阅[可视化体验编辑器选项](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#custom)。 |

## [!DNL Target Standard/Premium] 21.10.4（2021 年 10 月 21 日）

此维护版本包含以下增强功能：

| 功能 | 详细信息 |
| --- | --- |
| 基于购物车的推荐 | 添加了新的算法系列，可根据访客购物车的内容提供推荐。<br>有关更多信息，请参阅[创建标准](/help/c-recommendations/c-algorithms/create-new-algorithm.md)中的“基于购物车”，[计划和实施推荐](/help/c-recommendations/plan-implement.md)中的“购物车添加/购物车查看/结账页面”和“排除访客购物车中已有的商品”，以及[根据推荐键提供推荐](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md)中的“基于购物车”。 |

## [!DNL Target Standard/Premium] 21.10.3（2021 年 10 月 19 日）

此维护版本包含以下增强功能、修复和更改：

* 修复了阻止客户在 [!DNL Analysis Workspace] 中通过单击 [!DNL Target] 活动报告中的[!UICONTROL 在 Analytics 中查看]按钮来打开 [!UICONTROL A4T] 面板的问题。（TGT-42099、TGT-42100）
* 修复了在使用[!UICONTROL 基于表单的体验编辑器]来编辑 [!UICONTROL A/B 测试]和[!UICONTROL 体验定位] (XT) 活动时，导致[!UICONTROL 编辑设计]按钮不显示的问题。(TGT-41980)
* 修复了在创建新的[!UICONTROL 推荐]活动时，导致在标准选择中不显示[!UICONTROL 兼容]复选框的问题。(TGT-42053)
* 修复了由于缺少 [!DNL Analytics] 权限而无法选择 [!DNL Analytics] 作为报表源 (A4T) 时显示的不正确的错误消息。(TGT-41954)
* 实施了多个辅助功能修复，以改进 [!DNL Target] UI 中的键盘导航功能。

## [!DNL Target Standard/Premium] 21.10.2（2021 年 10 月 13 日）

在将 [!DNL Target] [!UICONTROL 受众]与 [!DNL Adobe Experience Platform Web SDK] 结合使用时，添加了以下增强功能：

* 在 [!DNL Target] UI 中的各个位置添加了警告图标、弹出框和消息，以指示已从来源中删除受众，并且受众不再可用于 [!DNL Target] 活动中。

   下图显示了这些图标、弹出框和消息的一些显示位置：

   * [!UICONTROL 活动]列表页面

      ![“活动”列表页面上的“已从来源中删除受众”消息](assets/deleted-at-source-audiences-list.png)

   * 活动[!UICONTROL 概述]页面：

      ![概述页面上的“已从来源中删除受众”消息](assets/deleted-at-source-overview.png)

   * 活动创建工作流的[!UICONTROL 体验]步骤：

      ![[!UICONTROL 体验]页面上的“已从来源中删除受众”消息](assets/deleted-at-source-experiences.png)

   * 活动创建工作流的[!UICONTROL 定位]步骤：

      ![[!UICONTROL 定位]页面上的“已从来源中删除受众”消息](assets/deleted-at-source-targeting.png)

   * 活动创建工作流的[!UICONTROL 目标与设置]步骤：

      ![[!UICONTROL 目标与设置]页面上的“已从来源中删除受众”消息](assets/deleted-at-source-goals-settings.png)

   * 受众细化（活动创建工作流的[!UICONTROL 定位]步骤中的[!UICONTROL 替换受众]）：

* 如果您尝试使用“合并受众”功能，而其中某个受众已从来源中删除，则将禁用[!UICONTROL 保存]。

## [!DNL Target Standard/Premium]21.10.1（2021 年 10 月 6 日）

此版本包含以下新功能：

| 功能 | 详细信息 |
| --- | --- |
| [!UICONTROL 受众] UI 刷新 | 作为 [!DNL Adobe Target] 团队努力改进的 [!DNL Target] 用户体验的一部分，此版本刷新了 [!DNL Target] UI 中的[!UICONTROL 受众]和[!UICONTROL 个人资料脚本]页面。此更新统一并标准化了以前不一致的设计模式，并添加了新的增强功能，例如：<ul><li>同时选择和删除多个受众的功能</li><li>刷新的[受众生成器设计](/help/c-target/c-audiences/create-audience.md)</li><li>[!UICONTROL 受众]库规则生成器中的排除规则支持</li><li>新的“受众来源”筛选器，可用于更快地发现受众</li><li>会话持久搜索和筛选选项</li></ul>有关更多信息，请参阅[受众](/help/c-target/target.md)。<br>**注意**：新的[!UICONTROL 受众] UI 仅向部分客户提供。该更新将于 2022 年 1 月面向所有客户逐步推出。 |
| [!UICONTROL 个人资料脚本] UI 刷新 | [!UICONTROL 个人资料脚本]库也已更新，并且包含一个更新后的界面和几项生产力更新：<ul><li>同时选择和删除多个个人资料脚本的功能</li><li>个人资料脚本的新代码编辑器</li><li>代码编辑器中的语法突出显示和错误检查</li><li>通过键盘快捷键自动完成令牌（mbox 或 profile）参数</li></ul>有关更多信息，请参阅[访客个人资料](/help/c-target/c-visitor-profile/visitor-profile.md)。<br>**注意**：新的[!UICONTROL 个人资料脚本] UI 仅向部分客户提供。该更新将于 2022 年 1 月面向所有客户逐步推出。 |
| ![Premium 徽章](/help/assets/premium.png) 推荐标准的创建和编辑 | [!UICONTROL 推荐标准]的创建和编辑工作流已经过简化，以简化选择正确的推荐算法和设置以实现目标的过程。<br>有关更多信息，请参阅[创建标准](/help/c-recommendations/c-algorithms/create-new-algorithm.md)。 |
| ![Premium 徽章](/help/assets/premium.png) 推荐的回溯时段和算法刷新率改进 | 您现在可以运行具有 6 小时的回溯时段的“查看次数最多”和“最畅销商品”算法，以捕获最近流行的内容。选择 6 小时的回溯时段后，您的推荐结果会全天每 3-6 小时更新一次。<br>有关更多信息，请参阅&#x200B;*创建标准*&#x200B;中的[数据源](/help/c-recommendations/c-algorithms/create-new-algorithm.md#data-source)。 |

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh_Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
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
