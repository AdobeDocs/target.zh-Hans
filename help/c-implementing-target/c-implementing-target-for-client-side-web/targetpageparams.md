---
keywords: targetPageParams;targetpageparams;pageParams;pageparams;page params;page parameters;at.js;functions;function
description: 有关 Adobe Target at.js JavaScript 库的 targetPageParams() 函数的信息。
title: 有关 Adobe Target at.js JavaScript 库的 targetPageParams() 函数的信息。
feature: client-side
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 89%

---


# targetPageParams() {#reference_B235C9F6DA79449ABE3E23F914FEABAE}

此方法允许您从请求代码外部将参数附加到全局 mbox。

在多个 mbox 调用中包含相同的一组参数时，此函数非常有用。该函数需由客户定义。它应返回一个只传递给全局 mbox 请求的参数数组。This function can be defined before at.js is loaded or in **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** > **[!UICONTROL Edit]** > **[!UICONTROL Library Header]**.

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
