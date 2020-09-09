---
keywords: qa;preview;bookmarklet;preview links
description: 帮助您使用Adobe TargetQA书签强制目标从QA模式中释放您的信息。
title: 活动Adobe TargetQA书签
feature: qa
topic: Advanced,Standard,Classic
uuid: 2890e215-16c9-4b22-a8eb-732cd6efede3
translation-type: tm+mt
source-git-commit: 620bb6dfbe160cf27ef5de9199c3d91fb806f316
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 26%

---


# 活动 QA 书签{#activity-qa-bookmarklet}

Information to help you use the [!DNL Target] QA bookmarklet to force [!DNL Target] to release you from QA mode.

>[!NOTE]
>
>创建书签的过程因浏览器类型和版本而异。请参阅浏览器的帮助或在 Internet 上搜索具体说明。

## 活动at.js 1的QA书签。*x*

由于 [QA 模式](../../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40)具有粘滞性，因此以 QA 模式浏览网站后，您必须终止 会话，或者需要让 将您从 QA 模式中释放出来，然后才能像普通访客一样查看您的网站。[!DNL Target][!DNL Target]Use the QA [!DNL Target] bookmarklet to force yourself out of QA mode.

To use the [!DNL Target] QA bookmarklet, create a bookmarklet containing the following JavaScript code and add it to your browser&#39;s Bookmarks Toolbar:

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

## 活动at.js 2的QA书签。*x*

与at.js 1不同。*x*,at.js 2.*x* 不支持第三方cookie，并且QA模式仅对第一方域具有粘性（通过at.js设置的第一方cookie）。 因此，在at.js 2中。*x*,QA模式会话仅在客户端进行管理，不向目标发送QA模式cookie。

To use the [!DNL Target] QA bookmarklet, create a bookmarklet containing the following JavaScript code and add it to your browser&#39;s Bookmarks Toolbar:

```
javascript:(
    function () {
        var AT_QA_MODE = 'at_qa_mode=';
        var isSet = document.cookie.split(';').some(function (cookie) {
            return cookie.trim().startsWith(AT_QA_MODE);
        });
        if (isSet) {
            document.cookie = AT_QA_MODE + '; Max-Age=-99999999;';
            var url = window.location.href.split('at_preview_token',2)[0];
            window.location.href = url.substring(0, url.length - 1);
        }
    })();
```

## 使用活动QA书签

单击浏览器工具栏上的书签。

You can also manually force yourself out of QA mode by loading a page on your site with the `at_preview_token` parameter with an empty value.

例如：

`https://www.mysite.com/?at_preview_token=`
