---
keywords: 内容安全策略；csp;at.js；白名单；闪烁；预隐藏；预隐藏；预隐藏
description: 有关Content Security Policy(CSP)指令的信息，在使用Adobe Target at.js 2.1或更高版本时应添加这些指令。
title: 内容安全策略(CSP)
subtopic: 入门指南
topic: Standard
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 内容安全策略(CSP)指令

如果您使用 [Content Security Policy](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP)进行Target实施，则在使用 [at.js 2.1或更高版本时应添加以下CSP指令](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` 已列入 `*.tt.omtrdc.net` 白名单。 必须允许向边缘发送网络请 [!DNL Target] 求。
* `style-src unsafe-inline`。预隐藏和闪烁控制必需。
* `script-src unsafe-inline`.  允许执行可能是HTML选件一部分的JavaScript时必需。
