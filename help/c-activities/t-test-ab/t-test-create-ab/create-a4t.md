---
keywords: Targeting;analytics;tracking server
description: 您可以将 Target Standard 中的活动配置为使用 Adobe Analytics 作为报表源 (A4T)。
title: 使用 Analytics 数据
feature: null
uuid: 4ac0c181-030b-4cf5-b138-acf02c7af4f6
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 95%

---


# 使用 Analytics 数据{#using-analytics-data}

您可以将 Target Standard 中的活动配置为使用 Adobe Analytics 作为报表源 (A4T)。

For detailed information about setting up Analytics as the data source for Target, see [Adobe Analytics as the Reporting Source for Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md).

在设置将 Analytics 用作报表源的活动之前，请先为该活动建立目标，例如提升每位访客带来的收入 (RPV) 或增加购物车的点击量。需为营销活动选择最终成功量度。尽管可以在 Analytics 中随时选择其他量度，但您仍然必须指定希望此测试影响的特定量度。

>[!NOTE]
>
>如果您已将 Adobe Experience Cloud 帐户与 Analytics 帐户和 Target 帐户均关联，则即使还没有为您的帐户设置 Target 与 Analytics 集成，Adobe Analytics 选项也将可用。

当选择 Analytics 作为 Target 的报告源时，您可以选择一个 Analytics 报表包来接收 Target 活动数据。要执行此操作，请先选择您的帐户绑定的任意 Analytics 公司，然后为活动选择合适的报表包。只有配置为连接至 Adobe Target 的报表包才可供选择。如果您看不到预期的报表包，请先注销 Adobe Experience Cloud，然后再重新登录以重试。如果报表包仍然没有出现在列表中，请联系客户关怀团队。

为正确报告结果，Analytics for Target 需要使用跟踪服务器。“跟踪服务器”字段中将显示默认的跟踪服务器。如果您使用多个跟踪服务器，则应进行检查以确保此字段中包含正确的跟踪服务器。请参阅[使用 Analytics 跟踪服务器](../../../c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)，以了解更多信息。

>[!NOTE]
>
>如果您使用 Adobe Analytics 作为活动的报表源，并且使用的是 mbox.js 版本 61（或更高版本）或者 at.js 版本 0.9.1（或更高版本），则无需在活动创建期间指定跟踪服务器。mbox.js 或 at.js 库会自动将跟踪服务器值发送到 [!DNL Target]。在活动创建期间，您可以将“[!UICONTROL 目标和设置]”页面上的“[!UICONTROL 跟踪服务器]”字段留空。

将 Analytics 设置为报表源后，在设置活动时，不会显示用于设置报表受众的选项。Analytics 区段在“目标活动”报表中可用。

您需要为每个测试选择一个用作目标的成功量度。您的活动目标是表示营销活动取得成功的转化活动。如果没有设定目标来以某种特定方式做出改进，最好不要运行测试。您可以选择 Analytics 量度选择器中提供的任意 Analytics 量度。

设置目标并不意味着您不能在评估测试结果时使用其他量度。但是，目标可提醒您要通过测试加以改进的方面。

访客完成您设定的目标后，便不会再将其包含在营销活动中。如果访客在完成活动后再次进入营销活动，则会将其计为一位新访客。
