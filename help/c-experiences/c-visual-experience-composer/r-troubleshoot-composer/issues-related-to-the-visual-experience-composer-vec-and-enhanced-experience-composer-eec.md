---
keywords: Targeting;visual experience composer;whitelist;white list;allowlist;allow list;enhanced visual experience composer;vec;troubleshoot visual experience composer;troubleshooting;eec;enhanced experience composer;tls;tls 1.2
description: 有时，在某些情况下，可视化体验编辑器 (VEC) 和增强型体验编辑器 (EEC) 可能会发生显示问题。
title: 对与可视化体验编辑器和增强型体验编辑器有关的问题进行故障诊断
feature: vec
uuid: 93f646d9-fcbc-43f0-9f84-0ce8e486ff7f
translation-type: tm+mt
source-git-commit: 870f3dc0d4c154b282021384071699fa2d477d18
workflow-type: tm+mt
source-wordcount: '1253'
ht-degree: 74%

---


# 对与可视化体验编辑器和增强型体验编辑器有关的问题进行故障诊断{#troubleshooting-issues-related-to-the-visual-experience-composer-and-enhanced-experience-composer}

在某些情况下，显示问题和其他问题有时会在Visual Experience Composer(VEC)和Enhanced Experience Composer(EEC)中出现。

## 最近发布的Google Chrome SameSite cookie实施策略对VEC和EEC有何影响？ {#samesite}

使用Chrome 80+浏览器版本的所有用户，通过最新更改（2020年8月）:

* 将 *无法* 在其站点的受密码保护的页面中使用VEC（安装或未启用VEC Helper扩展）。 这是因为他们的站点登录Cookie将被视为第三方Cookie，并且不会随登录请求一起发送。 唯一的例外情况是客户站点登录Cookie已将SameSite参数设置为“none”。
* 编 *辑活动* 时 [!DNL Target] （当站点上尚未下载库时）将无法下载库。 这是因为下载调用是从客户域向安全Adobe域发出的，并且作为未验证而被拒绝。
* EEC对所 *有用户* 都不起作用，因为它无法为上的cookie设置SameSite属性 `adobemc.com domain`。 如果没有此属性，浏览器将拒绝这些Cookie，导致EEC失败。

Adobe已将更新的VEC帮助程序扩展提交到Google Chrome商店。 此扩展会覆盖cookie属性，以根据需要 `SameSite="none"` 设置属性。 更新 [的扩展可在此处找到](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak?hl=en)。

### 备选方案和解决办法

使用以下选项之一确保您的VEC和EEC继续按预期工作：

* 下载并使用更新 [的VEC Helper扩展](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak?hl=en)。
* 使用Mozilla Firefox浏览器。 Firefox尚未执行此政策。
* 继续使用Chrome，但将标 `chrome://flags/#same-site-by-default-cookies` 志设置为“禁用”。

   >[!NOTE]
   >
   >如果 *Cookie* 已将服务器的SameSite属性设置为“Lax”或“Strict”，则这是不够的。

## Target 是否支持多级 iframe？

Target 不支持多级 iframe。如果您的网站加载的 iframe 具有子 iframe，则 Target 库（at.js 和 mbox.js）仅与父 iframe 进行交互。Target 库不会与子 iframe 进行交互。

作为解决方法，您可以在体验中添加一个页面，其中包含子 iframe 的 URL。

## 我在尝试编辑页面时，看到的只是一个旋转图标而不是我的页面。（VEC 和 EEC）{#section_313001039F79446DB28C70D932AF5F58}

如果 URL 包含 # 字符，则会出现此问题。要解决此问题，请在可视化体验编辑器中切换到“浏览”模式，然后再切换回“撰写”模式。此时，旋转图标应当消失，页面应会加载。

## 我网站上的内容安全策略 (CSP) 标头会阻止 Target 库。（VEC 和 EEC）{#section_89A30C7A213D43BFA0822E66B482B803}

如果您网站的 CSP 标头会阻止 Target 库，从而导致加载了网站却无法进行编辑，则请确保 Target 库不受阻止。

>[!NOTE]
>
>除了以下信息外，您还可以使用适用于 Google Chrome 的 [Adobe Target VEC 助手浏览器扩展](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)。

![](assets/cps_headers.png)

作为解决方法，您可以配置 Requestly 规则以删除 CSP 标头，如下所示：

![](assets/cps_headers_2.png)

您可以为导致资源无法在 VEC 中加载的任何标头配置类似的 Requestly 规则。

对于 Requestly，每当需要删除标头时，您都应该执行以下任一操作：

