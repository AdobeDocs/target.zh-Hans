---
keywords: cloud instances;public suffix list;public suffix;cookie;first-party cookie;1st-party cookie;azurewebsites.net;cloudapp.net;amazonaws.com;cloudfront.net;herokuapp.com;firebaseapp.com;targetGlobalSettings;cookieDomain
description: 此信息介绍了客户在使用基于云的实例来测试 Adobe Target 时遇到的一些问题。
title: 结合使用基于云的实例和 Target
feature: client-side
uuid: dcaba49e-7567-4970-bb9a-19377aff7d38
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 95%

---


# 结合使用基于云的实例和 Target{#use-cloud-based-instances-with-target}

此信息介绍了客户在使用基于云的实例来测试 [!DNL Adobe Target] 时遇到的一些问题。

 客户有时会将基于云的实例与 [!DNL Target]Target 结合使用来进行测试或简单的概念验证。这些实例可能包含以下域：

`azurewebsites.net`、`cloudapp.net`、`amazonaws.com`、`cloudfront.net`、`herokuapp.com` 或 `firebaseapp.com`

这些域以及其他许多域均是[公共后缀列表](https://publicsuffix.org/list/public_suffix_list.dat)的一部分。

**问题：**&#x200B;如果您使用这些域，新式浏览器不会保存 Cookie。

[!DNL at.js] 和 [!DNL mbox.js] JavaScript 库需要使用 Cookie 来跟踪用户，以确保 [!DNL Target] 始终提供一致的体验。如果 [!DNL Target] JavaScript 库无法保存 Cookie，则 [!DNL Target] 请求会被禁用。

**解决方案：**&#x200B;最佳做法是，如果您打算将基于云的实例与公共后缀列表中包含的域结合使用，请务必自定义 `cookieDomain` 设置。有关更多信息，请参阅 [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)。
