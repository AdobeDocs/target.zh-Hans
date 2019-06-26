---
description: '有关 at.js 的 targetPageParamsAll() 函数的信息。 '
keywords: adobe.target.notification;元素;选择器;通知;扩展
seo-description: 有关 Adobe Target at.js JavaScript 库的 targetPageParamsAll() 函数的信息。
seo-title: 有关 Adobe Target at.js JavaScript 库的 targetPageParamsAll() 函数的信息。
solution: Target
subtopic: 入门指南
title: targetPageParamsAll()
topic: Standard
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# targetPageParamsAll()

此方法允许您从请求代码外部将参数附加到所有 mbox。

在多个 mbox 调用中包含相同的一组参数时，这非常有用。该函数需由客户定义。它应返回一个参数数组，这些参数将传递给页面上的所有 mbox 请求。此函数可在 at.js 加载之前或在 **[!UICONTROL 设置]** &gt; **[!UICONTROL 实施]** &gt; **[!UICONTROL 编辑 at.js 设置]** &gt; **[!UICONTROL 代码设置]** &gt; **[!UICONTROL 库标头]** 中进行定义。

您可以通过以下任何方式使用 targetPageParamsAll() 函数将参数传递到 target-global-mbox：

* 以与号 (&amp;) 分隔的列表
* 数组
* JSON 对象

## 示例

以 &amp; 符号分隔的列表（值必须进行 URL 编码）：

```
function targetPageParamsAll() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

数组（值不需要进行 URL 编码）：

```
targetPageParamsAll = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

JSON（值不需要进行 URL 编码）：

```
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
