---
keywords: 可视化体验编辑器;可视化体验编辑器最佳实践;可视化体验编辑器限制;可视化体验编辑器注意事项;vec 最佳实践;vec
description: 了解最佳实践，以使您的体验在使用[!UICONTROL 可视化体验编辑器] (VEC)时按预期工作。
title: '[!UICONTROL 可视化体验编辑器]的最佳实践和限制是什么？'
feature: Visual Experience Composer (VEC)
exl-id: cf51bfec-d7fa-4ec1-a5dc-35edefefd3e4
TQID: 'https://experienceleague.adobe.com/upZDSyuS9VqUmYskNXrlYazhwRHmZGBpSR-cR-qliRs'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '2420'
ht-degree: 8%
---
# [!UICONTROL 可视化体验编辑器]最佳实践和限制 {#vec-best-practices}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解在&#x200B;**[!UICONTROL 可视化体验编辑器]** (VEC)中创建体验时要注意的最佳实践、警告和限制。

>[!ENDSHADEBOX]

遵循这些实践有助于在[!DNL Adobe Target] **[!UICONTROL 可视化体验编辑器]** (VEC)函数中创建的体验达到预期效果。 警告和限制描述了可能导致常见问题的行为，因此了解这些行为有助于避免问题和保持性能。

## 最佳实践 {#best-practices}

使用VEC时，以下实践适用。

### 启用[!UICONTROL 增强型体验编辑器] {#enable-eec}

可以在帐户级别启用&#x200B;**[!UICONTROL 增强型体验编辑器]**，以便为该帐户中创建的所有活动或单个活动级别启用该编辑器。

* **帐户级别：**&#x200B;单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 可视化体验编辑器]**，然后将&#x200B;**[!UICONTROL 启用增强型体验编辑器]**&#x200B;开关切换到“开启”位置。
* **活动级别：**&#x200B;在&#x200B;**[!UICONTROL 可视化体验编辑器]**&#x200B;中创建活动时，单击&#x200B;**[!UICONTROL 配置]** > **[!UICONTROL 页面交付]**，然后将&#x200B;**[!UICONTROL 启用增强型体验编辑器]**&#x200B;开关切换到“开启”位置。

### 页面设置和加载

+++ 将at.js引用放置在页面`<head>`部分的顶部。

如果还使用了&#x200B;**[!UICONTROL 访客API服务]**，请将访客API脚本放在at.js上方。

+++

+++ 如果[!UICONTROL 增强型体验编辑器]未在网站的安全页面上加载，则允许列表IP地址。

对用于&#x200B;**[!UICONTROL 增强型体验编辑器]**&#x200B;代理的[!DNL Adobe]服务器的IP地址进行列入允许列表可解决加载问题。 仅活动编辑需要这些IP地址。 站点的访客不需要进行列入允许列表。 IP地址在[中列出。在&#x200B;*与增强型体验编辑器*&#x200B;相关的问题疑难解答中，EEC无法加载在公共IP](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md#eec-ip-addresses)上不可访问的内部QA URL。

+++

+++ 请勿在网站中使用基本标记来解析URL和链接。

VEC（包括&#x200B;**[!UICONTROL 增强型体验编辑器]**）通过代理服务器在后台操作网站，该代理服务器会更新所有链接URL以使它们在代理中工作。 如果添加基本标记，则浏览器会再次解析这些URL，使其显示为已损坏。

+++

+++ 请勿在JavaScript代码中使用`top`或`self`变量。

启用&#x200B;**[!UICONTROL 增强型体验编辑器]**&#x200B;后，`top`和`self`变量的值将更新为禁用iframe嵌套。 使用X-Frame-Options标头可添加iframe嵌套而不是自定义JavaScript代码。

+++

+++ 如果在页面加载时添加参数，始终都应测试网站。

例如，以下URL参数用于打开`www.abc.com`以便在iframe中进行编辑：

`www.abc.com?mboxEdit=1&mboxDisable=1`

在添加此类参数后，请确保网站按预期加载。

+++

+++ 确保页面在iframe中按预期一样正常打开。

关闭网站上的iframe嵌套技术，并检查网站是否按预期在虚拟页面上的iframe中打开。 例如：

