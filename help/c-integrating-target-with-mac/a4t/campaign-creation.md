---
keywords: a4t;A4T;Analytics as the reporting source for Target
description: 您可以将 Target Standard/Premium 中的活动配置为使用 Adobe Analytics 作为报表源 (A4T)。
title: 创建使用A4T作为活动源的报告
feature: a4t general
topic: Advanced,Standard,Classic
uuid: b04ad535-62fb-4dd3-ab3f-23da60fbffbd
translation-type: tm+mt
source-git-commit: e18f18e6d6e0b8fc6eb5ada845e2fe5377d6c5d0
workflow-type: tm+mt
source-wordcount: '1393'
ht-degree: 17%

---


# 创建将Analytics用作活动源的报告

You can configure an activity in [!DNL Target] to use [!DNL Adobe Analytics] as the reporting source (A4T).

Before you set up an activity that uses [!DNL Analytics] as the reporting source, establish the goal for the activity, such as improving revenue per visitor (RPV) or increasing clicks on your shopping cart. 需为活动选择最终成功量度。Although you can select additional metrics at any time in [!DNL Analytics], you must still specify a particular metric you expect this test to affect.

## 创建活动

Creating a [!DNL Target] activity that uses [!DNL Analytics] as the reporting source is similar to setting up a regular [!DNL Target] activity, with a few important differences. For example, you cannot select a segment for reporting while creating the activity because all segments available in [!DNL Analytics] can be applied when viewing a report.

1. 单击&#x200B;**[!UICONTROL 创建活动]**。

   >[!NOTE]
   >
   >An activity name cannot include the &quot;%&quot; character if [!DNL Analytics] is used as the reporting source.

