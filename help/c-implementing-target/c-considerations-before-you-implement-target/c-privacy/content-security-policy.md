---
keywords: 内容安全策略；csp;at.js;whitelist;允许列表；闪烁；预隐藏；预隐藏；预隐藏
description: 了解使用Adobe Target时应添加的内容安全策略(CSP)指令。
title: 目标如何处理内容安全策略(CSP)?
feature: Privacy & Security
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 0%

---


# 内容安全策略(CSP)指令

如果您正在使用[内容安全策略](https://en.wikipedia.org/wiki/Content_Security_Policy)(CSP)来实现[!DNL Adobe Target]，则应在使用[at.js 2.1或更高版本](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)时添加以下CSP指令：

* `connect-src` 和 `*.tt.omtrdc.net` 列入允许列表。必须允许向[!DNL Target]边缘发送网络请求。
* `style-src unsafe-inline`。预隐藏和闪烁控制所需。
* `script-src unsafe-inline`.  允许执行可能是HTML优惠的一部分的JavaScript时必需。
