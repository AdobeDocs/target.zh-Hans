---
description: 可动态测试电子邮件中的图像，甚至在用户打开电子邮件后即时更改这些图像。
keywords: 电子邮件;adbox
seo-description: 可动态测试电子邮件中的图像，甚至在用户打开电子邮件后即时更改这些图像。
seo-title: 测试电子邮件图像 Adbox
solution: Target
title: 测试电子邮件图像 Adbox
topic: 推荐
uuid: d0710adb-4649-4b57-9b70-4b49d43fa591
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 测试电子邮件图像 Adbox{#test-an-email-image-adbox}

可动态测试电子邮件中的图像，甚至在用户打开电子邮件后即时更改这些图像。

可以在电子邮件中使用重定向器来跟踪点击量，并动态控制用户到达的登陆页面。

电子邮件图像测试通过使用 adbox 的修改版本实现。由于电子邮件客户端不允许设置 Cookie，因此必须为每个电子邮件生成一个唯一的标识符。该数字将被附加到 adbox URL 及任意在电子邮件中用于跟踪点击的重定向器上。

>[!NOTE]
>
>在电子邮件打开时，虽然 Target 可以在技术上提供图像优化，但每个电子邮件客户端都会以不同方式处理缓存，因此成功情况也有所不同。无论使用哪个电子邮件服务提供商，最终用户用于打开电子邮件的电子邮件客户端（Gmail 应用程序、Outlook、Hotmail 等）都会确定是否在打开时实际获取图像。例如，Gmail 会缓存大部分内容，因此最终用户看到的图像取决于 Gmail 何时选择调用和缓存图像。

**电子邮件图像 adbox 的示例代码：**

```
<img src=“https://{clientcode}.tt.omtrdc.net/m2/​{clientcode}/ubox/​image?
mbox={email_header}&
mboxDefault=​{http%3A%2F%2Fwww.domain.com%2Fheader.jpg}&
mboxXDomain=disabled&
mboxSession={123456}&
mboxPC={123456}” border=“0"/>
```

示例代码中的以下值由您指定：

| 值 | 描述 |
|--- |--- |
| clientcode | 您公司的客户端代码。可在 at.js 或 mbox.js 中查找此代码，此代码以 `clientCode='yourclientcode'` 形式列出。此代码为全小写的字母，且无特殊字符。 |
| image | 选件类型。对于图形广告，此代码始终为“image”；而对于重定向器，此代码始终为“page”。 |
| email_header | adbox 的名称。 |
| `mboxDefault=http%3A%2F%2Fwww.domain.com%2Fheader.jpg` | 必需。用适用于您的adbox的相应默认内容替换URL。它必须为绝对引用，且必须为 URL 编码。 |
| `mboxXDomain=disabled` | 告知 Target 不要尝试设置 Cookie。 |
| `mboxSession=123456` 和 `mboxPC=123456` | Target 需要使用这两个值将此用户的配置文件与您站点中的现有配置文件进行合并。123456 为每封电子邮件生成的唯一标识符。该值将被动态插入到每一个 adbox 及重定向器 URL 中。每封电子邮件的这一数字必须是唯一的。如果每周向 1000 名用户发送电子邮件，则必须生成 1000 个具有唯一性的 ID。<br>每封电子邮件的唯一标识符需要分配给每一个 adbox 及重定向器 URL 中的 mboxSession 和 mboxPC。建议该标识符采用 timestamp-NNNNN 格式，其中 NNNNN 是随机的 5 位数字，任何字母数字格式都适用。一些电子邮件群发服务及所有编程语言都可以生成此类唯一标识符。 |
