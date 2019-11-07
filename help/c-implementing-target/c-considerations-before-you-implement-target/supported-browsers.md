---
keywords: 浏览器;先决条件;要求;Internet Explorer;Chrome;Firefox;Safari;Android;Surface
description: 已在各种浏览器和设备上对 Adobe Target 应用程序和内容交付进行了测试。
title: 支持的浏览器
subtopic: 入门指南
topic: Standard
uuid: 614088da-412c-45e3-9f2d-6985391973be
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 支持的浏览器{#supported-browsers}

已在各种浏览器和设备上对 [!DNL Adobe Target] 应用程序和内容交付进行了测试。

有关 TLS 的其他重要信息，请参阅 [TLS（传输层安全性）加密更改](../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)。

## [!DNL Target] Standard/Premium 界面 {#section_1B73CA4B7BBC460BB7009DF00A2AFC4D}

[!DNL [!DNL Target]] Standard/Premium] 界面支持以下浏览器和设备：

| 设备类型 | 浏览器版本 |
|--- |--- |
| Windows | <ul><li>Microsoft Edge</li><li>Google Chrome（最新版本及其前一个版本）</li><li>Mozilla Firefox（最新版本及其前一个版本）</li></ul> |
| Mac | <ul><li>Firefox（最新版本及其前一个版本）</li><li>Chrome（最新版本及其前一个版本）</li></ul> |

## 内容交付 {#section_1045A946056441268D40025529918D3D}

已在以下浏览器和设备上对内容交付进行了测试：

| 设备类型 | 浏览器版本 |
|--- |--- |
| Windows | <ul><li>Internet Explorer 9 和 10。测试是在模拟模式下进行的。<br>**注意**：at.js 1.3.0（及更高版本）不再支持在 Microsoft Internet Explorer 9 上进行内容交付。</li><li>Internet Explorer 11</li><li>Microsoft Edge</li><li>Chrome（最新版本及其前一个版本）</li><li>Firefox（最新版本及其前一个版本）</li></ul> |
| Mac | <ul><li>Apple Safari（最新版本）<br>**注意**：有关 Safari 如何处理第一方 Cookie 和第三方 Cookie 的更多信息，请参阅 [Target Cookie](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/cookie-behavior.md)。</li><li>Firefox（最新版本及其前一个版本）</li><li>Chrome（最新版本及其前一个版本）</li></ul> |
| 移动设备/平板电脑 | <ul><li>Apple iOS（最新版本）</li><li>Android 设备和平板电脑（Android 4 及更高版本）</li><li>Microsoft Surface (Windows 8.1)</li></ul> |

对于 [!DNL at.js] 实施，在较低版本的 Internet Explorer 中，[!DNL Target] 会显示默认内容；在上面所列其他浏览器的较低版本中，Target 可能会显示默认内容。对于 [!DNL mbox.js] 实施，[!DNL Target] 会尝试渲染内容，但可能会失败。

[!DNL Target]在上面未列出的浏览器以及使用[怪异模式](https://en.wikipedia.org/wiki/Quirks_mode)的浏览器中， 会显示默认内容。at.js 要求使用可在标准模式下渲染的文档类型，例如：`<!DOCTYPE html>`。

>[!NOTE]
>
>Adobe 交付基础架构已确定在 2018 年 9 月 12 日之后“不”支持 TLS 1.0 设备和浏览器。请参阅 [TLS（传输层安全性）加密更改](../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)以了解此更改带来的总体影响。
