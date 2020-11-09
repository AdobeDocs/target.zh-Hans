---
keywords: analytics tracking server;A4T;Adobe Experience Cloud debugger;Adobe Experience Platform debugger;reporting source;developer tools
description: 如果您使用的是较低版本的 at.js 或 mbox.js，则必须为使用 Analytics for Target (A4T) 的活动指定 Analytics 跟踪服务器。
title: 使用 Analytics 跟踪服务器
feature: a4t general
uuid: ad700b90-f409-496a-bc26-0f0367410a85
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 27%

---


# 使用 Analytics 跟踪服务器

If you are using an older version of at.js or mbox.js, you must specify an Analytics tracking server for activities that use [!DNL Analytics] for [!DNL Target] (A4T).

>[!NOTE]
>
>If you use [!DNL Analytics] as your activity&#39;s reporting source, you do not need to specify a tracking server during activity creation if you are using mbox.js version 61 (or later) or at.js version 0.9.1 (or later). mbox.js 或 at.js 库会自动将跟踪服务器值发送到 [!DNL Target]。在活动创建期间，您可以将“[!UICONTROL 目标和设置]”页面上的“[!UICONTROL 跟踪服务器]”字段留空。
>
>团 [!DNL Target] 队支持at.js 1。*x* 与 at.js 2.*x* 之间的映射。请升级到at.js的任一主要版本的最新更新，以确保您运行的是受支持的版本。 For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

To ensure that data from [!DNL Target] goes to the correct location in [!DNL Analytics], A4T requires an Analytics tracking server to be sent in all calls to Modstats from [!DNL Target]. For implementations using multiple tracking servers you can use the [!DNL Adobe Experience Platform Debugger] or your browser&#39;s Developer Tools to determine the correct tracking server for your activity.

## 使用Adobe Experience Platform调试器获取Analytics跟踪服务器

应该在将交付活动的页面上查看该调试器，以确保您选择的跟踪服务器正确无误。您还可以为每个帐户指定一个默认的跟踪服务器。要指定或修改默认的跟踪服务器，请联系客户关怀团队。

1. 在创建活动的页面中，打开 [!DNL Adobe Experience Platform Debugger]。

   如果尚未安装调试器，请参 [阅Adobe Experience Platform调试器简介](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html)。

   ![](assets/Screen_DebuggerTrackServ.png)

1. 单击 **[!UICONTROL 左侧导]** 航菜单中的“分析”。

   The Analytics tracking server is found in the [!UICONTROL Hostname] section of the debugger.

   * **第一方跟踪服务器**:如果请求的主机名与您所在的域匹配，则它是第一方跟踪服务器。 例如，如果您在 `adobe.com`, `adobe.com` 则是第一方跟踪服务器。
   * **第三方跟踪服务器**:第三方跟踪服务器通常 `[company].sc.omtrdc.net` 将公司作为公司的名称，但始终以结尾 `sc.omtrdc.net`。
   * **CNAME实现**: `sstats.adobe.com` 是CNAME第一方跟踪服务器用于https(secure)请求的示例。 `stats.adobe.com` 是http（非安全）页面的CNAME第一方请求的示例。

1. 复制该字段的全部内容。

1. 在活动的“**[!UICONTROL 目标和设置]****[!UICONTROL ”屏幕的“]**&#x200B;报表设置&#x200B;**[!UICONTROL ”部分中，将复制的跟踪服务器信息粘贴到跟踪服务器]**&#x200B;字段中。

   >[!NOTE]
   >
   >You must select [!UICONTROL Analytics as the Reporting Source] for your activity for the [!UICONTROL Tracking Server] field to be available.

## 使用浏览器的开发人员工具获取分析跟踪服务器

应在将提供活动的页面上查看开发人员工具，以确保您选择正确的跟踪服务器。 您还可以为每个帐户指定一个默认的跟踪服务器。要指定或修改默认的跟踪服务器，请联系客户关怀团队。

1. 在创建活动的页面上，打开浏览器的“开发人员工具”（在Google Chrome中，单击右上角的三个垂直椭圆，>更多工具>开发人员工具）。

   ![Chrome开发人员工具](/help/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. Click the **[!UICONTROL Network]** tab.

1. 筛选以 `/ss,` 显示Analytics请求。

   ![带/ss搜索的Chrome开发人员工具](/help/c-integrating-target-with-mac/a4t/assets/chrome-search.png)

   跟踪服务器是请求的主机名。

   * **第一方跟踪服务器**:如果请求的主机名与您所在的域匹配，则它是第一方跟踪服务器。 例如，如果您在 `adobe.com`, `adobe.com` 则是第一方跟踪服务器。
   * **第三方跟踪服务器**:第三方跟踪服务器通常 `[company].sc.omtrdc.net` 将公司作为公司的名称，但始终以结尾 `sc.omtrdc.net`。
   * **CNAME实现**: `sstats.adobe.com` 是CNAME第一方跟踪服务器用于https(secure)请求的示例。 `stats.adobe.com` 是http（非安全）页面的CNAME第一方请求的示例。

1. 复制该字段的全部内容。

1. 在活动的“**[!UICONTROL 目标和设置]****[!UICONTROL ”屏幕的“]**&#x200B;报表设置&#x200B;**[!UICONTROL ”部分中，将复制的跟踪服务器信息粘贴到跟踪服务器]**&#x200B;字段中。

   >[!NOTE]
   >
   >You must select [!UICONTROL Analytics as the Reporting Source] for your activity for the [!UICONTROL Tracking Server] field to be available.

