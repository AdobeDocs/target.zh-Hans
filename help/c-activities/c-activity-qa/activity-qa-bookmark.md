---
description: 此信息可帮助您使用 Target QA 书签强制 Target 将您从 QA 模式中释放出来。
keywords: QA;预览;书签;预览链接
seo-description: 此信息可帮助您使用 Target QA 书签强制 Target 将您从 QA 模式中释放出来。
seo-title: 活动 QA 书签
solution: Target
title: 活动 QA 书签
topic: Advanced,Standard,Classic
uuid: 2890e215-16c9-4b22-a8eb-732cd6efede3
translation-type: tm+mt
source-git-commit: af3e1d9c6db4733b6eb37f8232b164be65c4dd2e

---


# 活动 QA 书签{#activity-qa-bookmarklet}

此信息可帮助您使用 Target QA 书签强制 Target 将您从 QA 模式中释放出来。

由于 [QA 模式](../../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40)具有粘滞性，因此以 QA 模式浏览网站后，您必须终止 Target 会话，或者需要让 Target 将您从 QA 模式中释放出来，然后才能像普通访客一样查看您的网站。可使用 Target QA 书签强制自己退出 QA 模式。

要使用 Target QA 书签，请创建包含以下 JavaScript 代码的书签，并将其添加到浏览器的书签工具栏：

```
javascript:(
    function () {
        if (window.location.href.indexOf('?') != -1) {
            var parts = window.location.href.split('at_preview_token',2);
            if (parts.length > 1) {
                window.location.href = parts[0].concat('at_preview_token=');
            } else {
                window.location.href = window.location.href.concat("&at_preview_token=")
            }
        } else {
            window.location.href = window.location.href.concat("?at_preview_token=")
        }
    }
)();
```

随后，该书签应该会显示在工具栏中，以供重复使用。

>[!NOTE]
>
>创建书签的过程因浏览器类型和版本而异。请参阅浏览器的帮助或在 Internet 上搜索具体说明。

您也可以手动强制自己退出 QA 模式，方法是在网站上使用具有空值的 `at_preview_token` 参数（例如 `https://www.mysite.com/?at_preview_token=`）来加载页面。
