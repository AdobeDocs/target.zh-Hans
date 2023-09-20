---
keywords: 定位；analytics；跟踪服务器；analytics for target；a4t
description: 了解如何在中配置活动 [!DNL Adobe Target] 使用 [!DNL Adobe Analytics] 作为报表源(A4T)。
title: 如何使用 [!DNL Analytics] 数据输入 [!DNL Target]？
feature: Analytics for Target (A4T)
exl-id: 85605ff9-c09a-4a1a-9784-bdacda377e1d
source-git-commit: 8682c24cf1740171dd2ce1862b3bdce1e2082869
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 19%

---

# 使用 [!DNL Adobe Analytics] 数据

您可以在中配置活动 [!DNL Adobe Target] 使用 [!DNL Adobe Analytics] 作为报表源(A4T)。

有关设置的详细信息 [!DNL Analytics] 作为的数据源 [!DNL Target]，请参见 [将Adobe Analytics作为Adobe Target报表源](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

在设置使用以下对象的活动之前： [!DNL Analytics] 作为报表源，建立活动的目标，如提高每位访客带来的收入(RPV)或增加购物车的点击次数。 需为活动选择最终成功量度。尽管您可以随时在以下内容中选择其他量度： [!DNL Analytics]时，您仍必须指定希望此测试影响的特定指标。

>[!NOTE]
>
>此 [!DNL Adobe Analytics] 选项仅在您关联 [!DNL Adobe Experience Cloud] 帐户（包含两者） [!DNL Analytics] 和 [!DNL Target]，即使集成介于 [!DNL Target] 和 [!DNL Analytics] 尚未为您的帐户设置。

选择时 [!DNL Analytics] 作为的报表源 [!DNL Target]，您选择 [!DNL Analytics] 要接收的报表包 [!DNL Target] 活动数据。 要指定报表源，请先从以下任意选项中选择 [!DNL Analytics] 您的帐户绑定的公司，然后为活动选择适当的报表包。 仅限配置为连接到的报表包 [!DNL Adobe Target] 可供选择。 如果您没有看到预期的报表包，请先尝试注销并重新登录到 [!DNL Adobe Experience Cloud] 再试一次。 如果列表中仍缺少报表包，请联系客户关怀团队。

[!UICONTROL 目标分析] (A4T)需要跟踪服务器才能正确报告结果。 默认跟踪服务器显示在 [!UICONTROL 跟踪服务器] 字段。 如果使用多个跟踪服务器，请确保在此字段中包含正确的跟踪服务器。 请参阅 [使用Analytics跟踪服务器](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) 以了解更多信息。

>[!NOTE]
>
>如果您使用 [!DNL Adobe Analytics] 作为活动的报表源，如果您使用at.js版本0.9.1（或更高版本），则无需在活动创建期间指定跟踪服务器。 at.js 库自动将跟踪服务器值发送到 [!DNL Target]。在活动创建期间，您可以将[!UICONTROL 目标和设置]页面上的[!UICONTROL 跟踪服务器]字段留空。

设置后设置活动时 [!DNL Analytics] 作为您的报表源，没有选项可用于设置报表受众。 [!DNL Analytics] 在以下位置提供了区段： [!DNL Target] [!UICONTROL 活动] 报告。

您必须选择一个成功量度以用作每个活动的目标。 您的活动目标是表示活动取得成功的转化活动。如果没有设定目标来以某种特定方式做出改进，最好不要运行测试。您可以选择任意 [!DNL Analytics] 中的可用量度 [!DNL Analytics] 量度选择器。

设置目标并不意味着您不能在评估测试结果时使用其他量度。但是，目标可提醒您要通过测试加以改进的方面。

访客完成目标后，该访客将不再包含在活动中。 如果访客在完成活动后重新进入您的活动，则该访客将被计为新访客。
