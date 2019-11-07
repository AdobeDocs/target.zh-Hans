---
keywords: Analytics 跟踪服务器;A4T;Adobe Experience Cloud 调试器;报表源
description: 如果您使用的是较低版本的 at.js 或 mbox.js，则必须为使用 Analytics for Target (A4T) 的活动指定 Analytics 跟踪服务器。
title: 使用 Analytics 跟踪服务器
uuid: ad700b90-f409-496a-bc26-0f0367410a85
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 使用 Analytics 跟踪服务器{#use-an-analytics-tracking-server}

如果您使用的是较低版本的 at.js 或 mbox.js，则必须为使用 Analytics for Target (A4T) 的活动指定 Analytics 跟踪服务器。

>[!NOTE]
>
>如果您使用 Adobe Analytics 作为活动的报表源，并且使用的是 mbox.js 版本 61（或更高版本）或者 at.js 版本 0.9.1（或更高版本），则无需在活动创建期间指定跟踪服务器。mbox.js 或 at.js 库会自动将跟踪服务器值发送到 [!DNL Target]。在活动创建期间，您可以将“[!UICONTROL 目标和设置]”页面上的“[!UICONTROL 跟踪服务器]”字段留空。

为确保来自 Target 的数据转到 Analytics 中的正确位置，A4T 要求在从 Target 进行的所有 Modstats 调用中都发送一个 Analytics 跟踪服务器。对于使用了多个跟踪服务器的实施，您可以使用 Adobe Experience Cloud 调试器来确定适用于您的活动的正确跟踪服务器。

应该在将交付活动的页面上查看该调试器，以确保您选择的跟踪服务器正确无误。您还可以为每个帐户指定一个默认的跟踪服务器。要指定或修改默认的跟踪服务器，请联系客户关怀团队。

1. 从您正在创建活动的页面上，打开 Adobe Experience Cloud 调试器。

   如果尚未安装调试器，请参阅安 [装Experience cloud调试器](https://docs.adobe.com/content/help/en/debugger/using/install-debugger.html)。

   ![](assets/Screen_DebuggerTrackServ.png)

   可在该调试器的“SiteCatalyst 图像”部分找到 Analytics 跟踪服务器。该跟踪服务器字段名为“第一方 Cookie”**&#x200B;或“第三方 Cookie”**（具体取决于实施），且其值将使用以下任一格式：

   * （对于 CNAME 实施）
   * （对于非 RDC 实施）
   * （对于 RDC 实施）
   *Company* 表示 Analytics 公司名称，*metrics* 是 CNAME 值的一个示例，而 *d1* 是 Analytics 数据中心的一个示例。
1. 复制该字段的全部内容。
1. 在活动的“[!UICONTROL 目标和设置][!UICONTROL ”屏幕的“]报表设置&#x200B;**”部分中，将复制的跟踪服务器信息粘贴到[!UICONTROL 跟踪服务器]**&#x200B;字段中。

   >[!NOTE]
   >
   >要使“跟踪服务器”字段可用，您必须选择 Adobe Analytics 作为活动的报表源。

