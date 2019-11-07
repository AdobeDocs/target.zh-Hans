---
keywords: 全局 mbox 参数;targetPageParams;查询字符串;数组;JSON;DTM;动态标签管理
description: 可使用 JavaScript targetPageParams 函数将参数传递到全局 mbox。对于要将额外的定位/上下文信息传递到 Target 的任何情况，都需要执行此操作。
title: 将参数传递到全局 mbox
subtopic: 入门指南
topic: Standard
uuid: 058f0ef5-037a-4daf-8a1e-a9c7ecc7f0bd
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 将参数传递到全局 mbox{#pass-parameters-to-a-global-mbox}

可使用 JavaScript targetPageParams 函数将参数传递到全局 mbox。对于要将额外的定位/上下文信息传递到 Target 的任何情况，都需要执行此操作。

例如，在“推荐”活动中，使用相应参数来表示当前正在查看的产品或类别。

用于调用 JavaScript 函数的代码必须位于页面上的全局 mbox 前面，不论该全局 mbox 是作为 mbox.js 的一部分触发，还是通过手动方式包含在页面代码中。

>[!NOTE]
>
>如果您想要将参数添加到页面上的所有 mbox，而不仅仅是全局 mbox，请使用 [targetPageParamsAll()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparamsall.md) 函数（仅限 at.js）。

您可以按照以下任一方式使用 `targetPageParams()` 函数将参数传递到 `target-global-mbox`：

* 数组
* JSON 对象
* 以与号 (&amp;) 分隔的列表

使用这三种方法可验证参数是否正确传递。您还可以使用 [Adobe Experience Cloud 调试器](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html)来验证参数的传递。

您必须先定义 JavaScript 函数，然后再向页面中添加全局 mbox。函数名称必须为 `targetPageParams`。

**查询字符串**

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
           
<b>return "p1=v1&p2=v2&p3=hello%20world"</b>; 
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

**数组**

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

**JSON**

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
* `profile.age`=26
* `profile.country.city`=San Francisco