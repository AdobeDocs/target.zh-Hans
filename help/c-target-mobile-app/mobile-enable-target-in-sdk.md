---
keywords: 移动设备应用程序;移动设备应用程序 SDK;定位移动设备应用程序;移动设备 Target SDK;在 SDK 中启用 Target
description: 了解如何将Adobe Mobile Services SDK添加到您的移动应用程序。
title: 如何在Adobe Mobile SDK中启用 [!DNL Target] ?
feature: 实施移动
role: Developer
exl-id: c34bd50c-e17f-4dfb-8470-8f4c8639ee9f
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 79%

---

# 在SDK中启用[!DNL Target]

可将 Adobe Mobile Services SDK 添加到应用程序。

1. 如果您尚未在应用程序中安装 Adobe Mobile Services SDK，请使用您的 Analytics 或 Experience Cloud 凭据从 [Adobe Mobile Services](https://mobilemarketing.adobe.com) 网站下载此 SDK。

1. 可将 Adobe Mobile Services SDK 添加到应用程序。

   您可以在[核心实施和生命周期](https://experienceleague.adobe.com/docs/mobile-services/ios/getting-started-ios/dev-qs.html)下找到相关说明。

1. 添加客户端代码和超时，并启用 SSL。

   在 Experience Cloud 中，打开 Mobile Services，然后转到&#x200B;**[!UICONTROL 管理应用程序设置]** > **[!UICONTROL SDK Target 选项]**。

   添加 Target 客户端代码和超时。客户端代码是您的帐户或公司的唯一代码。超时是指 Target 在显示默认内容之前将等待响应的时间（以秒为单位）。请确保在 Adobe Mobile Services 的“管理应用程序设置”页面上选中&#x200B;**[!UICONTROL 使用 HTTPS]** 选项。如果未启用HTTPS，则除非目标服务器，否则iOS9+中的所有调允许列表用都将被阻止。

   ![](assets/mobile-clientcode.png)

1. 创建/找到您的应用程序后，查找应用程序设置，并下载所需的 SDK。

   ![](assets/download-sdk.png)

>[!IMPORTANT]
>
> 如果您无权访问移动设备营销界面，则可以直接在配置文件的应用程序代码中进行更改；不过，所做更改不会与用户界面中的设置页面同步。