```html
<!DOCTYPE html>
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

### 页面标记

+++ 对于最上层元素，以及其他任何测试或定位较好候选者的元素，为其使用唯一ID。

紧接在body元素内的任何内容都应具有唯一的ID，以便至少父元素易于识别何时将新元素注入主体以及代码何时移动。

[!DNL Target]不需要ID，但ID会提高使用体验编辑器创建的体验的可靠性。 [!DNL Target]在交付体验时使用CSS选择器修改内容。 编辑体验时，**[!UICONTROL 可视化体验编辑器]**&#x200B;会将选择器锚定到具有非空ID属性的已修改HTML元素的最近祖先。 因此，建议不要使用任何用于设置或修改HTML ID属性的机制，包括JavaScript库。 这些ID在创建活动时可能可供体验编辑器使用，但如果JavaScript修改它们，则当体验运行时，创建时使用的ID可能不可用。 如果某个ID不可用，则锚定到该ID的选择器将失败。

+++

+++ 使用描述性CSS类名。

在&#x200B;**[!UICONTROL 可视化体验编辑器]**&#x200B;中编辑CSS类时，使用描述性类名可以轻松识别类。 这有助于确保编辑正确的CSS类并且页面按预期显示。

+++

+++ 隐藏或删除元素时，请勿使用`!important` CSS属性。

如果`!important` CSS属性存在，则网站的CSS规则将覆盖`target.js`在交付期间所做的更改。

+++

+++ 避免使用HTML表格进行页面布局。

[!DNL Target]使用JavaScript设置页面格式，而基于表的布局很难通过JavaScript进行修改。 基于表的布局在所有浏览器中的显示方式可能也不相同。 为获得最佳效果，请使用 CSS 创建页面布局。

+++

+++ 最大限度地减少 iFrame 的使用。

最小化iFrame可简化页面和测试管理。 **[!UICONTROL 可视化体验编辑器]**&#x200B;可以在iFrame中应用某些操作，但某些操作（如调整大小）无法正常工作。 使用多个iFrame的页面难以管理和调整大小，因此测试大量使用iFrame的页面可能会产生问题。

+++

+++ 在锚点元素中仅使用纯文本或图像标记。

锚点元素包含纯文本：

`<a>Anchor Text</a>`

或图像标记：

`<a href=""> <img src=""> </img> </a>`

+++

+++ 避免在内联元素中使用块级元素。

块级元素不应在内联元素中使用，例如锚点和跨度元素。 这样做会导致内联元素失去其高度和宽度，因此&#x200B;**[!UICONTROL 可视化体验编辑器]**&#x200B;中的叠加工具可能无法按预期工作。

+++

+++ 删除表单字段时要谨慎。

某些表单字段可能是提交必填字段，因此删除它们可能会影响提交。

+++

+++ 将可能用于在HTML代码中定位的重要文本保留在元素中。

例如，如果代码如下所示，则无法在VEC中定位购物车文本：

```html
<a href="https://www.botanicchoice.com/shop.axd/Cart">
   <img alt="Shopping Cart" src="/images/ico-cart.gif"></img>
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

### 编辑和交付

+++ 在DOM准备就绪后尽快排列所有动态DOM的修改。

如果在`target.js`应用体验之前修改无法应用，则内容交付可能会中断。 只有在目标元素的层次结构中应用 DOM 更改时才会出现此问题。

+++

+++ 使用“编辑HTML”处理DOM结构可能会破坏选择器。

例如，将执行两项操作：

* 一个类被添加到元素1中。
* 编辑元素1的HTML。

每次更改都会在VEC中创建一个新元素。 第二个操作将修改元素1，因此如果删除元素1，第二个操作将没有任何可修改的内容，并且更改不再有效。

同样，如果为某个元素添加了文本和单独的操作，然后又使用不同的文本编辑该元素，则代码编辑器会将这两个操作显示为单独的元素。 编辑操作将创建一个新元素，该元素将修改原始元素并包含已编辑的文本。 如果随后删除了原始元素，则编辑后的文本无法找到要修改的元素并且不显示。 第二个元素会保留在元素列表中，但它对页面没有影响，因为它更改的元素不再存在。

