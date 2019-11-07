---
keywords: a4t;A4T;Analytics 作为 Target 报表源
description: 您可以将 Target Standard/Premium 中的活动配置为使用 Adobe Analytics 作为报表源 (A4T)。
title: 活动创建
topic: Advanced,Standard,Classic
uuid: b04ad535-62fb-4dd3-ab3f-23da60fbffbd
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 活动创建{#activity-creation}

您可以将 Target Standard/Premium 中的活动配置为使用 Adobe Analytics 作为报表源 (A4T)。

在设置将 Analytics 用作报表源的活动之前，请先为该活动建立目标，例如提升每位访客带来的收入 (RPV) 或增加购物车的点击量。需为活动选择最终成功量度。尽管可以在 Analytics 中随时选择其他量度，但您仍然必须指定希望此测试影响的特定量度。

创建将 Analytics 用作报表源的 Target Standard 活动的过程与设置常规 Target Standard 活动大体类似，但也有几处重要的差异。例如，在创建活动时，您无法选择报表的区段，因为在查看报表时，可应用 Analytics 中的所有可用区段。

1. 单击&#x200B;**[!UICONTROL 创建活动]**。

   >[!NOTE]
   >
   >如果使用 Analytics 作为报表源，则活动名称中不能包含“%”字符。

1. 选择活动类型并开始设置活动。
1. 在活动创建流程的&#x200B;**[!UICONTROL 设置]**&#x200B;部分，选择 **[!UICONTROL Adobe Analytics]**，然后指定您的公司。
1. 选择一个报表包。

   可以选择您在 Adobe Analytics 中可用的任何报表包。报表包定义提供所收集数据的位置。报表包列表中不包含虚拟报表包。

   选择报表包时，您可能会遇到两种错误：

   * 遇到没有任何可用报表包的错误，但是您的帐户已正确设置。
   您可能需要检查自己的 Analytics 公司。如果您的 Experience Cloud 帐户已与多个 Analytics 公司绑定，请从 Target 注销，再通过正确的公司登录到 Analytics。然后，返回到 Target，此时将会加载报表包。

   * 看不到预期的报表包。
   只有配置为连接至 Adobe Target 的报表包才可供选择。如果您看不到预期的报表包，请先注销 Adobe Experience Cloud，然后再重新登录以重试。

   如果列表中仍然缺少相应的报表包，请[联系客户关怀团队](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。
1. 指定跟踪服务器。

   请参阅[使用 Analytics 跟踪服务器](../../c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)。

1. 定义体验。
1. 指定活动目标。

   您需要为每个测试选择一个用作目标的成功量度。您的活动目标是表示活动取得成功的转化活动。如果没有设定目标来以某种特定方式做出改进，最好不要运行测试。您可以选择 Analytics 量度选择器中提供的任意 Analytics 量度。

   >[!NOTE]
   >
   >您可以向 Analytics 发送基于 Target 的自定义量度，而不是只依赖于 Analytics 数据。例如，您可以监测页面上的点击操作，而 Analytics 通常不会跟踪该操作。此自定义量度会自动从 Target 服务器发送到 Analytics，并在 Analytics 的量度选择器中显示为“Target 转化”量度。如果您选择使用 Analytics 量度，则“Target 转化”量度将为空。

   设置目标并不意味着您不能在评估测试结果时使用其他量度。但是，目标可提醒您要通过活动加以改进的方面。

   达到目标后，访客会继续保留在活动中。访客会继续看到活动内容，但不会被计为一次新活动参加。

   >[!NOTE]
   >
   >将 Analytics 设置为报表源后，在设置活动时，不会显示用于设置报表受众的选项。Analytics 区段在“目标活动”报表中可用。

1. 单击&#x200B;**[!UICONTROL 保存]**。

