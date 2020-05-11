---
keywords: email;ESP;email service provider;rawbox;delivery API;download-only template;email template;batch processing;build-time email
description: 此信息介绍了将电子邮件与“推荐”集成的方法。
title: 将“推荐”与电子邮件集成
topic: Recommendations
uuid: ae137d7c-58c5-4601-92fc-2dc5548760fd
translation-type: tm+mt
source-git-commit: 32cfa346ae6aa3246d830e1ce153cb45baab8c89
workflow-type: tm+mt
source-wordcount: '1420'
ht-degree: 95%

---


# ![PREMIUM](/help/assets/premium.png) 将“推荐”与电子邮件集成{#integrate-recommendations-with-email}

此信息介绍了将电子邮件与“推荐”集成的方法。

您的电子邮件服务提供商所具有的功能决定了要使用哪种方法。您的帐户管理员或顾问可以帮助您选择最适合您的方法。

## 选项 1：使用交付 API {#section_9F00D271BABA4B7390B461F4C44EC319}

交付 API 是一种 POST 请求，适用于构建时电子邮件。此选项是构建时电子邮件的首选方法。

大多数电子邮件客户端都不允许使用 POST 请求；因此，不建议在打开时用例中使用此 API。有些电子邮件客户端（例如 Gmail 或 Outlook）可能会缓存内容或阻止图像，因而要求收件人主动允许呈现图像。

您无法使用交付 API 来返回默认内容。

以下代码是一个 API 交付请求示例：

```
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

其中，`clientcode` 是您的 Target 客户端代码。

>[!NOTE]
>
>请确保为每个电子邮件收件人（例如，每个 API 调用）的 `sessionId` 和 `tntId` 或 `thirdPartyId` 两者之一均提供唯一值。如果您没有为这些字段提供唯一值，则由于在单个配置文件中会生成大量事件，API 响应可能变慢或失败。

有关更多信息，请参阅[交付 API 文档](https://developers.adobetarget.com/api/#server-side-delivery)。

## 选项 2：使用 rawbox 电子邮件模板 {#section_C0D48A42BCCE45D6A68852F722C7C352}

rawbox 类似于 mbox 请求，但适用于诸如电子邮件服务提供商 (ESP) 之类的非 Web 环境。由于没有可用于 rawbox 请求的 [!DNL mbox.js] 或 [!DNL at.js]，因此您必须手动创建请求。以下示例介绍了如何在电子邮件中处理 rawbox 请求。

使用此方法，您可以跟踪推荐在电子邮件中的性能，像测试常规推荐那样测试电子邮件中的推荐，并继续跟踪网站。

在 [!DNL Adobe Target] 中，使用[基于表单的体验编辑器](../../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)选项设置 [!DNL Recommendations] 活动。对于位置，选择您之前选择的要用于来自 ESP 的 rawbox 请求的 mbox 名称。为电子邮件选择所需的外观设计。在构建电子邮件时，ESP 会向 [!DNL Adobe Target] 服务器发起调用，以在每个电子邮件中各生成一个 rawbox。您的 ESP 必须能够在电子邮件发送时将返回的 HTML 包含到电子邮件中。

您使用的电子邮件系统应该能够处理以下情形：

**收到了有效响应，但未显示任何推荐。**

* 在这种情况下，响应内容将为 mboxDefault 参数值，而不论该参数设置为何值。请参阅下面有关此参数的说明。
* 电子邮件提供商应具有可在这种情况下使用的默认 HTML 推荐块。

**Target 服务器超时，且未返回任何数据。**

* 在这种情况下，Target 服务器将返回以下内容：

   `//ERROR: application server timeout`

* 电子邮件应用程序应搜索上述文本，并能够处理此错误。电子邮件提供商可以选用多种方法来处理此情况：

   * 立即尝试再次调用服务器（建议使用此方法，或许还可以使用尝试计数器）。
   * 放弃该特定电子邮件，并继续处理下一个电子邮件。
   * 将该特定电子邮件排入队列，然后在初次运行结束后以批量方式再次运行之前失败的电子邮件。

**请求 URL 示例：**

```
https://client_code.tt.omtrdc.net/m2/client_code/ubox/raw?mbox=mbox_name&mboxSession=1396032094853-955654&mboxPC=1396032094853-955654&mboxXDomain=disabled&entity.event.detailsOnly=true&mboxDefault=nocontent&mboxNoRedirect=1&entity.id=2A229&entity.categoryId=5674
```

**必需的参数:**

>[!NOTE]
>
>要在电子邮件中使用 [!DNL Recommendations]，rawbox 调用通常必须包含 `entity.id` 或 `entity.categoryId`，或者同时包含这两者，具体取决于推荐标准的类型。上述调用示例同时包含这两者。

