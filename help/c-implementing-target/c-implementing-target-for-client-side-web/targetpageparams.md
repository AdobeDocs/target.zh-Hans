---
description: '有关 at.js 的 targetPageParams() 函数的信息。 '
keywords: targetPageParams;targetpageparams;pageParams;pageparams;page params;page params;page paramets;at.js;functions;function
seo-description: 有关 Adobe Target at.js JavaScript 库的 targetPageParams() 函数的信息。
seo-title: 有关 Adobe Target at.js JavaScript 库的 targetPageParams() 函数的信息。
solution: Target
subtopic: 入门指南
title: targetPageParams()
topic: Standard
translation-type: tm+mt
source-git-commit: ef2c4ac78fef5889d5a6e9e053dfd36b77919dd4

---


# targetPageParams() {#reference_B235C9F6DA79449ABE3E23F914FEABAE}

此方法允许您从请求代码外部将参数附加到全局 mbox。

在多个 mbox 调用中包含相同的一组参数时，此函数非常有用。该函数需由客户定义。它应返回一个只传递给全局 mbox 请求的参数数组。此函数可在 at.js 加载之前或在&#x200B;**[!UICONTROL 设置]** &gt; **[!UICONTROL 实施]** &gt; **[!UICONTROL 编辑 at.js 设置]** &gt; **[!UICONTROL 代码设置]** &gt; **[!UICONTROL 库标头]**&#x200B;中进行定义。

您可以按照以下任一方式使用 `targetPageParams()` 函数将参数传递到 target-global-mbox：

* 以与号 (&amp;) 分隔的列表
* 数组
* JSON 对象

## 示例

以 &amp; 符号分隔的列表（值必须进行 URL 编码）：

```
function targetPageParams() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

数组（值不需要进行 URL 编码）：

```
targetPageParams = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

JSON（值不需要进行 URL 编码）：

```
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
