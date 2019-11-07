---
keywords: mbox.js FAQ;mbox.js 常见问题解答;document.write;tt.omtrdc.net;解析器阻塞
description: 有关 mbox.js 的常见问题解答。
title: mbox.js 常见问题解答
subtopic: 入门指南
uuid: af3105ab-87d9-4dbf-a380-b72788928958
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# mbox.js 常见问题解答{#mbox-js-frequently-asked-questions}

有关 mbox.js 的常见问题解答。

## mbox.js 对页面加载时间有何影响？{#section_90B3B94FE0BF4B369577FCB97B67F089}

有关更多信息，请参阅 [at.js 的好处](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits)。

## 使用 mbox.js 和 document.write 时，我的 Google Chrome 中为何会显示“解析器阻塞”警告消息？{#section_355A3A5BF02F42EEB8271C96EF41590A}

在很多情况下，mbox.js 文件中会使用 `document.write` 函数，如果在这些情况中使用 Chrome，则会显示此控制台消息。这是一条警告消息，应该不会对您的活动设置过程造成影响。

防止出现这种情况的最好方法是[将您的 Target 实施迁移到 at.js JavaScript 库](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA)，该库不会用到 `document.write` 函数。与使用 mbox.js 相比，使用 at.js 可以带来很多益处。有关更多信息，请参阅 [at.js 常见问题解答](../../../c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/target-atjs-faq.md#concept_D6EFE8D84A06476DB5ABD494D7E8C769)。

## 为何 mbox 没有在我的网页上触发？{#section_4BA5DA424B734324AAB51E4588FA50F5}

 客户有时会将基于云的实例与 [!DNL Target]Target 结合使用来进行测试或简单的概念验证。这些域以及其他许多域均是[公共后缀列表](https://publicsuffix.org/list/public_suffix_list.dat)的一部分。

除非使用 targetGlobalSettings() 来自定义 `cookieDomain` 设置，否则在使用这些域时，新式浏览器将不会保存 Cookie。有关更多信息，请参阅[结合使用基于云的实例和 Target](../../../c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/targeting-using-cloud-based-instances.md#concept_A2077766948F4EA081CE592D8998F566)。

## Target 服务器调用所转到的域 tt.omtrdc.net 是什么域？{#section_999C29940E8B4CAD8A957A6B1D440317}

[!DNL tt.omtrdc.net] 是 Adobe 的边缘网络的域名，用于接收 Target 的所有服务器调用。

## 为什么 at.js 和 mbox.js 不使用 HttpOnly 和 Secure Cookie 标记？{#section_74527E3B41B54B0A83F217C3E664ED1F}

HttpOnly 只能通过服务器端代码进行设置。Target Cookie（例如 mbox）通过 JavaScript 代码创建和保存，因此 Target 无法使用 HttpOnly Cookie 标记。

只有在通过 HTTPS 加载页面时，才能通过 JavaScript 设置 Secure 标记。如果页面最初通过 HTTP 加载，则 JavaScript 无法设置此标记。此外，如果使用 Secure 标记，则 Cookie 将只在 HTTPS 页面上可用。

为确保 Target 能够正确跟踪用户，并且还由于 Cookie 是在客户端生成的，Target 不会使用这些标记中的任何一个。
