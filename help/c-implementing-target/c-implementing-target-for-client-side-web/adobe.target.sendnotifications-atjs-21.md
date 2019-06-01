---
description: '有关adobe. target. sendNoSear(options)函数的信息，请访问. js。 '
seo-description: 有关Adobe Target at. js JavaScript库的adobe. target. sendNotifeloper(选项)函数的信息。
seo-title: 有关Adobe Target at. js JavaScript库的adobe. target. sendNotifeloper(选项)函数的信息。
solution: Target
subtopic: 入门指南
title: adobe. target. sendNoSearch(选项)
topic: Standard
translation-type: tm+mt
source-git-commit: f3d4963da631c668fb53a3939df53c80adff468b

---


# adobe. target. sendNoSearch(选项)

在呈现体验时，此函数将向Target边缘发送通知，而无需使用 `adobe.target.applyOffer()` 或 `adobe.target.applyOffers()`。

>[!NOTE]
>
>此函数已在. js2.1.0中引入，可用于2.1.0以上的任何版本。

| 键值 | 类型 | 必需？ | 描述 |
| --- | --- | --- | --- |
| consumerId | 字符串 | 否 | 如果未提供，则默认值为客户端的全局 mbox。可使用此键值生成用于 A4T 集成的补充数据 ID。 |
| 请求 | 对象 | 是 | 请参阅下文的“请求”表。 |
| timeout | 数值 | 否 | 请求超时. 如果未指定，将使用默认的 at.js 超时值。 |

## 请求

