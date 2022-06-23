---
keywords: mboxCreate;mboxcreate;mbox 创建;at.js;函数;函数
description: 使用mboxCreate()函数进行Adobe [!DNL Target] at.js JavaScript库来使用mboxDefault类名称将选件应用到最近的DIV。 (at.js 1.x)
title: 如何使用mboxCreate()函数？
feature: at.js
role: Developer
exl-id: 821ad97a-345a-4e56-9be6-ab1c7d3a651d
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 73%

---

# mboxCreate(mbox,params) - at.js 1.x

可使用 mboxDefault 类名称执行请求并将选件应用到最近的 DIV。

>[!NOTE]
>
>此函数仅可用于 at.js 版本 1.*x*。此函数已在 at.js 2.x 版本中弃用。如果与 at.js 2.x 一起使用，此函数将返回默认内容。

此函数内置于 [!DNL at.js] 主要是为了简化 [!DNL mbox.js] （现已弃用） [!DNL at.js]. `mboxCreate()` 的最新替代方案是 `adobe.target.getOffer()`/`adobe.target.applyOffer()` 或 Angular 指令。

## 示例

```javascript
<div class="mboxDefault"> 
  default content to replace by offer 
</div> 
<script> 
  mboxCreate('mboxName','param1=value1','param2=value2'); 
</script>
```

## 注释

`mboxCreate()` 现在使用“json”端点而不是“standard”端点且会异步触发。因此：

* [调试](https://developer.adobe.com/target/implement/client-side/target-debugging-atjs/target-debugging-atjs/){target=_blank}稍有不同。
* 避免出现需要同步且阻止调用的选件代码。

   例如，设置由站点代码或稍后出现在页面上的其他 mbox 所使用的 JavaScript 变量的选件。

* 请确保在调用 `<div class="mboxDefault"></div>` 之前已具有 `mboxCreate()`，因为 [!DNL at.js] 不会为您添加它。

* 不建议将空白页面顶端的 `mboxCreate()` 函数作为全局 mbox。

   改用 [!DNL at.js] 中自动创建的全局 mbox 是一个更好的选择，因为它从 `<head>` 触发并可以更早返回内容。