* 为要在 VEC 中打开的 URL 添加 URL 规则，以便仅删除这些 URL 的标头。
* 在 VEC 中进行编辑时启用该规则，而在不使用 VEC 时禁用该规则。

## 重新编辑保存的活动时，VEC 或 EEC 显示为已损坏或未初始化。（VEC 和 EEC）{#section_5AC3BA8F8FBB451EA814F298D0645E54}

如果在定义体验后网站在可视化体验编辑器外部进行了更改，则在打开活动以进行重新编辑时，将无法找到之前执行操作时所用的选择器。页面会显示为已损坏，且不会出现任何警告。

## VEC 或 EEC 不显示我的旋转横幅以及其他包含 JavaScript 的内容。（VEC 和 EEC）{#section_8B5BE6EB050B42D6A14A054724C41330}

默认情况下，可视化体验编辑器会阻止 JavaScript 元素。如果在可视化体验编辑器设置中禁用 JavaScript，则可以使用这些元素。根据网站的设置方式，某些项目可能会继续以不正确方式显示或仍然不可用。

## 后续重新加载页面时，我托管的 target.js 文件加载失败。（VEC 和 EEC）{#section_87F6418C2CD142A7B4D1E7037935F81F}

当客户使用的 mbox.js 版本低于 57（即，使用版本 56 或更低版本）时，会出现此问题。

我们建议所有 VEC 用户升级到 [mbox.js 的最新版本](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)，或至少升级到版本 57。您还应该考虑[转换到 at.js](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17)。

## 我在页面上更改一个元素时，多个元素会发生更改。（VEC 和 EEC）{#section_309188ACF34942989BE473F63C5710AF}

如果页面上的多个元素使用相同的 DOM 元素 ID，则更改其中一个元素会导致具有该 ID 的所有元素都发生更改。为防止这种情况发生，一个 ID 只应在每个页面上使用一次。这是标准的 HTML 最佳实践。有关更多信息，请参阅[页面修改方案](../../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB)。

## 我无法编辑防 iFrame 嵌套网站的体验。（VEC 和 EEC）{#section_9FE266B964314F2EB75604B4D7047200}

启用增强型体验编辑器即可解决此问题。Click **[!UICONTROL Administation]** > **[!UICONTROL Visual Experience Composer]**, then select the check box that enables the Enhanced Experience Composer. 增强型体验编辑器使用 Adobe 管理的代理来加载页面以进行编辑。这允许在防 iFrame 嵌套的网站，以及尚未添加 Adobe Target 代码的网站和页面上进行编辑。在添加代码之前，活动不会向网站交付内容。有些网站可能无法通过增强型体验编辑器来加载，在这种情况下，您可以取消选中此选项以通过 iFrame 加载可视化体验编辑器。[]

>[!NOTE]
>
>Adobe 代理服务器无法访问本地托管页面或在您的网络外部不可访问的页面，这些页面无法在 EEC 中打开。这些页面可能包括测试 URL、用户验收测试 (UAT) URL 或本地托管页面。

## 我想在尚未完成 mbox/Target 实施的页面上设置测试。（VEC 和 EEC）{#section_DE63BCCB5B124E10A71FA579B582A80A}

请参阅上面的“我无法编辑防 iFrame 嵌套网站的体验”。

## 我的页面上不会显示使用“编辑文本/HTML”或“更改文本/HTML”设置的粗体和斜体文本样式。有时，在应用这些样式更改后，文本会消失。（VEC 和 EEC）{#section_7A71D6DF41084C58B34C18701E8774E5}

如果您在可视化体验编辑器中对 A/B 活动或体验定位活动使用&#x200B;**[!UICONTROL 编辑文本/HTML]**，或者对自动个性化活动或多变量测试活动使用&#x200B;**[!UICONTROL 更改文本/HTML]**，以使文本变为粗体或斜体，则这些样式可能不会在页面上应用，或者文本会从可视化体验编辑器内的页面中消失。这是因为富文本编辑器应用这些样式的方式可能会影响网站标记。

如果您遇到此问题：

1. 单击富文本编辑器中的 **[!UICONTROL HTML]** 按钮以进入源编辑模式。
1. 找到样式文本元素。

   * 对于粗体文本，请将 `<strong>` 元素更改为 `<b>`。

   * 对于斜体文本，请将 `<em>` 元素更改为 `<i>`。

## 对于自动个性化活动，VEC 或 EEC 中的图像交换显示为已中断。（VEC 和 EEC）{#section_88AABFDFE6A3420299B0D508B12A3994}

向某个位置添加图像选件会占据 VEC 或 EEC 中原始图像空间的整个大小范围。在交付时，图像不会展开，而是会按原样显示，这样便不会影响交付。
