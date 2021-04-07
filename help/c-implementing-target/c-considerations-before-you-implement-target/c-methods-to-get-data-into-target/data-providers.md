---
keywords: 实现；实现；设置；设置；数据提供器
description: 使用数据提供者将数据导入目标。
title: 如何使用数据提供者将数据导入目标?
feature: 实施
role: Developer
translation-type: tm+mt
source-git-commit: e8c25685341319fea4381386cad1ce0c5b80face
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 66%

---

# 数据提供者

数据提供者是一项功能，它允许您轻松将数据从第三方传递到[!DNL Adobe Target]。

注意：数据提供程序需要at.js 1.3或更高版本。

## 格式

`window.targetGlobalSettings.dataProviders` 设置是一个数据提供程序数组。

有关每个数据提供程序的结构的更多信息，请参阅[数据提供程序](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)。

## 示例用例

从第三方收集数据，例如气象服务、DMP，甚至您自己的 Web 服务。然后，您可以使用这些数据来构建受众、定位内容并丰富访客配置文件。

## 方法的优势

通过此设置，客户可以从第三方数据提供程序收集数据，例如 Demandbase、BlueKai 和自定义服务，并将这些数据作为全局 mbox 请求中的 mbox 参数传递给 Target。

支持通过异步和同步请求从多个提供程序收集数据。

使用这种方法可以轻松管理默认页面内容的闪烁，同时包含每个提供程序的独立超时时间以限制对页面性能的影响

## 注意事项

如果添加到`window.targetGlobalSettings.dataProviders`的数据提供程序是异步的，则它们将并行执行。 访客API请求与添加到`window.targetGlobalSettings.dataProviders`的函数并行执行，以允许最短等待时间。

at.js不尝试缓存数据。 如果数据提供程序仅提取一次数据，则应确保数据已缓存，并且在调用提供程序函数时为第二次调用提供缓存的数据。

## 代码示例

在[数据提供程序](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)中可以找到几个示例。

## 相关信息的链接

文档：[数据提供程序](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)

## 培训视频：

* [在 Adobe Target 中使用数据提供程序](https://helpx.adobe.com/cn/target/kt/using/dataProviders-atjs-feature-video-use.html)
* [在 Adobe Target 中实施数据提供程序](https://helpx.adobe.com/cn/target/kt/using/dataProviders-atjs-technical-video-implement.html)