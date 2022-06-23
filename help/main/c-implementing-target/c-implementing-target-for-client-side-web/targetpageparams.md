---
keywords: targetPageParams;targetpageparams;pageParams;pageparams;页面参数;页面参数;at.js;函数;函数
description: 将targetPageParams()函数用于Adobe [!DNL Target] at.js JavaScript库，以从请求代码外部将参数附加到全局mbox。
title: 如何使用targetPageParams()函数？
feature: at.js
role: Developer
exl-id: 0772b400-626c-45d8-a4b5-a12691978cf3
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 72%

---

# targetPageParams()

此方法允许您从请求代码外部将参数附加到全局 mbox。

在多个 mbox 调用中包含相同的一组参数时，此函数非常有用。该函数需由客户定义。它应返回一个只传递给全局 mbox 请求的参数数组。此函数可在at.js加载之前或在 **[!UICONTROL 管理]** > **[!UICONTROL 实施]** > **[!UICONTROL 编辑]** > **[!UICONTROL 库标题]**.

您可以按照以下任一方式使用 `targetPageParams()` 函数将参数传递到 target-global-mbox：

* 以与号 (&amp;) 分隔的列表
* 数组
* JSON 对象

## 示例

以 &amp; 符号分隔的列表（值必须进行 URL 编码）：

```javascript
function targetPageParams() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

数组（值不需要进行 URL 编码）：

```javascript
targetPageParams = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

JSON（值不需要进行 URL 编码）：

```javascript
targetPageParams = function() { 
  return { 
    "a": 1, 
    "b": 2, 
    "profile": { 
        "age": 26, 
        "country": { 
          "city": "San Francisco" 
        } 
      } 
  }; 
};
```
