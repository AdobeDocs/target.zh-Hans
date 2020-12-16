---
keywords: content security policy;csp;at.js;whitelist;allowlist;flicker;pre-hide;pre-hiding;prehiding
description: 有关使用Adobe Targetat.js 2.1或更高版本时应添加的内容安全策略(CSP)指令的信息。
title: 内容安全策略(CSP)
feature: privacy and security
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 0%

---


# 内容安全策略(CSP)指令

如果您使用[内容安全策略](https://en.wikipedia.org/wiki/Content_Security_Policy)(CSP)进行目标实现，则应在使用[at.js 2.1或更高版本](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)时添加以下CSP指令：

* `connect-src` 和 `*.tt.omtrdc.net` 列入允许列表。必须允许向[!DNL Target]边缘发送网络请求。
* `style-src unsafe-inline`。预隐藏和闪烁控制所需。
* `script-src unsafe-inline`.  允许执行可能是HTML优惠的一部分的JavaScript时必需。
