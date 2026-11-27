---
keywords: 电子邮件;ESP;电子邮件服务提供商;rawbox;交付 API;仅限下载模板;电子邮件模板;批量处理;构建时电子邮件
description: 了解如何将电子邮件与Adobe [!DNL Target Recommendations]集成，包括使用[!DNL Target]投放API、rawbox模板和仅限下载的模板。
title: 如何将“推荐”与电子邮件集成？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: 08fcb507-2c91-444a-b8ac-26165e359f6f
TQID: 'https://experienceleague.adobe.com/ZyeOl6ysM03a0mMiNgHuicOLPfgpXnrdqXJE1gHRRvE'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '1741'
ht-degree: 26%
---
# 将[!DNL Recommendations]与电子邮件集成 {#integrate-recs-email}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何将[!DNL Target Recommendations]与电子邮件服务提供商(ESP)集成，以在电子邮件中个性化设置推荐的发送时间。

>[!ENDSHADEBOX]

[!DNL Adobe Target] 支持在电子邮件中个性化设置推荐的发送时间。 不支持个性化设置推荐的打开时间。

三种方法可用于将[!DNL Target Recommendations]与ESP集成。 ESP的功能决定了要使用的方法，客户经理或顾问可以帮助您选择最佳选项。

| 方法 | 详细信息 |
| --- | --- |
| [方法 1: [!DNL Adobe Target Delivery API]](#delivery-api)（首选） | 使用[!DNL Adobe Target Delivery API]针对每位客户、每封电子邮件提出推荐请求。 |
| [方法 2: [!DNL Adobe Rawbox API]](#rawbox) | 使用[!DNL Adobe Target Rawbox API]针对每位客户、每封电子邮件提出推荐请求。 |
| [方法 3: [!DNL Recommendations Download API]](#download-api) | 使用[!DNL Recommendations Download API]请求批量推荐CSV格式的产品或类别列表。 |

方法1和2要求ESP以每位客户、每封电子邮件为基础调用外部API，并等待返回内容。 并非所有ESP都支持这些方法，因此必须联系ESP以确定它是否支持此集成模式。

方法3要求ESP按产品ID或类别ID将推荐列表加入电子邮件列表。 此加入可以基于属性，例如上次查看的产品、上次购买的产品或客户查看次数最多的类别。 ESP必须在其客户配置文件中拥有此数据的访问权限才能执行加入，因此必须联系ESP以确定它是否有权访问此数据以及是否支持此集成模式。

>[!IMPORTANT]
>
>以下容量指南适用于投放API和rawbox电子邮件模板方法（方法1和2）：
>
>* 请求速率应限制为每秒1,000个请求或每日流量峰值的25倍（以较低者为准）。
>* 流量应每分钟以每秒200个请求的速度递增。
>
>要使用更高的速率限制，请联系客户经理。

## 方法1：使用交付API（首选） {#delivery-api}

投放API是一个POST请求，可与构建时电子邮件配合使用。 此选项是构建时电子邮件的首选方法。

大多数电子邮件客户端都不允许POST请求，因此不建议在打开时用例中使用此API。 某些电子邮件客户端（如Gmail或Outlook）可能会缓存内容或阻止图像，因此需要收件人主动允许呈现图像。

默认内容不能与投放API一起返回。

以下代码是一个示例API投放请求，其中`clientcode`是[!DNL Target]客户端代码：

```javascript
curl -X POST \ 
  'https://clientcode.tt.omtrdc.net/rest/v1/mbox/?client=clientcode' \ 
  -H 'authorization: Bearer 3423614b-4843-4664-83c4-c6c3f6c8869b' \ 
  -H 'cache-control: no-cache' \ 
  -H 'content-type: application/json' \ 
  -d '{ 
  "mbox" : "email-mbox", 
  "tntId" : "111499796294071-449025.28_44", 
  "requestLocation" : { 
    "host" : "prod" 
  }, 
   "profileParameters" : { 
   }, 
  "mboxParameters" : { 
    "at_property": "b468a242-64a4-32a0-ca0c-890bddd78789", 
    "entity.id": "article-123", 
    "entity.event.detailsOnly" : "true" 
  } 
  "contentAsJson":  true 
}'
```

>[!NOTE]
>
>为每个电子邮件收件人（每个API调用）的`sessionId`以及`tntId`或`thirdPartyId`之一提供唯一值。 如果没有这些字段的唯一值，则由于在单个配置文件中会生成许多事件，API响应可能变慢或失败。

有关详细信息，请参阅[交付API文档](https://experienceleague.adobe.com/docs/target-dev/developer/api/delivery-api/overview.html){target=_blank}。

## 方法 2：使用 rawbox 电子邮件模板 {#rawbox}

rawbox类似于mbox请求，但适用于非Web环境，例如电子邮件服务提供商(ESP)。 [!DNL Adobe Experience Platform Web SDK]和[!DNL at.js]不适用于rawbox请求，因此必须手动创建请求。 以下示例说明了如何在电子邮件中使用rawbox请求。

通过此方法，您可以跟踪推荐在电子邮件中的性能，以正常方式测试推荐的表现，并继续跟踪网站。

>[!NOTE]
>
>在使用 rawbox 和 [!DNL Target] 时，请参阅[创建允许列表，其中指定有权将 mbox 调用发送到 [!DNL Target]](/help/main/administrating-target/hosts.md#allowlist)的主机下的重要安全声明。

1. 在[!DNL Target]中使用[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)选项设置[!DNL Recommendations]活动。

1. 对于位置，选择在来自ESP的rawbox请求中使用的mbox的名称。

1. Select一款设计，具有电子邮件所需的外观和风格。

在构建电子邮件时，ESP 会向 [!DNL Target] 服务器发起调用，以在每个电子邮件中各生成一个 rawbox。 ESP必须能够在电子邮件发送时将返回的HTML包含在电子邮件中。

电子邮件系统必须能够处理以下情况。

### 收到有效的响应，但不存在推荐

* 响应是`mboxDefault`参数中设置的值。 请参阅所需参数表中此参数的说明。
* 电子邮件提供商应具有可在这种情况下使用的默认 HTML 推荐块。

### [!DNL Target] 服务器超时，并且返回时无数据

* [!DNL Target]服务器返回以下内容：

  `//ERROR: application server timeout`

* 电子邮件应用程序应搜索上述文本，并能够处理此错误。 电子邮件提供商可以选用多种方法来处理此情况：

  * 立即尝试再次调用服务器（建议使用此方法，或许还可以使用尝试计数器）。
  * 放弃该特定电子邮件并继续处理下一封电子邮件。
  * 将该特定电子邮件排入队列，然后在初次运行结束后以批量方式重新运行失败的电子邮件。

### 请求 URL 示例

```
https://client_code.tt.omtrdc.net/m2/client_code/ubox/raw?mbox=mbox_name&mboxSession=1396032094853-955654&mboxPC=1396032094853-955654&mboxXDomain=disabled&entity.event.detailsOnly=true&mboxDefault=nocontent&mboxNoRedirect=1&entity.id=2A229&entity.categoryId=5674
```

### 必需的参数 {#reqparams}

>[!NOTE]
>
>要在电子邮件中使用[!DNL Recommendations]，rawbox调用通常必须包含`entity.id`或`entity.categoryId`，或者同时包含这两者，具体取决于推荐标准的类型。 上述调用示例同时包含这两者。

| 参数 | 值 | 描述 | 验证 |
|--- |--- |--- |--- |
| `client_code` | *client_code* | [!DNL Recommendations]中使用的客户端代码。 Adobe顾问可以提供此值。 |  |
| `mbox` | *mboxName* | 用于定位的 mbox 名称。 | 与所有mbox调用的验证相同。<br>250个字符限制。<br>不能包含以下任一字符：`', ", %22, %27, <, >, %3C, %3E` |
| `mboxXDomain` | disabled | 阻止响应在非 Web 环境中设置 Cookie。 |  |
| `entity.id`<br>（以下特定类型的标准需要使用此参数：已查看/已查看、已查看/已购买、已购买/已购买）。 | *entity_id* | 推荐所基于的产品ID，例如购物车中放弃的产品或之前的购买。<br>如果推荐标准具有相应要求，则 rawbox 必须包含 `entity.id`。 |  |
| `entity.event.detailsOnly` | true | 如果传递了`entity.id`，则强烈建议传递此参数，以防止请求递增某个项目的页面查看统计次数，从而不扭曲基于产品查看的算法。 |  |
| `entity.categoryId`<br>（以下特定类型的标准需要使用此参数：按类别查看次数最多的项目和按类别最畅销的商品） | *category_id* | 推荐所基于的类别，如类别中的最畅销商品。<br>如果推荐标准具有相应要求，则 rawbox 必须包含 `entity.categoryId`。 |  |
| `mboxDefault` | *`https://www.default.com`* | 如果 `mboxNoRedirect` 参数不存在，则 `mboxDefault` 应该是一个绝对 URL，在没有可用推荐的情况下，该 URL 将返回默认内容。 此 URL 可以是一个图像或其他静态内容。<br>如果`mboxNoRedirect`参数存在，则`mboxDefault`可以是指示没有推荐的任何文本，例如`no_content`。<br>电子邮件提供商必须处理返回此值的情况，并将默认HTML插入到电子邮件中。<br>请参阅表下方的安全最佳实践。 |  |
| `mboxHost` | *mbox_host* | 这是调用触发时添加到默认环境（主机组）的域。 |  |
| `mboxPC` | 留空 | （对于使用访客配置文件的推荐是必需的。）<br>如果未提供“thirdPartyId”，则新的tntId将生成并作为响应的一部分返回。 否则，值将保留为空。<br>查看表下关于唯一值的注释。 | 1 &lt; 长度 &lt; 128<br>最多只能包含一个“.” （点）。<br>仅允许在配置文件位置后缀中使用点。 |

### 可选参数

| 参数 | 值 | 描述 | 验证 |
|--- |--- |--- |--- |
| `mboxPC`<br>（可选） | *mboxPCId* | [!DNL Target]访客标识。 使用此值可在多次访问中或使用用户配置文件参数时完整跟踪返回网站的用户。<br>此值必须是从网站导出到CRM的用户实际[!DNL Adobe Target] PCID。 电子邮件提供商从CRM或Data Warehouse检索此ID，并将其用作此参数的值。<br>当推荐是A/B活动的一部分时，`mboxPC`值还可用于跟踪访客多次访问网站时的行为以进行量度跟踪。<br>查看表下关于唯一值的注释。 | 1 &lt; 长度 &lt; 128<br>最多只能包含一个“.” （点）。<br>仅允许在配置文件位置后缀中使用点。 |
| `mboxNoRedirect`<br>（可选） | 1 | 默认情况下，如果未找到可交付的内容，则会重定向调用方。 使用此参数可禁用默认行为。 |  |
| `mbox3rdPartyId` | *xxx* | 使用此选项可指定用于配置文件定位的自定义访客ID。 |  |

对于`mboxSession`和`mboxPC`，请为每个电子邮件收件人（每个API调用）提供唯一值。 如果没有这些字段的唯一值，则由于在单个配置文件中会生成大量事件，API响应可能变慢或失败。

作为`mboxDefault`的安全最佳实践，请使用授权的主机来允许列表默认的重定向URL域。 如果未列入允许列表`mboxDefault` URL中使用的域，则可能会出现“开放重定向漏洞”的风险。 授权的主机可避免第三方未经授权即使用重定向程序链接或`mboxDefault`。 [!DNL Target]使用主机来允许列表允许重定向到的域。 有关更多信息，请参阅本节开头的安全声明。

### 潜在的 [!DNL Target] 服务器响应

| 响应 | 描述 |
|--- |--- |
| //错误: | 在无法返回内容时由负载平衡器生成。 |
| 成功 | `mboxNoRedirect`参数设置为“true”，且服务器未返回任何推荐（mbox没有匹配项，或者服务器缓存未初始化）。 |
| 请求错误 | 缺少 `mbox` 参数。<ul><li>未指定 `mboxDefault` 或 `mboxNoRedirect` 参数。</li><li>指定了`mboxTrace`请求参数，但未指定`mboxNoRedirect`。</li><li>当mbox名称以`-clicked`后缀结尾时，未指定`mboxTarget`参数。</li></ul> |
| `Cannot redirect to default content, please specify mboxDefault parameter` | 当请求不存在匹配项时，未指定`mboxDefault`，并且未指定`mboxNoRedirect`参数。 |
| `Invalid mbox name:= MBOX_NAME` | `mbox`参数包含无效字符。 |
| `Mbox name [MBOX_NAME] is too long` | `mbox`参数长度超过250个字符。 |

## 方法 3: 使用推荐下载 API {#download-api}

按常规方法设置推荐，但在演示部分中选择&#x200B;**仅限下载**，而不是模板和 mbox 组合。 然后向ESP提供所创建推荐的ID。 ESP通过API访问推荐数据。 此数据会显示应为某个特定类别或重要项目推荐哪些项目，例如已放弃的购物车中的项目。 ESP存储这些数据，将其与自己的外观和感觉相关联，显示有关每个项目的信息，并在电子邮件中发送这些信息。

利用此选项，推荐服务器无法直接跟踪推荐的性能，也无法跨多个算法和模板组合拆分流量。 此外，推荐并未与访客配置文件绑定。

有关下载 API 的更多信息，请参阅[旧版 API > 下载](/help/main/assets/adobe-recommendations-classic.pdf)。
