---
keywords: a4t;A4T;Analytics 作为 Target 报表源
description: 了解如何在Adobe中配置活动 [!DNL Target] 使用Adobe Analytics作为报表源(A4T)的报表包。
title: 如何创建使用A4T的活动？
feature: Analytics for Target (A4T)
exl-id: 6a09764a-8bf1-4f69-b871-fb23136f933e
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 35%

---

# 创建使用 Analytics 作为报表源的活动

您可以在 [!DNL Adobe Target] 使用 [!DNL Adobe Analytics] 作为报表源(A4T)。

在设置使用 [!DNL Analytics] 作为报表源，确立活动目标，例如提高每位访客带来的收入(RPV)或增加购物车的点击量。 需为活动选择最终成功量度。尽管您可以在 [!DNL Analytics]，则您仍必须指定希望此测试影响的特定量度。

## 创建活动

创建 [!DNL Target] 使用 [!DNL Analytics] 因为报表源类似于设置常规 [!DNL Target] 活动，但存在一些重要差异。 例如，在创建活动时，您无法选择要报告的区段，因为 [!DNL Analytics] 可在查看报表时应用。

1. 单击&#x200B;**[!UICONTROL 创建活动]**。

   >[!NOTE]
   >
   >如果 [!DNL Analytics] 用作报表源。

1. 选择活动类型并开始设置活动。

   如果要创建 [!UICONTROL 自动分配] 或 [!UICONTROL 自动定位] 活动，请参阅 [对自动分配和自动定位活动的A4T支持](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md) 以了解更多信息。

1. 在活动创建流程的&#x200B;**[!UICONTROL 设置]**&#x200B;部分，选择 **[!UICONTROL Adobe Analytics]**，然后指定您的公司。
1. 选择一个报表包。

   您可以选择 [!DNL Analytics]. 报表包可定义收集数据的可用位置。 报表包列表中不包含虚拟报表包。

   选择报表包时，您可能会遇到两种错误：

   * 遇到没有任何可用报表包的错误，但是您的帐户已正确设置。

      检查 [!DNL Analytics] 公司。 如果 [!DNL Adobe Experience Cloud] 帐户绑定到多个 [!DNL Analytics] 公司注销 [!DNL Target]，然后登录到 [!DNL Analytics] 在正确的公司下。 然后返回到 [!DNL Target]，并加载报表包。

   * 看不到预期的报表包。

      仅配置为连接到的报表包 [!DNL Target] 可供选择。 如果您看不到预期的报表包，请首先尝试注销并重新登录到 [!DNL Adobe Experience Cloud] 再试一次。
   如果列表中仍缺少一个或多个报表包，请 [联系客户关怀团队](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

1. 指定跟踪服务器。

   请参阅[使用 Analytics 跟踪服务器](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)。

1. 定义体验。
1. 指定活动目标。

   您需要选择一个成功量度以用作每个活动的目标。 您的活动目标是表示活动取得成功的转化活动。如果没有设定目标来以某种特定方式做出改进，最好不要运行测试。您可以选择任意 [!DNL Analytics] 量度 [!DNL Analytics] 量度选择器。

   >[!NOTE]
   >
   >您可以将基于Target的自定义量度发送到 [!DNL Analytics] 而不是只依赖 [!DNL Analytics] 数据。 例如，您可以监视点击页面的情况，该情况通常不会被 [!DNL Analytics]. 此自定义量度将发送到 [!DNL Analytics] 自动从 [!DNL Target] 服务器，并显示为“[!DNL Target] 中量度选择器中的“转化”量度 [!DNL Analytics]. 的 [!DNL Target] 如果您选择使用 [!DNL Analytics] 量度。

   设置目标并不意味着您不能在评估测试结果时使用其他量度。但是，目标可提醒您要通过活动加以改进的方面。

   达到目标后，访客会继续保留在活动中。访客会继续看到活动内容，但不会被计为一次新活动参加。

   >[!NOTE]
   >
   >在设置 [!DNL Analytics] 作为报表源，没有选项可设置报表的受众。 [!DNL Analytics] 区段在 [!DNL Target] 活动报表。

1. 单击&#x200B;**[!UICONTROL 保存]**。

## A4T和自动分配和自动定位活动

有关更多信息，请参阅[自动分配和自动定位活动支持 A4T](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)。
