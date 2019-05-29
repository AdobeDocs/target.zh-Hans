---
description: '有关. js的mboxDefine()和mboxUpdate()函数的信息。 '
keywords: adobe.target.notification;元素;选择器;通知;扩展
seo-description: 有关Adobe Target at. js JavaScript库的mboxDefine()和mboxUpdate()函数的信息。
seo-title: 有关Adobe Target at. js JavaScript库的mboxDefine()和mboxUpdate()函数的信息。
solution: Target
subtopic: 入门指南
title: mboxDefine() 和 mboxUpdate() - at.js 1.x
topic: Standard
translation-type: tm+mt
source-git-commit: 126f62d8966beb8157f54f87cf68b092fe976c51

---


# mboxDefine() 和 mboxUpdate() - at.js 1.x

在Adobe Target中定义和更新mbox。

>[!NOTE]
>
>这些函数仅可用于 at.js 版本 1.*x*。这些函数已在. js2.x版本中弃用。如果与at. js2.x一起使用，这些函数将返回默认内容。

`mboxDefine()` 和 `mboxCreate()` 绑定到应显示选件的 HTML DIV 元素。这些 HTML DIV 元素应具有 `mboxDefault` 类。如果 HTML 元素不会附加此类，则您可能会看到一些明显的闪烁。

## mboxDefine {#section_134BAAE8EE9D49D8BAFEA5E7EAB93BA7}

创建 nodeId 和 mbox 名称之间的内部映射，但不执行请求。与 `mboxUpdate()` 一起使用。内置于 [!DNL at.js]，主要用于简化从 [!DNL mbox.js] 到 [!DNL at.js] 的转换。

## mboxUpdate {#section_D20B3E551884452A996305C12D5959D5}

执行请求并将选件应用到由 `nodeId` () 中的 `mboxDefine()` 标识的元素。也可以用来更新由 `mboxCreate` 发起的 mbox。内置于 [!DNL at.js]，主要用于简化从 [!DNL mbox.js] 到 [!DNL at.js] 的转换。`mboxDefine()`/ `mboxUpdate()` 可由 [adobe. target. getOffer()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md) 和 [adobe. target. applyOffer()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffer.md) 替换为选择器选项。

## 示例 {#section_9C1E75D9E4BA4DC7879D2B69877EB01A}

```
<div id="someId" class="mboxDefault"></div> 
<script> 
 mboxDefine('someId','mboxName','param1=value1','param2=value2'); 
 mboxUpdate('mboxName','param3=value3','param4=value4'); 
</script>
```
