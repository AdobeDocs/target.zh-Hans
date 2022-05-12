---
keywords: at.js版本；at.js版本；发行说明
description: 查看有关每个版本的Adobe更改的详细信息 [!DNL Target] at.js JavaScript库。
title: at.js的每个版本中都包含哪些内容？
feature: at.js
role: Developer
exl-id: ec1f1459-d539-4eac-a8f1-33a2d4910dec
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '4390'
ht-degree: 88%

---

# at.js 版本详细信息

有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。

>[!IMPORTANT]
>
>Target团队同时支持at.js 1.*x* 与 at.js 2.*x* 之间的映射。请升级到at.js任一主要版本的最新更新，以确保您运行的是受支持的版本。
>
>中的标记 [Adobe Experience Platform](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) 是升级at.js的首选方法。 扩展开发人员会不断向其扩展中添加新功能，并且会经常修复错误。 这些更新将打包到扩展的新版本中，并在 [!DNL Adobe Experience Platform] 目录作为升级。 有关更多信息，请参阅 [扩展升级](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/extensions/extension-upgrade.html) 在 *标记概述* 的双曲余切值。

## at.js 版本 2.8.1（2022 年 1 月 28 日）

* 修复了在[!UICONTROL 设备上决策] (ODD) 混合执行模式中 `pageLoad` 无法映射到 target-global-mbox 的问题
* 修复了有关 mbox 请求的分析详细信息的问题。
* 升级了开发依赖关系以修复安全漏洞。

## at.js 版本 2.8.0（2022 年 1 月 7 日）

