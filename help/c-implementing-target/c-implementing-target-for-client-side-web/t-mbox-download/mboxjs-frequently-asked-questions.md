---
keywords: mbox.js FAQ;mbox.js 常见问题解答;document.write;tt.omtrdc.net;解析器阻塞
description: 了解旧版mbox.js的Adobe Target实施。 迁移到Adobe Experience Platform Web SDK(AEP Web SDK)或at.js的最新版本。
title: 有关 [!DNL Target] mbox.js的一些常见问题？
feature: at.js
role: Developer
exl-id: 0e207896-d45b-45f9-8556-6532fda72a45
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 75%

---

# mbox.js 常见问题解答

有关 mbox.js 的常见问题解答。

>[!IMPORTANT]
>
>**mbox.js 生命周期结束**：从 2021 年 3 月 31 日起，[!DNL Adobe Target] 将不再支持 mbox.js 库。2021 年 3 月 31 日之后，所有从 mbox.js 进行的调用都将失败，并影响您通过提供默认内容而运行 [!DNL Target] 活动的页面。
>
>我们建议所有客户在此日期之前迁移到新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript库的最新版本，以避免您的网站出现任何潜在问题。 有关详细信息，请参阅[概述：为客户端 Web 实现 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

## 为何 mbox 没有在我的网页上触发？ {#section_4BA5DA424B734324AAB51E4588FA50F5}

 客户有时会将基于云的实例与 [!DNL Target]Target 结合使用来进行测试或简单的概念验证。这些域以及其他许多域均是[公共后缀列表](https://publicsuffix.org/list/public_suffix_list.dat)的一部分。

除非使用 targetGlobalSettings() 来自定义 `cookieDomain` 设置，否则在使用这些域时，新式浏览器将不会保存 Cookie。有关更多信息，请参阅[结合使用基于云的实例和 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/targeting-using-cloud-based-instances.md#concept_A2077766948F4EA081CE592D8998F566)。

## [!DNL Target]服务器调用所转到的域tt.omtrdc.net是什么域？ {#section_999C29940E8B4CAD8A957A6B1D440317}

[!DNL tt.omtrdc.net] 是 Adobe 的边缘网络的域名，用于接收 Target 的所有服务器调用。

## 为什么 at.js 和 mbox.js 不使用 HttpOnly 和 Secure Cookie 标记？ {#section_74527E3B41B54B0A83F217C3E664ED1F}

HttpOnly 只能通过服务器端代码进行设置。Target Cookie（例如 mbox）通过 JavaScript 代码创建和保存，因此 Target 无法使用 HttpOnly Cookie 标记。

只有在通过 HTTPS 加载页面时，才能通过 JavaScript 设置 Secure 标记。如果页面最初通过 HTTP 加载，则 JavaScript 无法设置此标记。此外，如果使用 Secure 标记，则 Cookie 将只在 HTTPS 页面上可用。

为确保 Target 能够正确跟踪用户，并且还由于 Cookie 是在客户端生成的，Target 不会使用这些标记中的任何一个。
