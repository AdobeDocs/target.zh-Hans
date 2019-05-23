---
description: 可以与 at.js 一起使用的函数列表。
keywords: adobe.target.notification;元素;选择器;通知;扩展
seo-description: 可以在 Adobe Target 中结合 at.js JavaScript 库一起使用的函数列表。
seo-title: Adobe Target at.js 函数
solution: Target
subtopic: 入门指南
title: at.js 函数
topic: Standard
uuid: ec5f27a7-b22a-48c9-968c-9eb02830a2a6
translation-type: tm+mt
source-git-commit: c607b241afb535f324cd1357c8784a88fb183658

---


# at.js 函数{#at-js-functions}

可以与 Adobe Target at.js JavaScript 库一起使用的函数列表。单击“函数”列中的链接以了解更多信息和示例。

| 函数 | 详细信息 |
| --- | --- | 
| [adobe.target.getOffer(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md) | 此函数会触发用于获取 Target 选件的请求。使用 `adobe.target.applyOffer()` 来处理响应或使用您自己的成功处理。 |
| [adobe. target. getOfFers(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md)<br>(at. js2.x) | 此函数允许您通过传递多个 mbox 来检索多个选件。此外，还可以针对活跃活动中的所有视图检索多个选件。<br>**注意：** 此函数在. js2.x中引入。此函数不适用于. js版本1。*x* 之间的差异。 |
| [adobe.target.applyOffer(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffer.md) | 此函数用于应用响应内容。 |
| [adobe. target. applyOffers(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffers-atjs-2.md)<br>(at. js2.x) | 此函数允许您应用由adobe. target. getOffers()检索的多个选件。<br>**注意：** 此函数在. js2.x中引入。此函数不适用于. js版本1。*x* 之间的差异。 |
| [adobe. target. righterView(ViewName，options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-triggerview-atjs-2.md)<br>(at. js2.x) | 每当加载新页面或重新渲染页面上的组件时，都可以调用此函数。<br> 此函数应针对单页应用程序(SPA)进行实施，以便使用Visual Experience Composer(CMS)创建A/B测试和体验定位(XT)活动。 |
| [adobe.target.trackEvent(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md) | 此函数会触发用户操作（例如点击和转化）报告请求。它不会在响应中交付活动。 |
| [mboxCreate(mbox，params)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxcreate-atjs.md)<br>(at. js1.x) | 可使用 mboxDefault 类名称执行请求并将选件应用到最近的 DIV。<br>**注意：** 此函数可用于. js版本1。*x*。此函数已在. js2.x发布时弃用。如果与at. js2.x一起使用，此函数将返回默认内容。 |
| [mboxDefine(options)和mboxUpdate(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxdefine-mboxupdate-atjs-1x.md)<br>(at. js1.x) | 定义和更新 mbox。<br>**注意：** 此函数可用于. js版本1。*x*。此函数已在. js2.x发布时弃用。如果与at. js2.x一起使用，此函数将返回默认内容。 |
| [targetGlobalSettings(选项)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | 您可以使用 `targetGlobalSettings()`，而不是在Target Standard/Premium UI中配置设置，或使用REST API来覆盖位于. js库中的设置。<ul><li>数据提供者：此设置允许客户收集第三方数据提供商(如Demandbase、BlueKai和自定义服务)中的数据，并将数据作为mbox参数传递给全局mbox请求中的mbox参数。</li></ul> |
| [targetpageParams(选项)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md) | 此方法允许您从请求代码外部将参数附加到全局 mbox。 |
| [targetpageParams全部(选项)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparamsall.md) | 此方法允许您从请求代码外部将参数附加到所有 mbox。 |
| [registerExtension(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/registerextension-atjs-1x.md)<br>(at. js1.x) | 可提供用于注册特定扩展的标准方法。<br>**注意：** 此函数可用于. js版本1。*x*。此函数已在. js2.x发布时弃用。如果与at. js2.x一起使用，此函数将返回默认内容。 |
| [at.js 自定义事件](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md) | at. js自定义事件可让您了解mbox请求或选件的成功与否。 |
