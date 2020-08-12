---
keywords: qa;preview;bookmarklet;preview links
description: 帮助您使用Adobe TargetQA书签强制目标从QA模式中释放您的信息。
title: 活动Adobe TargetQA书签
feature: null
topic: Advanced,Standard,Classic
uuid: 2890e215-16c9-4b22-a8eb-732cd6efede3
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 43%

---


# 活动 QA 书签{#activity-qa-bookmarklet}

Information to help you use the [!DNL Target] QA bookmarklet to force [!DNL Target] to release you from QA mode.

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

随后，该书签应该会显示在工具栏中，以供重复使用。

>[!NOTE]
>
>创建书签的过程因浏览器类型和版本而异。请参阅浏览器的帮助或在 Internet 上搜索具体说明。

You can also manually force yourself out of QA mode by loading a page on your site with the `at_preview_token` parameter with an empty value.

例如：

`https://www.mysite.com/?at_preview_token=`
