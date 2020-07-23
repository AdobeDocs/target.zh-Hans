---
keywords: visual experience composer;visual experience composer best practices;visual experience composer limitations;visual experience composer caveats;vec best practices;vec
description: 以下最佳实践有助于确保您的体验按预期运行。使用可视化体验编辑器 (VEC) 时，您还应注意其他一些提示和限制。
title: 可视化体验编辑器最佳实践和限制
topic: Classic
uuid: 8d1d199b-b3d7-4edb-ba05-bd97372a0b9e
translation-type: tm+mt
source-git-commit: 3edb13b196240bb1918fc66edcc653936e32d3ef
workflow-type: tm+mt
source-wordcount: '2448'
ht-degree: 97%

---


# 可视化体验编辑器最佳实践和限制{#visual-experience-composer-best-practices-and-limitations}

以下最佳实践有助于确保您的体验按预期运行。使用可视化体验编辑器 (VEC) 时，您还应注意其他一些提示和限制。

如果遵循这些最佳实践，那么您设计的体验就不太可能遇到意外问题。

## 最佳实践 {#section_86CF28C99CFF40329E4CBAFE4DD78BB4}

**对于 mbox.js 版本 57 及更高版本以及 at.js，请将 mbox.js 或 at.js 引用放置在页面`<head>`部分的顶部。**

如果您还使用访客 API 服务，请将访客 API 脚本放置在 mbox.js 或 at.js 上方。

**对于版本 57 之前的 mbox.js 版本，请将 mbox.js 代码尽可能放置在页面`<head>`部分的最底部。**

将 mbox.js 放置在 `<head>` 部分的末尾，其后不再放置其他声明。否则，任何脚本或链接标记都会移动到 `<body>` 部分中。

**您可以在帐户级别启用增强型体验编辑器（为该帐户中创建的所有活动启用），也可以在活动级别启用该编辑器。**

To enable the Enhanced Experience Composer at the account level, click [!UICONTROL Administration > Visual Experience Composer], then toggle the switch to the On position.

在“可视化体验编辑器”中创建活动时，要在活动级别启用“增强型体验编辑器”，请单击[!UICONTROL 配置 > URL]，然后将开关切换到“开启”位置。

**如果允许列表增强的视觉体验书写器无法加载到您站点上的安全页面上，则可以某些IP地址。**

加载增强的可视体验书写器时出现的问题，可列入允许列表以通过以下IP地址来解决。 用作增强型体验编辑器代理的 Adobe 服务器使用这些 IP 地址。仅在编辑活动时才需要这些地址。访客到您的站点不需要已列入允许列表这些IP地址。

美国：52.55.99.45、54.80.158.92 和 54.204.197.253

欧洲、中东和非洲 (EMEA)：52.51.238.221、52.210.199.44 和 54.72.56.50

亚太地区 (APAC)：52.193.67.35、54.199.198.109 和 54.199.241.57

**对于最上层元素，以及其他任何可能是测试/定位较好候选者的元素，为其使用唯一 ID。**

主体元素内的任何内容都应该具有唯一 ID。如果有新元素注入到主体中且移动了周围的代码，那么这样做至少有助于识别父元素。

Adobe Target 不要求必须有 ID，但使用 ID 可以提高通过体验编辑器创建的体验的可靠性。在交付体验时，Target 会使用 CSS 选择器修改您的内容。编辑体验时，可视化体验编辑器会将选择器锚定到距离最近的上级元素，且该元素具有适用于要修改的 HTML 元素的非空 ID 属性。因此，不建议使用任何机制（包括 JavaScript 库）来设置或修改 HTML ID 属性。尽管这些 ID 可供 Target 体验编辑器用于创建活动，但如果 JavaScript 修改了 ID，则在体验运行时，创建体验时使用的 ID 可能不可用。如果 ID 不可用，则定位到该 ID 的选择器将会失败。

**为 CSS 类命名，以便它们易于识别。**

在可视化体验编辑器中编辑 CSS 类时，使用描述性的类名称可帮助您更轻松识别类。这有助于确保您编辑的是正确的 CSS 类，并且您的页面会按预期显示。