1. 选择活动类型并开始设置活动。
1. 在活动创建流程的&#x200B;**[!UICONTROL 设置]**&#x200B;部分，选择 **[!UICONTROL Adobe Analytics]**，然后指定您的公司。
1. 选择一个报表包。

   You can choose any report suite that is available to you in [!DNL Analytics]. 报表包定义提供所收集数据的位置。报表包列表中不包含虚拟报表包。

   选择报表包时，您可能会遇到两种错误：

   * 遇到没有任何可用报表包的错误，但是您的帐户已正确设置。

      You might need to check your [!DNL Analytics] company. If your [!DNL Adobe Experience Cloud] account is tied to more than one [!DNL Analytics] company, log out of [!DNL Target], and log in to [!DNL Analytics] under the right company. Then return to [!DNL Target], and the report suites will load.

   * 看不到预期的报表包。

      Only report suites that are provisioned to connect to [!DNL Target] will be available for selection. If you don&#39;t see the report suite(s) you expect, first try logging out and logging back in to the [!DNL Adobe Experience Cloud] to try again.
   If the report suite(s) is still missing from the list, please [contact Customer Care](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

1. 指定跟踪服务器。

   请参阅[使用 Analytics 跟踪服务器](../../c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)。

1. 定义体验。
1. 指定活动目标。

   您需要选择成功量度，以用作每个活动的目标。 您的活动目标是表示活动取得成功的转化活动。如果没有设定目标来以某种特定方式做出改进，最好不要运行测试。You can choose any [!DNL Analytics] metric available in the [!DNL Analytics] metric selector.

   >[!NOTE]
   >
   >You can send a custom Target-based metric to [!DNL Analytics] rather than relying only on [!DNL Analytics] data. For example, you can monitor clicking on a page, which is usually not tracked by [!DNL Analytics]. This custom metric is sent to [!DNL Analytics] automatically from the [!DNL Target] server, and appears as the &quot;[!DNL Target] Conversion&quot; metric in the metrics selector in [!DNL Analytics]. The [!DNL Target] Conversion metric is empty if you choose to use [!DNL Analytics] metrics.

   设置目标并不意味着您不能在评估测试结果时使用其他量度。但是，目标可提醒您要通过活动加以改进的方面。

   达到目标后，访客会继续保留在活动中。访客会继续看到活动内容，但不会被计为一次新活动参加。

   >[!NOTE]
   >
   >When setting up an activity after setting up [!DNL Analytics] as your reporting source, there is no option to set up audiences for reporting. [!DNL Analytics] 区段可在活动报 [!DNL Target] 告中找到。

1. 单击&#x200B;**[!UICONTROL 保存]**。

## 目标分析(A4T)支持自动分配和自动目标活动 {#a4t-aa}

我们已升级了Adobe Target到Adobe Analytics的集成，即 [目标分析](/help/c-integrating-target-with-mac/a4t/a4t.md)。 自动分配和自动目标活动现在支持Analytics进行目标。

此集成允许您：

* 使 [用自动分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)(Auto-Allocate)的多武装强盗能力，推动交通畅通，赢得体验
* 使 [用自动目标](/help/c-activities/auto-target/auto-target-to-optimize.md)(Auto-)的集成机器学习算法，根据每个访客的用户档案、行为和上下文为其选择最佳体验，同时使用目标 [!DNL Adobe Analytics] 指标 [!DNL Adobe Analytics]和丰富的报告和分析功能。

确保已实 [施A4T以用于A/B测试和体验定位活动](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)。 如果您正在 `analyticsLogging = client_side`使用，则还需要将值 `sessionId` 传递给 [!DNL Analytics]。 有关详细信息，请 [参阅《Adobe TargetSDK指南》中的](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting) “目标分析( *A4T)* ”报告。

若要开始，请执行以下操作：

1. 创建A/B测试活动时，在“定位 **[!UICONTROL ”页]** 上，选择以下选项之一作为“流量 **[!UICONTROL 分配方法”]**:

   * 自动分配到最佳体验
   * 自动目标，实现个性化体验

1. 在“ **[!UICONTROL 目标和设]** 置”页面上为 **[!UICONTROL 报告源选]** 择“Adobe Analytics” **** ，然后选择与所需的优化目标对应的报表包。

1. 选择主要目标量度。

   * 选择 **[!UICONTROL 要用]** 于指 [!DNL Adobe Target] 定优化目标的转换。
   * 选 **[!UICONTROL 择使用Analytics]** 指标，然后从中选择 [!DNL Analytics] 一个指标以用作优化目标。 您可以使用现成的转换 [!DNL Analytics] 量度或自定 [!DNL Analytics] 义事件。

1. 保存并激活活动。

   [!UICONTROL “自动分配] ”将使用您选择的活动来优化访客，从而推动体验最大化目标指标。

   或

   [!UICONTROL 自动目标将] 使用您选择的指标来优化活动，从而推动访客获得个性化的最佳体验。

1. 使用“ **[!UICONTROL 报告]** ”选项卡根据您选择的指标视图活动的 [!DNL Adobe Analytics] 报告。 在Analytics **[!UICONTROL 中单击视图]** ，以深入细分报告数据并进一步细分数据。

### 支持的目标指标

[!UICONTROL A4T] for [!UICONTROL Auto-Allocate] and [!UICONTROL Auto-目标] 允许您选择以下任意度量类型作为优化的主要目标度量：

* [!DNL Adobe Target] 转化量度
* [!DNL Adobe Analytics] 转化量度
* [!DNL Adobe Analytics] 个自定义事件

[!UICONTROL A4T][!UICONTROL 用于自动分] 配和自动目标  ，要求您选择基于二项事件的度量，即不存在或未发生的事件，例如单击、转换、订单等。 (这些类型的事件有时也称为伯努利事件、二进制或离散数据。)

[!UICONTROL A4T] for [!UICONTROL Auto-Allocate] and  Auto-目标不支持对连续指标进行优化，如收入、订购的产品数量、会话持续时间、会话中的页面视图数量等。 （这些不受支持的度量类型有时也称为非二项式或非伯努利度量。）

不支持以下度量类型作为主要目标度量：

* [!DNL Adobe Target] 参与度和收入指标
* [!DNL Adobe Analytics] 参与度和收入指标

   可能会选择参与或收入 [!DNL Analytics] 量度作为主要目标量度，因 [!DNL Target] 为无法从中识别和排除所有参与和收入量度 [!DNL Analytics]。 务必小心，只选择二项式转化指标或自定义事件 [!DNL Analytics]。

* [!DNL Adobe Analytics] 计算量度

### 限制和说明

某些限制和注释适用于自动分配和自动目标。 其他限制和注释适用于一种活动类型或另一种。

#### 自动分配和自动目标

* 报告源在激活后 [!DNL Analytics] 不 [!DNL Target] 能从更改为活动源，反之亦然。
* 尽管计算的指标不作为主要目标指标受支持，但通常可以通过选择自定义事件作为主要目标指标来达到预期效果。 例如，如果要优化诸如“每个访客的表单完成情况”之类的指标，请选择与“表单完成情况”对应的自定义事件作为主要目标指标。 [!DNL Target] 根据每次访问自动标准化转化量度，以考虑流量分布不均，因此无需使用计算量度来执行标准化。
* [!DNL Target] 在自动分配A4T实施中使 [!UICONTROL 用“Same Touch] ”属性模型。

#### 自动分配

* [!UICONTROL 自动分配模型] (Auto-Allocate models)会像往常一样每两个小时进行一次培训。

#### 自动定位

* [!UICONTROL 自动目标] 模型照常每24小时进行一次培训。 但是，来自转化事件 [!DNL Analytics] 的数据会再延迟6到24小时。 此延迟意味着流量分配将跟 [!DNL Target] 踪记录的最新事件 [!DNL Analytics]。 在活动启动后的头48小时内，效果最大；活动的性能将更密切地反映 [!DNL Analytics] 经过五天后的转换行为。 您应考虑对 [!UICONTROL 短期活动使] 用“自动分配 [!UICONTROL ”，而不] 是“自动目标”，在短期中，大多数流量都发生在活动生命周期的前五天内。
* 当使 [!DNL Analytics] 用作自动目标 [!UICONTROL 活动的数据源时] ，会话被视为在经过6小时后结束。 六小时后发生的转换不会计算在内。

有关详细信息，请参 [阅《分析工具指南》中](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/models.html) 的归因 *模型和回顾窗口*。
