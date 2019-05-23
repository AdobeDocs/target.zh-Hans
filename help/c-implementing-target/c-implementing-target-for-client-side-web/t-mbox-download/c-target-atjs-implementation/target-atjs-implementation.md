---
description: at.js 库是适用于 Adobe Target 的新实施库，专为典型的 Web 实施和单页应用程序而设计。
keywords: Target Standard;at.js;实施
seo-description: at.js 库是适用于 Adobe Target 的新实施库，专为典型的 Web 实施和单页应用程序而设计。
seo-title: 从 mbox.js 迁移到 at.js
solution: Target
title: 从 mbox.js 迁移到 at.js
topic: Standard
uuid: 10da01d7-d308-44e3-9c6e-ff4f713bd312
translation-type: tm+mt
source-git-commit: ffa6585834b271838629d65ceb00d1770b37e80c

---


# 从 mbox.js 迁移到 at.js{#migrate-from-mbox-js-to-at-js}

at.js 库是适用于 [!DNL Adobe Target] 的新实施库，专为典型的 Web 实施和单页应用程序而设计。

使用 [!DNL at.js] 具有许多好处，包括缩短 Web 实施的页面加载时间，以及为单页应用程序提供更好的实施选项，等等。

[!DNL at.js] 取代了 [!DNL Target] 实施的 [!DNL mbox.js]。[!DNL at.js] 库中还包含 [!DNL target.js] 中所包含的组件，因此不再需要调用 [!DNL target.js]。

>[!NOTE]
>
>带有 FP-11577 的 Adobe Experience Manager (AEM) 6.2（或更高版本）支持通过其 Adobe Target 云服务集成来实施 at.js。有关更多信息，请参阅 Adobe Experience Manager 6.2 文档**中的[功能包](https://docs.adobe.com/docs/en/aem/6-2/release-notes/feature-packs.html)和[与 Adobe Target 集成](https://docs.adobe.com/docs/en/aem/6-2/administer/integration/marketing-cloud/target.html)。

要使用 [!DNL at.js]，请在要实施 at.js 的页面上替换 [!DNL mbox.js] 引用。不能在一个页面上同时使用 [!DNL mbox.js] 和 [!DNL at.js]。但是，您可以在网站的各个页面上使用任一库。

[!DNL at.js] 库适用于使用 `mboxCreate()`、`mboxDefine()` 和 `mboxUpdate()` 函数的现有实施，并且还支持专门用于基于单页应用程序的实施的新功能。

您可以在当前使用 [!DNL mbox.js] 的任意位置使用 [!DNL at.js]。

与 [!DNL mbox.js] 库相比，[!DNL at.js] 库提供了以下多项改进：

* 通过跨域 AJAX 实现完全异步通信

   >[!IMPORTANT]
   >
   >虽然 [!DNL at.js] 与 [!DNL Target] 服务器间的通信是异步的，但 [!DNL at.js] 文件本身必须在页面的 `<head>` 部分同步加载。理想情况下，此文件应该包含在最先加载的脚本中。加载后，[!DNL at.js] 会通过 `XMLHttpRequest` 异步执行 mbox 调用，且不会阻止页面渲染。

* 不再阻止调用
* 不使用 `document.write()`
* 不在 [!DNL Target] 响应中立即执行 JavaScript
* 可更好地处理超时和错误

   * 可为每个调用自定义 [超时](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)
   * 发生超时后不重新加载

* 专为单页应用程序/MVC 框架设计了函数

## 培训视频：at.js - 优势和实施最佳实践

此视频是“[办公时间](../../../../cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)”的录像，“办公时间”是 Adobe 客户关怀团队发起的一项计划。

* at.js 库的工作原理
* at.js 与 mbox.js 相比所具有的优势
* at.js 如何管理闪烁
* at.js 中的错误处理
* 调试方法
* 已知问题和未来路线图

>[!VIDEO](https://video.tv.adobe.com/v/22223/)
