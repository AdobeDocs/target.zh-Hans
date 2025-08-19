---
keywords: a4t;A4T;Analytics 作为 Target 报表源
description: 了解如何在Adobe [!DNL Target] 中配置使用Adobe Analytics作为报表源(A4T)的活动。
title: 如何创建使用A4T的活动？
feature: Analytics for Target (A4T)
exl-id: 6a09764a-8bf1-4f69-b871-fb23136f933e
source-git-commit: 981cff428d9e8849b9bbcbf7bef389dad0fbb32a
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 30%

---

# 创建使用 Analytics 作为报表源的活动

您可以将[!DNL Adobe Target]中的活动配置为使用[!DNL Adobe Analytics]作为报表源(A4T)。

在设置使用[!DNL Analytics]作为报表源的活动之前，请建立该活动的目标，如提高每位访客带来的收入(RPV)或增加购物车的点击次数。 需为活动选择最终成功量度。尽管您可以随时在[!DNL Analytics]中选择更多量度，但您仍必须指定希望此测试影响的特定量度。

## 创建活动

创建使用[!DNL Target]作为报表源的[!DNL Analytics]活动与设置常规[!DNL Target]活动类似，但存在一些重要差异。 例如，在创建活动时无法选择要报告的区段，因为可在查看报告时应用[!DNL Analytics]中所有可用的区段。

1. 单击 **[!UICONTROL Create Activity]**。

   >[!NOTE]
   >
   >如果使用[!DNL Analytics]作为报表源，则活动名称不能包含“%”字符。
   >
   >对于来自使用A4T报表的独立[工作区](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)的两个活动，请勿使用相同的活动名称。

1. 选择活动类型并开始设置活动。

   如果要创建[!UICONTROL Auto-Allocate]或[!UICONTROL Auto-Target]活动，请参阅自动分配和自动定位活动支持[A4T](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)以了解更多信息。

1. 进入活动创建流程的&#x200B;**[!UICONTROL Settings]**&#x200B;部分时，请选择&#x200B;**[!UICONTROL Adobe Analytics]**&#x200B;并指定您的公司。
1. 选择一个报表包。

   您可以在[!DNL Analytics]中选择任何可用的报表包。 报表包定义收集的数据在何处可用。 报表包列表中不包含虚拟报表包。

   选择报表包时，您可能会遇到两种错误：

   * 遇到没有任何可用报表包的错误，但是您的帐户已正确设置。

     检查您的[!DNL Analytics]公司。 如果您的[!DNL Adobe Experience Cloud]帐户与多个[!DNL Analytics]公司关联，请注销[!DNL Target]，然后在正确的公司下登录到[!DNL Analytics]。 然后返回到[!DNL Target]，并加载报表包。

   * 看不到预期的报表包。

     只有配置为连接到[!DNL Target]的报表包才可供选择。 如果您没有看到预期的报表包，请先尝试注销并重新登录到[!DNL Adobe Experience Cloud]以重试。

   如果列表中仍缺少一个或多个报表包，请[联系客户关怀团队](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

1. 指定跟踪服务器。

   请参阅[使用 Analytics 跟踪服务器](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)。

1. 定义体验。
1. 指定活动目标。

   您需要选择一个成功量度以用作每个活动的目标。 您的活动目标是表示活动取得成功的转化活动。如果没有设定目标来以某种特定方式做出改进，最好不要运行测试。您可以选择[!DNL Analytics]量度选择器中可用的任何[!DNL Analytics]量度。

   >[!NOTE]
   >
   >您可以向[!DNL Analytics]发送基于Target的自定义量度，而不是仅依赖于[!DNL Analytics]数据。 例如，您可以监视点击页面，该页面通常不受[!DNL Analytics]的跟踪。 此自定义指标自动从[!DNL Analytics]服务器发送到[!DNL Target]，并在[!DNL Target]的指标选择器中显示为“[!DNL Analytics]转化”指标。 如果您选择使用[!DNL Target]量度，[!DNL Analytics]转化量度为空。

   设置目标并不意味着您不能在评估测试结果时使用其他量度。但是，目标可提醒您要通过活动加以改进的方面。

   达到目标后，访客会继续保留在活动中。访客会继续看到活动内容，但不会被计为一次新活动参加。

   >[!NOTE]
   >
   >在将[!DNL Analytics]设置为报表源后设置活动时，没有用于设置报表受众的选项。 [!DNL Analytics]区段在[!DNL Target]活动报表中可用。

1. 单击 **[!UICONTROL Save]**。

## A4T以及自动分配和自动定位活动

有关详细信息，请参阅自动分配和自动定位活动支持[A4T](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)。