[!DNL Target] at.js JavaScript 库现在收集功能使用情况和性能遥测数据。不收集个人数据。可以在 `targetGlobalSettings` 中将 `telemetryEnabled` 设置为 false 来选择退出此功能。有关更多信息，请参阅 [targetGlobalSettings 中的 telemetryEnabled](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#telemetry)。

## at.js 版本 2.7.0（2021 年 10 月 28 日）

此版本包含以下增强功能：

* 添加了对 [Web 组件](https://developer.mozilla.org/en-US/docs/Web/Web_Components)的支持。在自定义元素以及自定义元素内部的元素上创建和测试个性化的体验及方案时，需要此版本的 at.js。此功能包括在 [!DNL Target Standard/Premium] 21.10.5 版本中。

## at.js 1.8.3（2021年9月21日） {#183}

此版本包含以下更改：

* 删除了 `reactor-window` 和 `reactor-document` [!DNL Adobe Experience Platform Launch] 模块，以确保 [!DNL Platform Launch] 为具有 `window.default` 或 `document-default` 设置。
* at.js 1.8.3现在已明确设置 `Samesite=None` 和 `Secure` 以确保正确设置第三方域cookie。

## at.js 2.6.1（2021 年 8 月 16 日）

* 修复了使用设备上决策时“混合模式没有缓存的构件可用”错误。

## at.js 2.6.0（2021 年 7 月 16 日）

* 每当 at.js 设置 `secureOnly` 设为 `true` 时，都向 Cookie 添加了安全属性。
* 现在可以在使用 `triggerView()` 时使用响应令牌。
* 修复了与 `CONTENT_RENDERING_NO_OFFERS` 事件相关的问题。现在，每当 [!DNL Target] 没有返回内容时，就会正确触发此事件。
* 使用 `prefetch` 请求时，正确返回了 [!DNL Anlytics for Target] (A4T) 单击指标详细信息。
* UUID 生成功能不再使用 `Math.random()`，而是依赖于 `window.crypto`。
* 在每次网络调用时都会正确延长 `sessionId` Cookie 到期日。
* [!UICONTROL 单页面应用程序] (SPA) 视图缓存初始化现在可以被正确处理并遵循 `viewsEnable` 设置。

## at.js 2.5.0（2021年5月13日）

此版本的 at.js 包括以下增强功能和更改：

* 对 at.js 的[设备上决策](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md)支持。
* 对 Automated Personalization 活动的[预览链接](/help/main/c-activities/c-activity-qa/activity-qa.md)支持。

此版本还移除了对 Microsoft Internet Explorer 10 及更高版本的支持。

## at.js 2.4.1（2021 年 3 月 23 日）

此版本的 at.js 是一个维护版本，它包括以下增强功能和修复：

* 修复了 mbox 请求中包含的 `targetPageParams` 存在的问题。`targetPageParams` 只能包含在 `pageLoad` 请求中。(TNT-40247)
* 优化了窗口和文档中的全局引用 [!DNL Adobe Experience Platform] 扩展。 (TNT-37124)

## at.js 2.4.0（2021 年 1 月 14 日）

at.js 的此版本是一个维护版本，其中包括以下修复：

* 新增支持将个人资料/平台 ID 统一成投放 API customerID。
* 修复了无效的样式标签注入。

## at.js 2.3.3（2020年11月13日）

at.js 的此版本是一个维护版本，其中包括以下修复：

* 修复了与mbox点击跟踪和A4T相关的问题。 通过单击0n，Target使用正确的mbox和mbox参数触发了交付API调用。 但是，SDID与 [!DNL Analytics] 调用，因此没有点击拼合和转化。 (TNT-38372)

## at.js 2.3.2（2020 年 7 月 24 日）

at.js 的此版本是一个维护版本，其中包括以下修复：

* 修复了脚本或代码将默认属性添加到窗口或文档时产生的错误。

## at.js 1.8.2（2020年6月15日）

at.js 的此版本是一个维护版本，其中包括以下修复：

* 修复了在使用 CNAME 和边缘覆盖 at.js 1 时出现的问题。*x* 可能无法正确地创建服务器域，从而导致了 [!DNL Target] 请求失败。(TNT-35064)

## at.js 2.3.1版本（2020年6月15日）

此版本的 at.js 是一个维护版本，它包括以下增强功能和修复：

* 使得可通过 [targetGlobalSettings](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) 覆盖 `deviceIdLifetime` 设置。(TNT-36349)
* 修复了在使用 CNAME 和边缘覆盖 at.js 2 时出现的问题。*x* 可能无法正确地创建服务器域，从而导致了 [!DNL Target] 请求失败。(TNT-35065)
* 修复了一个问题，在使用 [!DNL Target]  扩展程序 v2 和 [!DNL Adobe Analytics] [!DNL Launch] 扩展程序时，[!DNL Target] 延迟了 [!DNL Analytics] `sendBeacon` 调用。（TNT-36407、TNT-35990、TNT-36000）

## at.js 版本 2.3.0（2020 年 3 月 25 日）

此版本的 at.js 是一个维护版本，它包括以下增强功能和修复：

* 在应用已交付的Target选件时，支持在附加到页面DOM的SCRIPT和STYLE标记中设置内容安全策略不参数。 客户可以设置 `targetGlobalSettings.cspScriptNonce` 和 `targetGlobalSettings.cspStyleNonce` 以便at.js能够在已应用的选件上设置相应的脚本和样式标记nonce。 请参阅  [targetGlobalSettings](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) 以了解更多详细信息。
* 修复了使用Google Closure编译器编译Google Tag Manager部署的at.js时的问题。
* 将at.js检查Cookie从 `check` to `at_check` 以避免与客户实施发生冲突。

## at.js 版本 1.8.1（2020 年 3 月 25 日）

此版本的 at.js 是一个维护版本，它包括以下增强功能和修复：

* 将at.js检查Cookie从 `check` to `at_check` 以避免与客户实施发生冲突。

## at.js 版本 2.2.0（2019 年 10 月 10 日）

此版本的at.js包含以下增强功能和修复：

* 修复了当页面元素中不存在Adobe Analytics代码时，点击跟踪不会在Analytics for Target(A4T)中报告转化的问题。
* 改进了在网页上同时使用Experience CloudID服务(ECID)v4.4和at.js 2.2时的性能。
* 以前，只有在 ECID 作出两次阻塞调用之后，at.js 才能获取体验。此过程已减少为单次调用，从而显著提高性能。
* 修复了预取的视图处理不正确的问题，该问题导致默认选件中的事件令牌未包含在已发送的通知中。

   >[!NOTE]
   >
   >将您的ECID扩展升级到v4.4以利用此性能增强功能。

* at.js版本2.2还提供了一个名为 `serverState`. 当实施Target的混合集成时，可使用此设置来优化页面性能。 混合集成指的是在客户端使用 at.js 2.2 和更高版本，在服务器端使用交付 API 或 Target SDK，二者相结合以交付体验。`serverState` 让 at.js 2.2 和更高版本可直接从在服务器端获取并作为所提供的页面的一部分返回客户端的内容应用体验。有关更多信息，请在 [targetGlobalSettings](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#server-state) 中参阅“serverState”。

## at.js 版本 1.8.0（2019 年 10 月 10 日）

此版本的at.js包含以下增强功能和修复：

* 改进了在网页上同时使用Experience CloudID服务(ECID)v4.4和at.js 1.8时的性能。
* 以前，只有在 ECID 作出两次阻塞调用之后，at.js 才能获取体验。此过程已减少为单次调用，从而显著提高性能。

>[!NOTE]
>
>将您的ECID扩展升级到v4.4以利用此性能增强功能。

## at.js 版本 2.1.1（2019 年 7 月 24 日）

此版本的 at.js 是一个维护版本，它包括以下增强功能和修复：

（括号中的问题编号供 Adobe 内部使用。）

* 修复了在可视化体验编辑器 (VEC) 中的“目标和设置”页面上使用“点击跟踪”量度时导致多个信标触发的问题。(TNT-32812)
* 修复了导致 `triggerView()` 无法多次渲染选件的问题。(TNT-32780)
* 修复了 `triggerView()` 存在的一个问题，以确保请求包含 Marketing Cloud ID (MCID) 信息。(TNT-32776)
* 修复了即使没有保存的视图，也无法触发 `triggerView()` 通知的问题。(TNT-32614)
* 修复了由于使用 decodeURIcomponent 而导致错误的问题，当 URL 包含格式不正确的查询字符串参数时，decodeURIcomponent 会引发问题。(TNT-32710)
* 在通过 `Navigator.sendBeacon()` API 发送交付请求的上下文中，信标标志现在被设置为“true”。(TNT-32683)
* 修复了导致无法在网站上向少数客户显示“推荐”选件的问题。客户可以在交付 API 调用中看到选件内容，但该选件未在网站上应用。(TNT-32680)
* 修复了导致多个体验中的点击跟踪无法按预期工作的问题。(TNT-32644)
* 修复了导致 at.js 在第一个量度渲染失败后无法应用第二个量度的问题。(TNT-32628)
* 修复了使用 `mboxThirdPartyId` 函数传递 `targetPageParams` 时出现的问题，该问题导致请求有效负载不存在于查询参数或请求有效负载中。(TNT-32613)
* 修复了导致在基于 Chromium 的浏览器（包括 Google Chrome）中阻止显示和点击通知响应的问题。(TNT-32290)

## at.js 版本 2.1.0（2019 年 6 月 3 日）

此版本包括以下功能和增强功能：

* **Adobe 选择加入支持**：通过 Adobe 选择加入，可轻松将 Adobe 解决方案与同意管理平台集成。有关 Adobe 选择加入的更多信息，请参阅[隐私和《通用数据保护条例》(GDPR)](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md)。

* **符合行业标准 CSP**：at.js 不再使用 eval() 执行 JavaScript。

* **客户端分析日志记录**：无论是在客户端还是服务器端，均允许客户完全控制如何将分析数据发送到 Adobe Analytics

   有关更多信息，请参阅“实施之前”**&#x200B;中的[客户端分析日志记录](/help/main/c-integrating-target-with-mac/a4t/before-implement.md#client-side)。

* **发送通知**：允许开发人员在通过代码而不是使用 `applyOffer()` 或 `applyOffers()` 呈现体验时发送通知。

   有关更多信息，请参阅 [adobe.target.sendNotifications(options)](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md)。

* **at.js 大小减少了约 24%**：at.js 的大小减少了约 24%。较小的文件大小可提高页面加载性能并缩短在页面上下载 at.js 的时间。

## at.js 版本 2.0.1（2019 年 3 月 19 日）

此版本为维护版本，它包括以下增强功能和修复：

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

* 修复了 DOM 轮询代码中导致某些客户出现 JavaScript 异常的争用条件。(TNT-31869)
* 有关视图已渲染的通知已与点击跟踪事件处理程序分离。起初，如果无法附加属于已渲染视图的点击事件处理程序，则 Target 不会发送通知。现在，即使找不到点击元素，Target 也会发送视图通知。(TNT-31969)
* 修复了导致请求成功事件重定向标记始终设置为 true 的问题。(TNT-31907)
* 修复了导致即使元素缺失，VEC 重新排列操作也被记录为成功的问题。(TNT-31924)
* 修复了导致某些客户的通知不包含“企业权限”属性令牌的问题。(TNT-31999)

## at.js 版本 1.7.1（2019 年 3 月 19 日）

这个版本属于维护版本，它包括以下修复：

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

* 修复了 DOM 轮询代码中导致某些客户出现 JavaScript 异常的争用条件。(TNT-31869)

## at.js 版本 2.0.0 {#at-js-200}

at.js 2.x 提供了丰富的功能集，使您的企业能够在下一代客户端技术上实现个性化。这个新版本着重升级了 at.js 以与单页应用程序 (SPA) 进行良性的交互。

以下是使用 at.js 2.x 的一些好处，这些好处在以前的版本中未提供：

* 能够在页面加载时缓存所有选件，将多次服务器调用减少至一次服务器调用。
* 由于选件是通过缓存立即显示的，不存在传统服务器调用引入的任何时间延迟，因此极大地提升了最终用户在您网站上的体验。
* 通过简单的单行代码和一次性开发人员设置，您的营销人员能够通过可视化体验编辑器 (VEC) 在单页应用程序上创建和运行 A/B 和体验 (XT) 活动。

at.js 2.x 引入了以下新函数：

* getOffers()
* applyOffers()
* triggerView()

以下函数在引入 at.js 2.x 后被弃用：

* mboxCreate()
* mboxDefine
* registerExtension()

有关更多信息，请参阅[从 at.js 1.x 升级到 at.js 2.x](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md) 和 [at.js 函数](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md)。

>[!NOTE]
>
>如果您需要使用满足[《通用数据保护条例》](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md)(GDPR) 要求的 Adobe 选择加入支持，则当前必须使用 at.js 1.7.0 或 at.js 2.1.0。

## at.js 版本 1.7.0 {#at-js-170}

at.js 1.7.0 提供了 Adobe 选择加入支持。通过 Adobe 选择加入，可轻松将 Adobe 解决方案与同意管理平台集成。

有关 Adobe 选择加入的更多信息，请参阅[隐私和通用数据保护条例](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) (GDPR)。

此版本还修复了 Target 可能使用来自重定向 URL 的参数覆盖重定向 URL 参数的问题。

>[!NOTE]
>
>如果您需要使用满足 GDPR 要求的 Adobe 选择加入支持，则当前必须使用 at.js 1.7.0 或 2.1.0。<br>有关所有版本的列表，请参阅 [at.js 版本详细信息](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)。

## at.js 版本 1.6.4 {#at-js-164}

at.js 1.6.4 是一个维护版本，该版本解决了以下问题：

* 修复了 Microsoft Internet Explorer 11 中出现的导致应用重复选件的争用条件问题。

## at.js 版本 1.6.3 {#section_484A56774E004282B98FFFF851E4E670}

at.js 版本 1.6.3 包含以下修复和增强功能：

* 如果选择器包含 ID 或以数字、双连字符或后跟数字的连字符（例如 ＃-123）开头的 CSS 类，则它们现在会对 CSS 进行转义。(TNT-31061)
* 修复了 at.js 1.6.2 出现的问题：不同活动中应用于同一 CSS 选择器的可视化体验编辑器 (VEC) 选件不遵循活动优先级。(TNT-31052)
* 修复了在对 promise 没有本地支持的环境中 promise 超时的问题。(TNT-30974)
* 现在可以通过内容渲染失败事件正确捕获和报告问题。以前，可能会报告 JavaScript 已成功运行，即使情况并非如此。(TNT-30599)

## at.js 版本 1.6.2 {#section_88BE2F69943D4280B8170F377886B58E}

这是一个维护版本，该版本解决了以下问题：

* 修复了某些客户网站上出现的会导致无限“异步”循环的问题。

>[!IMPORTANT]
>
>此外，at.js 版本 1.6.2 还包含 at.js 版本 1.6.1 和 1.6.0 中包含的所有增强功能和修复。这些版本不再可供下载。如果您使用的是 1.6.1 或 1.6.0，我们建议您升级到 1.6.2 版本

以下是 at.js 版本 1.6.1 中包含的增强功能和修复：

* 修复了 at.js 1.6.0 中导致“推荐”体验在 Microsoft Internet Explorer 11 中重复出现的问题。(TNT-30593)
* at.js 现在确保边缘覆盖逻辑会检查是否存在边缘群集 Cookie，以避免用户在会话期间跳过边缘时使用不同的边缘编号。(TNT-30563)
* 修复了如果 HTML 内容包含无效的 JS 代码，则会阻止 at.js 执行后续操作的问题。at.js 现在会记录错误并渲染其它操作而不出现问题。(TNT-30546)
* 做出一些更改，从而在重定向页面重新符合重定向活动资格时会出现异常。(TNT-30532)
* 修复了阻止从 getOffer() API 请求传播正确请求超时的问题。(TNT-30498)
* 修复了在使用文件协议时会阻止 at.js 1.6.0 保存 Cookie 的问题。(TNT-30454)
* 修复了在使用 Analytics for Target (A4T) 时，通过重定向并不能交付所有体验的问题。(TNT-30444)
* 修复了导致页面在 Target 调用成功后被隐藏的问题。(TNT-30358)

以下是 at.js 版本 1.6.0 中包含的增强功能和修复：

* 现在，Analytics for Target (A4T) 集成中自动支持重定向选件。客户端解决方法已经删除。(TNT-30247)
* 现在客户端边缘路由默认处于启用状态。(TNT-30261)
* 修复了当操作之间存在依赖关系时，会渲染可视化体验编辑器 (VEC) 操作的问题。(TNT-30248)

## at.js 版本 1.5.0 {#section_128C6761884C4DA8AE50D6A605FF6F55}

at.js 版本 1.5.0 现已可用。

* `at-request-succeeded` 事件的详细信息中包含重定向标记。此标记可用于确定是否会将页面重定向到其他 URL。如果您要了解该 URL，请订阅 `at-content-rendering-redirect`。(TNT-29834)
* 修复了将 `window.targetGlobalSettings.enabled` 设置为 false 时，导致其失败并引发运行时异常的问题。(TNT-29829)
* 修复了如果对触发全局 mbox 请求使用自定义代码并使用主体隐藏，则在可视化体验编辑器 (VEC) 中加载页面时导致页面失败的问题。(TNT-29795)
* 添加了对 `screenOrientation`、`devicePixelRatio` 和 `webGLRenderer` 的支持。这些新的 Target 请求参数用于 iPhone X 和其他新型设备检测。有关更多信息，请参阅[移动设备](/help/main/c-target/c-audiences/c-target-rules/mobile.md#concept_2A794199DC1A4D349FFFBC7DCF1FEB89)。(TNT-29781)
* 修复了并非总是发送 Adobe Audience Manager (AAM) 位置提示的问题。(TNT-29695)
* 对于支持 at.js 1.5.0 的浏览器，at.js 1.5.0 会切换到 MutationObserver 以进行选择器轮询。at.js 1.0.0 之前的版本使用 MutationObserver polyfill，而这被证明是有问题的。为避免出现 polyfill 问题，版本 1.5.0 使用以下伪代码来确定使用哪种计划机制：

   ```
   if MutationObserver is supported
     scheduler = MutationObserver
   else if document is visible
     scheduler = requestAnimationFrame
   else
     scheduler = setTimeout
   ```

## at.js 版本 1.3.0 {#section_24EAAE1CFA814EF8B19E61842F4D8321}

at.js 版本 1.3.0 现已可用。

* 以下新事件可用于帮助跟踪、调试和自定义与 at.js 的交互：

   * LIBRARY_LOADED
   * REQUEST_START
   * CONTENT_RENDERING_START
   * CONTENT_RENDERING_NO_OFFERS
   * CONTENT_RENDERING_REDIRECT

   有关更多信息，请参阅 [at.js 自定义事件](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md)。

* 您可以使用来自数据提供程序的其他参数来增强 at.js 请求。应将数据提供程序添加到 `dataProviders key` 下方的 `window.targetGlobalSettings`。

   有关更多信息，请参阅[数据提供程序](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)。

* at.js 请求现在使用 GET，但当 URL 大小超过 2048 个字符时，它会转为使用 POST。新增了一个名为 `urlSizeLimit` 的属性，如有必要，您可以在此属性中提高大小限制。通过这项更改，Target 可以使 at.js 与使用相同技术的 AppMeasurement 保持一致。
* 现在，Target 强制要求在 `adobe.target.applyOffer(options)` 函数中使用 `mbox` 键。以往，这些键值是要求使用的，但现在，Target 强制使用该键值以确保 Target 正确验证并且客户正确地使用该函数。
* at.js 改进了事件和点击跟踪功能。at.js 会使用 `navigator.sendBeacon()` 发送事件跟踪数据，如果 `navigator.sendBeacon()` 不受支持，则将回退到同步 XHR。此回退行为主要影响 Internet Explorer 10 和 11 以及 Safari 的某些版本。Safari 在即将发布的 iOS 11.3 版本中将添加对 `navigator.sendBeacon()` 的支持。
* 现在，即使页面在后台选项卡中打开，at.js 也能渲染选件。有些 Target 客户遇到 `requestAnimationFrame()` 因浏览器对后台选项卡的限制行为而被禁用的问题。
* 此版本执行了许多性能方面的改进，包括缩短了检查 Chrome CPU 配置文件时的调用堆栈。
* at.js 1.3.0 不再支持在 Microsoft Internet Explorer 9 上交付内容。有关支持的浏览器列表，请参阅[支持的浏览器](/help/main/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100)。今后，所有请求都将通过支持 CORS 的 `XMLHttpRequest` 来执行，而不使用 JSONP 请求。这项更改显著提高了安全性。

## at.js 版本 1.2.3 {#section_CE4D14AF00D04F4C8A2F0513F5EA1A84}

[!DNL at.js] 版本 1.2.3 现已可用。

* 添加了对 JSON 选件的支持。JSON 选件仅在使用基于表单的体验编辑器创建的活动中受支持。目前只能通过直接 API 调用来使用 JSON 选件。请参阅[创建 JSON 选件](/help/main/c-experiences/c-manage-content/create-json-offer.md#concept_63C7BEE1F0DB4A7596D997219B7C136D)。

## at.js 版本 1.2.2 {#section_4E96D13F2DFE4F1F81A1089877D53649}

[!DNL at.js] 版本 1.2.2 现已可用。

* 修复了将 Target 库加载到使用 QUIRKS 模式的页面时返回 JavaScript 错误的问题。(TNT-28312)
* 修复了导致 Target 点击跟踪中断 Analytics 数据收集调用的问题。(TNT-28261)
* 修复了 `targetPageParams()` 返回空字符串时，导致 `getOffer() params` 失败的问题。(TNT-28359)
* 修复了使用“仅限 x”生成会话 ID 时出现的问题。(TNT-28361)

## at.js 版本 1.2.1 {#section_F757C8174BBA4F68AC5524ADC3D9C5E3}

[!DNL at.js] 版本 1.2.1 现已可用。

* 修复了对具有 target=&quot;_blank&quot; 的链接的点击跟踪阻止 Target 在新的选项卡中打开该链接的问题。

## at.js 版本 1.2.0 {#section_1C3A18C595C34B25A14A440D213F3B9C}

[!DNL at.js] 版本 1.2 现已作为维护版本提供，其中包含大多数错误修复。

* 修复了阻止对点击跟踪特殊案例执行默认操作的问题。(TNT-28089)
* 修复了对具有 `target="_blank"` 的链接的点击跟踪阻止 Target 在新的选项卡中打开该链接的问题。(TNT-28072)
* IP 地址可用作 Cookie 域。(TNT-28002)
* 修复了导致使用全局 mbox 或其他区域 mbox 的重定向选件闪烁的问题。(TNT-27978)
* 修复了在 VEC 中的“浏览”和“撰写”之间切换时，体验定位活动设置失败的问题。(TNT-27942)
* 修复了对点击跟踪元素的闪烁样式类处理不当的问题。(TNT-27896)
* 修复了导致全局 mbox 参数与所有 mbox 参数混合在一起的问题。(TNT-27846)
* 进行了相应更改，以确保 [!DNL at.js] 正确处理 Handlebars、Mustache 及其他客户端模板库。(TNT-27831)
* 进行了相应更改，以确保正确初始化 `sdidParamExpiry`，并将其传递到访客 API。这是添加到 `at.js 1.1.0` 中的回归参数。之前的 [!DNL at.js] 版本不会受到影响。此更改仅影响使用重定向选件和 A4T 的客户端。(TNT-27791)
* 进行了相应更改，以确保不论使用何种类型的属性，均会执行 `SCRIPT`。(TNT-27865)

## at.js 版本 1.1.0 {#section_8F494E1EA94E48A9B169F5CF9FE6DC56}

**日期：** 2017 年 8 月 2 日

[!DNL at.js] 版本 1.1 中包含以下增强功能和修复：

* 添加了响应令牌处理功能。有关更多信息，请参阅[响应令牌](/help/main/administrating-target/response-tokens.md#concept_2B21B222F6A344D68CA5929817E836C4)。
* 解决了相应问题，以便 `document.currentScript polyfill` 不会妨碍 Angular 1.X。
* 进行了相应更改，以确保点击跟踪不会妨碍可见性属性。点击跟踪元素使用 `at-element-click-tracking` CSS 类进行标记，而不使用 `at-element-marker`。

## at.js 版本 1.0.0 {#section_37A3D23FC4AD42A68AA831B89E03E725}

**日期：** 2017 年 7 月 7 日

at.js 版本 1.0 中包含以下增强功能和修复：

* 支持异步加载 at.js，以提高页面加载速度。
* 支持在异步加载 at.js 时预先隐藏页面内容。
* 改进了在禁用内容交付时显示的错误消息。
* 改进了交付多个活动时的性能。
* 支持 YUI 压缩工具。
* 在活动交付期间报告自定义事件的错误。
* 修复了 Microsoft Internet Explorer 11 中的性能问题。
* 修复了在某些网站上发生错误的 `getOffer()` 函数。
* 以异步方式加载 Target 库。有关更多信息，请参阅 [at.js 常见问题解答](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/target-atjs-faq.md#concept_D6EFE8D84A06476DB5ABD494D7E8C769)。

## at.js 版本 0.9.7 {#section_6C7B698BE21E40E495FD2850EFBF3E80}

**日期：** 2017 年 5 月 22 日

[!DNL at.js] 版本 0.9.7 中包含以下增强功能和修复：

* 修复了与可视化体验编辑器 (VEC) 的 `insertAfter` 和 `insertBefore` 操作中缺少的资产键有关的问题。此类问题与从可视化选件迁移到选件模板有关。

## at.js 版本 0.9.6 {#section_EEFA6413F2F947AD8C4A88128B90245D}

**日期：** 2017 年 4 月 13 日

[!DNL at.js] 版本 0.9.6 中包含以下增强功能和修复：

* 对 A4T 的重定向选件支持。下载并安装 [!DNL at.js] 版本 0.9.6 后，您可以在将 [!DNL Adobe Analytics] 用作 [!DNL Target] 报表源（即使用 A4T）的活动中使用重定向选件。除了 [!DNL at.js] 版本 0.9.6 之外，您的实施还必须满足其他最低要求，才能使用重定向选件和 A4T。有关更多信息以及其他应了解的重要信息，请参阅[重定向选件 - A4T 常见问题解答](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905)。
* 在 [!DNL at.js] 0.9.6 发布之前，如果页面上存在访客 API，且 `visitorApiTimeout` 设置过于短促，则 可能会出现以下情况：在 [!DNL Target]Target 请求中未发送任何 MCID 数据。使用 A4T 时，这可能会导致诸如 [!DNL Analytics] 中的点击无法整合的问题。

   [!DNL at.js] 0.9.6 已更改此行为，即使将 `visitorApiTimeout` 设置为 1 毫秒，Target 仍会尝试收集 SDID、跟踪服务器和客户 ID 数据，并在 Target 请求中发送这些数据。

* 添加了 `selectorsPollingTimeout` 设置。有关更多信息，请参阅 [targetGlobalSettings()](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)。
* 更改了来自 `getOffer()` 的响应格式。有关更多信息，请参阅 [adobe.target.getOffer(options)](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md)。
* 为不支持的 `<!DOCTYPE>` 声明添加了控制台日志记录。
* 修复了将多个默认选件交付到单个 mbox 时，无法正确应用 [!DNL Target Classic] 插件的问题。(TGT-22664)
* 改进了双字符顶级域 (TLD) 的 Cookie 设置，以确保为这些域（例如，[!DNL test.no]、[!DNL autodrives.ca] 等）正确设置 mbox Cookie。
* at.js 版本 0.9.6 中更改了对保存 Cookie 时应使用的顶级域进行提取的算法。由于进行了这项更改，Cookie 不能保存到使用 IP 的地址中。在大多数情况下，IP 地址都用于测试目的，但作为变通方法，您可以使用 DNS 条目或调整本地框中的主机文件。
* 修复了当属性是字符串值而不是整数时的移动和重新排列操作处理方式。

## at.js 版本 0.9.4 {#section_A15B12F12CD94F07B3F56613A79A815F}

**日期：** 2017 年 1 月 19 日

* mbox 名称现在可包含特殊字符，这些字符包括与号 (&amp;)。

   有关允许使用的特殊字符列表，请参阅 [at.js 配置](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#concept_2FA0456607D04F82B0539C5BF5309812)。

* 添加了 `secureOnly` 设置，以指示 at.js 是应仅使用 HTTPS，还是可以根据页面协议在 HTTP 和 HTTPS 之间进行切换。这是一项高级设置，其默认值为 False，可以通过 `targetGlobalSettings` 来覆盖此设置。
* at.js 版本 0.9.3 及更低版本中提供了“[!UICONTROL 旧版浏览器支持]”选项。此选项在 at.js 版本 0.9.4 中已删除。

## at.js 版本 0.9.3 {#section_DF13BC1D7C994AE7A36B81937A699DF4}

**日期：** 2016 年 10 月 10 日

* 确保在 at.js 设置中禁用旧版浏览器时，在 Microsoft Internet Explorer 11 中触发 mbox 调用。
* 确保在动态远程选件失败时（例如，如果 URL 不正确并返回 404 错误），渲染默认内容。
* 确保在 DOM 中找不到 VEC 点击跟踪选择器时，快速显示各元素。

## at.js 版本 0.9.2 {#section_148549CBB4F046BAA8F79C79B64EC889}

**日期：** 2016 年 9 月 21 日

* 添加了 `optoutEnabled` 设置，用于启用或禁用“设备图表”的选择退出功能。如果将此设置设为 `true`，且访客已选择退出跟踪，则访客的浏览器不会发起任何 mbox 调用。“设备图表”当前处于测试阶段。默认情况下，此设置将设为 `false`，但是如果您正在使用“设备图表”，则必须将此设置设为 `true`。
* 为通知机制添加了 `CustomEvent` 支持。以前，无法通过标准的 DOM API（例如 `document.addEventListener()` ）来使用 at.js 事件通知机制。现在，您可以使用 `document.addEventListener()` 订阅 at.js 事件，例如请求事件和内容渲染事件。
* 修复了与可视化体验编辑器 (VEC) 中创建的选件有关的问题。在此版本之前，Target 会隐藏选择器，并且只有在所有选择器都匹配时才会取消隐藏。在 at.js 0.9.2 中，当有选择器匹配时，Target 会立即取消隐藏匹配的选择器。

## at.js 版本 0.9.1 {#section_DAFB99114D604CFB8416C1BC7DEEAEEE}

**日期：** 2016 年 7 月 14 日

* 在 at.js 中为访客 ID 服务提供了一个超时，它与该服务自身的超时无关。
* 更正了0.9.0中的一个问题，该问题会影响在某些页面上使用at.js，而在其他页面上使用mbox.js（现已弃用）的实施。
* 如果您使用 Adobe Analytics 作为活动的报表源，并且使用的是 mbox.js 版本 61（或更高版本）或者 at.js 版本 0.9.1（或更高版本），则无需在活动创建期间指定跟踪服务器。at.js库会自动将跟踪服务器值发送到 [!DNL Target]. 在活动创建期间，您可以将“[!UICONTROL 目标和设置]”页面上的“[!UICONTROL 跟踪服务器]”字段留空。

## at.js 版本 0.9.0 {#section_2981CC9792F245389B39BB5B69F84C4E}

**Target 版本：** 16.6.1

**日期：** 2016 年 6 月 23 日

* 修复了使用 VEC 选件时出现的白屏问题。使用 [!DNL at.js] 的任何人都应该升级到此新版本。
* 新增了 `registerExtension` API。

   通过该新 API，开发人员可以访问 [!DNL at.js] 中使用的特定 jQuery 模块，以开发适用于库的扩展（即插件）。这项更改存在一些影响。这只会影响使用以下功能的用户：

   * 已删除 `getSettings()` API，但可使用 `registerExtension()` 实现相同的功能。
   * 已删除 `getTracking()` API，但可使用 `registerExtension()` 实现相同的功能。

   * 必须更新现有扩展（如 AngularJS 扩展），才能使用 `registerExtension()` 方法。

* 新增了at.js通知API。

   此通知系统的目标是针对 [!DNL at.js] 在页面上的行为以及在出现问题时提供更多信息。VEC 存在的常见问题是 IT 版本更改页面、VEC 选择器中断以及测试停止正确交付内容。此通知系统的目标是将此交付问题公布到页面上，从而使开发人员可以访问此信息，将其传递到 [!DNL Adobe Analytics] 等系统，并且还可以向测试被中断的业务所有者发送警报。

* 新增了 `targetGlobalSettings()` API 方法。

   您可以覆盖 at.js 库中的设置，而不是在 [!DNL Target Standard/Premium UI] 中或通过使用 REST API 来配置设置。

## at.js 版本 0.8.0 {#section_E1C7B08EC0494388A022C28A8B8FE807}

**日期：** 2016 年 5 月 5 日

这是 [!DNL at.js] 库的第一个正式版本。

[!DNL at.js] 是适用于 [!DNL Target] 的新实施库，专为典型的 Web 实施和单页应用程序而设计。

[!DNL at.js] 取代了 [!DNL Adobe Target] 实施的 [!DNL mbox.js]。

使用 [!DNL at.js] 具有许多好处，包括缩短 Web 实施的页面加载时间，增强安全性，以及为单页应用程序提供更好的实施选项，等等。

[!DNL at.js] 包含 [!DNL target.js] 中所包含的组件，因此不再需要调用 [!DNL target.js]。

实施 [!DNL at.js] 时，请注意以下事项：

* 不支持 Internet Explorer 8 以前的版本。
* 异步实施意味着 [!DNL Test&Target] 到 [!DNL SiteCatalyst] 插件等旧版集成可能无法工作。
* 不支持引用 [!DNL Target] 对象和方法的 [!DNL mbox.js] 插件。
* 对 [!DNL Target] 的所有调用均通过 XMLHTTPRequest 发起，内容则通过 JSON 返回。