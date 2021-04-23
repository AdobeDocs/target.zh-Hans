---
keywords: 内容安全策略；csp;at.js;whitelist;允许列表；闪烁；预隐藏；预隐藏；预隐藏
description: 了解使用Adobe Target时应添加的Content Security Policy(CSP)指令。
title: 如何 [!DNL Target] 处理内容安全策略(CSP)?
feature: 隐私和安全
role: Developer
exl-id: 31457b16-ed21-4540-8d0c-abfb49d1fbe9
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 0%

---

# 内容安全策略(CSP)指令

如果您正在使用[Content Security Policy](https://en.wikipedia.org/wiki/Content_Security_Policy)(CSP)来实现[!DNL Adobe Target]，则在使用[at.js 2.1或更高版本](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)时，应添加以下CSP指令：

* `connect-src`  `*.tt.omtrdc.net` 列入允许列表。必须允许对[!DNL Target]边缘进行网络请求。
* `style-src unsafe-inline`。预隐藏和闪烁控制所需。
* `script-src unsafe-inline`.  允许执行可能是HTML优惠一部分的JavaScript时必需。
