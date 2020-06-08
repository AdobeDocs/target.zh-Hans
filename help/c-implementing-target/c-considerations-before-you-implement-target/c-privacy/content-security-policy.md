---
keywords: content security policy;csp;at.js;whitelist;allowlist;flicker;pre-hide;pre-hiding;prehiding
description: 有关使用Adobe目标at.js 2.1或更高版本时应添加的内容安全策略(CSP)指令的信息。
title: 内容安全策略(CSP)
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: cf69c1d8472088d5f6a6b7250bedd1048cac5c10
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 0%

---


# 内容安全策略(CSP)指令

如果您正在使 [用Content Security](https://en.wikipedia.org/wiki/Content_Security_Policy) Policy(CSP)进行目标实施，则在使用at.js 2.1或更高版本时 [应添加以下CSP指令](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` 和 `*.tt.omtrdc.net` allowlisted。 允许对边缘进行网络请 [!DNL Target] 求。
* `style-src unsafe-inline`。预隐藏和闪烁控制所需。
* `script-src unsafe-inline`.  允许执行可能是HTML优惠的一部分的JavaScript时必需。
