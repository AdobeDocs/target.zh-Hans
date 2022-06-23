---
keywords: 内容安全策略;csp;at.js;白名单;允许列表;闪烁;预隐藏;预隐藏
description: 了解在使用 Adobe Target 时应该添加的内容安全策略 (CSP) 指令。
title: ' [!DNL Target] 如何处理内容安全策略 (CSP)？'
feature: Privacy & Security
role: Developer
exl-id: 31457b16-ed21-4540-8d0c-abfb49d1fbe9
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 97%

---

# 内容安全策略 (CSP) 指令

如果您在为 [!DNL Adobe Target] 实施使用[内容安全策略](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP)，则在使用 [at.js 2.1 或更高版本](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/)时应该添加以下 CSP 指令。

* `connect-src` 与 `*.tt.omtrdc.net` 已列入允许列表。要允许将网络请求发送到 [!DNL Target] 边缘时是必需的。
* `style-src unsafe-inline`。对于预隐藏和闪烁控制是必需的。
* `script-src unsafe-inline`.  需要此项以允许可能作为 HTML 选件一部分的 JavaScript 执行。

## 常见问题解答 (FAQs)

有关安全策略，请参阅以下常见问题解答：

### 跨源资源共享 (CORS) 和 Flash 跨域策略是否存在安全问题？

实施 CORS 策略的推荐方法是，只允许通过受信任域的允许列表访问需要它的受信任来源。Flash 跨域策略亦是如此。 一些 [!DNL Adobe Target] 客户担心在 [!DNL Target] 中的域使用通配符。问题在于，如果用户登录到应用程序，并访问策略允许的域，则该域上运行的任何恶意内容都可能从应用程序中检索敏感内容，并在登录用户的安全上下文中执行操作。这通常称为跨站点请求伪造 (CSRF)。

但是，在 [!DNL Adobe Target] 实施中，这些策略不应代表安全问题。

&quot;adobe.tt.omtrdc.net&quot; 是 Adobe 拥有的域。 [!DNL Adobe Target] 是一种测试和个性化工具，预计 [!DNL Target] 可以接收和处理来自任何地方的请求，而无需任何身份验证。 这些请求包含用于 A/B 测试、建议或内容个性化的键/值对。

[!DNL Adobe] 未在&quot;adobe.tt.omtrdc.net&quot;指向的 [!DNL Adobe Target] 边缘服务器上存储个人身份信息 (PII) 或其他敏感信息。

可以通过 JavaScript 调用从任何域访问 [!DNL Target]。 允许这种访问的唯一方法是利用带有通配符的&quot;Access-Control-Allow-Origin&quot;。
