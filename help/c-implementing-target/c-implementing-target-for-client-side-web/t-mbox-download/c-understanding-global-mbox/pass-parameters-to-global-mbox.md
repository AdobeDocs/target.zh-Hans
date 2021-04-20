---
keywords: 全局 mbox 参数;targetPageParams;查询字符串;数组;JSON;DTM;动态标签管理
description: 了解如何使用targetPageParams函数将其他定位或上下文信息传递到Adobe Target全局mbox。
title: 如何将参数传递给全局mbox?
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: a638da983bf39361be36a9cd68f3ef9f7eb39013
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 63%

---


# 将参数传递到全局 mbox

JavaScript `targetPageParams`函数用于将参数传递到[!DNL Adobe Target]中的全局mbox。 在要将其他定位/上下文信息传递到[!DNL Target]的任何情况下，都需要此设置。

例如，在[!DNL Recommendations]活动中，使用参数表示当前正在查看的产品或类别。

调用JavaScript函数的代码必须位于页面上的全局mbox之前，无论全局mbox是作为at.js的一部分触发还是手动包含在页面代码中。

>[!NOTE]
>
>如果要向页面上的所有mbox（而不仅仅是全局mbox）添加参数，请使用[targetPageParamsAll()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparamsall.md)函数。

您可以按照以下任一方式使用 `targetPageParams()` 函数将参数传递到 `target-global-mbox`：

* 数组
* JSON 对象
* 以与号 (&amp;) 分隔的列表

使用这三种方法可验证参数是否正确传递。您还可以使用 [Adobe Experience Cloud 调试器](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html)来验证参数的传递。

您必须先定义 JavaScript 函数，然后再向页面中添加全局 mbox。函数名称必须为 `targetPageParams`。

## 查询字符串

```
p1=v1&p2=v2&p3=hello%20world
```

* 名称: `targetPageParams`
* 返回值：以“&amp;”分隔的参数，这些参数包含 URL 编码参数值。

   示例：

   在此示例中，p3 的值为 `hello world`，该值已进行 URL 编码。

下面显示了页面代码内容的一个示例：

```
<html> 
  <head> 
    <title>Title here..</title> 
    <script type="text/javascript"> 
        function targetPageParams() { 
          return "p1=v1&p2=v2&p3=hello%20world";
        } 
    </script> 
    <script src="mbox.js" type="text/javascript"></script> 
  </head> 
  <body>Body here... 
  </body> 
</html>
```

此示例将以下数据发送到 mbox 边缘：

* p1=v1
* p2=v2
* p3=hello world

## 数组

```
<!--window.-->targetPageParams = function() { 
  return ["a=1", "b=2", "c=hello world"]; 
}; 
```

不需要对值进行 URL 编码。例如，如果某个值中包含空格，则无需对空格进行编码。

此示例将以下数据发送到 mbox 边缘：

* a=1
* b=2
* c=hello world

## JSON

JSON 是传递参数的有效方式。Target 使用 JSON 对象键将复杂的结构精简为简单的参数。

```
<!--window.-->targetPageParams = function() { 
  return { 
    "a": 1, 
    "b": 2, 
    "profile": { 
                  "memberStatus": Gold, 
                  "country": { 
                                "city": "San Francisco" 
                            } 
              } 
  }; 
}; 
```

不需要对值进行 URL 编码。例如，“San Francisco”不需要对空格进行编码。只需使用空格即可。

此示例将以下数据发送到 mbox 边缘：

* a=1
* b=2
* `profile.memberStatus`=金
* `profile.country.city`=San Francisco