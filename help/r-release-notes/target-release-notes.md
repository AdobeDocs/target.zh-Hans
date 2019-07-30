---
description: 提供有关最新或即将推出的[！DNL Adobe Target]版本。
keywords: 发行说明
seo-description: 提供有关最新或即将推出的[！DNL Adobe Target]版本。
seo-title: Adobe Target发行说明(预发行版)
solution: Target
title: Target 发行说明（预发行版本）
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: f49c0c94afe6bf8aadbfb76930b57bf7cd5602dc

---


# Target 发行说明（预发行版本）{#target-release-notes-prerelease}

下列发行说明将介绍 [!DNL Adobe Target] 最新版本或即将发布的版本的功能、增强功能、修复信息和已知问题。

**上次更新日期：2019 年 7 月 24 日**

>[!NOTE]
>
>下列发行说明包含预发布的信息。发行日期、功能和其他信息如有更改，恕不另行通知。要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。这些页面上的信息可能相同，也可能不同，具体取决于发行时间。
>
>The issue numbers in parentheses are for internal [!DNL Adobe] use.

## Target Standard/Premium 19.7.1（2019 年 7 月 24 日）{#tgt-19-7-1}

此版本包括以下新增功能和增强功能：

| 功能 / 增强功能 | 描述 |
| --- | --- |
| 移动设备应用程序可视化体验编辑器 | 移动App CMS中会显示一个新的修改面板，它显示您设置的用于单击跟踪的元素。(TGT-31741)<br> See [Set up click tracking in the Mobile App](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md). |
| ![Premium BadgereComments](/help/assets/premium.png)<br>A/B测试和体验定位(XT)活动 | 推荐选项(算法)状态显示在包含Recommendations选件的A/B Test和XT活动的概述页面上。状态包括：结果就绪、结果未准备好和源失败。(TGT-33649)<br>See [Recommendations as an offer](/help/c-recommendations/recommendations-as-an-offer.md#status). |
| 通过Experience Cloud ID(ECID)库对. js2.0+进行跨域跟踪支持 | 以前，在. js中不支持跨域跟踪。*x* 目前不支持选择加入支持。在此版本中，使用. js2.0或更高版本的客户现在可以通过ECID库使用跨域跟踪。必须将ECID库与at. js2.0或更高版本一起安装在页面上，以便跨域跟踪工作。[必须使用Experience Cloud ID库4.3.0+](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) 。<br>请参阅 [位于. js2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md#cross-domain)的跨域跟踪支持。 |
| 通过Experience Cloud ID(ECID)库4.3针对Apple的ITP2.1和ITP2.2提供支持 | 如今，Target客户可以通过利用Adobe的CNAME认证计划减轻Apple的ITP2.1和ITP2.2。<br>在此版本中，Target引入了与ECID库4.3的无缝集成，它利用服务器端Cookie减轻ITP2.1和ITP2.2。强烈建议Target客户与Target的JavaScript库一起部署 [EID库4.3+](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) ，以减轻将来的任何ITP版本。EID库将继续推出增强功能，为浏览器引入的不断变化的cookie策略提供强大的解决方案。<br>请参阅 [Apple智能跟踪预防(ITP)2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)。 |

## at. js version2.1.1(2019年月24日)

此版本的. js是维护版本，包含以下增强和修复：

（括号中的问题编号供 Adobe 内部使用。）

* 修复了使用Visual Experience Composer(CMS)中的“目标和设置”页面上的“单击跟踪”量度触发多个信标的问题。(TNT-32812)
* Fixed an issue that caused `triggerView()` to not render offers more than once. (TNT-32780)
* Fixed an issue with `triggerView()` to ensure that the request contains Marketing Cloud ID (MCID) information. (TNT-32776)
* Fixed an issue that prevented the `triggerView()` notification to fire even if there are no saved views. (TNT-32614)
* 修复了由于使用DecodeURIComponent导致URL包含格式错误的查询字符串参数导致错误的问题。(TNT-32710)
* The beacon flag is now set to "true" in the context of delivery requests sent via the `Navigator.sendBeacon()` API. (TNT-32683)
* 修复了阻止Recommendations选件在网站上为少数客户显示的问题。客户可以在交付API调用中看到选件内容，但该选件未在网站上应用。(TNT-32680)
* 修复了导致跨多个体验点击跟踪无法正常工作的问题。(TNT-32644)
* 修复了一个问题，该问题导致. js无法在第一个量度的渲染失败后应用第二个量度。(TNT-32628)
* Fixed an issue when passing `mboxThirdPartyId` using the `targetPageParams` function that caused the request payload to not be present in either the query parameters or in the request payload. (TNT-32613)
* 修复了一个问题，该问题导致在基于Chromium的浏览器(包括Google Chrome)中阻止显示和单击通知响应。(TNT-32290)

For information about this and previous versions of at.js, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

**增强功能、修复和更改**

* 修复了在添加重复值时无法清除Recommendations活动中的值的问题。(TGT-34996)
* 您现在可以从定位页面中删除“推荐”活动中的设计(三部分引导工作流的步骤2)。请注意，要删除设计，必须选择多个设计。(TGT-35118)
* 修复了某个问题导致某些客户无法在目标UI中正确加载或可编辑的问题。(TGT-35170)

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
