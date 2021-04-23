---
keywords: analytics跟踪服务器；A4T;Adobe Experience Cloud调试器；Adobe Experience Platform调试器；报告源；开发人员工具
description: '了解如何为使用Analytics for [!DNL Target] (A4T)的活动指定Analytics跟踪服务器（如果您使用的是at.js或mbox.js的旧版本）。 '
title: 如何使用Analytics跟踪服务器？
feature: Analytics for Target (A4T)
exl-id: 8066d6a6-661e-428b-9d5c-18537a80fb43
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 20%

---

# 使用 Analytics 跟踪服务器

如果您使用的是旧版at.js或mbox.js，则必须为使用[!DNL Adobe Analytics](A4T)的[!DNL Adobe Target](A4T)的活动指定Analytics跟踪服务器。

>[!NOTE]
>
>如果您使用mbox.js版本61（或更高版本）或at.js版本0.9.1（或更高版本），则在创建活动时无需指定跟踪服务器。 mbox.js 或 at.js 库会自动将跟踪服务器值发送到 [!DNL Target]。在活动创建期间，您可以将“[!UICONTROL 目标和设置]”页面上的“[!UICONTROL 跟踪服务器]”字段留空。
>
>[!DNL Target]团队同时支持at.js 1。*x* 与 at.js 2.*x* 之间的映射。升级到at.js的任一主要版本的最新更新，以确保您运行的是受支持的版本。 有关详细信息，请参阅[at.js版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)。

要确保[!DNL Target]中的数据到达[!DNL Analytics]中的正确位置，A4T要求在从[!DNL Target]发往Modstats的所有调用中发送Analytics跟踪服务器。 对于使用多个跟踪服务器的实施，请使用[!DNL Adobe Experience Platform Debugger]或浏览器的“开发人员工具”来确定适合您的活动的正确跟踪服务器。

## 使用Adobe Experience Platform调试器获取Analytics跟踪服务器

应在传送活动的页面上查看调试器，以确保您选择正确的跟踪服务器。 您还可以为每个帐户指定一个默认的跟踪服务器。要指定或修改默认的跟踪服务器，请联系客户关怀团队。

1. 在创建活动的页面中，打开[!DNL Adobe Experience Platform Debugger]。

   如果尚未安装调试器，请参阅[Adobe Experience Platform调试器简介](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html)。

   ![](assets/Screen_DebuggerTrackServ.png)

1. 单击左侧导航菜单中的&#x200B;**[!UICONTROL 分析]**。

   Analytics跟踪服务器位于调试器的[!UICONTROL Hostname]部分。

   * **第一方跟踪服务器**:如果请求的主机名与您所在的域匹配，则它是第一方跟踪服务器。例如，如果您位于`adobe.com`上，则`adobe.com`是第一方跟踪服务器。
   * **第三方跟踪服务器**:第三方跟踪服务器通常 `[company].sc.omtrdc.net` 将公司作为公司的名称，但始终以结尾 `sc.omtrdc.net`。
   * **CNAME实施**: `sstats.adobe.com` 是CNAME第一方跟踪服务器用于https(secure)请求的示例。`stats.adobe.com` 是CNAME第一方请求http（非安全）页的示例。

1. 复制该字段的全部内容。

1. 在活动的“**[!UICONTROL 目标和设置]****[!UICONTROL ”屏幕的“]**&#x200B;报表设置&#x200B;**[!UICONTROL ”部分中，将复制的跟踪服务器信息粘贴到跟踪服务器]**&#x200B;字段中。

   >[!NOTE]
   >
   >选择[!UICONTROL Analytics作为报告源]，以便活动[!UICONTROL 跟踪服务器]字段可用。

## 使用您浏览器的开发人员工具获取Analytics跟踪服务器

应在提供活动的页面上查看开发人员工具，以确保您选择正确的跟踪服务器。 您还可以为每个帐户指定一个默认的跟踪服务器。要指定或修改默认的跟踪服务器，请联系客户关怀团队。

1. 在创建活动的页面上，打开浏览器的开发人员工具（在Google Chrome中，单击右上角的三个垂直椭圆，然后单击更多工具>开发人员工具）。

   ![Chrome开发人员工具](/help/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. 单击&#x200B;**[!UICONTROL 网络]**&#x200B;选项卡。

1. 筛选`/ss,`以显示Analytics请求。

   ![带/ss搜索的Chrome开发人员工具](/help/c-integrating-target-with-mac/a4t/assets/chrome-search.png)

   跟踪服务器是请求的主机名。

   * **第一方跟踪服务器**:如果请求的主机名与您所在的域匹配，则它是第一方跟踪服务器。例如，如果您位于`adobe.com`上，则`adobe.com`是第一方跟踪服务器。
   * **第三方跟踪服务器**:第三方跟踪服务器通常 `[company].sc.omtrdc.net` 将公司作为公司的名称，但始终以结尾 `sc.omtrdc.net`。
   * **CNAME实施**: `sstats.adobe.com` 是CNAME第一方跟踪服务器用于https(secure)请求的示例。`stats.adobe.com` 是CNAME第一方请求http（非安全）页的示例。

1. 复制该字段的全部内容。

1. 在活动的“**[!UICONTROL 目标和设置]****[!UICONTROL ”屏幕的“]**&#x200B;报表设置&#x200B;**[!UICONTROL ”部分中，将复制的跟踪服务器信息粘贴到跟踪服务器]**&#x200B;字段中。

   >[!NOTE]
   >
   >选择[!UICONTROL Analytics作为报告源]，以便活动[!UICONTROL 跟踪服务器]字段可用。
