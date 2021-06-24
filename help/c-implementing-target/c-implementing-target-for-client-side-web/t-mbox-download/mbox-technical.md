---
keywords: 实施;mbox.js;DOM 操作库;target.js;可视化体验编辑器;iFrame;Angular 网站;单页应用程序;单页应用程序;SPA
description: 了解旧版mbox.js的Adobe Target实施。 迁移到Adobe Experience Platform Web SDK(AEP Web SDK)或at.js的最新版本。
title: ' [!DNL Target] mbox.js库有何用途？'
feature: at.js
role: Developer
exl-id: 62f0cbd2-17f0-43f4-98d3-ea39f314525e
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 78%

---

# mbox.js 的功能

此信息可帮助您的技术人员了解 mbox.js 实施以及它可能会对您的网站有何影响。

>[!IMPORTANT]
>
>**mbox.js 生命周期结束**：从 2021 年 3 月 31 日起，[!DNL Adobe Target] 将不再支持 mbox.js 库。2021 年 3 月 31 日之后，所有从 mbox.js 进行的调用都将失败，并影响您通过提供默认内容而运行 [!DNL Target] 活动的页面。
>
>我们建议所有客户在此日期之前迁移到新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript库的最新版本，以避免您的网站出现任何潜在问题。 有关详细信息，请参阅[概述：为客户端 Web 实现 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

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
