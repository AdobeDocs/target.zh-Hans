---
keywords: mbox.js 高级设置;客户端;服务器域;xdomain;压缩等级;客户端会话 ID 支持;secureOnly;客户端 PC ID 支持;传递页面;引荐 URL;流量级别;流量持续时间;mboxParameters() 函数体;mboxSupported() 函数体;mboxCookieDomain() 函数体;额外的 JavaScript;SiteCatalyst 插件;以自解压 JavaScript 文件形式获取 mbox.js;闪烁;主体隐藏;隐藏主体
description: 此信息可帮助您在 mbox.js“设置”页面上设定多个设置。
title: 配置 mbox.js
uuid: e79c7af7-f8bd-4e2b-8e67-b04eddf0c65d
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 配置 mbox.js{#configure-mbox-js}

此信息可帮助您在 mbox.js“设置”页面上设定多个设置。

[!DNL mbox.js] 函数库的默认设置可满足大多数 [!DNL Target] 客户的需求。

如有需要，可咨询客服专员更改 [!DNL mbox.js] 设置。

以下设置可供使用：

## 客户端

您帐户的客户代码。

查看[!UICONTROL 设置 &gt; 实施 &gt; 编辑 Mbox.js 设置]时，顶部的“客户端”即是您帐户的客户端代码。

## 超时

Target 请求超时。

查看[!UICONTROL 设置 &gt; 实施 &gt; 编辑 Mbox.js 设置]时，“压缩等级”后面的“超时”即是您的 Target 请求超时。默认情况下会将此值设置为 15 秒，但是我们建议将此值设置为介于 2 秒到 5 秒之间的某个值。

## XDomain

确定浏览器是在您自己的域中设置 Cookie（第一方 Cookie），还是在 Target 域中设置 Cookie，亦或在两者中都设置 Cookie。

更改此设置对 mbox.js 和 at.js 都会造成影响。

## 压缩等级

确定 mbox.js 库文件的压缩程度。增加压缩等级可缩短页面加载时间。

## mboxParameters() 函数体

返回要传递给每个 mbox 调用的额外参数。

例如：

return "test=123";

## mboxSupported() 函数体

返回 false 以排除指定用户。

例如：

return !navigator.userAgent.indexOf('Safari') != -1;

可以接受或排除下列浏览器：

* IE 5.0 或更高版本 (Windows)
* Netscape 5.0 或更高版本（Mac、Windows、Linux）
* Safari 1.2.4 或更高版本 (Mac)
* Mozilla Firefox 1.0 或更高版本（Mac、Windows、Linux）

## mboxCookieDomain() 函数体

返回域的描述字符串，以设置第一方 Cookie。

例如：

return "YOUR-DOMAIN";

## 额外 JavaScript

包含您想要在每个页面上执行的任意附加 JavaScript。

## SiteCatalyst 插件

启用 Analytics Target 插件。

启用后，Analytics 插件会在 mbox.js 中生成插件代码。此操作将带有 Analytics 标记的所有页面上的 Analytics 标记信息作为 mbox 请求发送给 Target 服务器。

请注意，仍必须在页面上引用 Analytics 插件。

## secureOnly

指示 mbox.js 是应该仅使用 HTTPS，还是可以根据页面协议在 HTTP 和 HTTPS 之前进行切换。这是一项高级设置，其默认值为 False。