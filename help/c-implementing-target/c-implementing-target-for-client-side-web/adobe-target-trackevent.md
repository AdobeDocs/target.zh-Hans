---
keywords: adobe.target.trackEvent;trackEvent;trackevent;track event;at.js;functions;function;preventDefault;preventdefault;prevent default
description: 有关 Adobe Target at.js JavaScript 库的 adobe.target.trackEvent(options) 函数的信息。
title: 有关 Adobe Target at.js JavaScript 库的 adobe.target.trackEvent(options) 函数的信息。
feature: client-side
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 100%

---


# adobe.target.trackEvent(options)

此函数会触发用户操作（例如点击和转化）报告请求。它不会在响应中交付活动。

这些事件跟踪 mbox 调用可以用来定义活动中的量度。有关更多信息，请参阅[成功量度](../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)和[跟踪转化](../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053)。

以下是该 API 的详细信息：

| 键值 | 类型 | 必需 | 描述 |
|--- |--- |--- |--- |
| mbox | 字符串 | 是 | Mbox 名称 |
| selector | 字符串 | 否 | 用于查找 HTML 元素的 CSS 选择器。事件监听程序将附加到找到的元素。 |
| type | 字符串 | 否 | 表示已注册的事件类型。它既可以是 HTML 已知的事件，如：click、mousedown 等，也可以是自定义 HTML 事件。 |
| preventDefault | 布尔值 | 否 | 表示是否在事件监听程序回调中使用 `event.preventDefault()`。默认为 false。<br>**注意**：仅支持 `form[submit] and `a[click]`。由于复杂性和要支持的方案数量太多，因此其他方案不受支持。 |
| 参数 | 对象 | 否 | Mbox 参数。键值对这一对象具有以下结构：<br>`{ "param1": "value1", "param2": "value2"}` |
| timeout | 数值 | 否 | 以毫秒为单位的超时时间。<br>如果未指定，则使用默认值：<br>`...timeoutInSeconds: 0.15...}` |
| success | 函数 | 否 | 用于表示该事件已报告的回调函数。 |
| error | 函数 | 否 | 用于表示该事件无法报告的回调函数。 |

## 示例

```
<a href="https://asite.com">click me!</a> 
```

加上用于分配 `trackEvent` 的 javaScript 代码：

```
<script> 
$('a').click(function(event){ 
  adobe.target.trackEvent({'mbox':'homePageHero'}) 
}); 
</script> 
```

或：

```
adobe.target.trackEvent({ 
    "mbox": "clicked-cta", 
    "params": { 
        "param1": "value1" 
    } 
});
```

>[!NOTE]
>
>如果未设置必填字段，则不会执行请求，并会引发错误。