---
keywords: 服务器端；API;SDK;node.js;NodeJS；节点JS；推荐API;API:api
description: 了解Adobe [!DNL Target] 服务器端交付API、SDK和 [!DNL Target] Recommendations API。
title: 我可以在何处了解 [!DNL Target] 服务器端交付API和SDK?
feature: Implement Server-side
role: Developer
exl-id: cdee007f-f54d-4cf3-9575-6319da3434a5
source-git-commit: db288fbb4ddf011b7051257fdc8126d1158c8469
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 23%

---

# 服务器端：实施 Target

有关 [!DNL Adobe Target] 服务器端交付API、SDK和 [!DNL Target Recommendations] API。

以下过程会在 [!DNL Target] 的服务器端实施中发生：

1. 客户端设备通过您的服务器请求获取体验。
1. 您的服务器将该请求发送至 [!DNL Target]。
1. [!DNL Target] 将响应发送回服务器。
1. 您的服务器会决定要将哪个体验交付到客户端设备进行呈现。

体验无需在浏览器中显示。 体验可以通过电子邮件或网亭、语音助手或其他一些非可视化体验或非基于浏览器的设备显示。 由于您的服务器位于客户端和 [!DNL Target] 之间，因此如果您需要更好地控制体验并提高其安全性，或者您希望在服务器上运行复杂的后端进程，则此类实施是最佳选择。

>[!NOTE]
>
>首次访客只能在客户端上进行初始化。 首次访客 *无法* 在服务器端初始化。

以下部分提供了有关各种API和NodeJS SDK的更多信息：

## 服务器端交付 API

链接： [服务器端交付API](https://developers.adobetarget.com/api/delivery-api/)

`/rest/v1/delivery`

使用 [!DNL Target] 交付API，您可以：

* 跨Web(包括SPA和移动渠道)以及不基于浏览器的IoT设备（如连接的电视、网亭或店内数字屏幕）提供体验。
* 从任何可以进行HTTP/s调用的服务器端平台或应用程序交付体验。
* 无论访客使用哪种渠道或设备与您的业务进行互动，都会向访客提供一致的个性化体验。
* 在服务器上的会话中缓存访客的体验，以避免多次API调用，从而获得更好的性能。
* 无缝集成 [!DNL Adobe Experience Cloud] 产品，例如 [!DNL Adobe Analytics], [!DNL Adobe Audience Manager] (AAM)和 [!DNL Experience Cloud ID Service] 从服务器端。

## 服务器端SDK

链接： [Adobe Target SDK](https://adobetarget-sdks.gitbook.io/docs/)

的 [!DNL Adobe Target] 服务器端SDK文档门户可帮助您实施 [!DNL Target] 使用您选择的语言在服务器上。

## Target 推荐 API

链接： [Target Recommendations API](https://developers.adobetarget.com/api/recommendations) 和 [Adobe Recommendations API概述](https://experienceleague.adobe.com/docs/target-learn/recommendations-api-tutorial/recs-api-overview.html).

Recommendations API允许您以编程方式与交互 [!DNL Target] 推荐服务器。 这些API可以与一系列应用程序堆栈集成，以执行您通常通过 [!DNL Target] 用户界面。