| 字段名称 | 类型 | 必需？ | 限制 | 描述 |
| --- | --- | --- | --- | --- |
| “请求”&gt;通知 | 对象数组 | 是 |  | 显示内容、被单击的选择器和/或访问的视图或mbox的通知。 |
| “请求”&gt;“通知”&gt;地址 | 对象 | 否 |  |  |
| “请求”&gt;“通知”&gt;“地址”&gt; url | 字符串 | 否 |  | 触发通知的URL。 |
| “请求”&gt;“通知”&gt;“地址”&gt;“引用URL” | 字符串 | 否 |  | 从中触发通知的引用URL。 |
| “请求”&gt;“通知”&gt;参数 | 对象 | 否 | 参数不允许使用以下名称：<ul><li>orderId</li><li>orderTotal</li><li>productPurchaseDS</li></ul>请考虑以下事项：<ul><li>max50参数限制。</li><li>参数名称不应为空。</li><li>参数名称max englength128。</li><li>参数名称不应以“profile”开头。</li><li>参数值长度max5000。</li></ul> |  |
| “请求”&gt;“通知”&gt;“profileParameters” | 对象 | 否 | 参数不允许使用以下名称：<ul><li>orderId</li><li>orderTotal</li><li>productPurchaseDS</li></ul>请考虑以下事项：<ul><li>max50参数限制。</li><li>参数名称不应为空。</li><li>参数名称max englength128。</li><li>参数名称不应以“profile”开头。</li><li>参数值长度max5000。</li></ul> |  |
| 请求&gt;通知&gt;订单 | 对象 | 否 |  | 描述顺序详细信息的对象。 |
| “请求”&gt;“通知”&gt;“顺序”&gt; id | 字符串 | 否 | `<=` 250 个字符. | 订单 ID. |
| “请求”&gt;“通知”&gt;“顺序”&gt;“总计” | 字符串 | 否 | `>=` 0 | 订单总计. |
| “请求”&gt;“通知”&gt;“订单”&gt;“购买产品” | String数组 | 否 | <ul><li>不允许使用空值。</li><li>每个产品ID max length50。</li><li>以逗号和连接方式分隔的产品ID不应超过250。</li></ul> | 订购产品ID。 |
| 请求&gt;通知&gt;产品 | 对象 | 否 |  |  |
| “请求”&gt;“通知”&gt;“产品”&gt; id | 字符串 | 否 | `<=` 128个字符；不能为空。 | 产品 ID. |
| “请求”&gt;“通知”&gt;“产品”&gt;“类别ID” | 字符串 | 否 | `<=` 128个字符；不能为空。 | 类别ID。 |
| “请求”&gt;“通知”&gt; id | 字符串 | 是 | `<=` 200个字符。 | 通知ID将返回响应并指示通知已成功处理。 |
| “请求”&gt;“通知”&gt;“impressionID” | 字符串 | 否 | `<= 128` 个字符. | 印象ID用于将当前通知与先前通知或执行请求拼接(链接)。如果两者都匹配，则第二个和后续后续请求不会给活动或体验带来新的印象。 |
| “请求”&gt;“通知”&gt;“类型” | 字符串 | 是 | 支持“单击”或“显示”。 | 通知类型。 |
| “请求”&gt;“通知”&gt;“时间戳” | 数值`<int64>` | 是 |  | 从UNIX环境中经过的通知时间戳(以毫秒为单位)。 |
| “请求”&gt;“通知”&gt;“令牌” | String数组 | 是 |  | 根据通知类型显示的内容或被单击的选择器的令牌列表。 |
| “请求”&gt;“通知”&gt;“mbox” | 对象 | 否 |  | mbox的通知。 |
| “请求”&gt;“通知”&gt;“mbox”&gt; name | 字符串 | 否 | 不允许使用空值。<br>允许的字符：请参阅此表后面的备注。 | mbox 名称. |
| “请求”&gt;“通知”&gt;“mbox”&gt;“状态” | 字符串 | 否 |  | mbox状态令牌。 |
| “请求”&gt;“通知”&gt;“视图” | 对象 | 否 |  |  |
| “请求”&gt;“通知”&gt;“视图”&gt; id | 整数 `<int64>` | 否 |  | 查看id。通过视图API创建视图时分配给视图的id。 |
| “请求”&gt;“通知”&gt;“视图”&gt;“名称” | 字符串 | 否 | `<= 128` 个字符. | 视图的名称。 |
| “请求”&gt;“通知”&gt;“视图”&gt;“密钥” | 字符串 | 否 | `<=` 512个字符。 | 查看键。通过API在视图中设置的键。 |
| “请求”&gt;“通知”&gt;“视图”&gt;“状态” | 字符串 | 否 |  | 查看状态令牌。 |

**注意**：允许以下字符 `Request > notifications > mbox > name`：

```
- '-, ./=`:;&!@#$%^&*()+|?~[]{}'
```

## 渲染预访存mbox后的sendNoSoft()调用

```
function createTokens(options) {
  return options.map(e => e.eventToken);
}

function createNotification(mbox, type, tokens) {
  const id = 11111; // here we should use a random ID like UUID
  const timestamp = Date.now();
  const { name, state, parameters, profileParameters, order, product } = mbox;
  const result = {
    id,
    type,
    timestamp,
    parameters,
    profileParameters,
    order,
    product
  };

  result.mbox = { name, state };
  result.tokens = tokens;

  return result;
}

adobe.target.getOffers({
  request: {
    prefetch: {
      mboxes: [
        {
          index: 0,
          name: "a1-serverside-ab"
        }
      ]
    }
  }
})
.then(response => {
  const mboxes = response.prefetch.mboxes;
  const notifications = mboxes.map(mbox => {
    const type = "display";
    const tokens = createTokens(mbox.options);

    return createNotification(mbox, type, tokens);
  });
  
  adobe.target.sendNotifications({
    request: { notifications }
  });
})
```

>[!NOTE]
>
>如果您使用的是Adobe Analytics， `getOffers()` 并且只能预购， `sendNotifications()`则必须在执行后触发Analytics `sendNotifications()` 请求。旨在确保生成的SSID符合发送 `sendNotifications()` 到Analytics和Target的SSID。