---
keywords: 可视化体验编辑器;可视化体验编辑器最佳实践;可视化体验编辑器限制;可视化体验编辑器注意事项;vec 最佳实践;vec
description: 了解最佳实践，以使您的体验在使用[!UICONTROL Visual Experience Composer] (VEC)时按预期工作。
title: '[!UICONTROL Visual Experience Composer]最佳实践和限制是什么？'
feature: Visual Experience Composer (VEC)
exl-id: cf51bfec-d7fa-4ec1-a5dc-35edefefd3e4
source-git-commit: d7ca0867314808f4d38c0de0b8c1e1f0cbf70cc0
workflow-type: tm+mt
source-wordcount: '2434'
ht-degree: 38%

---

# [!UICONTROL Visual Experience Composer]最佳实践和限制

为确保您的体验按预期运行，请在使用[!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC)时遵循最佳实践。 了解关键提示和限制以最大限度地提高性能并避免常见问题。

## 最佳实践 {#section_86CF28C99CFF40329E4CBAFE4DD78BB4}

以下是使用VEC时的最佳实践：

### 将at.js引用放置在页面`<head>`部分的顶部。

+++查看详细信息
如果您还使用[!UICONTROL Visitor API Service]，请将访客API脚本放置在at.js上方。

+++

### 您可以在帐户级别（为该帐户中创建的所有活动启用）或单个活动级别启用[!UICONTROL Enhanced Experience Composer]。

+++查看详细信息
要在帐户级别启用[!UICONTROL Enhanced Experience Composer]，请单击[!UICONTROL [!UICONTROL Administration] > [!UICONTROL Visual Experience Composer]]，然后将[!UICONTROL Enable Enhanced Experience Composer]开关切换到“开启”位置。

在[!UICONTROL Visual Experience Composer]中创建活动时，要在活动级别启用[!UICONTROL Enhanced Experience Composer]，请单击[!UICONTROL Configure > [!UICONTROL Page Delivery]]，然后将[!UICONTROL Enable Enhanced Experience Composer]开关切换到“开启”位置。

+++

### 如果[!UICONTROL Enhanced Experience Composer]无法在您的站点上的安全页面上加载，您可以允许列表某些IP地址。

+++查看详细信息
加载[!UICONTROL Enhanced Experience Composer]的问题可以通过列入允许列表以下IP地址来解决。 这些IP地址用于用于[!UICONTROL Enhanced Experience Composer]代理的[!DNL Adobe]服务器。 仅在编辑活动时才需要这些地址。您网站的访客不需要列入允许列表这些IP地址。

有关详细信息，请参阅&#x200B;*与增强型体验编辑器相关的问题疑难解答*&#x200B;中的[EEC无法加载在公共IP](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md)上不可访问的内部QA URL。

+++

### 对于最上层元素，以及其他任何可能是测试/定位较好候选者的元素，为其使用唯一 ID。

+++详细信息
正文元素内的任何内容都应具有唯一ID。 如果有新元素注入到主体中且移动了周围的代码，那么这样做至少有助于识别父元素。

[!DNL Target]不需要ID，但使用ID会提高通过体验编辑器创建的体验的可靠性。 在交付体验时，[!DNL Target]使用CSS选择器修改您的内容。 在编辑体验时，[!UICONTROL Visual Experience Composer]会将选择器定位到要修改的HTML元素的最近祖先（具有非null ID属性）。 因此，不建议使用任何机制（包括 JavaScript 库）来设置或修改 HTML ID 属性。尽管这些ID可能可供[!DNL Target]体验编辑器用于创建活动，但如果JavaScript修改ID，则创建体验时使用的ID在体验运行时可能不可用。 如果 ID 不可用，则定位到该 ID 的选择器将会失败。

+++

### 为 CSS 类命名，以便它们易于识别。

+++详细信息
在[!DNL Visual Experience Composer]中编辑CSS类时，使用描述性类名使类易于识别很有用。 这有助于确保您编辑的是正确的 CSS 类，并且您的页面会按预期显示。

隐藏或删除元素时，请勿使用 `!important` CSS 属性。

如果`!important` CSS属性存在，则`target.js`在交付期间所做的更改将会被站点的CSS规则覆盖。

+++

### 避免使用 HTML 表格进行页面布局。

