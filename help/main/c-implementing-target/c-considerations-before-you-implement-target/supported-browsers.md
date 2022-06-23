---
keywords: 浏览器;先决条件;要求;Internet Explorer;Chrome;Firefox;Safari;Android;Surface
description: 了解哪些Internet浏览器Adobe [!DNL Target] 支持其界面和内容交付。
title: 浏览器的功能 [!DNL Target] 支持？
feature: Implementation
role: Developer
exl-id: 8a366c79-d944-4d44-be5a-7c4f65385beb
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 44%

---

# 支持的浏览器

已在各种浏览器和设备上对 [!DNL Adobe Target] 应用程序和内容交付进行了测试。

有关TLS的更多重要信息，请参阅 [TLS（传输层安全性）加密更改](https://developer.adobe.com/target/before-implement/tls-transport-layer-security-encryption/).

## [!DNL Target] Standard/Premium 界面 {#section_1B73CA4B7BBC460BB7009DF00A2AFC4D}

的 [!DNL Target] 界面支持以下浏览器和设备：

| 设备类型 | 浏览器版本 |
|--- |--- |
| Windows | <ul><li>Microsoft Edge</li><li>Google Chrome（最新版、最新版 — 1）</li><li>Mozilla Firefox（最新版、最新版 — 1）</li></ul> |
| Mac | <ul><li>Firefox（最新，最新 — 1）</li><li>Chrome（最新，最新 — 1）</li></ul> |

## 内容投放 {#section_1045A946056441268D40025529918D3D}

已在以下浏览器和设备上对内容交付进行了测试：

| 设备类型 | 浏览器版本 |
|--- |--- |
| Windows | <ul><li>Microsoft Internet Explorer 9 和 10. 测试是在模拟模式下进行的。<br>**注意**:at.js 1.3.0（及更高版本）不再支持在IE 9上进行内容交付。 at.js 2.5.0（及更高版本）不再支持在IE 10、11以及所有旧版本上进行内容交付。</li><li>Internet Explorer 11 <br>**注意**:at.js 2.5.0（及更高版本）不再支持在IE 10、11以及所有旧版本上进行内容交付。</li><li>Microsoft Edge</li><li>Chrome（最新，最新 — 1）</li><li>Firefox（最新，最新 — 1）</li></ul> |
| Mac | <ul><li>Apple Safari（最新版本）<br>**注意**:有关Safari如何处理第一方和第三方Cookie的更多信息，请参阅 [Target Cookie](https://developer.adobe.com/target/before-implement/privacy/cookie-behavior/).</li><li>Firefox（最新，最新 — 1）</li><li>Chrome（最新，最新 — 1）</li></ul> |
| 移动设备/平板电脑 | <ul><li>Apple iOS（最新版本）</li><li>Android 设备和平板电脑（Android 4 及更高版本）</li><li>Microsoft Surface (Windows 8.1)</li></ul> |

请注意以下事项：

* 对于 [!DNL at.js] 实施，在较低版本的 Internet Explorer 中，[!DNL Target] 会显示默认内容；在上面所列其他浏览器的较低版本中，Target 可能会显示默认内容。
* Internet Explorer将所有未知元素（如自定义元素）视为相同的元素类型。 因此，交付不适用于自定义元素。
* [!DNL Target]在上面未列出的浏览器以及使用[怪异模式](https://en.wikipedia.org/wiki/Quirks_mode)的浏览器中， 会显示默认内容。at.js 要求使用可在标准模式下渲染的文档类型，例如：`<!DOCTYPE html>`。
* Adobe 交付基础架构已确定在 2018 年 9 月 12 日之后“不”支持 TLS 1.0 设备和浏览器。请参阅 [TLS（传输层安全性）加密更改](https://developer.adobe.com/target/before-implement/tls-transport-layer-security-encryption/)以了解此更改带来的总体影响。
