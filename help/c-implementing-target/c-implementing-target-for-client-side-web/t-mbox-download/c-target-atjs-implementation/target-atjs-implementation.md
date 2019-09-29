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
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 从 mbox.js 迁移到 at.js{#migrate-from-mbox-js-to-at-js}

at.js 库是适用于 [!DNL Adobe Target] 的新实施库，专为典型的 Web 实施和单页应用程序而设计。

使用 [!DNL at.js] 具有许多好处，包括缩短 Web 实施的页面加载时间，以及为单页应用程序提供更好的实施选项，等等。

[!DNL at.js] 取代了 [!DNL Target] 实施的 [!DNL mbox.js]。[!DNL at.js] 库中还包含 [!DNL target.js] 中所包含的组件，因此不再需要调用 [!DNL target.js]。

>[!NOTE]
>
>带有 FP-11577 的 Adobe Experience Manager (AEM) 6.2（或更高版本）支持通过其 Adobe Target 云服务集成来实施 at.js。有关更多信息，请参阅 Adobe Experience Manager 6.2 文档&#x200B;**&#x200B;中的[功能包](https://docs.adobe.com/docs/en/aem/6-2/release-notes/feature-packs.html)和[与 Adobe Target 集成](https://docs.adobe.com/docs/en/aem/6-2/administer/integration/marketing-cloud/target.html)。

## at.js 的好处 {#benefits}

下表说明了这两个库之间的差异：

| 库引用 | 描述 |
|--- |--- |
| at.js | at.js 取代了用于 [!DNL Target] 实施的 mbox.js。<br>使用 at.js 具有许多好处，包括缩短 Web 实施的页面加载时间，增强安全性，在 Google Chrome 中阻止 document.write 警告，以及为单页应用程序提供更好的实施选项，等等。<br>有关更多信息，请参阅 [at.js 实施](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md)。 |
| mbox.js | 在 [!DNL Target] 16.3.1（2016 年 3 月版）之前，[!DNL Target] 需要调用 mbox.js 来创建 [!DNL Target] 交付活动、跟踪点击和跟踪大多数成功量度所需的全局 mbox。此文件包含所有活动所需的库。您不需要为该文件维护特定于活动的不同版本。<br>如果您的页面上已经有来自旧版 [!DNL Target] 实施的封装 mbox，则在新界面中仍然能够使用这些 mbox。更新的 mbox.js 文件仍然是必需的，但可以使用可视化体验编辑器为活动选择和编辑这些 mbox。<br>[!DNL Target] Standard 和 Premium 通过引用 target.js 文件来更新和增补 mbox.js。target.js 文件由 Adobe 托管。通过 target.js 文件，您可以使用可视化体验编辑器编辑任何页面上的内容，即使页面不包含预定义的 mbox 也可编辑。您必须在网站的每个页面上都引用此文件。<br>有关更多信息，请参阅 [mbox.js 实施](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)。<br>**重要信息**：虽然现在仍支持 mbox.js 库，但是以后不会再提供此库的功能更新。因此，所有客户都应迁移到 at.js。有关更多信息，请参阅[从 mbox.js 迁移到 at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md)<br> |

## 实施 at.js

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

>[!VIDEO](https://video.tv.adobe.com/v/22223/?captions=chi_hans)
