---
keywords: analytics tracking server;A4T;Adobe Experience Cloud debugger;reporting source
description: 如果您使用的是较低版本的 at.js 或 mbox.js，则必须为使用 Analytics for Target (A4T) 的活动指定 Analytics 跟踪服务器。
title: 使用 Analytics 跟踪服务器
feature: a4t general
uuid: ad700b90-f409-496a-bc26-0f0367410a85
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 46%

---


# 使用 Analytics 跟踪服务器{#use-an-analytics-tracking-server}

If you are using an older version of at.js or mbox.js, you must specify an analytics tracking server for activities that use [!DNL Analytics] for [!DNL Target] (A4T).

>[!NOTE]
>
>If you use [!DNL Analytics] as your activity&#39;s reporting source, you do not need to specify a tracking server during activity creation if you are using mbox.js version 61 (or later) or at.js version 0.9.1 (or later). mbox.js 或 at.js 库会自动将跟踪服务器值发送到 [!DNL Target]。在活动创建期间，您可以将“[!UICONTROL 目标和设置]”页面上的“[!UICONTROL 跟踪服务器]”字段留空。

To ensure that data from [!DNL Target] goes to the correct location in [!DNL Analytics], A4T requires an analytics tracking server to be sent in all calls to Modstats from [!DNL Target]. For implementations using multiple tracking servers you can use the [!DNL Adobe Experience Cloud Debugger] to determine the correct tracking server for your activity.

应该在将交付活动的页面上查看该调试器，以确保您选择的跟踪服务器正确无误。您还可以为每个帐户指定一个默认的跟踪服务器。要指定或修改默认的跟踪服务器，请联系客户关怀团队。

1. 在创建活动的页面中，打开 [!DNL Adobe Experience Cloud Debugger]。

   如果尚未安装调试器，请参阅安 [装Experience Cloud Debugger](https://docs.adobe.com/content/help/en/debugger/using/install-debugger.html)。

   ![](assets/Screen_DebuggerTrackServ.png)

   The analytics tracking server is found in the [!UICONTROL SiteCatalyst Image] section of the debugger. The field is called *First Party Cookies* or *Third Party Cookies* depending on the implementation, and the [!DNL Analytics] tracking server value will be in one of these formats:

   * （对于 CNAME 实施）
   * （对于非 RDC 实施）
   * （对于 RDC 实施）

   *Company*[!DNL Analytics] 表示 公司名称，*metrics* 是 CNAME 值的一个示例，而 *d1* 是 数据中心的一个示例。[!DNL Analytics]
1. 复制该字段的全部内容。
1. 在活动的“[!UICONTROL 目标和设置][!UICONTROL ”屏幕的“]报表设置&#x200B;**[!UICONTROL ”部分中，将复制的跟踪服务器信息粘贴到跟踪服务器]**&#x200B;字段中。

   >[!NOTE]
   >
   >You must select [!UICONTROL Analytics as the Reporting Source] for your activity for the [!UICONTROL Tracking Server] field to be available.

