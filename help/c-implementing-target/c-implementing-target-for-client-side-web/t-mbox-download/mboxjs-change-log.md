---
keywords: mbox.js 更改;mbox.js 版本
description: 此页面显示对 mbox.js 的每个版本所做的更改。
title: mbox.js 版本详细信息
subtopic: 入门指南
uuid: 5f8e0511-637b-4c17-bb19-aa7f4d7c98ea
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# mbox.js 版本详细信息{#mbox-js-version-details}

此页面显示对 mbox.js 的每个版本所做的更改。

>[!NOTE]
>
>我们建议所有 mbox.js 用户都升级到版本 57 或更高版本。有些用户遇到了超时问题，无法加载 `target.js`。版本 57 已修复该问题。但是，如果您正在使用 [!DNL Experience Cloud Visitor ID] 服务，则要求使用版本 58 或更高版本。

Target 如何响应从您的页面发出的调用，取决于您使用的 Target 库的版本、访客 ID 实施是否存在以及访客 ID 是否存在。有关信息，请参阅 [Target 按库版本响应调用](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/call-responses-library-version.md#concept_A95A4758A1E7405D947E9B4BCB5D62F0)。

>[!NOTE]
>
>mbox.js 库将不再开发。所有客户都应该从 mbox.js 迁移到 at.js。有关更多信息，请参阅[从 mbox.js 迁移到 at.js](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA)。

## mbox.js 版本 63 {#section_ED8EFCF653A845ED8927F759578C4A33}

**Target 版本：** 17.7.1

[!DNL mbox.js] 版本 63 现已可用。有关更多信息，请参阅[下载 mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/target-download-config-mbox.md)。

[!DNL mbox.js] 版本 63 中包含以下增强功能和修复：

* 修复了使用 `mboxDefine()` 和 `mboxUpdate()` 生成 SDID 时出现的问题。此问题仅影响在页面上具有访客 API 的客户端。

## mbox.js 版本 62 {#section_723A9119FE204183847D3B0929A99B41}

* 修复了在 Google Chrome 浏览器中查看重定向活动时出现的闪烁问题。
* 添加了 `secureOnly` 设置，以指示 mbox.js 是应仅使用 HTTPS，还是可以根据页面协议在 HTTP 和 HTTPS 之间进行切换。这是一项高级设置，其默认值为 False。

## mbox.js 版本 61 {#section_F3B59C5578B64883AE013B9342151193}

**Target 版本：** 16.7.2

**发行日期：** 2016 年 7 月 28 日

mbox.js 版本 61 包含以下增强功能：

* JavaScript 日期 API 中的 mboxSession ID 生成算法现在会生成随机字符串，而不是使用时间戳外加随机字符串。
* 仅当您在页面上具有访客 API 时，以下详细信息才适用：

   * [!DNL mbox.js] 版本 61 不会覆盖访客 API `loadTimeout` 属性。客户端可以使用 `visitorApiTimeout` 和 `visitorApiPageDisplayTimeout` 来控制访客 API 集成。
   * 添加了 `optoutEnabled` 设置，用于支持将来的 Adobe Experience Cloud 选择退出功能。默认值为 false。如果启用此属性，则会像版本 60 一样，对 [!DNL /ajax] 端点异步执行所有请求。
   * 默认情况下将禁用主体隐藏功能。仅当启用了全局 mbox 自动创建并且也启用了主体隐藏功能时，Target 才会使用主体隐藏功能。
   * 如果不存在 Experience Cloud 访客 ID Cookie，则在首次加载页面时，将会对 [!DNL /ajax] 异步执行所有请求。在第二次加载页面时，Target 将使用正常的流程，因为访客 ID 值已经存在。
   * 如果您使用 Adobe Analytics 作为活动的报表源，并且使用的是 mbox.js 版本 61（或更高版本）或者 at.js 版本 0.9.1（或更高版本），则无需在活动创建期间指定跟踪服务器。mbox.js 或 at.js 库会自动将跟踪服务器值发送到 [!DNL Target]。在活动创建期间，您可以将“[!UICONTROL 目标和设置]”页面上的“[!UICONTROL 跟踪服务器]”字段留空。

## mbox.js 版本 60 {#section_3BDAB885FA13444A8D35940A4BFF5825}

**Target 版本：** 16.4.1

**发行日期：** 2016 年 4 月 21 日

默认情况下不会隐藏页面内容。仅当“自动创建全局 mbox”选项被启用时，版本 60 才会隐藏页面内容。它会使用 CSS `opacity:0` 属性隐藏页面，而非 `display:none`。这可确保正确交付响应式网站，并与 [!DNL at.js] 保持一致。

您可以使用两个设置启用主体隐藏功能：

* `bodyHidingEnabled`默认值为 false，表示不隐藏 HTML 主体。

* bodyHiddenStyle

   默认值为 `body{opacity:0}`. 可将此值更改为其他内容，如 `body{display:none}`。

可通过包含如下内容来覆盖这些设置：

```
<script> 
window.targetGlobalSettings = { 
 bodyHidingEnabled: true, 
 bodyHiddenStyle: "body{opacity:0}", 
 visitorApiPageDisplayTimeout: 2000 
}; 
</script>
```

页面隐藏技术使用样式标记来添加和删除样式。这可确保在页面隐藏代码执行后网站的样式保持不变。

**DTM 用户：**&#x200B;请注意，这将阻止您使用自动导入选项，因为无法在 Target UI 中保存上述配置。您必须按照上述说明将这些内容粘贴到“自定义托管”选项的代码框中。

此外，在版本 60 中，如果 Experience Cloud 访客 ID 服务存在 [!DNL visitorAPI.js] 文件，则所有 mbox 都将通过 AJAX 端点来请求。这是必需的，因为访客 API 方法是异步方法。此方法的优势之一在于“开始呈现”时间显著缩短，因为 mbox 请求不会阻止呈现。但是，这也意味着所有 [!DNL Target] 选件内容都以异步方式运行，因此必须相应地编写所有选件代码。如果选件包含 `document.write` 以及其他假定将在初始页面加载时运行的代码，该选件将无法按预期执行。

* 版本 60 导步调用

   在将版本 60 与访客 ID 服务一起使用时，所有 mbox 调用都以异步方式发起。这改变了 mbox 一直以来的工作方式，因此请谨慎升级到此版本。请参阅 [ 文档中的](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-limitations.md#section_B586360A3DD34E2995AE25A18E3FB953)异步注意事项[!DNL at.js]部分（[!DNL at.js] 也使用异步调用）以了解可能面临的部分风险。
* 新访客可能遇到闪烁的情况

   将版本 58 到版本 60 与访客 ID 服务一起使用时，mbox 调用在触发之前（或在发生超时之前），将一直等待设置访客 ID。这种情况发生在新访客首次加载页面时。

## mbox.js 版本 59 {#section_FF0E70C4C17E402D8374DE428C5D996E}

**Target 版本：** 16.2.1

**发行日期：** 2016 年 2 月 17 日

mbox.js 版本 59 包含以下增强功能：

* 禁用的 mbox 已被降低至 30 分钟
* 修复了与页面隐藏/取消隐藏相关的问题

   与使用 `display:none` 隐藏页面的版本 58 不同，而是使用 `opacity:0`。这解决了响应式设计网站中因之前的页面隐藏方法而导致的问题。

## mbox.js 版本 58 {#section_5070B0D1C87F4937BB97727923DD36C7}

**Target 版本：** 15.7.1

**发行日期：** 2015 年 7 月 30 日

如果您要将 Analytics 用作 Target 的报告源，则必须使用此版本的 mbox.js，且强烈建议将此版本的 mbox.js 用于配置文件和受众。

mbox.js 版本 58 可确保 Experience Cloud 访客 ID 服务在发起 Target 调用之前返回访客 ID。这能够确保通过配置文件和受众核心服务共享的受众数据可用于访客会话中的第一次 Target 调用。为避免默认内容在测试内容返回之前闪烁，在访客 ID 服务返回之前，Target 会隐藏 `<BODY>`。`display:none` 用于隐藏页面。

此更新还修复了当使用 Analytics 作为 Target 的报告源时，导致在 Analytics 中针对仅包含一个页面的访问报告的访客人数被夸大的问题。

Mbox.js 会设置超时值，以防不返回访客 ID 服务。访客 ID 服务的默认超时值为 500 毫秒（0.5 秒）。还有一个超时用于设置 `<BODY>` 标记隐藏时间的上限。其默认值为 500 毫秒（0.5 秒）。在每个页面上的 mbox.js 引用前插入以下代码可更改这些超时：

```
<script> 
window.targetGlobalSettings = { 
 visitorApiTimeout: 500, 
 visitorApiPageDisplayTimeout: 500 
}; 
</script> 
```

在 HTML `BODY` 标记出现后，mbox.js 版本 58 及更高版本会立即执行全局 mbox 的非 JavaScript 内容。`DOMContentLoaded` 事件触发后，全局 mbox 的 `<script>` 标记内的 JavaScript 内容便会执行。这种内容交付顺序可确保全局 mbox 的 JavaScript 内容被正确交付和渲染。

## mbox.js 版本 57 {#section_6BA1CDBF75B14A94B59E8624ACF583D4}

**Target 版本：** 15.4.1

**发行日期：** 2015 年 4 月 21 日

此版本进行了以下更改：

* 为 Target Standard 自动创建的全局 mbox 响应不再使用 document.write() 或创建 <div> 元素。

   因此不再要求 mbox.js 文件必须是页面 <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> 中的最后一个项目。升级至此新版本时建议完成严密的质量保证工作。

   此更改可能会导致在发送一些选件类型时行为发生变化。以下是需要考虑的特定情况：

   * 作为“插件选件”的一部分返回的 HTML 内容无法正常呈现，但是选件中的 JavaScript 能够按照预期执行。
   * 返回到全局 mbox 的 JavaScript 选件可能会在 `<script>` 标记中嵌入 JavaScript 代码，或者被 `src` 属性引用。

      要执行此操作，请向脚本调用中添加 `async` 属性，如下所示：

      `<script src='external-url' async='true'></script>`

      请注意，Internet Explorer 对 `async` 属性的支持有限（详情请参阅此处：[https://developer.mozilla.org/cn/docs/Web/HTML/Element/script#Browser_compatibility](https://developer.mozilla.org/en/docs/Web/HTML/Element/script#Browser_compatibility)），因此您应该将使用旧版 IE 的访客从包含这些第三方脚本的测试中排除。

* 修复了版本 56 中报告的由于 mbox.js 中的“额外 JavaScript”部分发生更改而导致的问题。同样，“额外 JavaScript”部分中的所有代码在全局范围内可用。

mbox.js 版本 57 不支持以下功能：

* Target Standard 中生成的自动创建的全局 mbox 无法用于 Target Classic 中的托管选件类型。托管选件类型包含“网站上的选件”和“Test&amp;Target 外的选件”。

   这就意味着在 Target Classic 中，当需要其中一种选件时，您不得选择 Target Standard 中自动创建的全局 mbox。
* 仅支持 JavaScript 插件。

   如果插件的选件包含 JavaScript 代码以及 HTML，则会执行 JavaScript 代码，但不显示 HTML 内容。

mbox.js 版本 57 还包含重要修复：

* 修复了导致 SiteCatalyst 插件无法在 mbox.js v56 中运行的问题。
* 修复了因范围更改所产生的“额外 JavaScript”错误而导致的问题。
* 撤消对 mboxFactory 构造器的更改。

## mbox.js 版本 56 {#section_C4F4A53584B741FF9FD907D81CB7E164}

**Target 版本：** 15.1.2

**发行日期：** 2015 年 2 月 17 日

>[!NOTE]
>
>有些用户遇到了超时问题，无法加载 `target.js`。版本 57 已修复该问题。但是，如果您正在使用 [!DNL Experience Cloud Visitor ID] 服务，则要求使用版本 58 或更高版本。

此版本进行了以下更改：

* 对 Premium Recommendations 进行了更改，以支持将参数传递到全局 mbox。
* 向 target.js 加载调用增加了 5 秒超时限制。在极少数情况下会出现文件不加载的现象，发生这种情况时，页面将呈现并且不显示任何 Target Standard 活动。
* 将“额外 JavaScript”移动到在全局 mbox 之前执行。

   v56 及以上版本中的所有设置都具有命名空间。如果有函数在“额外的 JavaScript”中声明，则必须为它们添加前缀 `window`。

   例如：

   `function foo {`

   `}`

   变为：

   `window.foo = function() {`

   `}`

   任何应该在全局范围内可访问的变量也必须添加前缀 `window`。

* 添加了一个名为“em-disabled”的 Cookie，如果 target.js 在发送过程中加载失败，mbox.js 便会将此 Cookie 提供给用户。此 Cookie 可防止使用 Visual Experience Composer 创建的选件呈现在网站上。具有此 Cookie 的用户既不会看到测试内容，也不会被计入这些活动报表。所有其他选件内容（例如，来自 Target Classic 中的营销活动）将继续加载。此 Cookie 的生命周期为自加载失败之时起 30 分钟。

## mbox 版本 55

**Target 版本：** 15.1

**发行日期：** 2015 年 1 月 19 日

通过 IE 修复修改了版本 53。

## mbox 版本 54

**Target 版本：** 14.9.2

**发行日期：** 2014 年 9 月 30 日

将全局 mbox 实施从 document.write 更改为 AJAX。因此不再要求 mbox.js 文件必须是页面 <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> 部分中的最后一个项目。此版本只能通过 API 获取。客户端可以下载此版本并使用此 mbox.js 文件。某些网站在采用此实施时会出现内容闪烁的情况，因此请在您的网站上验证集成性。

## mbox 版本 53

**Target 版本：** 14.9.1

**发行日期：** 2014 年 9 月 14 日

修复了 Target 页面参数在 Internet Explorer 中无法正常触发的问题。

## mbox 版本 52

**Target 版本：** 14.8

**发行日期：** 2014 年 8 月 14 日

mboxParameter 函数现在可以在 Target Standard 和 Premium 中使用。

修复了导致 Analytics 跟踪功能无法在 IE 9 和 11 中使用的问题。此更改只会影响 Analytics 的用户。

现在您可以使用 targetPageParams() 函数，以数组、JSON 对象或逗号分隔列表（以前支持）的形式，[将参数传入](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md) target-global-mbox。

重命名了 M2PcId 以及与 VisitorId 相关的所有内容。

允许清除注册的 mbox 中的 defaultDiv。

## mbox 版本 51

**Target 版本：** 14.6

**发布日期：** 2014 年 6 月 25 日

修复了为顶级域中有两个字符的网站设置不正确的 Cookie 的错误。

修复了 mbox.js 中导致返回井号标签值的次要错误。

## mbox 版本 50

改进了 Target Standard 与 Target Classic 之间的同步。

## mbox 版本 49

改进了对嵌套 mbox 的 Internet Explorer 10 支持。

## mbox 版本 48

添加了对“将 Adobe Analytics 作为 Target 报告源”的支持。

## mbox 版本 47

mbox.js 当前支持在 Target Standard 中使用自定义全局 mbox 名称。

## mbox 版本 46

为 Target Standard 的单行代码实施添加了对 Experience Cloud 访客 ID 服务的完整支持。这会启用服务器端 Adobe Analytics 集成和 Experience Cloud 共享配置文件。

修复了 IE10 中在文档模式下提交内容时存在的问题。

## mbox 版本 45

添加了对 Experience Cloud 访客 ID 服务的完整支持。这会启用服务器端 Adobe Analytics 集成和 Experience Cloud 共享配置文件。

## mbox 版本 44

通过 mboxVizTarget，在 URL 中添加了新参数：

mboxDOMLoaded

## mbox 版本 43

添加了对 Target Standard 的支持。

## mbox 版本 42

添加了对 Experience Cloud 共享访客 ID 服务的初步支持。

## mbox 版本 41

* 甚至可以通过 x-only 设置，禁用第一方 Cookie，以缩短加载时间并防止页面不断刷新。

   设置了超时 Cookie，以防对 Target 的调用无法按时返回。这种方法比只使用第三方 Cookie 更快。如果只使用第三方 Cookie，则页面在等待来自 Target 服务器的正常响应时会不断刷新。

* 修复了流量限制以便只在启用 mbox.js 时发生

   如果客户对其 mbox.js 设置了流量限制，导致超时设置无法正常起作用，则会出现此问题。这会导致页面在等待来自 Target 服务器的正常响应时进行刷新。

* 修复了 SiteCalyst 插件以始终使用 Ajax 抓取器

   在进行此更改之前，Test&amp;Target 到 SiteCatalyst 插件的用户在某些情况下会遇到以下问题：根据插件加载的时间，可能会触发将会擦除页面的 document.write。

## mbox 版本 38

添加了对基于页面的 SiteCatalyst 到 Test&amp;Target 集成的支持（必须启用）

## mbox 版本 37

对 URL 键值进行编码

## mbox 版本 36

更改了 mbox 以使用 tt.omtrdc.net

## mbox 版本 35

* 现在总是可以远程执行 Mbox 调试
* 添加了 mboxTime 参数。此参数是用户看到它时的时间，是从 epoch 开始的 GMT 时间，单位为毫秒。该参数只计算一次。

## mbox 版本 34

* 总是尝试获取最新的默认 div，而不是引用缓存的版本。

   这修复了缓存的默认内容 div 不在 DOM 中的问题，问题的原因是 mboxUpdate 提供了默认 div 的内容。

* mbox.getDefaultDiv 具有新的可选布尔值参数。如果为 true，则返回当前默认的 div。如果为 false，则返回最新缓存的默认 div。
* 更新了 mbox.loaded 以支持 Ajax 负载
* mboxURL 参数现在使用 encodeURIComponent 而不是 escape 进行编码
* 测试 encodeURIComponent 是否受浏览器支持，如果不受支持则显示默认内容。此外还删除了以下 mbox.js 配置选项：
   * encode\_mbox\_parameters
   * mbox\_signal\_support