隐藏或删除元素时，请勿使用 `!important` CSS 属性。

如果存在 1!important1 CSS 属性，则 target.js 所做的更改将会在交付过程中被网站的 CSS 规则覆盖。

**避免使用 HTML 表格进行页面布局。**

Target Standard 和 Premium 使用 JavaScript 来设置页面格式。使用 JavaScript 修改基于表格的布局比较困难。此外，基于表格的布局在不同浏览器中可能会以不同的方式显示。为获得最佳效果，请使用 CSS 创建页面布局。

**最大限度地减少 iFrame 的使用。**

最大限度地减少 iFrame 的使用、简化页面和测试管理是不错的实践方式。可视化体验编辑器可以在 iFrame 中应用某些操作，但有些操作（如调整大小）无法正常工作。管理使用多个 iFrame 的页面以及调整这些页面的大小比较困难。因此，测试使用多个 iFrame 的页面可能会产生问题。

**在 DOM 准备就绪后尽快安排所有动态 DOM 的修改。**

如果在使用 target.js 应用体验之前无法应用所做的修改，则可能会中断内容交付。只有在目标元素的层次结构中应用 DOM 更改时才会出现此问题。

**在锚点元素中仅使用纯文本或图像标记。**

`<a>Anchor Text</a>`

或

`<a href=""> <img src=""> </img> </a>`

**避免在内联元素中使用块级元素。**

不应在内联元素（如锚点、范围等）中使用块级元素。否则，内联元素会丢失其高度和宽度，从而导致可视化体验编辑器中的叠加工具可能无法正常工作。

**请勿在您的网站中使用基本标记来解析 URL 和链接。**

可视化体验编辑器使用代理服务器在后台操作网站，该代理服务器对链接进行更新。如果添加基本标记，则浏览器会再次解析代理服务器使用的 URL，这样 URL 会显示为已损坏。

**使用“编辑 HTML”处理 DOM 结构可能会破坏选择器。**

例如，如果您执行了 2 项操作：

* 将一个类添加到 Element 1
* 为 Element 1 编辑 HTML

每次更改都会在可视化体验编辑器中创建一个新元素。因为第 2 个操作修改了 Element 1，如果删除 Element 1，则第 2 个操作将没有任何可修改的内容，因此更改不再有效。

换言之，如果您添加一个带有文本的元素，然后在单独的操作中使用不同的文本对该元素进行编辑，则代码编辑器会将两种操作当做单独的元素显示。在编辑元素时，您创建了一个新元素，该元素修改了之前创建的原始元素，在其中包含已编辑的文本。如果删除了原始元素，则编辑后的文本将无法找到被编辑的元素，而且也不会显示出来。第二个元素会保留在元素列表中，但不会对页面产生影响，因为它所更改的元素不再存在。

请参阅[可视化体验编辑器中使用的元素选择器](../../c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337)。

**使用富文本编辑器为文本元素设置样式时，请使用`<b>`和`<i>`标记。**

* 对于粗体文本，请使用 `<b>` 而不是 `<strong>`。
* 对于斜体文本，请使用 `<i>` 而不是 `<em>`。

使用 `<strong>` 和 `<em>` 标记可能会导致意外结果。

**删除表单字段时要谨慎。**

某些表单字段可能是提交时必需的字段。删除这些表单字段可能会影响提交。

**请勿在脚本中包含`mboxCreate`。**

由于 `mboxCreate` 使用的是 `document.write`，因此不建议在脚本中包含 `mboxCreate`。请改为使用 `mboxDefine` 和 `mboxUpdate` 来达到相同目的。

**如果需要 JavaScript 代码进行初始化，则不要使用 Target Standard 更新 html 代码段。**

当在页面组件（如滑块、旋转等）上执行操作（编辑 HTML）时，交付可能中断。可视化体验编辑器会在 JavaScript 将页面组件实例化之后执行操作。

但是，当页面内容交付给访客时，会在组件实例化之前应用该操作。因此，此组件的功能可能会也可能不会中断交付操作。功能取决于其页面上用于定义组件的脚本的性质。

