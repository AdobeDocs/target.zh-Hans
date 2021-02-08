---
keywords: mbox.js 高级设置;客户端;服务器域;xdomain;压缩等级;客户端会话 ID 支持;secureOnly;客户端 PC ID 支持;传递页面;引荐 URL;流量级别;流量持续时间;mboxParameters() 函数体;mboxSupported() 函数体;mboxCookieDomain() 函数体;额外的 JavaScript;SiteCatalyst 插件;以自解压 JavaScript 文件形式获取 mbox.js;闪烁;主体隐藏;隐藏主体
description: 了解旧版mbox.js对Adobe Target的实施。 迁移至Adobe Experience PlatformWeb SDK(AEP Web SDK)或最新版at.js。
title: 如何配置目标mbox.js库？
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 70%

---


# 配置 mbox.js

此信息可帮助您在 mbox.js“设置”页面上设定多个设置。

>[!IMPORTANT]
>
>**mbox.js终止使用**:2021年3月31日 [!DNL Adobe Target] 将不再支持mbox.js库。2021年3月31日之后，mbox.js发出的所有调用将正常失败，并会通过提供默认内容影响[!DNL Target]活动运行的页面。
>
>我们建议所有客户在此日期之前迁移到新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript库的最新版本，以避免您的站点出现任何潜在问题。 有关详细信息，请参阅[概述：实现客户端web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)的目标。

[!DNL mbox.js] 函数库的默认设置可满足大多数 [!DNL Target] 客户的需求。

如有需要，可咨询客服专员更改 [!DNL mbox.js] 设置。

以下设置可供使用：

## 客户端

您帐户的客户代码。

查看[!UICONTROL 管理>实施]时，顶部的客户端是您帐户的客户端代码。

## 超时

Target 请求超时。

查看[!UICONTROL 管理>实施]时，超时（秒）设置是目标请求超时。 默认情况下会将此值设置为 15 秒，但是我们建议将此值设置为介于 2 秒到 5 秒之间的某个值。

## XDomain

确定浏览器是在您自己的域中设置 Cookie（第一方 Cookie），还是在 Target 域中设置 Cookie，亦或在两者中都设置 Cookie。

更改此设置对 mbox.js 和 at.js 都会造成影响。

## 压缩等级

确定 mbox.js 库文件的压缩程度。增加压缩等级可缩短页面加载时间。

## mboxParameters() 函数体

返回要传递给每个 mbox 调用的额外参数。

例如：

return &quot;test=123&quot;;

## mboxSupported() 函数体

返回 false 以排除指定用户。

例如：

return !navigator.userAgent.indexOf(&#39;Safari&#39;) != -1;

可以接受或排除下列浏览器：

* IE 5.0 或更高版本 (Windows)
* Netscape 5.0 或更高版本（Mac、Windows、Linux）
* Safari 1.2.4 或更高版本 (Mac)
* Mozilla Firefox 1.0 或更高版本（Mac、Windows、Linux）

## mboxCookieDomain() 函数体

返回域的描述字符串，以设置第一方 Cookie。

例如：

return &quot;YOUR-DOMAIN&quot;;

## 额外 JavaScript

包含您想要在每个页面上执行的任意附加 JavaScript。

## SiteCatalyst 插件

启用 Analytics Target 插件。

启用后，Analytics 插件会在 mbox.js 中生成插件代码。此操作将带有 Analytics 标记的所有页面上的 Analytics 标记信息作为 mbox 请求发送给 Target 服务器。

请注意，仍必须在页面上引用 Analytics 插件。

## secureOnly

指示 mbox.js 是应该仅使用 HTTPS，还是可以根据页面协议在 HTTP 和 HTTPS 之前进行切换。这是一项高级设置，其默认值为 False。