---
keywords: Analytics跟踪服务器；A4T；Adobe Experience Cloud Debugger；Adobe Experience Platform Debugger；报表源；开发人员工具
description: 了解如何为使用Analytics的活动指定Analytics跟踪服务器 [!DNL Target] (A4T)。
title: 如何使用Analytics跟踪服务器？
feature: Analytics for Target (A4T)
exl-id: 8066d6a6-661e-428b-9d5c-18537a80fb43
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 21%

---

# 使用 [!DNL Analytics] 跟踪服务器

如果您使用的是较低版本的at.js，则必须指定 [!DNL Analytics] 使用的活动的跟踪服务器 [!DNL Adobe Analytics] 对象 [!DNL Adobe Target] (A4T)。

>[!NOTE]
>
>如果您使用 at.js 版本 0.9.1（或更高版本），则在活动创建期间无需指定跟踪服务器。at.js 库自动将跟踪服务器值发送到 [!DNL Target]。在活动创建期间，您可以将[!UICONTROL 目标和设置]页面上的[!UICONTROL 跟踪服务器]字段留空。
>
>此 [!DNL Target] 团队同时支持at.js 1.*x* 与 at.js 2.*x* 之间的映射。请升级到任一主要版本的at.js的最新更新，以确保您运行的是受支持的版本。 有关更多信息，请参阅 [at.js版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank}.

为确保数据来自 [!DNL Target] 转到中的正确位置 [!DNL Analytics]， A4T需要 [!DNL Analytics] 要发送的所有对Modstats的调用中的跟踪服务器 [!DNL Target]. 对于使用多个跟踪服务器的实施，请使用 [!DNL Adobe Experience Platform Debugger] 或浏览器的开发人员工具来确定活动的正确跟踪服务器。

## 获取 [!DNL Analytics] 跟踪服务器使用 [!DNL Adobe Experience Platform Debugger]

应在交付活动的页面上查看调试器，以确保选择正确的跟踪服务器。 您还可以为每个帐户指定一个默认的跟踪服务器。要指定或修改默认的跟踪服务器，请联系客户关怀团队。

1. 从要创建活动的页面中，打开 [!DNL Adobe Experience Platform Debugger].

   如果尚未安装调试器，请参阅 [Adobe Experience Platform Debugger概述](https://experienceleague.adobe.com/docs/platform-learn/data-collection/debugger/overview.html).

1. 单击 **[!UICONTROL 分析]** 左侧导航菜单中。

   ![Screen_DebuggerTrackServ图像](assets/Screen_DebuggerTrackServ.png)

   此 [!DNL Analytics] 跟踪服务器位于 [!UICONTROL 主机名] 部分。

   * **第一方跟踪服务器**：如果请求的主机名与您所在的域匹配，则它是第一方跟踪服务器。 例如，如果您在 `adobe.com`， `adobe.com` 是第一方跟踪服务器。
   * **第三方跟踪服务器**：第三方跟踪服务器通常 `[company].sc.omtrdc.net` 其中，公司是公司的名称，但总是以 `sc.omtrdc.net`.
   * **CNAME实施**： `sstats.adobe.com` 是https （安全）请求的CNAME第一方跟踪服务器示例。 `stats.adobe.com` 是http（非安全）页面的CNAME第一方请求示例。

1. 复制该字段的全部内容。

1. 在活动的“**[!UICONTROL 目标和设置]****[!UICONTROL ”屏幕的“]**&#x200B;报表设置&#x200B;**[!UICONTROL ”部分中，将复制的跟踪服务器信息粘贴到跟踪服务器]**&#x200B;字段中。

   >[!NOTE]
   >
   >选择 [!UICONTROL 将Analytics作为报表源] （对于您的活动） [!UICONTROL 跟踪服务器] 字段可用。

## 获取 [!DNL Analytics] 使用浏览器的开发人员工具跟踪服务器

应在交付活动的页面上查看开发人员工具，以确保选择正确的跟踪服务器。 您还可以为每个帐户指定一个默认的跟踪服务器。要指定或修改默认的跟踪服务器，请联系客户关怀团队。

1. 从创建活动的页面上，打开浏览器的开发人员工具(在Google Chrome中，单击右上角的三个垂直省略号> “更多工具” > “开发人员工具”)。

   ![Chrome开发人员工具](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. 单击 **[!UICONTROL 网络]** 选项卡。

1. 筛选对象 `/ss,` 以显示 [!DNL Analytics] 请求。

   ![带有/ss搜索的Chrome开发人员工具](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-search.png)

   跟踪服务器是请求的主机名。

   * **第一方跟踪服务器**：如果请求的主机名与您所在的域匹配，则它是第一方跟踪服务器。 例如，如果您在 `adobe.com`， `adobe.com` 是第一方跟踪服务器。
   * **第三方跟踪服务器**：第三方跟踪服务器通常 `[company].sc.omtrdc.net` 其中，公司是公司的名称，但总是以 `sc.omtrdc.net`.
   * **CNAME实施**： `sstats.adobe.com` 是https （安全）请求的CNAME第一方跟踪服务器示例。 `stats.adobe.com` 是http（非安全）页面的CNAME第一方请求示例。

1. 复制该字段的全部内容。

1. 在活动的“**[!UICONTROL 目标和设置]****[!UICONTROL ”屏幕的“]**&#x200B;报表设置&#x200B;**[!UICONTROL ”部分中，将复制的跟踪服务器信息粘贴到跟踪服务器]**&#x200B;字段中。

   >[!NOTE]
   >
   >选择 [!UICONTROL 将Analytics作为报表源] （对于您的活动） [!UICONTROL 跟踪服务器] 字段可用。