如果您对交付进行了测试，且在第一次可以正常交付，您仍无法保证它会继续正常工作。因为可能会（或可能不会）存在争用条件。

* 如果存在争用条件，则会间歇性地交付。
* 如果没有争用条件，则会始终正常交付。

多次测试您的页面，以确保可以按预期正常预期。

**请勿在您的网站中使用基本标记来解析 URL 和链接。**

使用增强型体验编辑器时，代理服务器会在后台操作该网站，该代理服务器可更新所有链接 URL 以使它们在代理中起作用。如果添加基本标记，则浏览器会解析所有这些 URL，这样这些 URL 会显示为已损坏。

**网站上可能用于定位的重要文本应保存在元素内的 HTML 代码中。**

例如，如果您的代码如下所示，则无法在 VEC 中定位购物车 (Shopping Cart) 文本：

```
<a href="https://www.botanicchoice.com/shop.axd/Cart"> 
   <img alt="Shopping Cart"src="/images/ico-cart.gif"></img> 
   Shopping Cart: 
   <span id="HeaderCartQtyTotal">
      0 
  </span> 
  Items 
  <span id="HeaderCartPriceTotal"></span> 
</a>
```

在此示例中，系统已在 VEC 中选择整个锚点元素，此时如果执行定位，则会对其他元素产生不利影响。

**请勿在 JavaScript 代码中使用`top`或`self`变量。**

启用增强型体验编辑器后，将更新 top 和 self 变量的值以禁用 iframe 嵌套。使用 X-frame-options 标头可添加 iframe 嵌套而不是自定义 JavaScript 代码。

**如果在加载页面时添加参数，始终都应测试您的网站。**

例如，要打开 www.abc.com，使用了以下 url 参数：

`www.abc.com?mboxEdit=1&mboxDisable=1`

这些参数允许您在 iframe 中进行编辑。

添加这些参数后，请确保您的网站会按预期加载。

**确保您的页面可在 iframe 中按预期一样正常打开。**

关闭您网站上的 iframe 嵌套技术，并查看它是否按预期在虚拟页面上的 iframe 中打开。例如：

```
<!DOCTYPE 
<html> 
<html> 
<head> 
  <meta charset="utf-8"> 
  <meta name="viewport" content="width=device-width"> 
  <title>JS Bin</title> 
</head> 
<body> 
  <iframe src="https://www.homedepot.com"</iframe> 
</body> 
</html>
```

## 注意事项 {#section_A0436B7B85BA467FA9DE13A9A40E6A6E}

使用可视化体验编辑器设计活动时，请考虑以下注意事项。

**“移动”功能不支持 z-index。**

由于没有 z-index 功能，因此被移动的元素不能移动到其他元素上方。有关详细信息，请参阅[限制](../../c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721)。

**重新排列元素会影响点击跟踪。**

如果已标记为点击跟踪的元素进行了重新排列，则重新排列元素的路径会发生更改。因此，位于重新排列之前原始元素所在位置的元素是跟踪其点击的元素。

之所以会发生这种情况，是因为交付活动内容的代码和跟踪点击的代码都包含在一段传递到页面的代码中。如果您浏览到其他页面并设置点击跟踪，则活动内容代码和点击跟踪代码都会传递到该页面。如果点击跟踪页面具有与运行测试的页面类似的页面结构，则测试内容也可能会出现在点击跟踪页面上。

**在作为 mbox 的`<div>`中可能无法正常插入元素。**

如果 mbox 包含选件，则在未正确实施 mbox 时，插入元素操作可能会显示为 insertBefore 而不是 insertAfter。

**既要编辑父元素、也要编辑子元素时，请先编辑父元素。**

如果在元素上执行了图像交换操作，然后再编辑其父元素上的文本或 HTML，则交付可能会出现问题。先编辑父元素，然后再交换子元素上的图像，这才是最佳的工作流程。

**无法选择包含作为子元素的 mbox 的页面元素。**

例如，如果您的页面包含：

