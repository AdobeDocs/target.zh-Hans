---
keywords: adobe.target.applyOffer;applyOffer;applyoffer;申请选件;at.js;函数;函数
description: 有关 Adobe Target at.js JavaScript 库的 adobe.target.applyOffer(options) 函数的信息。
title: 有关 Adobe Target at.js JavaScript 库的 adobe.target.applyOffer() 函数的信息。
subtopic: 入门指南
topic: Standard
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# adobe.target.applyOffer(options) {#reference_BBE83F513B5B4E03BBC3F50D90864245}

此函数用于应用响应内容。

>[!NOTE]
>
>`applyOffer` 需要使用 `mbox` 参数。如果未指定 mbox 名称，则会发生错误。

options 参数是强制性的，具有以下结构：

| 键值 | 类型 | 必需 | 描述 |
|--- |--- |--- |--- |
| mbox | 字符串 | 是 | Mbox 名称<br>使用 at.js 1.3.0（及更高版本）的 Target 强制使用 mbox 键值。以往，这些键值是要求使用的，但现在，Target 强制使用该键值以确保 Target 正确验证并且客户正确地使用该函数。 |
| selector | 字符串或 DOM 元素 | 否 | HTML 元素或 CSS 选择器，用于标识 Target 应将选件内容放置在其中的 HTML 元素。如果未提供选择器，则 Target 会假定我们应使用的 HTML 元素是 HTML HEAD。 |
| offer（选件） | 数组 | 是 | 应用于元素的数组操作。 |

## 示例 {#section_D8D6A17B73DE4542937CDB687193A5CC}

以下示例显示如何将 `getOffer` 和 `applyOffer` 一起使用：

```
adobe.target.getOffer({   
  "mbox": "mbox",   
  "success": function(offers) {           
        adobe.target.applyOffer( {  
           "mbox": "mbox", 
           "offer": offers  
        } ); 
  },   
  "error": function(status, error) {           
      if (console && console.log) { 
        console.log(status); 
        console.log(error); 
      } 
  }, 
 "timeout": 5000 
}); 
```
