---
keywords: system diagram;flicker;at.js;implementation;javascript library;js;atjs
description: Adobe Target 系统图显示了使用 at.js 为自动创建的全局 mbox 发送或收集调用和信息的流程。
title: Adobe Targetat.js JavaScript库的工作方式
topic: Standard
uuid: 8ed04881-3dd9-496f-9c9c-feb9c740ed80
translation-type: tm+mt
source-git-commit: 6c94110c42ef5a7a9b44d58346f0f3b18a4b6cdc
workflow-type: tm+mt
source-wordcount: '1106'
ht-degree: 88%

---


# at.js 的工作原理{#how-at-js-works}

To implement [!DNL Adobe Target] client-side, you must use the at.js JavaScript library.

在 [!DNL Adobe Target] 的客户端实施中，[!DNL Target] 会将与活动相关联的体验直接交付给客户端浏览器。浏览器将决定要显示的体验，然后显示该体验。借助客户端实施，您可以使用 WYSIWYG 编辑器、[可视化体验编辑器](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC)，或者非可视化界面（[基于表单的体验编辑器](/help/c-experiences/form-experience-composer.md)）来创建测试和个性化体验。

## 什么是 at.js？

[at.js 库](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17)是适用于 Target 的新实施库。使用 at.js 可缩短 Web 实施的页面加载时间，并为单页应用程序提供更好的实施选项。at.js 是推荐使用的实施库，会经常更新功能。我们建议所有客户都实施或迁移到[最新版本的 at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)。