```
<div> 
  <div class="mboxDefault" > 
  </div>
  <script>mboxCreate('myMbox'); 
</div>`
```

不应在体验中选择外部 div，因为页面中硬编码的 mbox 仍会调用 Target 并收到响应。此响应会干扰本是针对较大页面元素的响应。

**客户环境中可能会阻止代理 IP。**

您在非实时网站（例如暂存环境）上使用增强型体验编辑器时，如果您的网站阻止 RIP，那么您可能会看到超时和拒绝访问错误。

**添加多个页面时，会同时打开体验边栏和页面边栏。这会缩小可视化体验编辑器的宽度，以显示要进行优化的网站。因此，在可缩小的空间中，可回流网站可能会以不同于预期的形式显示。**

要解决此问题，您可以单击顶部向左的 V 形图标来折叠体验边栏和页面边栏。

## 限制 {#section_F33C2EA27F2E417AA036BC199DD6C721}

**移动功能**

无法将元素移动到后接 CSS 属性的容器之外。

**只能在 mbox 上执行交换选件操作。**

mbox 中不允许使用“编辑类”和“重新排列”等操作。Mbox 内容由 mbox.js 提供。

**您不应重新排列和移动相同的元素。**

如果元素已移动到其他位置，并且您选择了父容器并尝试重新排列子元素，则移动的元素不会受到影响并保持在原位置不变。可能不会按预期重新排列。

**“交换图像”操作不适用于轮播中的图像。**

例如，如果您的页面包含带六个图像的轮播，并且您想要将图像与旋转中的第二个图像交换，则“交换图像”操作将不起作用。

要解决此问题，您可以选择父容器并使用“编辑 HTML”操作来编辑轮播的 HTML 以更新所需图像的图像源。

**无法在 mbox 中调整图像大小。**

如果在 mbox 元素中交换图像，然后尝试根据 mbox 元素大小调整该图像的大小，则调整大小会失败。

**交换图像后，无法选择“编辑”操作。**

交换图像后，无法编辑 Scene7 URL。

**无法编辑具有外部源的 HTML 元素。**

例如：视频、音频标记、嵌入、iFrame、框架。

**点击跟踪不适用于包含纯文本或图像标记以外的任何内容的锚点元素。**

例如，如果元素包含 JavaScript，则点击跟踪不起作用。

**页面必须接受 URL 参数，可视化体验编辑器才能工作。**

有些网站会删除其页面的所有 URL 参数。但是，可视化体验编辑器需要这些参数。

**使用脚本作为 html 的一部分时，任何从外部访问的变量和函数都应在窗口命名空间下进行声明。**

页面加载后，会在 target.js 范围内执行脚本。因此，无法从脚本块外部访问本地声明的任何变量或函数。

*错误：*

```
<script> 
  var myVar = 123; 
  function myFunc() { 
    // 
  } 
</script>`
```

*正确：*

```
<script> 
  window.myVar = 123; 
  window.myFunc = function() { 
    // 
  }; 
</script>
```

**从内容库 (Scene7) 插入图像并编辑 HTML 会破坏图像 URL。**

使用一些虚拟文本在“customHeaderMessage”div 中添加一个锚点元素：

```
<a href="#"> 
<span> Dummy text </span>
</a>
```

使用“插入元素”操作选择此 div，以插入作为此虚拟文本 div 同级项的图像。

插入图像后，它看起来如下所示：

```
<a href="#">  
<span> Dummy text </span> 
<img src=""> This is inserted Image. </img> 
</a>
```

删除虚拟文本范围。

**可视化体验编辑器中的 customCode 操作不适用于 Internet Explorer 8。**

由于处理脚本内容时 IE8 存在限制，因此 target.js 在 IE8 中不支持此功能。作为解决方法，如果页面包含 jQuery 并在全局窗口对象中显示，则 target.js 可以使用传递 customCode 操作。确保已定义 window.jQuery 和 window.jQuery.fn.prepend。

**仅在创建体验的页面或重定向页面上支持点击跟踪。**

虽然在点击跟踪 VEC 中提供浏览模式，但不能使用该模式在页面上添加点击跟踪。