查看&#x200B;**[!UICONTROL 可视化体验编辑器]**](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#vec-selectors)中使用的[元素选择器。

+++

+++ 使用富文本编辑器为文本元素设置样式时，请使用`<b>`和`<i>`标记。

* 对于粗体文本，请使用 `<b>` 而不是 `<strong>`。
* 对于斜体文本，请使用 `<i>` 而不是 `<em>`。

`<strong>`和`<em>`标记可能会导致意外结果。

+++

+++ 请勿在脚本中包含`mboxCreate`。

`mboxCreate`使用`document.write`，因此不建议将其包含在脚本中。 将`mboxDefine`和`mboxUpdate`用于相同目的。

+++

+++ 如果某个HTML代码片段需要JavaScript代码进行初始化，请勿使用[!DNL Target]更新该代码片段。

对滑块和轮播等页面组件执行操作（编辑HTML）时，投放可能显示为已中断。 VEC在JavaScript实例化页面组件后执行操作。 但是，当页面内容交付给访客时，将在实例化组件之前应用操作。 因此，组件的功能在交付时可能会中断，也可能不会中断，具体取决于在页面上定义该组件的脚本。

首次工作的投放测试无法保证投放可继续工作，因为可能存在争用条件：

* 如果存在争用情况，投放会间歇性工作。
* 如果没有竞争条件，则始终可以进行交付。

多次测试页面以确保投放按预期运行。

+++

## 注意事项 {#caveats}

以下注意事项适用于使用&#x200B;**[!UICONTROL 可视化体验编辑器]**&#x200B;设计活动。

+++ [!UICONTROL 移动]功能不支持z-index。

如果没有z-index功能，则被移动的元素不能放在另一个元素的上方。 有关详细信息，请参阅[限制](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721)。

+++

+++ 重新排列元素会影响点击跟踪。

如果重新排列标记为点击跟踪的元素，则重新排列的元素的路径会发生变化。 因此，点击会被跟踪到原始元素重新排列之前所在位置的元素。

出现这种情况的原因是，交付活动内容的代码和跟踪点击的代码包含在交付给页面的一段代码中。 如果浏览到其他页面并在其中设置了点击跟踪，则代码段都会交付到该页面。 如果点击跟踪页面的页面结构与测试运行所在页面的页面结构类似，则测试内容可能也会显示在点击跟踪页面上。

+++

+++ 在作为mbox的`<div>`中可能无法正常插入元素。

如果mbox包含选件并且mbox未正确实施，则插入的元素可能会显示为`insertBefore`，而不是`insertAfter`。

+++

+++ 同时编辑父元素和子元素时，请先编辑父元素。

如果在元素上交换图像操作，然后编辑其父元素的文本或HTML，则可能会出现投放问题。 先编辑父元素，然后再交换子元素上的图像，这才是最佳的工作流程。

+++

+++ 请勿选择包含mbox作为子元素的页面元素。

例如，如果页面包含以下代码：

```html
<div>
  <div class="mboxDefault" >
  </div>
  <script>mboxCreate('myMbox');
</script>
</div>
```

不应在体验中选择外部div，因为页面中硬编码的mbox仍会调用[!DNL Target]并接收响应。 此响应会干扰本是针对较大页面元素的响应。

+++

+++ 客户环境中可能会阻止代理IP地址。

如果在非实时站点（例如暂存环境）上使用&#x200B;**[!UICONTROL 增强型体验编辑器]**，则如果该站点阻止代理IP地址，则可能会发生超时和拒绝访问错误。

+++

## 限制 {#section_F33C2EA27F2E417AA036BC199DD6C721}

以下限制适用于使用VEC。

### 页面要求

+++ 处理与[!DNL Chrome]扩展策略更改的VEC兼容性。

