---
keywords: 内容安全策略；CSP;at.js；白名单；允许列表；闪烁；预隐藏；预隐藏；预隐藏
description: 了解使用Adobe Target时应添加的内容安全策略(CSP)指令。
title: 操作方法 [!DNL Target] 处理内容安全策略(CSP)?
feature: Privacy & Security
role: Developer
exl-id: 31457b16-ed21-4540-8d0c-abfb49d1fbe9
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 5%

---

# 内容安全策略 (CSP) 指令

如果您使用 [内容安全策略](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP) [!DNL Adobe Target] 实施中，您应在使用 [at.js 2.1或更高版本](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` with `*.tt.omtrdc.net` 列入允许列表。 允许对 [!DNL Target] 边缘。
* `style-src unsafe-inline`。预隐藏和闪烁控制需要。
* `script-src unsafe-inline`.  允许执行可能属于HTML选件的JavaScript时需要。
