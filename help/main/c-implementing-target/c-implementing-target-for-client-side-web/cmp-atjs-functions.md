---
keywords: at.js;函数;javascript 库
description: 查看可与1.x和2.x版本的at.js JavaScript库一起使用的函数列表(在Adobe Target中)。
title: 我可以将哪些函数与at.js一起使用？
feature: at.js
role: Developer
exl-id: a386e478-16f4-4bf6-9771-6b1e75f2e362
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 78%

---

# at.js 函数

可以与 Adobe Target at.js JavaScript 库一起使用的函数列表。单击“函数”列中的链接以获取更多信息和示例。

| 函数 | 详细信息 |
| --- | --- | 
| [adobe.target.getOffer(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffer/) | 此函数会触发用于获取 Target 选件的请求。使用 `adobe.target.applyOffer()` 来处理响应或使用您自己的成功处理。 |
| [adobe.target.getOffers(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffers-atjs-2/)<br>(at.js 2.x) | 此函数允许您通过传递多个 mbox 来检索多个选件。此外，还可以针对活跃活动中的所有视图检索多个选件。<br>**注意：**&#x200B;此函数已在 at.js 2.x 中引入。但此函数不适用于 at.js 版本 1.*x*。 |
| [adobe.target.applyOffer(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-applyoffer/) | 此函数用于应用响应内容。 |
| [adobe.target.applyOffers(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-applyoffers-atjs-2/)<br>(at.js 2.x) | 此函数允许您应用 adobe.target.getOffers() 检索到的多个选件。<br>**注意：**&#x200B;此函数已在 at.js 2.x 中引入。但此函数不适用于 at.js 版本 1.*x* 目前不支持选择加入支持。 |
| [adobe.target.triggerView (viewName, options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-triggerview-atjs-2/)<br>(at.js 2.x) | 每当加载新页面或重新渲染页面上的组件时，都可以调用此函数。<br>应该为单页应用程序 (SPA) 实施此函数，以便使用可视化体验编辑器 (VEC) 创建 A/B 测试和体验定位 (XT) 活动。 |
| [adobe.target.trackEvent(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-trackevent/) | 此函数会触发用户操作（例如点击和转化）报告请求。它不会在响应中交付活动。 |
| [mboxCreate(mbox,params)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/mboxcreate-atjs/)<br>(at.js 1.x) | 可使用 mboxDefault 类名称执行请求并将选件应用到最近的 DIV。<br>**注意：**&#x200B;此函数仅可用于 at.js 版本 1.*x*。此函数已在 at.js 2.x 版本中弃用。如果与 at.js 2.x 一起使用，此函数将返回默认内容。 |
| [mboxDefine(options) 和 mboxUpdate(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/mboxdefine-mboxupdate-atjs-1x/)<br>(at.js 1.x) | 定义和更新 mbox。<br>**注意：**&#x200B;此函数仅可用于 at.js 版本 1.*x*。此函数已在 at.js 2.x 版本中弃用。如果与 at.js 2.x 一起使用，此函数将返回默认内容。 |
| [targetGlobalSettings(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/) | 您可以使用 `targetGlobalSettings()` 覆盖 at.js 库中的设置，而不是在 Target Standard/Premium UI 中或通过使用 REST API 来配置设置。<ul><li>数据提供程序：通过此设置，客户可以从第三方数据提供程序收集数据，例如 Demandbase、BlueKai 和自定义服务，并将这些数据作为全局 mbox 请求中的 mbox 参数传递给 Target。</li></ul> |
| [targetPageParams(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetpageparams/) | 此方法允许您从请求代码外部将参数附加到全局 mbox。 |
| [targetPageParamsAll(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetpageparamsall/) | 此方法允许您从请求代码外部将参数附加到所有 mbox。 |
| [registerExtension(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/registerextension-atjs-1x/)<br>(at.js 1.x) | 可提供用于注册特定扩展的标准方法。<br>**注意：**&#x200B;此函数仅可用于 at.js 版本 1.*x*。此函数已在 at.js 2.x 版本中弃用。如果与 at.js 2.x 一起使用，此函数将返回默认内容。 |
| [at.js 自定义事件](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/atjs-custom-events/) | 通过 at.js 自定义事件，您可以知道 mbox 请求或选件何时成功或失败。 |
| [adobe.target.sendNotifications(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-sendnotifications-atjs-21/)<br>(at.js 2.1.0) | 在不使用 `adobe.target.applyOffer()` 或 `adobe.target.applyOffers()` 呈现体验时，此函数会向 Target 边缘发送通知。<br>**注意**：此函数已在 at.js 2.1.0 中引入，可用于 2.1.0 以上的任何版本。 |
