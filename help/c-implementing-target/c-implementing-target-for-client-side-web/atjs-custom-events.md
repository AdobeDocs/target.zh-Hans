---
keywords: custom events;at.js;request failed;request succeeded;content rendering failed;content rendering succeeded;library loaded;request start;content rendering start;content rendering no offers;content rendering rediret
description: 有关 Adobe Target at.js JavaScript 库自定义事件的信息。
title: 有关 Adobe Target at.js JavaScript 库自定义事件的信息。
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: 65a4fd0d05ad065c9291a83dc0b3066451f7373e

---


# at.js 自定义事件

有关 `at.js custom events` 的信息，可让您知道 mbox 请求或选件何时失败或成功。

一直以来，mbox.js 并不允许在页面上运行的其他 JavaScript 代码了解后台的情况。随着 at.js 的进步，我们有一个难得的机会来解决此问题。

根据客户的反映，他们想要在几种情况出现时得到通知，包括：

* 由于超时、状态码错误、JSON 解析错误等原因，mbox 请求失败。
* 某个 mbox 请求成功。
* 由于封装 mbox 元素缺失、无法找到选择器等原因，导致选件渲染失败。
* 选件渲染成功。已应用 DOM 更改。

预定义事件具有一个结构，允许您根据事件类型提取所需的数据。

为了确保可以在不同方案中使用事件，自定义事件具有一个有效负荷对象，该对象被分配给事件对象的详细属性（传递给处理程序）。另外，为了避免将字符串作为事件名称传递，系统会使用 `adobe.target.event` 命名空间将这些事件作为常量显示。

## 结构 {#section_0E5C9A13DE234A5DAECBCBF9F23F94FE}

| 键值 | 类型 | 描述 |
|--- |--- |--- |
| type | 字符串 | 在有些情况下，您希望了解如何跟踪、调试和自定义与 at.js 的交互。<br>下面列出的每个自定义事件都有两种格式：“常量”和“字符串值”。<ul><li>**常量**：前面预置 `adobe.target.event.`，全部大写，并包含下划线字符。要在加载 at.js *之后*、收到 mbox 响应&#x200B;*之前*&#x200B;订阅自定义事件，请使用常量。</li><li>**字符串值**：小写并包含破折号。要在加载 at.js *之前*&#x200B;订阅自定义事件，请使用字符串值。</li></ul>**请求失败&#x200B;**<br>Constant:`adobe.target.event.REQUEST_FAILED`<br>String value:`at-request-failed`<br>Description: An mbox request failed due to timeout, wrong status code, JSON parse error, etc.<br>**请求成功**<br>常量：`adobe.target.event.REQUEST_SUCCEEDED`<br>字符串值：`at-request-succeeded`<br>描述：mbox 请求成功。<br>**内容渲染失败&#x200B;**<br>常量：`adobe.target.event.CONTENT_RENDERING_FAILED`<br>字符串值：`at-content-rendering-failed`<br>描述：由于封装 mbox 元素缺失、无法找到选择器等原因，选件渲染失败。<br>**内容渲染成功**<br>常量：`adobe.target.event.CONTENT_RENDERING_SUCCEEDED`<br>字符串值：`at-content-rendering-succeeded`<br>描述：选件渲染已成功。已应用 DOM 更改。<br>**已加载库&#x200B;**<br>常量：`adobe.target.event.LIBRARY_LOADED`<br>字符串值：`at-library-loaded`<br>描述：此事件非常适用于跟踪 at.js 完全加载的时间。您可以使用此事件来自定义全局 mbox 执行。您也可以使用此事件来禁用全局 mbox，然后侦听此事件以便稍后再触发全局 mbox。<br>**请求启动**<br>常量：`adobe.target.event.REQUEST_START`<br>字符串值：`at-request-start`<br>描述：此事件在执行 HTTP 请求之前触发。您可以使用此事件进行使用 Resource Timing API 的性能测量。<br>**内容渲染启动&#x200B;**<br>常量：`adobe.target.event.CONTENT_RENDERING_START`<br>字符串值：`at-content-rendering-start`<br>描述：此事件在启动选择器轮询并将内容渲染到页面之前触发。您可以使用此事件来跟踪内容渲染进度。<br>**内容渲染（无选件）**<br>常量：`adobe.target.event.CONTENT_RENDERING_NO_OFFERS`<br>字符串值：`at-content-rendering-no-offers`<br>描述：此事件在未返回选件时触发。<br>**内容渲染重定向&#x200B;**<br>常量：`adobe.target.event.CONTENT_RENDERING_REDIRECT`<br>字符串值：`at-content-rendering-redirect`<br>描述：此事件在选件是重定向选件并且 Target 将重定向到其他 URL 时触发。 |
| mbox | 字符串 | mbox 名称 |
| message | 字符串 | 包含通俗易懂的描述，例如出现什么错误、错误消息等。 |
| tracking | 对象 | 包含 `sessionId` 和 `deviceId`。在某些情况下，`deviceId` 可能缺失，因为 [!DNL Target] 无法从边缘服务器检索到它。 |

## 使用情况 {#section_0500FF09D3A04450B5DC8F85C6F793E0}

```
document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(event) { 
  console.log('Event', event); 
});
```

## 培训视频：响应令牌和 at.js 自定义事件{#section_ED304A7137DC42A4BDCD6D57C989F1FA} 教 ![程徽章](/help/assets/tutorial.png)

观看以下视频，了解如何使用响应令牌和 at.js 自定义事件将 Target 中的配置文件信息共享到第三方系统。

>[!VIDEO](https://video.tv.adobe.com/v/23253/)