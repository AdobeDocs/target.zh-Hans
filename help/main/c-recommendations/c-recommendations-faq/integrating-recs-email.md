---
keywords: 电子邮件;ESP;电子邮件服务提供商;rawbox;交付 API;仅限下载模板;电子邮件模板;批量处理;构建时电子邮件
description: 了解如何将电子邮件与 Adobe  [!DNL Target Recommendations], including using the [!DNL Target] 投放 API、rawbox 模板和仅限下载的模板集成。
title: 如何将“推荐”与电子邮件集成？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 08fcb507-2c91-444a-b8ac-26165e359f6f
source-git-commit: 2a25fdb42ce4470f9126b7e0e7f6fd9e60c350e5
workflow-type: tm+mt
source-wordcount: '1715'
ht-degree: 96%

---

# 将[!DNL Recommendations]与电子邮件集成

[!DNL Adobe Target] 支持在电子邮件中个性化设置推荐的发送时间。

可以使用三种方法将 [!DNL Target Recommendations] 与您的电子邮件服务提供商 (ESP) 集成。ESP 的功能决定了要使用的方法。您的客户经理或顾问可以帮助您选择最适合您的方法。

| 方法 | 详细信息 |
| --- | --- |
| [方法 1: [!DNL Adobe Target Delivery API]](#delivery-api)（首选） | 使用 [!DNL Adobe Target Delivery API] 针对每个客户/每封电子邮件提出推荐请求。 |
| [方法 2: [!DNL Adobe Rawbox API]](#rawbox) | 使用 [!DNL Adobe Target Rawbox API] 针对每个客户/每封电子邮件提出推荐请求。 |
| [方法 3: [!DNL Recommendations Download API]](#download-api) | 使用推荐下载 API 请求批量推荐 CSV 格式的产品或类别列表。 |

如果要使用方法 1 或方法 2，那么您的 ESP 需要对每个客户/每封电子邮件调用外部 API，并等待返回内容。并非所有 ESP 都支持这些方法；请联系您的 ESP 以确定它是否支持此集成模式。

如果要使用方法 3，则您的 ESP 需要按产品 ID 或类别 ID 将推荐列表加入您的电子邮件列表。此方法可以基于诸如客户上次查看的产品、上次购买的产品或查看次数最多的类别等属性。 但是，您的 ESP 必须有权访问其客户个人资料中的此数据才能执行加入。请联系您的 ESP 以确定它是否有权访问此数据以及是否支持此集成模式。

[!DNL Adobe Target] 不支持个性化设置推荐的打开时间。

>[!IMPORTANT]
>
>以下容量指南适用于如下所述的投放 API 和 rawbox 电子邮件模板方法（方法 1 和 2）：
>
>* 请求速率应限制为每秒 1,000 个请求或您的每日流量峰值的 25 倍（以较低者为准）。
>* 每分钟都以每秒 200 个请求的速度增加流量。
> 
>如果您想使用更高的速率限制，请与您的客户经理联系。

## 方法 1：使用交付 API（首选） {#delivery-api}

交付 API 是一种 POST 请求，适用于构建时电子邮件。此选项是构建时电子邮件的首选方法。

大多数电子邮件客户端都不允许使用 POST 请求；因此，不建议在打开时用例中使用此 API。有些电子邮件客户端（例如 Gmail 或 Outlook）可能会缓存内容或阻止图像，因而要求收件人主动允许呈现图像。

您无法使用交付 API 来返回默认内容。

以下代码是一个 API 交付请求示例：

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

其中，`clientcode` 是您的 [!DNL Target] 客户端代码。

>[!NOTE]
>
>请确保为每个电子邮件收件人（例如，每个 API 调用）的 `sessionId` 和 `tntId` 或 `thirdPartyId` 两者之一均提供唯一值。如果您没有为这些字段提供唯一值，则由于在单个配置文件中会生成许多事件，API 响应可能变慢或失败。

有关更多信息，请参阅[交付 API 文档](https://experienceleague.corp.adobe.com/docs/target-dev/developer/implementation/delivery-api/overview.html)。{target=_blank}

## 方法 2：使用 rawbox 电子邮件模板 {#rawbox}

rawbox 类似于 mbox 请求，但适用于诸如电子邮件服务提供商 (ESP) 之类的非 Web 环境。由于没有可用于 rawbox 请求的 [!DNL Adobe Experience Platform Web SDK] 或 [!DNL at.js]，因此您必须手动创建请求。以下示例介绍了如何在电子邮件中处理 rawbox 请求。

>[!NOTE]
>
>在使用 rawbox 和 [!DNL Target] 时，请参阅[创建允许列表，其中指定有权将 mbox 调用发送到 [!DNL Target]](/help/main/administrating-target/hosts.md#allowlist)的主机下的重要安全声明。

使用此方法，您可以跟踪推荐在电子邮件中的性能，像测试常规推荐那样测试电子邮件中的推荐，并继续跟踪网站。

在 [!DNL Target] 中，使用[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)选项设置 [!DNL Recommendations] 活动。对于位置，选择您之前选择的要用于来自 ESP 的 rawbox 请求的 mbox 名称。为电子邮件选择所需的外观设计。在构建电子邮件时，ESP 会向 [!DNL Target] 服务器发起调用，以在每个电子邮件中各生成一个 rawbox。您的 ESP 必须能够在电子邮件发送时将返回的 HTML 包含到电子邮件中。

您使用的电子邮件系统必须能够处理以下情形：

### 收到有效的响应，但不存在推荐

* 在这种情况下，响应内容将为 `mboxDefault` 参数值，而不论该参数设置为何值。请参阅下面有关此参数的说明。
* 电子邮件提供商应具有可在这种情况下使用的默认 HTML 推荐块。

### [!DNL Target] 服务器超时，并且返回时无数据

* 在这种情况下，[!DNL Target] 服务器将返回以下内容：

   `//ERROR: application server timeout`

* 电子邮件应用程序应搜索上述文本，并能够处理此错误。电子邮件提供商可以选用多种方法来处理此情况：

   * 立即尝试再次调用服务器（建议使用此方法，或许还可以使用尝试计数器）。
   * 放弃该特定电子邮件，并继续处理下一个电子邮件。
   * 将该特定电子邮件排入队列，然后在初次运行结束后以批量方式再次运行之前失败的电子邮件。

### 请求 URL 示例

```
https://client_code.tt.omtrdc.net/m2/client_code/ubox/raw?mbox=mbox_name&mboxSession=1396032094853-955654&mboxPC=1396032094853-955654&mboxXDomain=disabled&entity.event.detailsOnly=true&mboxDefault=nocontent&mboxNoRedirect=1&entity.id=2A229&entity.categoryId=5674
```

### 必需的参数: {#reqparams}

>[!NOTE]
>
>要在电子邮件中使用 [!DNL Recommendations]，rawbox 调用通常必须包含 `entity.id` 或 `entity.categoryId`，或者同时包含这两者，具体取决于推荐标准的类型。上述调用示例同时包含这两者。

| 参数 | 值 | 描述 | 验证 |
|--- |--- |--- |--- |
| `client_code` | *client_code* | Recommendations中使用的客户端代码。 您的 Adobe 顾问可以提供此值。 |  |
| `mbox` | *mboxName* | 用于定位的 mbox 名称。 | 验证方式与所有 mbox 调用相同。<br>250 个字符限制。<br>不能包含以下任一字符：`', ", %22, %27, <, >, %3C, %3E` |
| `mboxXDomain` | disabled | 阻止响应在非 Web 环境中设置 Cookie。 |  |
| `entity.id`<br>（以下特定类型的标准需要使用此参数：已查看/已查看、已查看/已购买、已购买/已购买）。 | *entity_id* | 推荐所基于的产品 ID，例如在购物车中放弃的产品或以前购买的产品。<br>如果推荐标准具有相应要求，则 rawbox 必须包含 `entity.id`。 |  |
| `entity.event.detailsOnly` | true | 如果传递了 `entity.id`，则强烈建议您也传递此参数，以阻止请求递增某个项目的页面查看统计次数，从而使基于产品查看的算法不会出现偏差。 |  |
| `entity.categoryId`<br>（以下特定类型的标准需要使用此参数：按类别查看次数最多的项目和按类别最畅销的商品） | *category_id* | 推荐所基于的类别，例如某个类别中最畅销的商品。<br>如果推荐标准具有相应要求，则 rawbox 必须包含 `entity.categoryId`。 |  |
| `mboxDefault` | *`https://www.default.com`* | 如果 `mboxNoRedirect` 参数不存在，则 `mboxDefault` 应该是一个绝对 URL，在没有可用推荐的情况下，该 URL 将返回默认内容。此 URL 可以是一个图像或其他静态内容。<br>如果 `mboxNoRedirect` 参数存在，则 `mboxDefault` 可以是用于指示没有推荐的任何文本，例如 `no_content`。<br>电子邮件提供商必须处理返回此值的情况，并将默认 HTML 插入到电子邮件中。<br> **安全最佳实践**：如果在 `mboxDefault` URL 中使用的域未被列入允许列表，则可能面临开放重定向漏洞的风险。为避免第三方未经授权即使用重定向程序链接或 `mboxDefault`，Adobe 建议您使用“授权的主机”将默认的重定向 URL 域列入允许列表。Target 使用主机将您要允许重定向到的域列入允许列表。有关更多信息，请参阅[创建允许列表，其中指定有权将 mbox 调用发送到 [!DNL Target]](/help/main/administrating-target/hosts.md#allowlist)的主机（在&#x200B;*主机*&#x200B;中）。 |  |
| `mboxHost` | *mbox_host* | 这是调用触发时添加到默认环境（主机组）的域。 |  |
| `mboxPC` | 留空 | （使用访客配置文件的推荐需要使用此参数。）<br>如果未提供“thirdPartyId”，则会生成新的tntId，并将其作为响应的一部分返回。 否则，此值将继续留空。<br>**注意：**&#x200B;请确保为每个电子邮件收件人（即，每个 API 调用）的 `mboxSession` 和 `mboxPC` 提供唯一值。如果您没有为这些字段提供唯一值，则由于在单个配置文件中会生成大量事件，API 响应可能变慢或失败。 | 1 &lt; 长度 &lt; 128<br>最多只能包含一个“.”（圆点）。<br>仅允许在配置文件位置后缀中使用圆点。 |

### 可选参数

| 参数 | 值 | 描述 | 验证 |
|--- |--- |--- |--- |
| `mboxPC`<br>（可选） | *mboxPCId* | Target 访客 ID。如果您想要在用户多次访问您网站时进行全程跟踪，或者需要使用用户配置文件参数，请使用此值。<br>此值需是用户真实的 [!DNL Adobe Target] PCID，可从网站中将此 ID 导出到您的 CRM。电子邮件提供商将从您的 CRM 或 Data Warehouse 中检索此 ID，并将其用作此参数的值。<br>如果 A/B 活动中包含推荐，则 `mboxPC` 值还可用于跟踪访客多次访问您网站时的行为，以及跟踪量度。<br>**注意：**&#x200B;请确保为每个电子邮件收件人（即，每个 API 调用）的 `mboxSession` 和 `mboxPC` 提供唯一值。如果您没有为这些字段提供唯一值，则由于在单个配置文件中会生成大量事件，API 响应可能变慢或失败。 | 1 &lt; 长度 &lt; 128<br>最多只能包含一个“.”（圆点）。<br>仅允许在配置文件位置后缀中使用圆点。 |
| `mboxNoRedirect`<br>（可选） | 1 | 默认情况下，如果未找到可交付的内容，则会重定向调用方。可用于禁用默认行为。 |  |
| `mbox3rdPartyId` | *xxx* | 如果您具有用于侧写定位的自定义访客 ID，请使用此选项。 |  |

### 潜在的 [!DNL Target] 服务器响应

| 响应 | 描述 |
|--- |--- |
| //错误: | 由负载平衡器在无法返回内容时生成 |
| 成功 | `mboxNoRedirect` 参数设置为“true”，且服务器未返回任何推荐（即，mbox 没有匹配项，或服务器缓存未初始化）。 |
| 请求错误 | 缺少 `mbox` 参数。<ul><li>未指定 `mboxDefault` 或 `mboxNoRedirect` 参数。</li><li>指定了 `mboxTrace` 请求参数，但未指定 `mboxNoRedirect` 参数。</li><li>mbox 名称以 `-clicked` 后缀结尾时，未指定 `mboxTarget` 参数。</li></ul> |
| `Cannot redirect to default content, please specify mboxDefault parameter` | 请求不存在匹配项时，未指定 `mboxDefault` 参数，同时也未指定 `mboxNoRedirect` 参数。 |
| `Invalid mbox name:= MBOX_NAME` | 指示 `mbox` 参数包含无效字符。 |
| `Mbox name [MBOX_NAME] is too long` | 指示 `mbox` 参数长度超过 250 个字符。 |

## 方法 3: 使用推荐下载 API {#download-api}

按常规方法设置推荐，但在演示部分中选择&#x200B;**仅限下载**，而不是模板和 mbox 组合。然后，在 ESP 中，告诉 ESP 您创建了什么推荐 ID。ESP 将通过 API 访问推荐数据。此数据会显示应为某个特定类别或重要项目推荐哪些项目，例如已放弃的购物车中的项目。ESP 会存储此数据并将此数据与其自身的外观相关联，还会显示有关每个项目的信息，并通过电子邮件交付此类信息。

选用这一方法时，推荐服务器无法直接跟踪推荐的性能或多个算法/模板组合中的分离流量。此外，推荐并未与访客配置文件绑定。

有关下载 API 的更多信息，请参阅[旧版 API > 下载](/help/main/assets/adobe-recommendations-classic.pdf)。
