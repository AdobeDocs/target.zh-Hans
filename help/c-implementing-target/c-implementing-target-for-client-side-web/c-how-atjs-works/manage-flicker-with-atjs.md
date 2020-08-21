---
keywords: flicker;at.js;implementation;asynchronously;asynchronous;synchronously;synchronous
description: 有关 Adobe Target at.js JavaScript 库如何在页面或应用程序加载期间阻止闪烁的信息。
title: Adobe Target at.js 如何管理闪烁
feature: client-side
topic: Standard
uuid: 65f67c4a-a931-4e0d-80d9-29ab67b62573
translation-type: tm+mt
source-git-commit: 8d0faeb83e7fe854dcf99c89081fb656cf16c4c0
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 80%

---


# at.js 如何管理闪烁{#how-at-js-manages-flicker}

有关 Target at.js JavaScript 库如何在页面或应用程序加载期间阻止闪烁的信息。

在默认内容被替换为活动内容之前，系统会暂时向访客显示默认内容，在此期间会发生闪烁。闪烁可能会使访客感到困惑，因此是一种不良体验。

## 使用自动创建的全局mbox {#section_C502170D551C4F52AAFD8E82C41BB63A}

如果启用[自动创建全局 Mbox](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/understanding-global-mbox.md#concept_76AC0EC995A048238F3220F53773DB13) 设置，at.js 会在页面加载时通过更改不透明度设置来管理闪烁。加载 at.js 时，它会将 <body> 元素的不透明度设置更改为“0”，从而使访客在最初时看不到该页面。收到来自 Target 的响应后，或者如果检测到 Target 请求出错，at.js 会将不透明度重置为“1”。这可确保访客只有在应用您的活动内容后才会看到该页面。

在配置 at.js 时，如果您启用该设置，at.js 会将 HTML 主体样式的不透明度设置为 0。收到来自 Target 的响应后，at.js 会将 HTML 主体的不透明度重置为 1。

通过将不透明度设置为 0，可保持页面内容处于隐藏状态以防止闪烁，但浏览器仍会渲染页面并加载所有必需的资产，如 CSS、图像等。

如果在您的实施中将不透明度设置为 0 不起作用，您还可以通过自定义 `bodyHiddenStyle` 并将其设置为 `body {visibility:hidden !important}` 来管理闪烁。You can use either value body `{opacity:0 !important}` or `body {visibility:hidden !important}`, whichever works best for your specific circumstance.

下图显示了 at.js 1.*x* 和 at.js 2.x 中的“隐藏主体”和“显示主体”调用。

**at.js 2.x**

![Target 流程：at.js 页面加载请求](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-flow-page-load-request.png)

**at.js 1.*x***

![](assets/target-flow2.png)

有关 `bodyHiddenStyle` 覆盖的更多信息，请参阅 [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)。

## 异步加载 at.js 时管理闪烁

异步加载 at.js 有利于避免阻止浏览器渲染；但是，此技术可能会导致网页闪烁。

您可以通过使用预先隐藏的代码片段来避免闪烁，在 [!DNL Target] 对相关 HTML 元素进行个性化后，系统会显示这些代码片段。

at.js可以异步加载，直接嵌入到页面中或通过标签管理器(Adobe启动、动态标签管理器(DTM)等)。

如果at.js嵌入到页面中，则必须在加载at.js之前添加片段。 如果通过标记管理器加载at.js，则在加载标记管理器之前必须添加片段。 如果标记管理器同步加载，则脚本可能会包含在标记管理器中at.js之前。

预先隐藏的代码片段如下所示：

```
;(function(win, doc, style, timeout) {
  var STYLE_ID = 'at-body-style';

  function getParent() {
    return doc.getElementsByTagName('head')[0];
  }

  function addStyle(parent, id, def) {
    if (!parent) {
      return;
    }

    var style = doc.createElement('style');
    style.id = id;
    style.innerHTML = def;
    parent.appendChild(style);
  }

  function removeStyle(parent, id) {
    if (!parent) {
      return;
    }

    var style = doc.getElementById(id);

    if (!style) {
      return;
    }

    parent.removeChild(style);
  }

  addStyle(getParent(), STYLE_ID, style);
  setTimeout(function() {
    removeStyle(getParent(), STYLE_ID);
  }, timeout);
}(window, document, "body {opacity: 0 !important}", 3000));
```

默认情况下，该代码片段会预先隐藏整个 HTML 主体。在某些情况下，您可能只想预先隐藏某些 HTML 元素，而不是整个页面。您可以通过自定义样式参数来实现这一点。可以将该参数替换为仅预先隐藏页面特定区域的内容。

例如，您有两个分别采用 ID container-1 和 container-2 进行标识的区域，则可以将样式替换为以下内容：

```
#container-1, #container-2 {opacity: 0 !important}
```

而不是默认内容：

```
body {opacity: 0 !important}
```

## 管理at.js 2.x中的flickerView()

当使用 `triggerView()` 在 SPA 中显示目标内容时，开箱即用地提供闪烁管理。这意味着无需手动添加预先隐藏逻辑。相反，at.js 2.x 会在应用目标内容之前预先隐藏需要显示视图的位置。

## 使用getOffer()和applyOffer()管理闪烁

因为 `getOffer()` 和 `applyOffer()` 都是较低级别的 API，因此没有内置的闪烁控制。您可以将某个选择器或 HTML 元素作为一个选项传递到 `applyOffer()`，在此示例中，`applyOffer()` 会将活动内容添加到此特定元素；但是在调用 `getOffer()` 和 `applyOffer()` 之前，您必须确保已相应地预先隐藏该元素。

```
document.documentElement.style.opacity = "0";
 
adobe.target.getOffer({
    mbox: 'target-global-mbox',
    success: function(offer) {
        adobe.target.applyOffer({
            mbox: 'target-global-mbox',
            offer: offer
        });
 
        document.documentElement.style.opacity = "1";
    },
    error: function() {
        document.documentElement.style.opacity = "1";        
    }
});
```

## 在at.js 1.x（at.js 2.x中不支持）中使用带mboxCreate()的区域mbox

如果您使用区域 mbox 实施，则可以在配置以下类似示例代码的页面中使用 `mboxCreate()`：

```
<div class="mboxDefault">
Some default content
</div>
<script>
mboxCreate('some-mbox');
</script>
```

如果您的页面进行了正确配置，at.js 将会使用 mboxDefault 类相应转换元素的 CSS“可见性”属性，从而管理闪烁。