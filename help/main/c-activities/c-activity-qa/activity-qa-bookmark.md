---
keywords: QA;预览;书签;预览链接
description: 了解如何使用Adobe [!DNL Target] QA书签强制[!DNL Target]将您从QA模式中释放出来。
title: 如何使用活动QA书签？
feature: Activities
exl-id: dbfe59eb-6853-4909-abf1-e5630e979a98
TQID: 'https://experienceleague.adobe.com/kOQcdF2WgiAGkOS3rrLWfDSFTvRJX8jb-IeaahWnM0c'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0a683f6e68bb7481b9e45c91a275a46b84a1ffd8
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 6%
---
# 活动 QA 书签 {#activity-qa-bookmarklet}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何使用[!DNL Target] QA小书签退出&#x200B;**[!UICONTROL 活动QA]**&#x200B;模式并像普通访客一样查看您的网站。

>[!ENDSHADEBOX]

以[QA模式](/help/main/c-activities/c-activity-qa/activity-qa.md)浏览网站后，QA模式会在各个页面中持续存在，直到[!DNL Target]会话过期为止。 小书签是运行JavaScript的浏览器书签。 [!DNL Target] QA书签强制[!DNL Target]将您从QA模式中释放，因此您不必等待会话过期。 使用与网站上部署的at.js版本匹配的版本。

>[!NOTE]
>
>创建书签的过程因浏览器类型和版本而异。 请参阅浏览器的帮助或在Internet上搜索特定说明。

## at.js 1.*x*&#x200B;的活动QA书签

要使用[!DNL Target] QA书签，请创建包含以下JavaScript代码的书签，并将其添加到浏览器的书签工具栏：

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

您也可以手动强制自己退出QA模式，方法是在将`at_preview_token`参数设置为空值的网站上加载页面。 例如：

`https://www.mysite.com/?at_preview_token=`

## at.js 2.*x*&#x200B;的活动QA书签

与at.js 1.*x*&#x200B;相比，at.js 2.*x*&#x200B;不支持第三方Cookie。 QA模式仅通过at.js设置的第一方Cookie在第一方域中持续存在。 因此，QA模式会话仅在客户端进行管理，并且不会向[!DNL Target]发送任何QA模式Cookie。

要使用[!DNL Target] QA书签，请创建包含以下JavaScript代码的书签，并将其添加到浏览器的书签工具栏：

```javascript
javascript:(
    function () {
        var AT_QA_MODE = 'at_qa_mode=';
        var isSet = document.cookie.split(';').some(function (cookie) {
            return cookie.trim().startsWith(AT_QA_MODE);
        });
        if (isSet) {            
            document.cookie = AT_QA_MODE + ';domain='+window.location.hostname+";Path=/; Max-Age=-0;";
            var token = window.location.href.indexOf("?at_preview_token")<0? "&at_preview_token" : "?at_preview_token";
            var url = window.location.href.split(token,2)[0];
            window.open(url, '_self', 'noreferrer');
        }
    })(); 
```

## 使用活动QA书签

将与at.js版本匹配的书签添加到浏览器后，无论何时要退出QA模式，均可使用它：

1. 在QA模式下打开网站的任何页面。
1. 单击浏览器书签工具栏中的小书签。
1. 加载网站的页面。 [!DNL Target]将会话从QA模式中释放，网站将像普通访客一样显示。