+++详细信息
[!DNL Target]使用JavaScript设置页面格式。 使用 JavaScript 修改基于表格的布局比较困难。此外，基于表格的布局在不同浏览器中可能会以不同的方式显示。为获得最佳效果，请使用 CSS 创建页面布局。

+++

### 最大限度地减少 iFrame 的使用。

+++详细信息
最大限度地减少iFrame的使用，简化页面和测试管理，是一个不错的做法。 可视化体验编辑器可以在iFrame中应用某些操作，但某些操作（如调整大小）无法正常工作。 管理使用多个 iFrame 的页面以及调整这些页面的大小比较困难。因此，测试使用多个 iFrame 的页面可能会产生问题。

+++

### 在 DOM 准备就绪后尽快安排所有动态 DOM 的修改。

+++详细信息
如果您的修改未能在`target.js`进行的体验应用程序之前应用，则内容交付可能会中断。 只有在目标元素的层次结构中应用 DOM 更改时才会出现此问题。

+++

### 在锚点元素中仅使用纯文本或图像标记。

+++详细信息
`<a>Anchor Text</a>`

或

`<a href=""> <img src=""> </img> </a>`

+++

### 避免在内联元素中使用块级元素。

+++详细信息
块级元素不应在内联元素中使用，例如锚点、跨距等。 这样做会导致内联元素失去其高度和宽度，因此[!UICONTROL Visual Experience Composer]中的叠加工具可能无法按预期工作。

+++

### 请勿在您的网站中使用基本标记来解析 URL 和链接。

+++详细信息
VEC使用更新链接的代理服务器在后台操作网站。 如果添加基本标记，则浏览器会再次解析代理服务器使用的 URL，这样 URL 会显示为已损坏。

+++

### 使用“编辑 HTML”处理 DOM 结构可能会破坏选择器。

+++详细信息
例如，如果您已经执行了以下两项操作：

* 将一个类添加到 Element 1
* 为 Element 1 编辑 HTML

每次更改都会在VEC中创建一个新元素。 因为第 2 个操作修改了 Element 1，如果删除 Element 1，则第 2 个操作将没有任何可修改的内容，因此更改不再有效。

换言之，如果您添加一个带有文本的元素，然后在单独的操作中使用不同的文本对该元素进行编辑，则代码编辑器会将两种操作当做单独的元素显示。在编辑元素时，您创建了一个新元素，该元素修改了之前创建的原始元素，在其中包含已编辑的文本。如果删除了原始元素，则编辑后的文本将无法找到被编辑的元素，而且也不会显示出来。第二个元素会保留在元素列表中，但不会对页面产生影响，因为它所更改的元素不再存在。

