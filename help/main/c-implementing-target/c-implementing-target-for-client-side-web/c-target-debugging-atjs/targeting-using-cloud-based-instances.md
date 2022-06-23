---
keywords: 云实例;公共后缀列表;公共后缀;Cookie;第一方 Cookie;azurewebsites.net;cloudapp.net;amazonaws.com;cloudfront.net;herokuapp.com;firebaseapp.com;targetGlobalSettings;cookieDomain
description: 探索客户在使用基于云的实例来测试Adobe时遇到的问题（与解决方案有关） [!DNL Target] 或用于概念验证。
title: 我能用 [!DNL Target] 是否使用基于云的实例？
feature: at.js
role: Developer
exl-id: 220371a9-ba57-4e67-b82f-8fec6f9d2833
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 64%

---

# 结合使用基于云的实例和 Target

此信息介绍了客户在使用基于云的实例来测试 [!DNL Adobe Target] 时遇到的一些问题。

 客户有时会将基于云的实例与 [!DNL Target]Target 结合使用来进行测试或简单的概念验证。这些实例可能包含以下域：

`azurewebsites.net`、`cloudapp.net`、`amazonaws.com`、`cloudfront.net`、`herokuapp.com` 或 `firebaseapp.com`

这些域以及其他许多域均是[公共后缀列表](https://publicsuffix.org/list/public_suffix_list.dat)的一部分。

**问题：**&#x200B;如果您使用这些域，新式浏览器不会保存 Cookie。

的 [!DNL at.js] JavaScript库使用Cookie来跟踪用户，以确保 [!DNL Target] 始终提供一致的体验。 如果 [!DNL Target] JavaScript库无法保存Cookie， [!DNL Target] 请求处于禁用状态。

**解决方案：**&#x200B;最佳做法是，如果您打算将基于云的实例与公共后缀列表中包含的域结合使用，请务必自定义 `cookieDomain` 设置。有关更多信息，请参阅 [targetGlobalSettings()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)。