有关更多信息，请参阅 [Target JavaScript 库](/help/c-intro/how-target-works.md#libraries)。

In the [!DNL Target] implementation illustrated below, the following [!DNL Adobe Experience Cloud] solutions are implemented: Analytics, Target, and Audience Manager. 此外，还实施了以下 Experience Cloud 核心服务：Adobe Launch、受众和访客 ID 服务。

## at.js 1之间有何差异。*x* 和 at.js 2.x 工作流程图之间有何差异？

请参阅[从 at.js 1.x 升级到 at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md)，以了解有关 2.O 与 1.*x* 之间的差异。

从高层次来看，两个版本之间存在一些差异：

* at.js 2.x 没有全局 mbox 请求概念，但有页面加载请求概念。页面加载请求可以视为检索应该被应用于网站初始页面加载的内容的请求。
* at.js 2.x管理称为视图的概念，这些概念用于单页应用程序(SPA)。 at.js 1.*x* 并没有此概念。

## at.js 2.x 图

下图可帮助您了解含有视图的 at.js 2.x 工作流程以及其如何增强 SPA 集成。要更好地了解 at.js 2.x 中使用的概念，请参阅[单页应用程序实施](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md)。

![使用 at.js 2.x 的 Target 流程](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/system-diagram-atjs-20.png)

| 步骤 | 详细信息 |
| --- | --- |
| 1 | 如果用户通过了身份验证，则调用会返回 [!DNL Experience Cloud ID]；另一调用会同步客户 ID。 |
| 2 | at.js 库会同步加载，并隐藏文档正文。<br>也可以选择预先隐藏页面上实施的代码段，以异步方式加载 at.js。 |
| 3 | 将会发出页面加载请求，其中包括已配置的所有参数（例如，MCID、SDID 和客户 ID）。 |
| 4 | 配置文件脚本在执行后进入配置文件存储区。存储区向受众库请求符合条件的受众（例如从 Adobe Analytics、Audience Management 等共享的受众）。<br>客户属性会以批量过程发送到配置文件存储区。 |
| 5 | 根据 URL 请求参数和配置文件数据，[!DNL Target] 可决定将哪些活动和体验返回给查看当前页面和未来视图的访客。 |
| 6 | 目标内容会发送回页面，其中可能包含其他个性化的配置文件值。<br>当前页面上的目标内容会在默认内容不发生闪烁的情况下尽快显示。<br>SPA中因用户操作而显示的视图的目标内容会在浏览器中进行缓存，因此当视图通过触发时，无需额外的服务器调用即可立即应用该内容 `triggerView()`。 |
| 7 | Analytics 数据会发送到数据收集服务器。 |
| 8 | 目标数据会通过 SDID 匹配到 Analytics 数据，并且会进行相应处理以保存到 Analytics 报表存储中。之后，便可以在 Analytics 和 Target 中通过 Analytics for Target (A4T) 报表查看 <br>Analytics 数据。 |

现在，无论在 SPA 上的什么位置实施 `triggerView()`，都会从缓存中检索查看次数和操作，并在没有服务器调用的情况下显示给用户。`triggerView()` 还会向 [!DNL Target] 后端发出通知请求，以增加和记录展示次数计数。有关带有视图的 SPA 的 at.js 的更多信息，请参阅[单页应用程序实施](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md)。

![Target 流程 at.js 2.x triggerView](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-triggerview.png)

| 步骤 | 详细信息 |
| --- | --- |
| 1 | 在 SPA 中调用 `triggerView()` 以渲染视图并应用操作来修改可视化元素。 |
| 2 | 从缓存中读取视图的目标内容。 |
| 3 | 目标内容会在默认内容不发生闪烁的情况下尽快显示。 |
| 4 | 通知请求将发送到 [!DNL Target] 配置文件存储区，以计算活动中的访客和递增量度。 |
| 5 | Analytics 数据会发送到数据收集服务器。 |
| 6 | Target 数据会通过 SDID 匹配到 Analytics 数据，并且会进行相应处理以保存到 Analytics 报表存储中。之后，便可以在 Analytics 和 Target 中通过 A4T 报表查看 Analytics 数据。 |

### 视频- at.js 2.x架构图

at.js 2.x 增强了 Adobe Target 对 SPA 的支持，并与其他 Experience Cloud 解决方案集成。该视频介绍了如何将所有内容结合到一起。

>[!VIDEO](https://video.tv.adobe.com/v/26250)

有 [关更多信息，请参阅了解at.js 2](https://helpx.adobe.com/target/kt/using/atjs20-diagram-technical-video-understand.html) .x的工作方式。

## at.js 1.x 流程图

![Target 流程 - at.js 1.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/target-flow.png)

| 步骤 | 描述 | 调用 | 描述 |
|--- |--- |--- |--- |
| 1 | 如果用户通过了身份验证，则调用会返回 [!DNL Experience Cloud ID] (MCID)；另一调用会同步客户 ID。 | 2 | at.js 库会同步加载，并隐藏文档正文。 |
| 3 | 将会发出全局 mbox 请求，其中包括已配置的所有参数，例如 MCID、SDID 和访客 ID（可选）。 | 4 | 配置文件脚本在执行后进入配置文件存储区。存储区向[!UICONTROL 受众库]请求符合条件的受众（例如从 [!DNL Adobe Analytics]、[!DNL Audience Manager] 等共享的受众）。<br>客户属性会以批量过程发送到[!DNL Profile Store]。 |
| 5 | [!DNL Target] 根据 URL、mbox 参数和配置文件数据确定要返回给访客的活动和体验。 | 6 | 目标内容会发送回页面，其中可能包含其他个性化的配置文件值。<br>体验会在默认内容不发生闪烁的情况下尽快显示。 |
| 7 | [!DNL Analytics] 数据会发送到数据收集服务器。 | 8 | [!DNL Target] 数据会通过 SDID 匹配到 [!DNL Analytics] 数据，并且会进行相应处理以保存到 [!DNL Analytics] 报表存储中。<br>[!DNL Analytics]之后，便可以在 [!DNL Analytics] 和 [!DNL Target] 中通过 [!DNL Analytics for Target] (A4T) 报表查看  数据。 |

### 视频——办公时间： at.js tips and overview（2019年6月26日）

此视频是“办公时间”的录像，“办公时间”是 Adobe 客户关怀团队发起的一项计划。

* 使用at.js的优势
* at.js设置
* 闪烁处理
* 调试 at.js
* 已知问题
* 常见问题解答

>[!VIDEO](https://video.tv.adobe.com/v/27959)

## at.js 如何渲染带有 HTML 内容的选件 {#render}

在渲染带有 HTML 内容的选件时，at.js 会应用以下算法：

1. 预先加载图像（如果 HTML 内容中包含任何 `<img>` 标记）。

1. 将 HTML 内容附加到 DOM 节点。

1. 执行内联脚本（代码包含在 `<script>` 标记中）。

1. 以异步方式加载并执行远程脚本（`<script>` 标记具有 `src` 属性）。

重要说明：

* at.js 对远程脚本的执行顺序不提供任何保证，因为它们是异步加载的。
* 内联脚本不应对远程脚本有任何依赖关系，因为远程脚本稍后才会加载和执行。