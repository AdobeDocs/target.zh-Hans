---
keywords: a4t;A4T;Analytics 作为 Target 报表源
description: 了解如何在Adobe [!DNL Target] 中配置将Adobe Analytics用作报告源(A4T)的活动。
title: 如何创建使用A4T的活动?
feature: Analytics for Target (A4T)
exl-id: 6a09764a-8bf1-4f69-b871-fb23136f933e
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 32%

---

# 创建将Analytics用作活动源的报告

可以在[!DNL Adobe Target]中配置活动以使用[!DNL Adobe Analytics]作为报告源(A4T)。

在设置使用[!DNL Analytics]作为报告源的活动之前，请确定活动的目标，如提高每访客收入(RPV)或增加购物车的点击量。 需为活动选择最终成功量度。尽管您可以在[!DNL Analytics]中随时选择更多量度，但您仍必须指定您希望此测试影响的特定量度。

## 创建活动

创建使用[!DNL Analytics]作为报告源的[!DNL Target]活动与设置常规[!DNL Target]活动类似，但有一些重要差异。 例如，在创建活动时，您无法选择报告区段，因为在查看报表时，[!DNL Analytics]中可用的所有区段均可应用。

1. 单击&#x200B;**[!UICONTROL 创建活动]**。

   >[!NOTE]
   >
   >如果[!DNL Analytics]用作活动源，则报告名称不能包含“%”字符。

1. 选择活动类型并开始设置活动。

   如果要创建[!UICONTROL 自动分配]或[!UICONTROL 自动目标]活动，请参阅[自动分配和自动目标活动支持](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md)以了解详细信息。

1. 在活动创建流程的&#x200B;**[!UICONTROL 设置]**&#x200B;部分，选择 **[!UICONTROL Adobe Analytics]**，然后指定您的公司。
1. 选择一个报表包。

   您可以选择[!DNL Analytics]中任何可用的报表包。 报表包定义收集数据的可用位置。 报表包列表中不包含虚拟报表包。

   选择报表包时，您可能会遇到两种错误：

   * 遇到没有任何可用报表包的错误，但是您的帐户已正确设置。

      检查您的[!DNL Analytics]公司。 如果您的[!DNL Adobe Experience Cloud]帐户与多个[!DNL Analytics]公司关联，请注销[!DNL Target]，然后在正确的公司下登录到[!DNL Analytics]。 然后返回[!DNL Target]，报表包将加载。

   * 看不到预期的报表包。

      只有设置为连接到[!DNL Target]的报表包才可供选择。 如果未看到预期的报表包，请先尝试注销，然后登录[!DNL Adobe Experience Cloud]以重试。
   如果列表中仍有一个或多个报表包缺失，请[联系客户关怀部门](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

1. 指定跟踪服务器。

   请参阅[使用 Analytics 跟踪服务器](/help/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)。

1. 定义体验。
1. 指定活动目标。

   您需要选择一个成功量度以用作每个活动的目标。 您的活动目标是表示活动取得成功的转化活动。如果没有设定目标来以某种特定方式做出改进，最好不要运行测试。您可以选择[!DNL Analytics]量度选择器中可用的任何[!DNL Analytics]量度。

   >[!NOTE]
   >
   >您可以将基于目标的自定义量度发送到[!DNL Analytics]，而不是仅依赖[!DNL Analytics]数据。 例如，您可以监视单击页面的情况，该页面通常不由[!DNL Analytics]跟踪。 此自定义量度会从[!DNL Target]服务器自动发送到[!DNL Analytics]，并在[!DNL Analytics]的量度选择器中显示为“[!DNL Target]转换”量度。 如果选择使用[!DNL Analytics]量度，则[!DNL Target]转换量度为空。

   设置目标并不意味着您不能在评估测试结果时使用其他量度。但是，目标可提醒您要通过活动加以改进的方面。

   达到目标后，访客会继续保留在活动中。访客会继续看到活动内容，但不会被计为一次新活动参加。

   >[!NOTE]
   >
   >在将[!DNL Analytics]设置为活动源后设置报告时，没有设置报告受众的选项。 [!DNL Analytics] 区段可在“活动”报 [!DNL Target] 表中使用。

1. 单击&#x200B;**[!UICONTROL 保存]**。

## A4T和自动分配和自动目标活动

有关详细信息，请参阅[A4T支持自动分配和自动目标活动](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md)。
