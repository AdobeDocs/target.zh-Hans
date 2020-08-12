---
keywords: mboxCreate;mboxcreate;mbox create;at.js;functions;function
description: 有关 Adobe Target at.js JavaScript 库的 mboxCreate(mbox,params) 函数的信息。
title: 有关 Adobe Target at.js JavaScript 库的 mboxCreate(mbox,params) 函数的信息。
feature: null
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 100%

---


# mboxCreate(mbox,params) - at.js 1.x {#reference_E68805FE86C64792B2066DB17B253D74}

可使用 mboxDefault 类名称执行请求并将选件应用到最近的 DIV。

>[!NOTE]
>
>此函数仅可用于 at.js 版本 1.*x*。此函数已在 at.js 2.x 版本中弃用。如果与 at.js 2.x 一起使用，此函数将返回默认内容。

此函数内置于 [!DNL at.js]，主要用于简化从 [!DNL mbox.js] 到 [!DNL at.js] 的转换。`mboxCreate()` 的最新替代方案是 `adobe.target.getOffer()`/`adobe.target.applyOffer()` 或 Angular 指令。

## 示例

```
<div class="mboxDefault"> 
  default content to replace by offer 
</div> 
<script> 
  mboxCreate('mboxName','param1=value1','param2=value2'); 
</script>
```

## 注释

`mboxCreate()` 现在使用“json”端点而不是“standard”端点且会异步触发。因此：

* [调试](../../c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md#concept_CAE591DA8C404C22917584ECD4F7494F)稍有不同。
* 避免出现需要同步且阻止调用的选件代码。

   例如，设置由站点代码或稍后出现在页面上的其他 mbox 所使用的 JavaScript 变量的选件。

* 请确保在调用 `<div class="mboxDefault"></div>` 之前已具有 `mboxCreate()`，因为 [!DNL at.js] 不会为您添加它。

* 不建议将空白页面顶端的 `mboxCreate()` 函数作为全局 mbox。

   改用 [!DNL at.js] 中自动创建的全局 mbox 是一个更好的选择，因为它从 `<head>` 触发并可以更早返回内容。