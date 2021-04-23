---
keywords: QA;预览;书签;预览链接
description: 了解如何使用Adobe [!DNL Target] QA bookmarklet to force [!DNL Target] 从QA模式中释放您。
title: 如何使用活动 QA书签？
feature: 活动
exl-id: dbfe59eb-6853-4909-abf1-e5630e979a98
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 28%

---

# 活动 QA 书签

帮助您使用[!DNL Target] QA书签以强制[!DNL Target]从QA模式中释放您的信息。

>[!NOTE]
>
>创建书签的过程因浏览器类型和版本而异。请参阅浏览器的帮助或在 Internet 上搜索具体说明。

## 活动at.js 1的QA书签。*x*

由于 [QA 模式](/help/c-activities/c-activity-qa/activity-qa.md)具有粘滞性，因此以 QA 模式浏览网站后，您必须终止 会话，或者需要让 将您从 QA 模式中释放出来，然后才能像普通访客一样查看您的网站。[!DNL Target][!DNL Target]使用QA [!DNL Target]书签工具将您自己强制退出QA模式。

要使用[!DNL Target] QA书签工具，请创建一个包含以下JavaScript代码的书签工具，并将其添加到浏览器的“书签工具栏”中：

```javascript
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

您还可以通过在站点上加载包含`at_preview_token`参数且值为空的页面，手动将自己强制退出QA模式。

例如：

`https://www.mysite.com/?at_preview_token=`

## 活动 QA书签工具(at.js 2)*x*

与at.js 1不同。*x*,at.js 2。*xdoes* 不支持第三方cookie，并且QA模式仅对第一方域具有粘性（通过at.js设置的第一方cookie）。因此，在at.js 2中。*x*,QA模式会话仅在客户端进行管理，不会向目标发送QA模式Cookie。

要使用[!DNL Target] QA书签工具，请创建一个包含以下JavaScript代码的书签工具，并将其添加到浏览器的“书签工具栏”中：

```javascript
javascript:(
    function () {
        var AT_QA_MODE = 'at_qa_mode=';
        var isSet = document.cookie.split(';').some(function (cookie) {
            return cookie.trim().startsWith(AT_QA_MODE);
        });
        if (isSet) {
            document.cookie = AT_QA_MODE + '; Path=/; Max-Age=-0;';
            var url = window.location.href.split('at_preview_token',2)[0];
            window.open(url.substring(0, url.length - 1), '_self', 'noreferrer');
        }
    })();
```

## 使用活动 QA书签

单击浏览器工具栏上的书签。
