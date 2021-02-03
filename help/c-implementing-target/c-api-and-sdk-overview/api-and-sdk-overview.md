---
keywords: 服务器端；服务器端；api;sdk;node.js;nodejs;nodejs;recommendations api;api:api
description: 有关Adobe Target服务器端投放API、SDK和目标RecommendationsAPI的信息。
title: 有关服务器端投放API、Node.js SDK和RecommendationsAPI的信息
feature: Implement Server-side
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 20%

---


# 服务器端：实施 Target

有关[!DNL Adobe Target]服务器端投放API、SDK和[!DNL Target Recommendations] API的信息。

以下过程会在 [!DNL Target] 的服务器端实施中发生：

1. 客户端设备通过您的服务器请求获取体验。
1. 您的服务器将该请求发送至 [!DNL Target]。
1. [!DNL Target] 将响应发送回服务器。
1. 您的服务器决定要向客户端设备提供哪些体验以供其呈现。

无需在浏览器中显示体验。 该体验可以通过电子邮件或自助终端、语音助手或其他非视觉体验或基于浏览器的设备显示。 由于您的服务器位于客户端和 [!DNL Target] 之间，因此如果您需要更好地控制体验并提高其安全性，或者您希望在服务器上运行复杂的后端进程，则此类实施是最佳选择。

>[!NOTE]
>
>首次访客只能在客户端进行初始化。 首次访客&#x200B;*不能*&#x200B;在服务器端进行初始化。

以下各节提供有关各种API和NodeJS SDK的更多信息：

## 服务器端交付 API

链接：[服务器端投放API](https://developers.adobetarget.com/api/delivery-api/)

`/rest/v1/delivery`

通过[!DNL Target]投放API，您可以：

* 跨网络提供体验，包括SPA、移动渠道以及基于非浏览器的IoT设备，如网络电视、报亭或店内数字屏幕。
* 从任何可进行HTTP/s调用的服务器端平台或应用程序提供体验。
* 向访客提供一致、个性化的体验，无论访客使用何种渠道或设备与您的业务互动。
* 在服务器上的会话中缓存访客体验，以避免多个API调用，从而获得更好的性能。
* 从服务器端无缝集成[!DNL Adobe Experience Cloud]产品，如[!DNL Adobe Analytics]、[!DNL Adobe Audience Manager](AAM)和[!DNL Experience Cloud ID Service]。

## 服务器端SDK

链接：[Adobe TargetSDK](https://adobetarget-sdks.gitbook.io/docs/)

[!DNL Adobe Target]服务器端SDK文档门户可帮助您以所选语言在服务器上实施[!DNL Target]。

## Target 推荐 API

链接：[目标RecommendationsAPI](https://developers.adobetarget.com/api/recommendations)和[Adobe RecommendationsAPI概述](https://experienceleague.adobe.com/docs/target-learn/recommendations-api-tutorial/recs-api-overview.html)。

利用RecommendationsAPI，您可以与[!DNL Target]推荐服务器进行有序交互。 这些API可以与一系列应用程序堆栈集成，以执行通常通过[!DNL Target]用户界面执行的功能。
