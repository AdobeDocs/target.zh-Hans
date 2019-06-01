---
description: '有关adobe. target. getOffers(options)函数的信息，请访问. js。 '
keywords: adobe.target.notification;元素;选择器;通知;扩展
seo-description: 有关Adobe Target. js JavaScript库的adobe. target. getOfFers(选项)函数的信息。
seo-title: 有关Adobe Target. js JavaScript库的adobe. target. getOfFers(选项)函数的信息。
solution: Target
subtopic: 入门指南
title: adobe.target.getOffers(options)
topic: Standard
translation-type: tm+mt
source-git-commit: cc7dc21321816e7f71b67e31abc0855184a285c6

---


# adobe. target. getOffers(options)- at. js2.x

此函数允许您通过传递多个 mbox 来检索多个选件。此外，还可以针对活跃活动中的所有视图检索多个选件。

>[!NOTE]
>
>此函数在. js2.x中引入。此函数不适用于. js版本1。*x*。

| 键值 | 类型 | 必需？ | 描述 |
| --- | --- | --- | --- |
| consumerId | 字符串 | 否 | 如果未提供，则默认值为客户端的全局 mbox。可使用此键值生成用于 A4T 集成的补充数据 ID。 |
| request | 对象 | 是 | 请参阅下文的“请求”表。 |
| timeout | 数值 | 否 | 请求超时。如果未指定，将使用默认的 at.js 超时值。 |

## 请求

