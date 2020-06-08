---
keywords: mobile app;mobile app sdk;target mobile app;mobile target sdk;mobile app sdk;enable target in sdk
description: 可将 Adobe Mobile Services SDK 添加到应用程序。
title: 在 SDK 中启用 Target
topic: Target
uuid: 673dd5c7-9c09-4a6e-bc41-c6ad27cf269c
translation-type: tm+mt
source-git-commit: cf69c1d8472088d5f6a6b7250bedd1048cac5c10
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 88%

---


# 在 SDK 中启用 Target{#enable-target-in-the-sdk}

可将 Adobe Mobile Services SDK 添加到应用程序。

1. 如果您尚未在应用程序中安装 Adobe Mobile Services SDK，请使用您的 Analytics 或 Experience Cloud 凭据从 [Adobe Mobile Services](https://mobilemarketing.adobe.com) 网站下载此 SDK。

1. 可将 Adobe Mobile Services SDK 添加到应用程序。

   您可以在[核心实施和生命周期](https://docs.adobe.com/content/help/en/mobile-services/ios/getting-started-ios/dev-qs.html)下找到相关说明。

1. 添加客户端代码和超时，并启用 SSL。

   在 Experience Cloud 中，打开 Mobile Services，然后转到&#x200B;**[!UICONTROL 管理应用程序设置]** > **[!UICONTROL SDK Target 选项]**。

   添加 Target 客户端代码和超时。客户端代码是您的帐户或公司的唯一代码。超时是指 Target 在显示默认内容之前将等待响应的时间（以秒为单位）。请确保在 Adobe Mobile Services 的“管理应用程序设置”页面上选中&#x200B;**[!UICONTROL 使用 HTTPS]** 选项。如果未启用HTTPS，则iOS9+中的所有调用将被阻止，除非您允许列出目标服务器。

   ![](assets/mobile-clientcode.png)

1. 创建/找到您的应用程序后，查找应用程序设置，并下载所需的 SDK。

   ![](assets/download-sdk.png)

>[!IMPORTANT]
>
> 如果您无权访问移动设备营销界面，则可以直接在配置文件的应用程序代码中进行更改；不过，所做更改不会与用户界面中的设置页面同步。