| 参数 | 值 | 描述 | 验证 |
|--- |--- |--- |--- |
| `client_code` | *client_code* | 推荐中使用的客户端代码。您的 Adobe 顾问可以提供此值。 |  |
| `mbox` | *mboxName* | 用于定位的 mbox 名称。 | 验证方式与所有 mbox 调用相同。<br>250 个字符限制。<br>不能包含以下任一字符：`', ", %22, %27, <, >, %3C, %3E` |
| `mboxXDomain` | disabled | 阻止响应在非 Web 环境中设置 Cookie。 |  |
| `entity.id`<br>（以下特定类型的标准需要使用此参数：已查看/已查看、已查看/已购买、已购买/已购买）。 | *entity_id* | 推荐所基于的产品 ID，例如在购物车中放弃的产品或以前购买的产品。<br>如果推荐标准具有相应要求，则 rawbox 必须包含 `entity.id`。 |  |
| `entity.event.detailsOnly` | true | 如果传递了 `entity.id`，则强烈建议您也传递此参数，以阻止请求递增某个项目的页面查看统计次数，从而使基于产品查看的算法不会出现偏差。 |  |
| `entity.categoryId`<br>（以下特定类型的标准需要使用此参数：按类别查看次数最多的项目和按类别最畅销的商品） | *category_id* | 推荐所基于的类别，例如某个类别中最畅销的商品。<br>如果推荐标准具有相应要求，则 rawbox 必须包含 `entity.categoryId`。 |  |
| `mboxDefault` | *`https://www.default.com`* | 如果 `mboxNoRedirect` 参数不存在，则 `mboxDefault` 应该是一个绝对 URL，在没有可用推荐的情况下，该 URL 将返回默认内容。默认内容可以是一个图像或其他静态内容。<br>如果 `mboxNoRedirect` 参数存在，则 `mboxDefault` 可以是用于指示没有推荐的任何文本，例如 `no_content`。<br>电子邮件提供商将需要处理返回此值的情况，并将默认 HTML 插入到电子邮件中。<br> 请注意，如果URL中使用的 `mboxDefault` 域未列入白名单，您可能会面临“开放重定向”漏洞的风险。 为避免重定向器链接或第三方 `mboxDefault` 未经授权而使用，我们建议您使用“授权主机”将默认重定向URL域列入白名单。 目标使用主机将要允许重定向的域列入白名单。 有关更多信息，请参阅[主机](https://developers.adobetarget.com/api/#server-side-delivery)。 |  |
| `mboxHost` | *mbox_host* | 这是调用触发时添加到默认环境（主机组）的域。 |  |
| `mboxPC` | 留空 | （使用访客配置文件的推荐需要使用此参数。）<br>如果未提供“thirdPartyId”，则新的 tntId 将会生成，并在响应中返回。否则，此值将继续留空。<br>**注意：**请确保为每个电子邮件收件人（即，每个 API 调用）的`mboxSession`和`mboxPC`提供唯一值。如果您没有为这些字段提供唯一值，则由于在单个配置文件中会生成大量事件，API 响应可能变慢或失败。 | 1 &lt; 长度 &lt; 128<br>最多只能包含一个“.”（圆点）。<br>仅允许在配置文件位置后缀中使用圆点。 |

**可选参数**：

| 参数 | 值 | 描述 | 验证 |
|--- |--- |--- |--- |
| `mboxPC`<br>（可选） | *mboxPCId* | Target 访客 ID。如果您想要在用户多次访问您网站时进行全程跟踪，或者需要使用用户配置文件参数，请使用此值。<br>此值需是用户真实的 Adobe Target PCID，可从网站中将此 ID 导出到您的 CRM。电子邮件提供商将从您的 CRM 或 Data Warehouse 中检索此 ID，并将其用作此参数的值。<br>如果 A/B 活动中包含推荐，则 `mboxPC` 值还可用于跟踪访客多次访问您网站时的行为，以及跟踪量度。<br>**注意：**请确保为每个电子邮件收件人（即，每个 API 调用）的`mboxSession`和`mboxPC`提供唯一值。如果您没有为这些字段提供唯一值，则由于在单个配置文件中会生成大量事件，API 响应可能变慢或失败。 | 1 &lt; 长度 &lt; 128<br>最多只能包含一个“.”（圆点）。<br>仅允许在配置文件位置后缀中使用圆点。 |
| `mboxNoRedirect`<br>（可选） | 1 | 默认情况下，如果未找到可交付的内容，则会重定向调用方。可用于禁用默认行为。 |  |
| `mbox3rdPartyId` | *xxx* | 如果您具有用于配置文件定位的自定义访客 ID，请使用此参数。 |  |

**可能的 Target 服务器响应**：

| 响应 | 描述 |
|--- |--- |
| //错误: | 由负载平衡器在无法返回内容时生成 |
| success | `mboxNoRedirect` 参数设置为“true”，且服务器未返回任何推荐（即，mbox 没有匹配项，或服务器缓存未初始化）。 |
| 请求错误 | 缺少 `mbox` 参数。<ul><li>未指定 `mboxDefault` 或 `mboxNoRedirect` 参数。</li><li>指定了 `mboxTrace` 请求参数，但未指定 `mboxNoRedirect` 参数。</li><li>mbox 名称以 `-clicked` 后缀结尾时，未指定 `mboxTarget` 参数。</li></ul> |
| `Cannot redirect to default content, please specify mboxDefault parameter` | 请求不存在匹配项时，未指定 `mboxDefault` 参数，同时也未指定 `mboxNoRedirect` 参数。 |
| `Invalid mbox name:= MBOX_NAME` | 指示 `mbox` 参数包含无效字符。 |
| `Mbox name [MBOX_NAME] is too long` | 指示 `mbox` 参数长度超过 250 个字符。 |

## 选项 3：使用“仅限下载”模板 {#section_518C279AF0094BE780F4EA40A832A164}

按常规方法设置推荐，但在演示部分中选择&#x200B;**仅限下载**，而不是模板和 mbox 组合。然后，在 ESP 中，告诉 ESP 您创建了什么推荐 ID。ESP 将通过 API 访问推荐数据。此数据会显示应为某个特定类别或重要项目推荐哪些项目，例如已放弃的购物车中的项目。ESP 会存储此数据并将此数据与其自身的外观相关联，还会显示有关每个项目的信息，并通过电子邮件交付此类信息。

选用这一方法时，推荐服务器无法直接跟踪推荐的性能或多个算法/模板组合中的分离流量。此外，推荐并未与访客配置文件绑定。

有关下载 API 的更多信息，请参阅[旧版 API > 下载](../../assets/adobe-recommendations-classic.pdf)。