| 字段名称 | 必需？ | 限制 | 描述 |
| --- | --- | --- | --- |
| request &gt; id | 否 |  | 需要使用 `tntId`、`thirdPartyId` 或 `marketingCloudVisitorId` 中的一个。 |
| request &gt; id &gt; thirdPartyId | 否 | 最大大小 = 128 |  |  |
| 请求&gt; Experience Cloud | 否 |  |  |
| “请求”&gt;“Experience Cloud”&gt;“分析” | 否 |  | Adobe Analytics集成 |
| “请求”&gt;“Experience Cloud”&gt;“分析”&gt;“日志记录” | 否 | 以下必须在页面上实现：<ul><li>访客 ID 服务</li><li>AppMeasurement. js</li></ul> | 支持以下值：<br>**client_ side**：指定后，分析有效负荷将返回到应通过数据插入API发送到Adobe Analytics的调用者。<br>**server_ side**：这是Target和Analytics后端将使用SSID组合调用以进行报告的默认值。 |
| request &gt; prefetch | 否 |  |  |
| request &gt; prefetch &gt; views | 否 | 最大计数 50<br>名称不为空<br>名称长度 `<=` 128<br>值长度 `<=` 5000<br>名称不应以“profile”开头<br>不允许的名称：“orderId”、“orderTotal”、“productPurchasedId” | 传递用于检索活跃活动中相关视图的参数。 |
| request &gt; prefetch &gt; views &gt; profileParameters | 否 | 最大计数 50<br>名称不为空<br>名称长度 `<=` 128<br>值长度 `<=` 5000<br>名称不应以“profile”开头 | 传递用于检索活跃活动中相关视图的配置文件参数。 |
| request &gt; prefetch &gt; views &gt; product | 否 |  |  |
| request &gt; prefetch &gt; views &gt; product -&gt; id | 否 | 不为空<br>最大大小 = 128 | 传递用于检索活跃活动中相关视图的产品 ID。 |
| request &gt; prefetch &gt; views &gt; product &gt; categoryId | 否 | 不为空<br>最大大小 = 128 | 传递用于检索活跃活动中相关视图的产品类别 ID。 |
| request &gt; prefetch &gt; views &gt; order | 否 |  |  |
| request &gt; prefetch &gt; views &gt; order &gt; id | 否 | 最大长度 = 250 | 传递用于检索活跃活动中相关视图的订单 ID。 |
| request &gt; prefetch &gt; views &gt; order &gt; total | 否 | 总额 `>=` 0 | 传递用于检索活跃活动中相关视图的订单总额。 |
| request &gt; prefetch &gt; views &gt; order &gt; purchasedProductIds | 否 | 无空值<br>每个值的最大长度为 50<br>用逗号连接和分隔<br>产品 ID 总长度 `<=` 250 | 传递用于检索活跃活动中相关视图的已购买产品 ID。 |
| request &gt; execute | 否 |  |  |
| request &gt; execute &gt; pageLoad | 否 |  |  |
| request &gt; execute &gt; pageLoad &gt; parameters | 否 | 最大计数 50<br>名称不为空<br>名称长度 `<=` 128<br>值长度 `<=` 5000<br>名称不应以“profile”开头。<br>不允许的名称：“orderId”、“orderTotal”、“productPurchasedId” | 页面加载时使用指定的参数检索选件。 |
| request &gt; execute &gt; pageLoad &gt; profileParameters | 否 | 最大计数 50<br>名称不为空<br>名称长度 `<=` 128<br>值长度 `<=` 256<br>名称不应以“profile”开头。 | 页面加载时使用指定的配置文件参数检索选件。 |
| request &gt; execute &gt; pageLoad &gt; product | 否 |  |  |
| request &gt; execute &gt; pageLoad &gt; product -&gt; id | 否 | 不为空<br>最大大小 = 128 | 页面加载时使用指定的产品 ID 检索选件。 |
| request &gt; execute &gt; pageLoad &gt; product &gt; categoryId | 否 | 不为空<br>最大大小 = 128 | 页面加载时使用指定的产品类别 ID 检索选件。 |
| request &gt; execute &gt; pageLoad &gt; order | 否 |  |  |
| request &gt; execute &gt; pageLoad &gt; order &gt; id | 否 | 最大长度 = 250 | 页面加载时使用指定的订单 ID 检索选件。 |
| request &gt; execute &gt; pageLoad &gt; order &gt; total | 否 | `>=` 0 | 页面加载时使用指定的订单总额检索选件。 |
| request &gt; execute &gt; pageLoad &gt; order &gt; purchasedProductIds | 否 | 无空值<br>每个值的最大长度为 50<br>用逗号连接和分隔<br>产品 ID 总长度 `<=` 250 | 页面加载时使用指定的已购产品 ID 检索选件。 |
| request &gt; execute &gt; mboxes | 否 | 最大大小 = 50<br>无 null 元素 |  |
| request &gt; execute &gt; mboxes &gt; mbox | 是 | 不为空<br>无“-clicked”后缀<br>最大大小 = 250<br>允许的字符：`'-, ._\/=:;&!@#$%^&*()_+|?~[]{}'` | mbox 的名称。 |
| request &gt; execute &gt; mboxes &gt; mbox &gt; index | 是 | 不为 null<br>唯一值<br>`>=` 0 | 请注意，index 并不表示 mbox 的处理顺序。与具有多个区域 mbox 的网页相同，无法指定这些 mbox 的处理顺序。 |
| request &gt; execute &gt; mboxes &gt; mbox &gt; parameters | 否 | 最大计数 = 50<br>名称不为空<br>名称长度 `<=` 128<br>值长度 `<=` 5000<br>名称不应以“profile”开头。<br>不允许的名称：“orderId”、“orderTotal”、“productPurchasedId” | 使用指定的参数针对给定 mbox 检索选件。 |
| request &gt; execute &gt; mboxes &gt; mbox &gt; profileParameters | 否 | 最大计数 = 50<br>名称不为空<br>名称长度 `<=` 128<br>值长度 `<=`256<br>名称不应以“profile”开头。 | 使用指定的配置文件参数检索给定 mbox 的选件。 |
| request &gt; execute &gt; mboxes &gt; mbox &gt; product | 否 |  |  |
| request &gt; execute &gt; mboxes &gt; mbox &gt; product &gt; id | 否 | 不为空<br>最大大小 = 128 | 使用指定的产品 ID 检索给定 mbox 的选件。 |
| request &gt; execute &gt; mboxes &gt; mbox &gt; product &gt; categoryId | 否 | 不为空<br>最大大小 = 128 | 使用指定的产品类别 ID 检索给定 mbox 的选件。 |
| request &gt; execute &gt; mboxes &gt; mbox &gt; order | 否 |  |  |
| request &gt; execute &gt; mboxes &gt; mbox &gt; order &gt; id | 否 | 最大长度 = 250 | 使用指定的订单 ID 检索给定 mbox 的选件。 |
| request &gt; execute &gt; mboxes &gt; mbox &gt; order &gt; total | 否 | `>=` 0 | 使用指定的订单总额检索给定 mbox 的选件。 |
| request &gt; execute &gt; mboxes &gt; mbox &gt; order &gt; purchasedProductIds | 否 | 非空值<br>每个值的最大长度 = 50<br>用逗号连接和分隔<br>产品 ID 总长度 `<=` 250 | 使用指定的订单已购产品 ID 检索给定 mbox 的选件。 |

## 为所有视图调用 `getOffers()`

