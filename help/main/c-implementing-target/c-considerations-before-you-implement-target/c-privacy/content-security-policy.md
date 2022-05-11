---
keywords: 内容安全策略;csp;at.js;白名单;允许列表;闪烁;预隐藏;预先隐藏
description: 了解在使用 Adobe Target 时应该添加的内容安全策略 (CSP) 指令。
title: ' [!DNL Target] 如何处理内容安全策略 (CSP)？'
feature: Privacy & Security
role: Developer
exl-id: 31457b16-ed21-4540-8d0c-abfb49d1fbe9
source-git-commit: db632225d21c2e061e82269bec168341b410575a
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 29%

---

# 内容安全策略 (CSP) 指令

如果您在为 [!DNL Adobe Target] 实施使用[内容安全策略](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP)，则在使用 [at.js 2.1 或更高版本](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)时应该添加以下 CSP 指令。

* `connect-src` 与 `*.tt.omtrdc.net` 已列入允许列表。要允许将网络请求发送到 [!DNL Target] 边缘时是必需的。
* `style-src unsafe-inline`。对于预隐藏和闪烁控制是必需的。
* `script-src unsafe-inline`.  需要此项以允许可能作为 HTML 选件一部分的 JavaScript 执行。

## 常见问题解答(FAQ)

请参阅以下有关安全策略的常见问题解答：

### 跨域资源共享(CORS)和Flash跨域策略是否会出现安全问题？

实施CORS策略的建议方法是允许仅访问需要通过可信域的一允许列表组可信源。 Flash跨域策略也是如此。 部分 [!DNL Adobe Target] 客户担心在 [!DNL Target]. 问题在于，如果用户登录到某个应用程序，并访问该策略允许的域，则在该域上运行的任何恶意内容都可能从该应用程序中检索敏感内容，并在登录用户的安全上下文中执行操作。 这通常称为跨站点请求伪造(CSRF)。

在 [!DNL Adobe Target] 但是，这些政策的实施不应代表安全问题。

“adobe.tt.omtrdc.net”是Adobe拥有的域。 [!DNL Adobe Target] 是一个测试和个性化工具，预计 [!DNL Target] 可以从任何位置接收和处理请求，而无需任何身份验证。 这些请求包含用于A/B测试、推荐或内容个性化的键/值对。

[!DNL Adobe] 不存储个人身份信息(PII)或 [!DNL Adobe Target] 边缘服务器，“adobe.tt.omtrdc.net”指向该边缘服务器。

预计 [!DNL Target] 可通过JavaScript调用从任何域访问。 允许此访问的唯一方法是使用带通配符的“Access-Control-Allow-Origin”。
