---
keywords: at.js；浏览器用户代理；用户代理；客户端提示；用户代理
description: 了解如何 [!DNL Adobe Target] 使用用户代理和客户端提示来确定访客是否符合分段和个性化条件。
title: 用户代理和客户端提示
feature: at.js
role: Developer
exl-id: 22d29bfe-e022-44b2-913f-c8c32c65bc48
source-git-commit: c351044163a6fb32ca72fa015724d3b0388c059a
workflow-type: tm+mt
source-wordcount: '1332'
ht-degree: 3%

---

# 用户代理和客户端提示

[!DNL Adobe Target] 使用用户代理来确定访客是否符合分段和个性化条件。

>[!NOTE]
>
>本文中的信息适用于 [at.js版本2.9.0](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) （或更高版本）。


每次Web浏览器向服务器发出请求时，请求的标题中都会包含有关浏览器以及浏览器运行环境的信息。 自Internet问世初期以来，此数据已汇总到一个名为用户代理的字符串中。

以下文本是使用Safari浏览器的基于Mac OS X的计算机的示例用户代理：

```
Mozilla/5.0 (Linux; Android 12; SM-S908E) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/101.0.4951.41 Mobile Safari/537.36 
```

从该用户代理中，接收请求的服务器可以识别有关浏览器和操作系统的以下信息：

| 信息 | 详细信息 |
| --- | --- |
| 软件名称 | Chrome |
| 软件版本 | 101 |
| 完整软件版本 | 101.0.4951.41 |
| 布局引擎名称 | AppleWebKit |
| 布局引擎版本 | 537.36 |
| 操作系统 | Android |
| 操作系统版本 | Android 12（雪锥） |
| 设备 | SM-S908E(Samsung Galaxy S22Ultra) |

多年来，用户代理字符串中包含的浏览器和设备信息量有所增加。

## 用户代理用例

长期以来，用户代理一直用于向营销和开发人员团队提供有关浏览器、操作系统的重要洞察信息。 和设备可显示网站内容，以及用户与网站的交互方式。 用户代理还用于阻止垃圾邮件和过滤爬网站的机器人，以实现各种其他目的。

但是，近年来，一些网站所有者和营销供应商使用用户代理以及请求标题中包含的其他信息来创建数字指纹，这些数字指纹可用作在不知情的情况下识别用户的手段。 尽管用户代理为站点所有者提供了重要用途，但浏览器开发人员仍决定更改用户代理的操作方式，以限制站点访客潜在的隐私问题。

用户代理客户端提示是浏览器开发人员开发的解决方案。 客户端提示仍允许站点收集必要的浏览器、操作系统和设备信息，同时还可以增强对隐藏跟踪方法（如指纹）的保护。

## 客户端提示

用户代理客户端提示使网站所有者能够以更保护隐私的方式访问用户代理中提供的大部分相同信息。 当现代浏览器将用户代理发送到Web服务器时，无论是否需要，每个请求都会发送整个用户代理。 另一方面，客户端提示强制实施一个模型，服务器必须在该模型中向浏览器询问其希望了解的有关客户端的其他信息。 在收到此请求后，浏览器可以应用其自己的策略或用户配置来确定返回哪些数据。 现在，以明确且可审核的方式管理访问权限，而不是默认在所有请求上公开整个用户代理。

自版本89起，Chrome中便提供了用户代理客户端提示。 基于Chromium的浏览器(如Microsoft Edge、Opera、Brave、Chrome Android、Opera Android和Samsung Internet)的最新版本也支持客户端提示API。

在浏览器向Web服务器发出的第一个请求的标头中包含的客户端提示包含浏览器品牌、浏览器的主要版本以及客户端是否为移动设备的指示器。 每个数据都有其自己的标头值，而不是分组到单个用户代理字符串中，如以下示例所示：

```
Sec-CH-UA: "Chromium";v="101", "Google Chrome";v="101", " Not;A Brand";v="99" 
Sec-CH-UA-Mobile: ?0 
Sec-CH-UA-Platform: "macOS"
```

以下示例是同一浏览器的用户代理：

```
Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/101.0.4951.54 Safari/537.36 
```

尽管信息相似，但对服务器的第一个请求包含客户端提示，该提示仅包含用户代理字符串中可用内容的子集。 请求中缺少的是操作系统架构、完整的操作系统版本、布局引擎名称、布局引擎版本和完整的浏览器版本。 但是，在后续请求中，客户端提示API允许Web服务器请求有关该设备的其他高熵详细信息。 当根据浏览器策略或用户设置请求这些高熵值时，浏览器响应可以包含该信息。

以下示例是请求高熵值时客户端提示API返回的JSON对象：

```
{ 

    "architecture":"x86", 
    "bitness":"64", 
    "brands":[ 
        { 
            "brand":" Not A;Brand", 
            "version":"99" 
        }, 
        { 
            "brand":"Chromium", 
            "version":"100" 
        }, 
        { 
            "brand":"Google Chrome", 
            "version":"100" 
        } 
    ], 
    "fullVersionList":[ 
        { 
            "brand":" Not A;Brand", 
            "version":"99.0.0.0" 
        }, 
        { 
            "brand":"Chromium", 
            "version":"100.0.4896.127" 
        }, 
        { 
            "brand":"Google Chrome", 
            "version":"100.0.4896.127" 
        } 
    ], 
    "mobile":false, 
    "model":"", 
    "platformVersion":"12.2.1" 
} 
```

