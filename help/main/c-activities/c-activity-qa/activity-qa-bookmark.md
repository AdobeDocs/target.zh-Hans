---
keywords: QA;预览;书签;预览链接
description: 了解如何使用Adobe [!DNL Target] 强制使用QA书签 [!DNL Target] 从QA模式中释放您。
title: 如何使用活动QA书签？
feature: Activities
exl-id: dbfe59eb-6853-4909-abf1-e5630e979a98
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 27%

---

# 活动 QA 书签

可帮助您使用 [!DNL Target] 强制使用QA书签 [!DNL Target] 从QA模式中释放您。

>[!NOTE]
>
>创建书签的过程因浏览器类型和版本而异。请参阅浏览器的帮助或在 Internet 上搜索具体说明。

## at.js 1的活动QA书签。*x*

由于 [QA 模式](/help/main/c-activities/c-activity-qa/activity-qa.md)具有粘滞性，因此以 QA 模式浏览网站后，您必须终止 会话，或者需要让 将您从 QA 模式中释放出来，然后才能像普通访客一样查看您的网站。[!DNL Target][!DNL Target]使用QA [!DNL Target] 书签强制自己退出QA模式。

使用 [!DNL Target] QA书签，创建包含以下JavaScript代码的小书签，并将其添加到浏览器的“书签”工具栏：

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

您也可以手动强制自己退出QA模式，方法是在网站上使用 `at_preview_token` 参数。

例如：

`https://www.mysite.com/?at_preview_token=`

## at.js 2.*x*

与at.js 1.*x*, at.js 2.*x* 不支持第三方Cookie，并且QA模式仅对第一方域具有粘滞性（通过at.js设置的第一方Cookie）。 因此，在at.js 2.*x*，则QA模式会话仅在客户端进行管理，并且不会将QA模式Cookie发送到Target。

使用 [!DNL Target] QA书签，创建包含以下JavaScript代码的小书签，并将其添加到浏览器的“书签”工具栏：

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

## 使用活动QA书签

单击浏览器工具栏上的小书签。
