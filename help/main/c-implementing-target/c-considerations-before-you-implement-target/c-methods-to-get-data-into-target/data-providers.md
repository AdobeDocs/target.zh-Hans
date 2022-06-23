---
keywords: 实施；设置；设置；数据提供程序
description: 将数据导入 [!DNL Target] 使用数据提供程序。
title: 如何将数据导入 [!DNL Target] 使用数据提供程序？
feature: Implementation
role: Developer
exl-id: 05fe9190-4d36-43e2-9fc7-c354a6821bfb
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 62%

---

# 数据提供程序

数据提供商是一项功能，允许您轻松将数据从第三方传递到 [!DNL Adobe Target].

注意：数据提供程序需要使用at.js 1.3或更高版本。

## 格式

`window.targetGlobalSettings.dataProviders` 设置是一个数据提供程序数组。

有关每个数据提供程序的结构的更多信息，请参阅[数据提供程序](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)。

## 用例示例

从第三方收集数据，例如气象服务、DMP，甚至您自己的 Web 服务。然后，您可以使用这些数据来构建受众、定位内容并丰富访客配置文件。

## 方法的好处

通过此设置，客户可以从第三方数据提供程序收集数据，例如 Demandbase、BlueKai 和自定义服务，并将这些数据作为全局 mbox 请求中的 mbox 参数传递给 Target。

支持通过异步和同步请求从多个提供程序收集数据。

使用这种方法可以轻松管理默认页面内容的闪烁，同时包含每个提供程序的独立超时时间以限制对页面性能的影响

## 注意事项

如果数据提供程序已添加到 `window.targetGlobalSettings.dataProviders` 异步，则会并行执行。 访客API请求与添加到的函数并行执行 `window.targetGlobalSettings.dataProviders` 以允许最短等待时间。

at.js不会尝试缓存数据。 如果数据提供程序仅提取一次数据，则应确保数据已缓存，并且在调用提供程序函数时为第二次调用提供缓存的数据。

## 代码示例

在[数据提供程序](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)中可以找到几个示例。

## 相关信息的链接

文档：[数据提供程序](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)

## 培训视频：

* [在 Adobe Target 中使用数据提供程序](https://helpx.adobe.com/cn/target/kt/using/dataProviders-atjs-feature-video-use.html)
* [在 Adobe Target 中实施数据提供程序](https://helpx.adobe.com/cn/target/kt/using/dataProviders-atjs-technical-video-implement.html)