高熵值包括一些在默认客户端提示信息中不可用的其他信息。 下表包含有关默认请求中可用数据的详细信息以及高熵User-Agent客户端提示信息。

| HTTP头 | JavaScript | 用户代理 | 客户端提示 | 高熵客户端提示 |
| --- | --- | --- | --- | --- |
| Sec-CH-UA | 品牌 | 是 | 是 | 否 |
| Sec-CH-UA-Platform | 平台 | 是 | 是 | 否 |
| Sec-CH-UA-Mobile | mobile | 是 | 是 | 否 |
| Sec-CH-UA-Platform-Version | platformVersion | 是 | 否 | 是 |
| Sec-CH-UA-Arch | 架构 | 是 | 否 | 是 |
| Sec-CH-UA-Model | model | 是 | 否 | 是 |
| Sec-CH-UA-Bitness | 比特 | 是 | 否 | 是 |
| Sec-CH-UA-Full-Version-List | fullVersionList | 是 | 否 | 是 |

## 迁移到客户端提示

目前，基于Chromium的浏览器会继续在向Web服务器发出的请求标头中发送用户代理和客户端提示。 但是，从2022年4月开始，直到2023年2月，用户代理字符串中包含的数据量将会减少。 其他浏览器（如Safari和Firefox）将继续利用用户代理字符串；然而，它们也将减少其中所载信息量。

## [!DNL Target] 需要点击提示的用例

Target中的以下用例需要客户端提示：

### 受众属性

如果您使用 [!DNL Target] 受众，并使用以下任意受众属性， [!DNL Target] 需要客户提示才能执行正确的分段：

* 浏览器
* 操作系统
* 移动设备

### 个人资料脚本

如果您使用配置文件脚本并引用 `user.browser` 属性（指用户代理），您可能需要更新配置文件脚本以同时检查一个或多个客户端提示。 您可以使用函数访问任何客户端提示 `user.clientHint('sec-ch-ua-xxxxx')`. 客户端提示标头名称必须全部为小写。

以下示例显示如何在配置文件脚本中正确检测Windows操作系统：

```
"return (((user.browser != null) && (user.browser.indexOf(\"Windows\") > -1)) || " + 
      "((user.clientHint('sec-ch-ua-platform') != null) && 
(user.clientHint('sec-ch-ua-platform') === 'Windows')));" 
```

以下部分显示了客户端提示标题及其相应的配置文件脚本使用语义。

#### Sec-CH-UA

熵：低文档： [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA){target=_blank}受众属性：浏览器配置文件脚本用法： `user.clientHint('sec-ch-ua')`

#### Sec-CH-UA-Arch

熵：高文档： [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Arch](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Arch){target=_blank}受众属性：通过配置文件脚本向用户公开。
配置文件脚本用法： `user.clientHint('sec-ch-ua-arch')`

#### Sec-CH-UA-Bitness

熵：高文档： [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Bitness](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Bitness){target=_blank}受众属性：通过配置文件脚本向用户公开。
配置文件脚本用法： `user.clientHint('sec-ch-ua-bitness')`

#### Sec-CH-UA-Full-Version-List

熵：高文档： [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Full-Version-List](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Full-Version-List){target=_blank}受众属性：浏览器配置文件脚本用法： `user.clientHint('sec-ch-ua-full-version-list')`

#### Sec-CH-UA-Mobile

熵：低文档： [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Mobile](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Mobile){target=_blank}受众属性：移动配置文件脚本用法： `user.clientHint('sec-ch-ua-mobile')`

#### Sec-CH-UA-Model

熵：高文档： [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Model](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Model){target=_blank}受众属性：移动配置文件脚本用法： `user.clientHint('sec-ch-ua-model')`

#### Sec-CH-UA-Platform

熵：低文档： [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform){target=_blank}受众属性：操作系统配置文件脚本用法： `user.clientHint('sec-ch-ua-platform')`

#### Sec-CH-UA-Platform-Version

熵：高文档： [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform-Version](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform-Version){target=_blank}受众属性：通过配置文件脚本向用户公开。
配置文件脚本用法： `user.clientHint('sec-ch-ua-platform-version')`

## 如何将客户端提示传递到 [!DNL Adobe Target]

以下各节包含有关如何根据您的 [!DNL Target] 实施。

### at.js版本2.9.0（或更高版本）

从at.js 2.9.0开始，将自动从浏览器收集用户代理客户端提示，并将其发送到 [!DNL Target] when `getOffer/getOffers()` 调用。 默认情况下，at.js仅收集“低熵”客户端提示。 如果根据前面各节中分类为“高熵”的数据执行受众分段或使用配置文件脚本，则您需要配置at.js以通过从浏览器中收集“高熵”客户端提示 `targetGlobalSettings`.

`window.targetGlobalSettings = { allowHighEntropyClientHints: true };`

### 服务器端SDK

有关如何通过服务器端SDK传递客户端提示的更多信息，请参阅 [客户端提示](https://adobetarget-sdks.gitbook.io/docs/core-principles/audience-targeting#client-hints){target=_blank} *Adobe Target SDK* 文档。
