---
keywords: registerExtension;registerextension;注册扩展;at.js;函数;函数;clientCode;serverDomain;globalMboxName;globalMboxAutoCreate;超时
description: 使用registerExtension()函数进行Adobe [!DNL Target] at.js JavaScript库来注册特定扩展。 (at.js 1.x)
title: 如何使用registerExtension()函数？
feature: at.js
role: Developer
exl-id: 7f0898b4-ddd5-425c-99dc-94f9b30f8ba7
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 90%

---

# registerExtension() - at.js 1.x

可提供用于注册特定扩展的标准方法。

>[!NOTE]
>
>此函数仅可用于 at.js 版本 1.*x*。此函数已在 at.js 2.x 版本中弃用。如果与 at.js 2.x 一起使用，此函数将返回默认内容。

options 参数是强制性的，具有以下结构：

| 键值 | 类型 | 必需 | 描述 |
|--- |--- |--- |--- |
| name | 字符串 | 是 | 扩展名。 |
| modules | Array[String] | 是 | 一个字符串数组，表示请求的模块名称。 |
| register | 函数 | 是 | 用于初始化和构建扩展的函数。该函数接收基于模块数组的参数。 |

注释:

* 如果未提供其中任何一个参数，都会引发异常。
* 如果模块数组为空，则会引发异常。

有关如何使用 `registerExtension` 的更多信息和示例，请参阅 GitHub 上的 [Adobe Experience Cloud Target atjs 扩展](https://github.com/Adobe-Marketing-Cloud/target-atjs-extensions)页面。

## 设置模块方法 {#section_8501CDD4B0624FA2B10532C98C5F4328}

| 键值 | 类型 | 描述 |
|--- |--- |--- |
| clientCode | 字符串 | 客户端代码 |
| serverDomain | 字符串 | 边缘服务器域 |
| globalMboxName | 字符串 | Target 全局 mbox 名称 |
| globalMboxAutoCreate | 布尔值 | 指示是否已启用自动创建 |
| timeout | 数值 | 请求超时 |

## 记录器模块方法 {#section_10AF62B49AEF48F981E950D26E176138}

| 键值 | 类型 | 描述 |
|--- |--- |--- |
| log | 函数 | 将参数变量列表记录到浏览器控制台（如果存在）。只有当 `mboxDebug=true` 传递到 URL 时才会激活它。 |
| error | 函数 | 将参数变量列表记录到浏览器控制台。只有在出现严重错误（如网络超时、未找到 HTML 节点等）时才会激活它。 |