---
keywords: implementation;mbox.js;dom manipulation library;target.js;visual experience composer;iframe;angular sites;single page applications;single page app;SPA
description: 此信息可帮助您的技术人员了解 mbox.js 实施以及它可能会对您的网站有何影响。
title: mbox.js 的功能
feature: null
subtopic: Getting Started
topic: Standard
uuid: 5529d620-4a33-479c-871f-18dcd59abb07
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 100%

---


# mbox.js 的功能{#what-mbox-js-does}

此信息可帮助您的技术人员了解 mbox.js 实施以及它可能会对您的网站有何影响。

Target Standard 要求使用 [!DNL mbox.js] 版本 58 或更高版本。有关如何下载和更新 [!DNL mbox.js] 的说明，请参阅 [Mbox 实施](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md#task_4EAE26BB84FD4E1D858F411AEDF4B420)。

对于 Target Standard，[!DNL mbox.js] 会调用另一个 JavaScript 文件 [!DNL target.js]。[!DNL Target.js] 由 Adobe 托管，并由 Adobe 自动更新。您不需要执行任何操作即可更新 [!DNL target.js]，而且也不存在任何特定于客户端的自定义设置。

[!DNL Target.js] 会在您页面的 `<head>` 部分中创建一个名为 `target-global-mbox` 的 mbox。

[!DNL Target.js] 由在 [!DNL mbox.js] 的“[!UICONTROL 额外的 JavaScript]”字段中添加的一行 JavaScript 代码，来从 [!DNL mbox.js] 中进行调用。禁用 [!DNL target.js] 的唯一方法是不包含这一行代码，这样做也会禁用 [!DNL Target]。

[!DNL Target.js] 在 [!DNL Target] 中具有以下两项功能：

* DOM 操作
* 启用[!UICONTROL 可视化体验编辑器]的可视化元素

## DOM 操作 {#section_169F8D4C077948DCB4F891ABBB03FF63}

[!DNL Target.js] 可控制由 Standard 使用的 DOM 操作库。为了显示网站内容，[!DNL target.js] 会引用 [!DNL sizzle.js]（版本 1.10.8 及更低版本）。[!DNL Sizzle.js] 会启用 HTML 元素选择器。除 [!DNL sizzle.js] 之外，只会使用原生 JavaScript。不需要使用 jquery。

此外，还会使用以下代码片段轮询 DOM：
`https://github.com/dperini/ContentLoaded`

## target.js 和可视化体验编辑器 {#section_2B3FF6AC5B8D431C83D9EDCF53CB1472}

使用[!UICONTROL 可视化体验编辑器]设置活动体验时，您的网页会在 iFrame 中打开。加载 iFrame 后，Standard 会发送 HTML5 `postMessage` API 调用。[!DNL Target.js] 会检测任何 `postMessage` 调用并将以下 JavaScript 库包含到网站中：

* 对于缩览图生成：[!DNL https://html2canvas.hertzen.com/]
* 对于跨域查询：[!DNL Admin.js]、[!DNL CDQ.base.js]、[!DNL CDQ.host.js] 和 [!DNL admin.css] 用于在各 iFrame 间发送消息。这些脚本允许 Adobe 在页面之间发送数据。

## 有关 Angular 网站和单页应用程序的注意事项 {#section_16D76F16077A434FAE8CEC6FD43BE6D7}

如果您是在 Angular 网站或任何单页应用程序 (SPA) 中实施 Target，您应该使用 at.js 库，而不应使用 mbox.js。

有关更多信息，请参阅 [at.js 实施](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17)。
