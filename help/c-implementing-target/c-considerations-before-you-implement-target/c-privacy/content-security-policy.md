---
description: 有关在使用Adobe Target at. js2.1或更高版本时应添加的内容安全策略(CSP)指令的信息。
keywords: 内容安全策略；csp；at. js；白名单；闪烁；pre-hide；预隐藏；隐藏
seo-description: 有关在使用Adobe Target at. js2.1或更高版本时应添加的内容安全策略(CSP)指令的信息。
seo-title: 内容安全策略(CSP)
solution: Target
subtopic: 入门指南
title: Content Security Policy(CSP)指令
topic: Standard
translation-type: tm+mt
source-git-commit: df40d69676cea586451e3b64b56ef602da91173f

---


# Content Security Policy(CSP)指令

如果您正在 [使用Target实施的内容安全策略](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP)，则在. js2.1或更高版本上使用时 [应添加以下CSS指令](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)：

* `connect-src``*.tt.omtrdc.net` 已列入白名单。必需允许网络请求 [!DNL Target] 边缘。
* `style-src unsafe-inline`。预隐藏和闪烁控件所必需的。
* `script-src unsafe-inline`.  要求执行可能是HTML选件一部分的JavaScript执行。
