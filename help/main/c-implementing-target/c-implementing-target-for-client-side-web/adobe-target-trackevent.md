---
keywords: adobe.target.trackEvent;trackEvent;trackevent;跟踪事件;at.js;函数;函数;preventDefault;preventdefault;阻止默认值
description: 使用adobe.target.trackEvent()函数进行Adobe [!DNL Target] at.js JavaScript库来触发报告用户操作（如您网站上的点击和转化）的请求。
title: 如何使用adobe.target.trackEvent()函数？
feature: at.js
role: Developer
exl-id: 36005236-ce18-4845-b4fb-e52056018bc7
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 64%

---

# adobe.target.trackEvent(options)

此函数会触发用户操作（例如点击和转化）报告请求。它不会在响应中交付活动。

这些事件跟踪 mbox 调用可以用来定义活动中的量度。有关更多信息，请参阅 [成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) 和 [跟踪转化](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-without-a-tag-manager/){target=_blank}。

以下是该 API 的详细信息：

| 键值 | 类型 | 必需 | 描述 |
|--- |--- |--- |--- |
| mbox | 字符串 | 是 | Mbox名称&#x200B;<br>**注意**:如果触发的trackEvent()调用的mbox名称已在页面上触发，则trackEvent()的SDID将会重置，并且将与页面上的Target调用不同。 但是，如果触发具有不同mbox名称的trackEvent()调用，则该调用的SDID会与页面上的页面加载请求/triggerView()调用保持一致。 |
| selector | 字符串 | 否 | 用于查找 HTML 元素的 CSS 选择器。事件监听程序将附加到找到的元素。 |
| type | 字符串 | 否 | 表示已注册的事件类型。它既可以是 HTML 已知的事件，如：click、mousedown 等，也可以是自定义 HTML 事件。 |
| preventDefault | 布尔值 | 否 | 表示是否在事件监听程序回调中使用 `event.preventDefault()`。默认为 false。<br>**注意**:仅 `form[submit]` 和 `a[click]` 。 由于复杂性和要支持的方案数量太多，因此其他方案不受支持。 |
| 参数 | 对象 | 否 | Mbox 参数。键值对这一对象具有以下结构：<br>`{ "param1": "value1", "param2": "value2"}` |
| timeout | 数值 | 否 | 以毫秒为单位的超时时间。<br>如果未指定，则使用默认值：<br>`...timeoutInSeconds: 0.15...}` |
| success | 函数 | 否 | 用于表示该事件已报告的回调函数。 |
| error | 函数 | 否 | 用于表示该事件无法报告的回调函数。 |

## 示例

```javascript
<a href="https://asite.com">click me!</a> 
```

加上用于分配 `trackEvent` 的 javaScript 代码：

```javascript
<script> 
$('a').click(function(event){ 
  adobe.target.trackEvent({'mbox':'homePageHero'}) 
}); 
</script> 
```

或：

```javascript
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
