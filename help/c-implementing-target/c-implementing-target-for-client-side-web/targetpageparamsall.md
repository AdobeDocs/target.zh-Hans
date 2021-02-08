---
keywords: targetPageParamsAll;targetpageparamsall;PageParamsAll;pageparamsall;页面参数;页面参数;at.js;函数;函数
description: 使用Adobe Targetat.js JavaScript库的targetPageParamsAll()函数将参数从请求代码外附加到所有mbox。
title: 如何使用targetPageParamsAll()函数？
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 71%

---


# targetPageParamsAll()

此方法允许您从请求代码外部将参数附加到所有 mbox。

在多个 mbox 调用中包含相同的一组参数时，这非常有用。该函数需由客户定义。它应返回一个参数数组，这些参数将传递给页面上的所有 mbox 请求。在加载at.js之前或在&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 实施]** > **[!UICONTROL 编辑]** > **[!UICONTROL 代码设置]** > **[!UICONTROL 库头]**&#x200B;中定义此函数。

您可以通过以下任何方式使用 targetPageParamsAll() 函数将参数传递到 target-global-mbox：

* 以与号 (&amp;) 分隔的列表
* 数组
* JSON 对象

## 示例

以 &amp; 符号分隔的列表（值必须进行 URL 编码）：

```javascript
function targetPageParamsAll() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

数组（值不需要进行 URL 编码）：

```javascript
targetPageParamsAll = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

JSON（值不需要进行 URL 编码）：

```javascript
targetPageParamsAll = function() { 
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