查看[!UICONTROL Visual Experience Composer][&#128279;](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337)中使用的元素选择器。

+++

### 使用富文本编辑器为文本元素设置样式时，请使用`<b>`和`<i>`标记。

+++详细信息
* 对于粗体文本，请使用 `<b>` 而不是 `<strong>`。
* 对于斜体文本，请使用 `<i>` 而不是 `<em>`。

使用 `<strong>` 和 `<em>` 标记可能会导致意外结果。

+++

### 删除表单字段时要谨慎。

+++详细信息
某些表单字段可能是提交所必需的。 删除这些表单字段可能会影响提交。

+++

### 请勿在脚本中包含`mboxCreate`。

+++详细信息
由于`mboxCreate`使用`document.write`，因此不建议在脚本中包含`mboxCreate`。 请改为使用 `mboxDefine` 和 `mboxUpdate` 来达到相同目的。

+++

### 如果需要HTML代码进行初始化，则不要使用[!DNL Target]更新JavaScript代码段。


+++详细信息
对页面组件（例如，滑块、轮播等）执行操作(编辑HTML)时，投放可能会显示为已中断。 VEC会在JavaScript实例化页面组件后执行操作。

但是，当页面内容交付给访客时，会在组件实例化之前应用该操作。因此，此组件的功能可能会也可能不会中断交付操作。功能取决于其页面上用于定义组件的脚本的性质。

如果您对交付进行了测试，且在第一次可以正常交付，您仍无法保证它会继续正常工作。因为可能会（或可能不会）存在争用条件。

* 如果存在争用情况，投放会间歇性工作。
* 如果没有竞争条件，则始终可以进行交付。

多次测试您的页面，以确保可以按预期正常预期。

+++

### 请勿在您的网站中使用基本标记来解析 URL 和链接。

+++详细信息
当您使用[!UICONTROL Enhanced Experience Composer]时，网站在幕后被代理服务器操控，该代理服务器会更新所有链接URL以使它们在代理中工作。 如果添加基本标记，则所有这些URL都将由浏览器解析，因此看起来已损坏。

+++

### 网站上可能用于定位的重要文本应保存在元素内的 HTML 代码中。

+++详细信息
例如，如果您的代码如下所示，则无法在VEC中定位购物车文本：

```html
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

在此示例中，在VEC中选择了整个锚点元素，如果执行了定位，则会对其他元素产生不利影响。

+++

### 请勿在JavaScript代码中使用`top`或`self`变量。

+++详细信息
启用[!UICONTROL Enhanced Experience Composer]后，将更新top和self变量的值以禁用iframe嵌套。 使用 X-frame-options 标头可添加 iframe 嵌套而不是自定义 JavaScript 代码。

+++

### 如果在加载页面时添加参数，始终都应测试您的网站。

+++详细信息
例如，为了打开`www.abc.com`，使用了以下URL参数：

`www.abc.com?mboxEdit=1&mboxDisable=1`

这些参数允许您在 iframe 中进行编辑。

添加这些参数后，请确保您的网站会按预期加载。

+++

### 确保您的页面可在 iframe 中按预期一样正常打开。

+++详细信息
关闭网站上的iframe嵌套技术，并检查网站是否按预期在虚拟页面上的iframe中打开。 例如：

```html
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

+++

## 注意事项 {#section_A0436B7B85BA467FA9DE13A9A40E6A6E}

使用[!UICONTROL Visual Experience Composer]设计活动时，请考虑以下注意事项。

### [!UICONTROL Move]功能不支持z-index。

+++详细信息
由于没有z-index功能，因此被移动的元素不能移动到其他元素上方。 有关详细信息，请参阅[限制](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721)。

+++

### 重新排列元素会影响点击跟踪。

+++详细信息
如果重新排列标记为点击跟踪的元素，则重新排列的元素的路径会发生变化。 因此，位于重新排列之前原始元素所在位置的元素是跟踪其点击的元素。

之所以会发生这种情况，是因为交付活动内容的代码和跟踪点击的代码都包含在一段传递到页面的代码中。如果您浏览到其他页面并设置点击跟踪，则活动内容代码和点击跟踪代码都会传递到该页面。如果点击跟踪页面具有与运行测试的页面类似的页面结构，则测试内容也可能会出现在点击跟踪页面上。

+++

### 在作为mbox的`<div>`中可能无法正常插入元素。

+++详细信息
如果mbox包含选件，则如果mbox实施不正确，则插入元素时可能会显示为`insertBefore`，而不是`insertAfter`。

+++

### 既要编辑父元素、也要编辑子元素时，请先编辑父元素。

+++详细信息
如果交换元素上的图像操作，然后编辑其父元素上的文本或HTML，则可能会出现投放问题。 先编辑父元素，然后再交换子元素上的图像，这才是最佳的工作流程。

+++

### 无法选择包含作为子元素的 mbox 的页面元素。

+++详细信息
例如，如果您的页面包含：

```html
<div> 
  <div class="mboxDefault" > 
  </div>
  <script>mboxCreate('myMbox'); 
</div>`
```

不应在体验中选择外部div，因为页面中硬编码的mbox仍会调用[!DNL Target]并收到响应。 此响应会干扰本是针对较大页面元素的响应。

+++

### 客户环境中可能会阻止代理IP。

+++详细信息
如果您在非实时站点（如暂存环境）上使用[!UICONTROL Enhanced Experienced Composer]，如果您的站点阻止RIP，则可能会看到超时和拒绝访问错误。

+++

## 限制 {#section_F33C2EA27F2E417AA036BC199DD6C721}

使用VEC时，请考虑以下限制：

### 正在处理与[!DNL Chrome]扩展策略更改的VEC兼容性。 {#ext}

由于Google Chrome[&#128279;](https://developer.chrome.com/docs/extensions/develop/migrate/what-is-mv3){target=_blank}中更新了V3清单策略，在浏览器分析原始DOM之前，扩展无法再对其进行修改。 因此，某些安全脚本（例如iframe-busting实施）可能会阻止页面在VEC中加载。

为确保兼容性，当页面加载到[!DNL Target] iframe中时，应有条件地禁用这些脚本。 通过检查`window.adobeVecExtension`对象的存在可以安全地完成此过程，该对象在VEC加载期间由[!DNL Target]注入。

以下代码片段是iframe-busting代码的示例，此类代码可能会导致VEC中无法加载网页：

`window.top.location = window.self.location;`

`top.location.href = self.location.href;`

当网页嵌入到[!DNL Target]中时，可以使用简单检查进行验证。 代码片段应如下所示：

```
if(!window.adobeVecExtension) {
    // additional security logic
}
```

+++

### 无法将元素移到后跟CSS属性的容器之外。

+++详细信息
无法将元素移动到后接CSS属性的容器之外。

+++

### 无法选择要重新排列的[!UICONTROL Button]元素。

+++详细信息
无法直接选择[!UICONTROL Button]元素进行重新排列。 要启用重新排列，请将按钮放入较大的容器中。

+++

### 只能在 mbox 上执行交换选件操作。

+++详细信息
不允许在mbox中执行[!UICONTROL Edit Class]和[!UICONTROL Rearrange]等操作。

+++

### 您不应重新排列和移动相同的元素。

+++详细信息
如果某个元素已移动到其他位置，并且您选择父容器并尝试重新排列子元素，则移动的元素不会受到影响，并会保留在原来的位置。 可能不会按预期重新排列。

+++

### [!UICONTROL Change Image]操作不适用于轮播中的图像。

+++详细信息
例如，如果您的页面包含一个带有六个图像的轮播，并且您想要将一个图像与轮播的第二个图像交换，则[!UICONTROL Change Image]操作不起作用。

解决方法是选择父容器并使用[!UICONTROL Edit HTML]操作编辑轮盘的HTML以更新所需图像的图像源。

+++

### 无法在 mbox 中调整图像大小。

+++详细信息
如果在mbox元素中交换图像，然后尝试根据mbox元素大小调整该图像的大小，则调整大小是不允许的。

+++

### 交换图像后，无法选择[!UICONTROL Edit]操作。

+++详细信息
交换图像后，无法编辑Scene7 URL。

+++

### 无法编辑具有外部源的HTML元素。

+++详细信息
例如：视频、音频标记、嵌入、iFrame、帧。

+++

### 点击跟踪不适用于包含纯文本或图像标记以外的任何内容的锚点元素。

+++详细信息
例如，如果元素包含JavaScript，则点击跟踪不起作用。

+++

### 页面必须接受URL参数才能使VEC正常工作。

+++详细信息
某些网站会删除其页面的任何URL参数。 但是，VEC需要这些参数。

+++

### 在HTML中使用脚本时，任何从外部访问的变量和函数都应在窗口命名空间下声明。

+++详细信息
加载页面后，该脚本将在`target.js`的范围内执行。 因此，无法从脚本块外部访问本地声明的任何变量或函数。

*错误：*

```html
<script> 
  var myVar = 123; 
  function myFunc() { 
    // 
  } 
</script>`
```

*正确：*

```html
<script> 
  window.myVar = 123; 
  window.myFunc = function() { 
    // 
  }; 
</script>
```

+++

### 从[!UICONTROL Content]库(Scene7)插入图像并编辑HTML会破坏图像URL。

+++详细信息
在“customHeaderMessage”div中添加一个包含一些伪文本的锚点元素：

```html
<a href="#"> 
<span> Dummy text </span>
</a>
```

使用[!UICONTROL Insert Element]操作选择此div以将图像作为此虚拟文本div的同级插入。

插入图像后，它看起来如下所示：

```html
<a href="#">  
<span> Dummy text </span> 
<img src=""> This is inserted Image. </img> 
</a>
```

删除虚拟文本范围。

+++

### VEC中的`customCode`操作不适用于[!DNL Internet Explorer] 8。

+++详细信息
由于处理脚本内容时IE8存在限制，`target.js`在IE8中不支持此功能。 作为解决方法，如果页面包含jQuery并在全局窗口对象中公开，则`target.js`可以使用传递`customCode`操作。 确保已定义`window.jQuery`和`window.jQuery.fn.prepend`。

+++

### 仅在创建体验的页面或重定向页面上支持点击跟踪。

+++详细信息
尽管[!UICONTROL Browse]模式可用于VEC中的点击跟踪，但[!UICONTROL Browse]模式不能用于在页面上添加点击跟踪。

+++
