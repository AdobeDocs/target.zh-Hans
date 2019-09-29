---
description: Information about Content Security Policy (CSP) directives you should add when using Adobe Target at.js 2.1 or later.
keywords: content security policy;csp;at.js;whitelist;flicker;pre-hide;pre-hiding;prehiding
seo-description: Information about Content Security Policy (CSP) directives you should add when using Adobe Target at.js 2.1 or later.
seo-title: Content Security Policies (CSP)
solution: Target
subtopic: 入门指南
title: Content Security Policy (CSP) directives
topic: Standard
translation-type: tm+mt
source-git-commit: df40d69676cea586451e3b64b56ef602da91173f

---


# Content Security Policy (CSP) directives

If you are using Content Security Policy (CSP) for your Target implementation, you should add the following CSP directives when using at.js 2.1 or later:[](https://en.wikipedia.org/wiki/Content_Security_Policy)[](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)

* `connect-src` with  whitelisted. `*.tt.omtrdc.net`必须允许向边缘发送网络请 [!DNL Target] 求。
* `style-src unsafe-inline`。预隐藏和闪烁控制必需。
* `script-src unsafe-inline`.  允许执行可能是HTML选件一部分的JavaScript时必需。
