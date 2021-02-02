---
keywords: a4t;A4T;Analytics 作为 Target 报表源
description: 您可以将 Target Standard/Premium 中的活动配置为使用 Adobe Analytics 作为报表源 (A4T)。
title: 创建使用A4T作为活动源的报告
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 4f0f1df1bcb6baad0e20c4dc1ae7e12751080d91
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 36%

---


# 创建将Analytics用作活动源的报告

可以在[!DNL Target]中配置活动以使用[!DNL Adobe Analytics]作为报告源(A4T)。

在设置使用[!DNL Analytics]作为活动源的报告之前，建立活动的目标，如提高每访客收入(RPV)或增加购物车的点击量。 需为活动选择最终成功量度。尽管您可以随时在[!DNL Analytics]中选择其他度量，但您仍必须指定您希望此测试影响的特定度量。

## 创建活动

创建使用[!DNL Analytics]作为活动源的[!DNL Target]报告与设置常规[!DNL Target]活动相似，但有一些重要区别。 例如，在创建报告时，您无法选择活动段，因为在查看报告时，可以应用[!DNL Analytics]中可用的所有段。

1. 单击&#x200B;**[!UICONTROL 创建活动]**。

   >[!NOTE]
   >
   >如果[!DNL Analytics]用作活动源，则报告名称不能包括“%”字符。

1. 选择活动类型并开始设置活动。

   如果要创建[!UICONTROL 自动分配]或[!UICONTROL 自动目标]活动，请参阅[自动分配和自动目标活动的A4T支持，以了解详细信息。](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md)

1. 在活动创建流程的&#x200B;**[!UICONTROL 设置]**&#x200B;部分，选择 **[!UICONTROL Adobe Analytics]**，然后指定您的公司。
1. 选择一个报表包。

   您可以选择[!DNL Analytics]中任何可用的报表包。 报表包定义提供所收集数据的位置。报表包列表中不包含虚拟报表包。

   选择报表包时，您可能会遇到两种错误：

   * 遇到没有任何可用报表包的错误，但是您的帐户已正确设置。

      您可能需要检查[!DNL Analytics]公司。 如果您的[!DNL Adobe Experience Cloud]帐户绑定到多个[!DNL Analytics]公司，请注销[!DNL Target]，然后在正确的公司下登录到[!DNL Analytics]。 然后返回[!DNL Target]，将加载报表包。

   * 看不到预期的报表包。

      只有设置为连接到[!DNL Target]的报表包才可供选择。 如果您没有看到您期望的报表包，请先尝试注销，然后重新登录到[!DNL Adobe Experience Cloud]以重试。
   如果列表中仍缺少报告套件，请[联系客户服务部门](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

1. 指定跟踪服务器。

   请参阅[使用 Analytics 跟踪服务器](/help/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)。

1. 定义体验。
1. 指定活动目标。

   您需要选择成功量度，以用作每个活动的目标。 您的活动目标是表示活动取得成功的转化活动。如果没有设定目标来以某种特定方式做出改进，最好不要运行测试。您可以选择[!DNL Analytics]度量选择器中可用的任何[!DNL Analytics]度量。

   >[!NOTE]
   >
   >可以向[!DNL Analytics]发送基于目标的自定义度量，而不是仅依赖[!DNL Analytics]数据。 例如，您可以监视单击某页面的情况，该页面通常不由[!DNL Analytics]跟踪。 此自定义度量会从[!DNL Target]服务器自动发送到[!DNL Analytics]，并在[!DNL Analytics]的度量选择器中显示为“[!DNL Target]转换”度量。 如果选择使用[!DNL Analytics]度量，则[!DNL Target]转换度量为空。

   设置目标并不意味着您不能在评估测试结果时使用其他量度。但是，目标可提醒您要通过活动加以改进的方面。

   达到目标后，访客会继续保留在活动中。访客会继续看到活动内容，但不会被计为一次新活动参加。

   >[!NOTE]
   >
   >在将[!DNL Analytics]设置为活动源后设置报告时，没有设置受众的选项。 [!DNL Analytics] 区段可在活动报 [!DNL Target] 告中找到。

1. 单击&#x200B;**[!UICONTROL 保存]**。

## A4T和自动分配和自动目标活动

有关详细信息，请参阅[A4T支持自动分配和自动目标活动](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md)。