在Google Chrome](https://developer.chrome.com/docs/extensions/develop/migrate/what-is-mv3){target=_blank}中更新的[V3清单策略下，扩展在浏览器分析原始DOM之前无法再对其进行修改。 因此，某些安全脚本（例如iframe-busting实施）可能会阻止页面在VEC中加载。

为确保兼容性，当页面加载到[!DNL Target] iframe中时，有条件地禁用这些脚本。 可以通过检查是否存在`window.adobeVecExtension`对象来安全地完成此操作，该对象在VEC加载时[!DNL Target]注入。

以下代码片段是iframe-busting代码的示例，此类代码可以阻止网页在VEC中加载：

`window.top.location = window.self.location;`

`top.location.href = self.location.href;`

简单检查可验证网页是否嵌入到[!DNL Target]中。 代码片段如下所示：

```
if(!window.adobeVecExtension) {
    // additional security logic
}
```

+++

+++ 页面必须接受URL参数才能使VEC正常工作。

某些网站会从其页面中剥离任何URL参数，但VEC需要这些参数。

+++

+++ 当脚本用作HTML的一部分时，请在窗口命名空间下声明从外部访问的任何变量和函数。

加载页面后，该脚本将在`target.js`的范围内执行，因此从脚本块外部无法访问任何在本地声明的变量或函数。

*错误：*

```html
<script>
  var myVar = 123;
  function myFunc() {
    //
  }
</script>
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

+++ VEC中的`customCode`操作不适用于[!DNL Internet Explorer] 8。

由于IE8在处理脚本内容时存在限制，`target.js`在IE8中不支持此操作。 作为解决方法，如果页面包含jQuery并且jQuery在窗口对象上全局公开，则`target.js`可以传递`customCode`操作。 确保已定义`window.jQuery`和`window.jQuery.fn.prepend`。

+++

### 重新排列和mbox

**无法将元素移动到后接CSS属性的容器之外。**

+++ 无法选择要重新排列的[!UICONTROL Button]元素。

无法直接选择&#x200B;**[!UICONTROL Button]**&#x200B;元素进行重新排列。 要启用重新排列，请将按钮放入较大的容器中。

+++

+++ 请勿重新排列和移动同一元素。

如果某个元素已被移动到其他位置，并且随后选择了父容器来重新排列子元素，则移动的元素不会受到影响，并会保留在原来的位置。 可能不会按预期重新排列。

+++

+++ 只能在 mbox 上执行交换选件操作。

在mbox中不允许执行诸如&#x200B;**[!UICONTROL 编辑类]**&#x200B;和&#x200B;**[!UICONTROL 重新排列]**&#x200B;之类的操作。

+++

### 图像

+++ [!UICONTROL 更改图像]操作不适用于轮播中的图像。

例如，如果页面包含带有六个图像的轮播，并且一个图像要与轮播的第二个图像交换，则&#x200B;**[!UICONTROL 更改图像]**&#x200B;操作不起作用。

作为解决方法，请选择父容器并使用&#x200B;**[!UICONTROL 编辑HTML]**&#x200B;操作来编辑轮盘的HTML并更新所需图像的图像源。

+++

+++ 无法在 mbox 中调整图像大小。

如果在mbox元素中交换图像，然后根据mbox元素的大小调整大小，则不允许调整大小。

+++

+++ 交换图像后，无法选择[!UICONTROL 编辑]操作。

交换图像后，无法编辑Scene7 URL。

+++

+++ 从[!UICONTROL Content]库(Scene7)插入图像并编辑HTML会破坏图像URL。

在`customHeaderMessage` div中添加一个包含一些虚设文本的锚点元素：

```html
<a href="#">
<span> Dummy text </span>
</a>
```

使用&#x200B;**[!UICONTROL Insert Element]**&#x200B;操作Select此div以插入图像作为虚拟文本的同级。

插入图像后，代码将如下所示：

```html
<a href="#">
<span> Dummy text </span>
<img src=""> This is inserted Image. </img>
</a>
```

删除虚拟文本范围。

+++

### 点击跟踪和外部内容

+++ 点击跟踪不适用于包含纯文本或图像标记以外的任何内容的锚点元素。

例如，如果元素包含 JavaScript，则点击跟踪不起作用。

+++

+++ 仅在创建体验的页面或重定向页面上支持点击跟踪。

虽然&#x200B;**[!UICONTROL 浏览]**&#x200B;模式可用于VEC中的点击跟踪，但&#x200B;**[!UICONTROL 浏览]**&#x200B;模式不能用于在页面上添加点击跟踪。

+++

+++ 无法编辑具有外部源的HTML元素。

例如： video、audio标记、embed、iFrame和frame。

+++
