---
keywords: a4t;A4T;Analytics as the reporting source for Target
description: 您可以将 Target Standard/Premium 中的活动配置为使用 Adobe Analytics 作为报表源 (A4T)。
title: 创建使用A4T作为活动源的报告
feature: a4t general
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '1391'
ht-degree: 17%

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

## 目标分析(A4T)支持自动分配和自动目标活动{#a4t-aa}

我们已升级了Adobe Target到Adobe Analytics的集成，称为[目标分析](/help/c-integrating-target-with-mac/a4t/a4t.md)。 自动分配和自动目标活动现在支持Analytics进行目标。

此集成允许您：

* 使用[自动分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)的多武装强盗能力，推动流量增长，赢得体验
* 使用[自动目标](/help/c-activities/auto-target/auto-target-to-optimize.md)的集成机器学习算法，根据每个访客的用户档案、行为和上下文选择最佳体验，同时使用[!DNL Adobe Analytics]目标指标和[!DNL Adobe Analytics]的丰富报告和分析功能。

确保您已实施[ A4T，以与A/B测试和体验定位活动](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)一起使用。 如果您使用`analyticsLogging = client_side`，则还需要将`sessionId`值传递给[!DNL Analytics]。 有关详细信息，请参阅&#x200B;*Adobe TargetSDK*&#x200B;指南中的[目标分析(A4T)报告](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting)。

若要开始，请执行以下操作：

1. 在创建A/B测试活动时，在&#x200B;**[!UICONTROL 定位]**&#x200B;页面上，选择以下选项之一作为&#x200B;**[!UICONTROL 流量分配方法]**:

   * 自动分配到最佳体验
   * 自动目标，实现个性化体验

1. 在&#x200B;**[!UICONTROL 目标和设置]**&#x200B;页面上为&#x200B;**[!UICONTROL 报告源]**&#x200B;选择&#x200B;**[!UICONTROL Adobe Analytics]**&lt;a3/>&lt;a5/>&lt;a0/>，然后选择与所需优化目标对应的报表包。

1. 选择主要目标量度。

   * 选择&#x200B;**[!UICONTROL 转换]**&#x200B;以使用[!DNL Adobe Target]指定优化目标。
   * 选择&#x200B;**[!UICONTROL 使用Analytics度量]**，然后从[!DNL Analytics]中选择一个度量以用作优化目标。 您可以使用现成的[!DNL Analytics]转换度量或[!DNL Analytics]自定义事件。

1. 保存并激活活动。

   [!UICONTROL 自动分] 配将使用您选择的活动来优化访客，从而推动体验最大化目标指标。

   或

   [!UICONTROL 自动定] 位将使用您选定的指标优化活动，从而推动访客获得个性化的最佳体验。

1. 使用&#x200B;**[!UICONTROL 报告]**&#x200B;选项卡根据您选择的[!DNL Adobe Analytics]指标视图活动的报告。 单击Analytics ]**中的**[!UICONTROL &#x200B;视图，深入细分报告数据并进一步细分数据。

### 支持的目标指标

[!UICONTROL A4对于] 自 [!UICONTROL 动分] 配和自 [!UICONTROL 动定] 位，您可以选择以下任意指标类型作为优化的主要目标指标：

* [!DNL Adobe Target] 转化量度
* [!DNL Adobe Analytics] 转化量度
* [!DNL Adobe Analytics] 个自定义事件

[!UICONTROL A4] Tfor    [!UICONTROL Auto-] Allocate和Auto-Target要求您选择基于二项式事件(即不存在或未发生的事件)的度量，例如单击、转换、订单等。(这些类型的事件有时也称为伯努利事件、二进制或离散数据。)

[!UICONTROL A4T]  for  [!UICONTROL Auto-] Allocate和 [!UICONTROL Auto-Target不支持对连续指] 标(如收入、订购的产品数量、会话持续时间、会话中的页面视图数等)进行优化。（这些不受支持的度量类型有时也称为非二项式或非伯努利度量。）

不支持以下度量类型作为主要目标度量：

* [!DNL Adobe Target] 参与度和收入指标
* [!DNL Adobe Analytics] 参与度和收入指标

   可以选择[!DNL Analytics]参与度或收入指标作为主要目标指标，因为[!DNL Target]不能识别和排除来自[!DNL Analytics]的所有参与度和收入指标。 请务必从[!DNL Analytics]中仅选择二项式转换指标或自定义事件。

* [!DNL Adobe Analytics] 计算量度

### 限制和说明

某些限制和注释适用于自动分配和自动目标。 其他限制和注释适用于一种活动类型或另一种。

#### 自动分配和自动目标

* 报告源在激活活动后不能从[!DNL Analytics]更改为[!DNL Target]，反之亦然。
* 尽管计算的指标不作为主要目标指标受支持，但通常可以通过选择自定义事件作为主要目标指标来达到预期效果。 例如，如果要优化诸如“每个访客的表单完成情况”之类的指标，请选择与“表单完成情况”对应的自定义事件作为主要目标指标。 [!DNL Target] 根据每次访问自动标准化转化量度，以考虑流量分布不均，因此无需使用计算量度来执行标准化。
* [!DNL Target] 在Auto-AllocateA4T实现中使用“ [!UICONTROL Same Touch”] 归因模型。

#### 自动分配

* [!UICONTROL 自动分] 配模型继续像往常一样每两个小时进行一次培训。

#### 自动定位

* [!UICONTROL 自动定] 位模型照常每24小时进行一次培训。但是，来自[!DNL Analytics]的转换事件数据会额外延迟6到24小时。 此延迟意味着[!DNL Target]的流量分配将跟踪[!DNL Analytics]中记录的最新事件。 在活动启动后的头48小时内，效果最大；活动的性能将更密切地反映经过五天后的[!DNL Analytics]转换行为。 您应考虑对短时活动使用[!UICONTROL 自动分配]而不是[!UICONTROL 自动目标]，在短时间活动生命周期的前五天内，大多数流量都发生在短时间。
* 当使用[!DNL Analytics]作为[!UICONTROL 自动目标]活动的数据源时，会话被视为在经过6小时后结束。 六小时后发生的转换不会计算在内。

有关详细信息，请参阅&#x200B;*分析工具指南*&#x200B;中的[归因模型和回顾窗口](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html)。
