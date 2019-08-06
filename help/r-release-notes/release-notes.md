---
description: 这些发行说明提供了每个 Target Standard 和 Target Premium 版本的功能、增强、修复问题和已知问题等信息。
keywords: 发行说明;预发行
seo-description: 这些发行说明介绍了每个 Target Standard 和 Target Premium 版本的功能、增强功能、修复信息和已知问题。
seo-title: Adobe Target发行说明(当前版本)
solution: Target
title: Target 发行说明（当前版本）
topic: 推荐
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 51f52bb40a0af4dac63236d46e6d6f0286cbb877

---


# Target 发行说明（当前版本）{#target-release-notes-current}

这些发行说明介绍了每个 Target Standard 和 Target Premium 版本的功能、增强功能和修复信息。

## 公告

**2019年月31日**

[!UICONTROL 企业权限] 允许 [!DNL Target] 客户使用单个组织，但将其划分为不同团队或工作流程的工作区。[!UICONTROL 企业权限] 功能有助于跨团队有效扩展优化程序。尽管此功能在 [!DNL Target] UI中可用，但在2019年 [!DNL Target] 月发布之前，管理员API一直缺少相应的支持。Adobe更新了管理员API，以便您可以使用集成帐户访问单位中创建的所有工作区。因此，在早期，Admin API仅限于默认工作区，2019年月更新已授予具有 [!UICONTROL 审批人] 访问权限的所有工作区的访问权限。

在即将 [!DNL Target] 发布的2019年月版本中 [!UICONTROL ，Enterprise Permissions] 将为客户提供以下访问控制：

* 您可以选择可将集成应用到的工作区
* 您可以对Adobe I/集成应用角色： [!UICONTROL 审批人]、 [!UICONTROL 编辑者]或 [!UICONTROL 观察者]。

**需要操作**：当前，在所有工作区中对资源(活动、受众、优惠和报告)利用API进行CRUD操作的客户需要授予其现有的Adobe I/集成访问所需角色的所有工作区。在月发布之前，所有使用 [!UICONTROL 审批人] 访问权限操作的集成，无论从 [!UICONTROL “产品角色”] 下拉列表中选择的角色如何。在即将发布的版本中，您现在可以选择所需的角色。

此操作应在2019 **年月的一个月**&#x200B;内执行。在2019 [!DNL Target] 年月发布之后，访问控制将激活，如果您当前设置了该工作区，则您将仅观察到默认工作区。预先设置集成角色不会产生不利后果。

有关分步说明和更多信息，请参阅 [授予Adobe I/O集成权限以访问工作区和分配角色](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md)。

## 目标Mobile CMS SDK iOS2.1.0和Android1.1.0(2019年月日)

此版本的Mobile CMS SDK包含以下增强和修复：

（括号中的问题编号供 Adobe 内部使用。）

* 增加了在移动设备上预览“可视活动”的支持。(TGT-27875)
* 修复了 `UIImagePickerController` 由于使用而导致Apple Standard违规的问题。
* 删除了Android SDK中的GSON依赖关系。(TGT-31710)
* 修复了在创作时无法重置交付选件的问题。(TGT-35270)

## Target Standard/Premium 19.7.1（2019 年 7 月 24 日）{#tgt-19-7-1}

此版本包括以下新增功能和增强功能：

（括号中的问题编号供 Adobe 内部使用。）

