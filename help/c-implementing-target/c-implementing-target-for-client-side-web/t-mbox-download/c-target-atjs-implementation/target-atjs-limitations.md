---
keywords: visual experience composer limitations;browser support;integrations;plugins;asynchronous considerations
description: at.js 与 mbox.js 之间存在一些差异。本节列出了部分差异和限制，以帮助您成功使用 at.js。
title: at.js 限制
feature: null
uuid: 6c2dfd85-4c4d-4204-a9e9-e358f0b70ded
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 100%

---


# at.js 限制{#at-js-limitations}

at.js 与 mbox.js 之间存在一些差异。本节列出了部分差异和限制，以帮助您成功使用 at.js。

## 已知的可视化体验编辑器限制 {#section_4B63C97169DE4C93B22944E880FD3DF1}

* 在单页应用程序中，应避免在可视化体验编辑器中使用“插入元素”和“重新排列”选项。

   与传统网站不同，单页应用程序并不会清除页面加载事件中的 DOM，因此“插入元素”和“重新排列”操作可能会被重复应用多次，具体次数取决于访客在单页应用程序中导航的方式。

## 集成和插件 {#section_D92E31170176406AAC7B5005F03D3425}

[!DNL mbox.js] 中的某些函数在 [!DNL at.js] 中不可用。[!DNL at.js] 已不再支持内部 [mbox.js 对象和方法](../../../../c-target/c-visitor-profile/variables-profiles-parameters-methods.md#section_8C78059D15D9452F95636A5640188537)（例如 `mbox`、`mboxCurrent`、`mboxFactoryDefault`、`mboxFactories` 等）（示例：`mboxFactoryDefault`）。这是特意设计的，其目的是阻止您“盗用”[!DNL at.js] 来开发不受支持的功能，因为如果长期使用不受支持的功能，可能会损坏实施，并使其无法升级。本文档的 API 页面中只介绍了已公开的方法。因此：

* 与其他 Adobe 解决方案的基于页面的旧版[集成](../../../../c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39)可能无法正常运行，应该将其升级到较新版本的服务器端集成。
* [为 mbox.js 开发的自定义插件](../../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-plugins.md#concept_F5D4C0A4DACF41409CC42FDD93B13FAF)可能无法正常使用，除非针对 [!DNL at.js] 对其进行更新。

   确保在测试中包含所有[插件](../../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-plugins.md#concept_F5D4C0A4DACF41409CC42FDD93B13FAF)。

## 异步注意事项 {#section_B586360A3DD34E2995AE25A18E3FB953}

由于所有 mbox 现在均为异步，因此它们不会阻止页面按照其触发的顺序进行呈现或返回。

* 如果您在[基于表单的体验编辑器](../../../../c-experiences/experiences.md#section_3643394BD424463C8768F2907DEBCC22)中使用全局 mbox，请注意 HTML 选件应仅包含 `<script>`、`<style>` 和 `<link>` 标记。

   在交付过程中，[!DNL at.js] 会在应用全局 mbox 选件时筛选出所有其他 HTML 标记。全局 mbox 选件会应用于 HTML 标头，HTML 标头中不允许使用 DIV、SPAN 等。例如，无法应用 `<div>test</div>`，因为 `<div>` 标记只能在 HTML 主体中使用。

* 基于页面的旧版 [!DNL Target] 与 [!DNL Analytics] 集成将无法正常运行。

   该集成要求先调用 [!DNL Target]，然后再调用 [!DNL Analytics]。

* 请注意选件和页面之间的 JavaScript 依赖关系。

   您不应假定会先执行选件中的 JavaScript，然后再执行 mbox 下经过硬编码的 JavaScript。

* 请注意页面上多个选件之间的 JavaScript 依赖关系。

   您不能再假定会先执行由第一个 mbox 交付的选件，然后再执行由第二个 mbox 交付的选件。

* DOM 操作和重定向选件应通过 [!DNL at.js] 中自动创建的全局 mbox 来交付，且应在 `<head>` 中交付。

   `<body>` 顶部的 `mboxCreate()` 函数可能会导致默认内容闪烁。

