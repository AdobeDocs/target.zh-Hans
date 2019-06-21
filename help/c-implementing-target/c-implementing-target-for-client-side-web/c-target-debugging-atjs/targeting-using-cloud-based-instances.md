---
description: 此信息介绍了客户在使用基于云的实例来测试 Adobe Target 时遇到的一些问题。
keywords: 云实例;公共后缀列表;公共后缀;Cookie;第一方 Cookie;azurewebsites.net;cloudapp.net;amazonaws.com;cloudfront.net;herokuapp.com;firebaseapp.com;targetGlobalSettings;cookieDomain
seo-description: 此信息介绍了客户在使用基于云的实例来测试 Adobe Target 时遇到的一些问题。
seo-title: 结合使用基于云的实例和 Target
solution: Target
title: 结合使用基于云的实例和 Target
uuid: dcaba49e-7567-4970-bb9a-19377aff7d38
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 结合使用基于云的实例和 Target{#use-cloud-based-instances-with-target}

此信息介绍了客户在使用基于云的实例来测试 [!DNL Adobe Target] 时遇到的一些问题。

 客户有时会将基于云的实例与 [!DNL Target]Target 结合使用来进行测试或简单的概念验证。这些实例可能包含以下域：

`azurewebsites.net`、`cloudapp.net`、`amazonaws.com`、`cloudfront.net`、`herokuapp.com` 或 `firebaseapp.com`

这些域以及许多其他域均包含在[公共后缀列表](https://publicsuffix.org/list/public_suffix_list.dat)中。

**问题：** 如果您使用这些域，新式浏览器不会保存 Cookie。

[!DNL at.js] 和 [!DNL mbox.js] JavaScript 库需要使用 Cookie 来跟踪用户，以确保 [!DNL Target] 始终提供一致的体验。如果 [!DNL Target] JavaScript 库无法保存 Cookie，则 [!DNL Target] 请求会被禁用。

**解决方案：** 最佳做法是，如果您打算将基于云的实例与公共后缀列表中包含的域结合使用，请务必自定义 `cookieDomain` 设置。有关更多信息，请参阅 [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)。
