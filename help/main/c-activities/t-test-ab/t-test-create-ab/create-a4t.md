---
keywords: 定位；analytics；跟踪服务器；analytics for target；a4t
description: 了解如何在 [!DNL Adobe Target] 中配置活动以使用 [!DNL Adobe Analytics] 作为报表源(A4T)。
title: 如何在 [!DNL Target]中使用 [!DNL Analytics] 数据？
feature: Analytics for Target (A4T)
exl-id: 85605ff9-c09a-4a1a-9784-bdacda377e1d
source-git-commit: 8682c24cf1740171dd2ce1862b3bdce1e2082869
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 16%

---

# 使用[!DNL Adobe Analytics]数据

您可以将[!DNL Adobe Target]中的活动配置为使用[!DNL Adobe Analytics]作为报表源(A4T)。

有关将[!DNL Analytics]设置为[!DNL Target]的数据源的详细信息，请参阅[Adobe Analytics作为Adobe Target的报表Source](/help/main/c-integrating-target-with-mac/a4t/a4t.md)。

在设置使用[!DNL Analytics]作为报表源的活动之前，请建立该活动的目标，如提高每位访客带来的收入(RPV)或增加购物车的点击次数。 需为活动选择最终成功量度。尽管您可以随时在[!DNL Analytics]中选择其他量度，但您仍必须指定希望此测试影响的特定量度。

>[!NOTE]
>
>如果您已将您的[!DNL Adobe Experience Cloud]帐户与[!DNL Analytics]和[!DNL Target]都关联，则即使尚未为您的帐户设置[!DNL Target]和[!DNL Analytics]之间的集成，也可以使用[!DNL Adobe Analytics]选项。

选择[!DNL Analytics]作为[!DNL Target]的报告源时，请选择一个[!DNL Analytics]报告包来接收[!DNL Target]活动数据。 要指定报表源，请先从您的帐户绑定的[!DNL Analytics]家公司中选择任意，然后为活动选择合适的报表包。 只有配置为连接到[!DNL Adobe Target]的报表包才可供选择。 如果您没有看到预期的报表包，请先尝试注销并重新登录到[!DNL Adobe Experience Cloud]以重试。 如果列表中仍缺少报表包，请联系客户关怀团队。

[!UICONTROL Analytics for Target] (A4T)需要跟踪服务器才能正确报告结果。 [!UICONTROL Tracking Server]字段中将显示默认跟踪服务器。 如果使用多个跟踪服务器，请确保在此字段中包含正确的跟踪服务器。 有关详细信息，请参阅[使用Analytics跟踪服务器](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)。

>[!NOTE]
>
>如果您使用[!DNL Adobe Analytics]作为活动的报表源，并且使用的是at.js版本0.9.1（或更高版本），则无需在活动创建期间指定跟踪服务器。 at.js 库自动将跟踪服务器值发送到 [!DNL Target]。在活动创建期间，您可以将[!UICONTROL Goals & Settings]页面上的[!UICONTROL Tracking Server]字段留空。

在将[!DNL Analytics]设置为报表源后设置活动时，没有用于设置报表受众的选项。 [!DNL Analytics]区段在[!DNL Target] [!UICONTROL Activities]报表中可用。

您必须选择一个成功量度以用作每个活动的目标。 您的活动目标是表示活动取得成功的转化活动。如果没有设定目标来以某种特定方式做出改进，最好不要运行测试。您可以选择[!DNL Analytics]量度选择器中可用的任何[!DNL Analytics]量度。

设置目标并不意味着您不能在评估测试结果时使用其他量度。但是，目标可提醒您要通过测试加以改进的方面。

访客完成目标后，该访客将不再包含在活动中。 如果访客在完成活动后重新进入您的活动，则该访客将被计为新访客。
