---
keywords: 云实例;公共后缀列表;公共后缀;Cookie;第一方 Cookie;azurewebsites.net;cloudapp.net;amazonaws.com;cloudfront.net;herokuapp.com;firebaseapp.com;targetGlobalSettings;cookieDomain
description: 探索客户在使用基于云的实例测试Adobe Target或用于概念验证时面临的问题（使用解决方案）。
title: 我是否可以对基于云的实例使用目标?
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 81%

---


# 结合使用基于云的实例和 Target{#use-cloud-based-instances-with-target}

此信息介绍了客户在使用基于云的实例来测试 [!DNL Adobe Target] 时遇到的一些问题。

 客户有时会将基于云的实例与 [!DNL Target]Target 结合使用来进行测试或简单的概念验证。这些实例可能包含以下域：

`azurewebsites.net`、`cloudapp.net`、`amazonaws.com`、`cloudfront.net`、`herokuapp.com` 或 `firebaseapp.com`

这些域以及其他许多域均是[公共后缀列表](https://publicsuffix.org/list/public_suffix_list.dat)的一部分。

**问题：**&#x200B;如果您使用这些域，新式浏览器不会保存 Cookie。

[!DNL at.js] 和 [!DNL mbox.js] JavaScript 库需要使用 Cookie 来跟踪用户，以确保 [!DNL Target] 始终提供一致的体验。如果 [!DNL Target] JavaScript 库无法保存 Cookie，则 [!DNL Target] 请求会被禁用。

**解决方案：**&#x200B;最佳做法是，如果您打算将基于云的实例与公共后缀列表中包含的域结合使用，请务必自定义 `cookieDomain` 设置。有关更多信息，请参阅 [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)。