```
adobe.target.getOffers({
    prefetch: {
      views: []
    }
  }
});
```

## 调用 `getOffers()` 以使用传递的参数和配置文件参数检索最新的视图

```
adobe.target.getOffers({
  request: {
    "prefetch": {
      "views": [
        {
          "parameters": {
            "ad": "1"
          },
          "profileParameters": {
            "age": 23
          }
        }
      ]
    }
  }
});
```

## 调用 `getOffers()` 以使用传递的参数和配置文件参数检索 mbox。

```
adobe.target.getOffers({
  request: {
    execute: {
      mboxes: [
        {
          index: 0,
          name: "first-mbox"
        },
        {
          index: 1,
          name: "second-mbox",
          parameters: {
            a: 1
          },
          profileParameters: {
            b: 2
          }
        }
      ]
    }
  }
});
```

## 调用getOffers()以从客户端检索分析有效负荷

```
adobe.target.getOffers({
      request: {
        experienceCloud: {
          analytics: {
            logging: "client_side"
          }
        },
        prefetch: {
          mboxes: [{
            index: 0,
            name: "a1-serverside-xt"
          }]
        }
      }
    })
    .then(console.log)
```

**响应**:

```
{
  "prefetch": {
    "mboxes": [{
      "index": 0,
      "name": "a1-serverside-xt",
      "options": [{
        "content": "<img src=\"http://s7d2.scene7.com/is/image/TargetAdobeTargetMobile/L4242-xt-usa?tm=1490025518668&fit=constrain&hei=491&wid=980&fmt=png-alpha\"/>",
        "type": "html",
        "eventToken": "n/K05qdH0MxsiyH4gX05/2qipfsIHvVzTQxHolz2IpSCnQ9Y9OaLL2gsdrWQTvE54PwSz67rmXWmSnkXpSSS2Q==",
        "responseTokens": {
          "profile.memberlevel": "0",
          "geo.city": "bucharest",
          "activity.id": "167169",
          "experience.name": "USA Experience",
          "geo.country": "romania"
        }
      }],
      "analytics": {
        "payload": {
          "pe": "tnt",
          "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
        }
      }
    }]
  }
}
```

然后，可以通过 [数据插入API将有效负荷转发给Adobe Analytics](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)。

## 通过getOffers()和applyOffers()从多个mbox提取和渲染数据 {#multiple}

at. js2.x可让您通过 `getOffers()` API获取多个mbox。您还可以获取多个mbox的数据，然后用于 `applyOffers()` 渲染CSS选择器确定的不同位置中的数据。

以下示例展示了实现. js2.x的简单HTML页面：

```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>at.js 2.x, multiple selectors and multiple mboxes</title>
  <script src="at.js"></script>
</head>
<body>
  <div id="container1">Default content 1</div>
  
  <div id="container2">Default content 2</div>

  <div id="container3">Default content 3</div>
</body>
</html>
```

假定您有三个要通过从中接收的内容进行修改的容器 [!DNL Target]。您可以为三个mbox构造一个请求，其中每个mbox都有一些内容可渲染到各自的容器中。

请求和渲染代码可能类似于以下示例：

```
adobe.target.getOffers({
  request: {
    prefetch: {
      mboxes: [
        {
          index: 0,
          name: "mbox1"
        },
        {
          index: 1,
          name: "mbox2"
        },
        {
          index: 2,
          name: "mbox3"
        }
      ]
    }
  }
})
.then(response => {
  // get all mboxes from response
  const mboxes = response.prefetch.mboxes;
  let count = 1;

  mboxes.forEach(el => {
    adobe.target.applyOffers({
      selector: "#container" + count,
      response: {
        prefetch: {
          mboxes: [el]
        }
      }
    });

    count += 1;
  });
});
```

`request > prefetch > mboxes` 在该部分中，有三个不同的mbox。如果请求成功完成，您将收到每个mbox的响应 `response > prefetch > mboxes`。在您具有响应和要用于渲染的位置之后，您可以调用 `applyOffers()` 渲染从 [!DNL Target]中检索的内容。在本示例中，我们有以下映射：

* mbox&gt; CSS选择器# container1
* mbox&gt; CSS选择器# container2
* mbox3&gt; CSS选择器# container3

此示例使用计数变量构建CSS选择器。在真实情况下，您可以在CSS选择器和mbox之间使用不同的映射。

请注意，此示例使用 `prefetch > mboxes`，但您也可以使用 `execute > mboxes`。确保在中 `getOffers()`使用预检，您也应在 `applyOffers()` 调用中使用预检。