| 功能/增强 | 描述 |
| --- | --- |
| 移动设备应用程序可视化体验编辑器 | 移动App CMS中会显示一个新的修改面板，它显示您设置的用于单击跟踪的元素。(TGT-31741)<br> 请参阅 [在移动应用程序中设置单击跟踪](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md)。 |
| ![Premium BadgereComments](/help/assets/premium.png)<br>A/B测试和体验定位(XT)活动 | 推荐选项(算法)状态显示在包含Recommendations选件的A/B Test和XT活动的概述页面上。状态包括：结果就绪、结果未准备好和源失败。(TGT-33649)<br>See [Recommendations as an offer](/help/c-recommendations/recommendations-as-an-offer.md#status). |
| 通过Experience Cloud ID(ECID)库对. js2.0+进行跨域跟踪支持 | 以前，在. js中不支持跨域跟踪。*x* 目前不支持选择加入支持。在此版本中，使用. js2.0或更高版本的客户现在可以通过ECID库使用跨域跟踪。必须将ECID库与at. js2.0或更高版本一起安装在页面上，以便跨域跟踪工作。[必须使用Experience Cloud ID库4.3.0+](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) 。<br>请参阅 [位于. js2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md#cross-domain)的跨域跟踪支持。 |
| 通过Experience Cloud ID(ECID)库4.3针对Apple的ITP2.1和ITP2.2提供支持 | 如今，Target客户可以通过利用Adobe的CNAME认证计划减轻Apple的ITP2.1和ITP2.2。<br>在此版本中，Target引入了与ECID库4.3的无缝集成，它利用服务器端Cookie减轻ITP2.1和ITP2.2。强烈建议Target客户与Target的JavaScript库一起部署 [EID库4.3+](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) ，以减轻将来的任何ITP版本。EID库将继续推出增强功能，为浏览器引入的不断变化的cookie策略提供强大的解决方案。<br>请参阅 [Apple智能跟踪预防(ITP)2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)。 |

**增强功能、修复和更改**

* 修复了在添加重复值时无法清除Recommendations活动中的值的问题。(TGT-34996)
* 您现在可以从定位页面中删除“推荐”活动中的设计(三部分引导工作流的步骤2)。请注意，要删除设计，必须选择多个设计。(TGT-35118)
* 修复了某个问题导致某些客户无法在目标UI中正确加载或可编辑的问题。(TGT-35170)

## at. js version2.1.1(2019年月24日)

此版本的. js是维护版本，包含以下增强和修复：

（括号中的问题编号供 Adobe 内部使用。）

* 修复了使用Visual Experience Composer(CMS)中的“目标和设置”页面上的“单击跟踪”量度触发多个信标的问题。(TNT-32812)
* 修复了导致不 `triggerView()` 渲染选件的问题。(TNT-32780)
* 修复了一 `triggerView()` 个问题，以确保请求包含Marketing Cloud ID(MCID)信息。(TNT-32776)
* 修复了即使没有保存的视图也会阻止 `triggerView()` 通知开火的问题。(TNT-32614)
* 修复了由于使用DecodeURIComponent导致URL包含格式错误的查询字符串参数导致错误的问题。(TNT-32710)
* 在通过 `Navigator.sendBeacon()` API发送的交付请求上下文中，信标标志现在设置为“true”。(TNT-32683)
* 修复了阻止Recommendations选件在网站上为少数客户显示的问题。客户可以在交付API调用中看到选件内容，但该选件未在网站上应用。(TNT-32680)
* 修复了导致跨多个体验点击跟踪无法正常工作的问题。(TNT-32644)
* 修复了一个问题，该问题导致. js无法在第一个量度的渲染失败后应用第二个量度。(TNT-32628)
* 修复了使用 `mboxThirdPartyId` 导致请求有效负荷不存在于查询参数或请求有效负荷中 `targetPageParams` 的函数时出现的问题。(TNT-32613)
* 修复了一个问题，该问题导致在基于Chromium的浏览器(包括Google Chrome)中阻止显示和单击通知响应。(TNT-32290)

For information about this and previous versions of at.js, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

## 文档更改、以往的发行说明和 Experience Cloud 发行说明 {#section_1BC5F5208DA548E9B4344A0836E4B943}

除了针对每个发行的说明外，以下资源还提供更多其他信息：

| 资源 | 详细信息 |
|--- |--- |
| 文档更改 | 查看可能未包含在这些发行说明中的针对该指南的详细更新信息。<br>有关更多信息，请参阅[文档更改](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)。 |
| 以前版本的发行说明 | 查看与以前版本的 Target Standard 和 Target Premium 中的新增功能和增强功能相关的信息。<br>有关更多信息，请参阅[以前版本的发行说明](../r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 发行说明 | 查看 Adobe Experience Cloud 解决方案的最新发行说明。<br>有关更多信息，请参阅 [Experience Cloud发行说明](https://marketing.adobe.com/resources/help/en_US/whatsnew/)。 |

## 预发行信息 {#section_5D588F0415A2435B851A4D0113ACA3A0}

您可以通过以下资源了解下一个 Target 版本即将包含的功能。

| 资源 | 详细信息 |
|--- |--- |
| Adobe 优先产品更新列表 | 若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| 即将推出的发行说明 | 有关当月 Target 发行版本的信息（包括预发行信息），请参阅 [Target 发行说明 - 预发行](/help/r-release-notes/target-release-notes.md)页面。 |
