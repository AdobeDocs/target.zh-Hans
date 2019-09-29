---
description: '有关 at.js 的 adobe.target.applyOffers() 函数的信息。 '
keywords: adobe.target.applyOffers;applyOffers;applyoffers;apply offers;at.js;functions;function
seo-description: 有关 Adobe Target at.js JavaScript 库的 adobe.target.applyOffers(options) 函数的信息。
seo-title: 有关 Adobe Target at.js JavaScript 库的 adobe.target.applyOffers(options) 函数的信息。
solution: Target
subtopic: 入门指南
title: adobe.target.applyOffers(options)
topic: Standard
translation-type: tm+mt
source-git-commit: ef2c4ac78fef5889d5a6e9e053dfd36b77919dd4

---


# adobe.target.applyOffers(options) - at.js 2.x

此函数允许您应用 `adobe.target.getOffers()` 检索到的多个选件。

>[!NOTE]
>
>此函数已在 at.js 2.x 中引入。但此函数不适用于 at.js 版本 1.*x*。

| 键值 | 类型 | 必需？ | 描述 |
| --- | --- | --- | --- |
| selector | 字符串 | 否 | HTML 元素或 CSS 选择器，用于标识 [!DNL Target] 应将选件内容放置在其中的 HTML 元素。如果未提供选择器，则 [!DNL Target] 会假定我们应使用的 HTML 元素是 HTML HEAD。 |
| 响应 | 对象 | 是 | 来自 `getOffers()` 的响应对象。<br>请参阅下文的“请求”表。 |

## 响应

| 字段名称 | 描述 |
| --- | --- |
| response &gt; prefetch &gt; views &gt; options &gt; content | 请注意，“options”内容的定义不明确，将直接取决于选项类型/模板结构。 |
| response &gt; prefetch &gt; views &gt; options &gt; type | 选项类型。反映“content”字段的类型。受支持的类型是“action”。 |
| response &gt; prefetch &gt; views &gt; state | 应该与视图的显示通知一起转发的不透明视图状态令牌 |
| response &gt; prefetch &gt; views &gt; options &gt; responseTokens | 包含在处理当前选项时收集的 `responseTokens` 映射。 |
| response &gt; prefetch &gt; views &gt; analytics &gt; payload | 用于客户端集成的 Analytics 有效负荷，应在应用视图后将其发送到 Analytics。 |
| response &gt; prefetch &gt; views &gt; trace | 包含每个视图预取调用的所有跟踪数据的对象。<br>跟踪对象还将包含跟踪的版本。<br>跟踪对象还将包含当前视图的详细信息。 |
| response &gt; prefetch &gt; views &gt; options &gt; eventToken | 按选项完成事件日志记录。对于已应用的选项，应将相应的事件令牌添加到通知令牌列表。请注意，一个视图由多个选项组成。如果已应用并可看到所有选项，则需要将所有 `eventTokens` 包含在通知中。 |
| response &gt; prefetch &gt; views &gt; name | 可读的视图名称。 |
| response &gt; prefetch &gt; views &gt; metrics | 应监视并通知 [!DNL Target] 的报告量度。目前，仅支持点击量度。如果发生点击该元素的情况，则应收集相应的 `eventTokens` 并发送通知。 |
| response &gt; prefetch &gt; views &gt; key | 可标识视图的键值或指纹。 |
| response &gt; prefetch &gt; views &gt; id | 视图的 ID。 |
| response &gt; notifications &gt; id | 通知 ID。 |
| response &gt; notifications &gt; events &gt; type | 通知、点击或显示的类型。 |
| response &gt; notifications &gt; events &gt; trace | 针对通知事件的跟踪。 |
| response &gt; notifications &gt; events &gt; token | 与通知事件一起发送的令牌。 |
| response &gt; notifications &gt; events &gt; timestamp | 与通知事件一起发送的时间戳。 |
| response &gt; notifications &gt; events &gt; errorCode | 如果通知失败，则代码将指明失败的原因。 |
| response &gt; notifications &gt; events | 为当前通知记录或未能记录的事件。 |
| response &gt; notifications | 指示已记录或已失败的通知。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt; trace | 包含单个 mbox 请求的所有跟踪数据的对象。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt; responseTokens | 包含针对特定 mbox 请求执行的 `responseTokens` 映射。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt; option &gt; content | 请注意，“options”内容的定义不明确，将直接取决于选项类型/模板结构。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt; option &gt; type | 选项类型。反映“content”字段的类型。支持的类型包括：html、重定向、JSON 和动态。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt; options | 响应选项。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt; metrics &gt; eventToken | 点击事件的令牌。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt; metrics &gt; type | "click" |
| response &gt; execute &gt; mboxes &gt; mbox &gt; metrics | 包含 `clickThrough` 量度列表。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt; mbox | mbox 的名称。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt;index | 表示响应用于请求中具有此索引的 mbox。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt; analytics &gt; payload | 用于客户端集成的 Analytics 有效负荷，应在应用 mbox 后将其发送到 Analytics。（请参阅“启用 A4T 的营销活动”部分。） |
| response &gt; execute &gt; mboxes | 已执行的 mbox 列表。 |
| response &gt; execute &gt; pageLoad &gt; options &gt; content | 请注意，“options”内容的定义不明确，将直接取决于选项类型/模板结构。 |
| response &gt; execute &gt; pageLoad &gt; options &gt; type | 选项类型。反映“content”字段的类型。支持的类型包括：html、重定向、JSON、动态和操作。 |
| response &gt; execute &gt; pageLoad &gt; options | 未按视图进行分组的选项（target-global-mbox + 活动中的选项，这些活动包含未按视图进行分组的视图）。 |
| response &gt; execute &gt; pageLoad &gt; metrics | 未设置为属于特定视图的点击量度。 |
| response &gt; execute &gt; pageLoad &gt; trace | 包含 pageLoad 请求的所有跟踪数据的对象。 |
| response &gt; execute &gt; pageLoad &gt; analytics &gt; payload | 用于客户端集成的 Analytics 有效负荷，应在应用页面加载内容后将其发送到 Analytics。（请参阅“启用 A4T 的营销活动”部分。） |

## applyOffers() 调用示例

```
adobe.target.applyOffers({response:{
  "execute": {
    "pageLoad": {
      "options": [{
        "type": "html",
        "content": "page-load"
      },
      {
        "type": "actions",
        "content": [{
          "type": "setHtml",
          "content": "<h1>Container 1</h1>",
          "selector": "#container1",
          "cssSelector": "#container1"
        },
        {
          "type": "setHtml",
          "content": "<h3>Container 3</h3>",
          "selector": "#container3",
          "cssSelector": "#container3"
        }]
      }],
 
 
      "metrics": [{
        "type": "click",
        "selector": "#container1",
        "eventToken": "page-load-click-metric" 
      }]
    }
  }
}});
```

## 使用 `getOffers()` 和 `applyOffers()` 链接的示例 Promise 调用，因为这些函数基于 Promise

```
adobe.target.getOffers({...})
.then(response => adobe.target.applyOffers({ response: response }))
.then(() => console.log("Success"))
.catch(error => console.log("Error", error));
```
