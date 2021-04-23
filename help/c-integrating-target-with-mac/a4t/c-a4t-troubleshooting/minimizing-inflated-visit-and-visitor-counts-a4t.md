---
keywords: 局部数据;部分数据;A4T;差异;analytics for target;孤立;虚拟报表包;虚拟;故障诊断;未拼合;夸大;未指定
description: 了解在使用 [!DNL Target] (A4t)的Analytics时，如何将夸大的访问和访客计数的影响降至最低。 了解什么是“部分数据”以及如何减少数据。
title: 如何将A4T中的夸大访问和访客计数降至最低？
feature: Analytics for Target (A4T)
exl-id: 308711f7-e630-4f6b-8a6d-a1f36ed7902d
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '1362'
ht-degree: 48%

---

# 在 A4T 中最大限度地减少夸大的访问和访客计数

在将[!DNL Adobe Analytics]用作[!DNL Adobe Target](A4T)的报告源时，帮助您将夸大的“访问”和“访客”计数的影响降至最低的信息。

>[!IMPORTANT]
>2016 年 11 月 14 日，Adobe Analytics 针对那些使用 A4T（适用于 Target 的 Analytics 报表）的客户，更改了某些数据的处理方式。这些更改使 Adobe Target 数据更好地与 Adobe Analytics 的数据模型保持一致，并已为所有使用 A4T 的客户推出。这些更改具体解决了某些客户发现的在运行 Target 活动时访客数量夸大的问题。
>
>此更改不具有可回溯性。如果您的历史报表显示了夸大的计数，且您希望将这部分数字从报表中排除，则可以创建虚拟报表包，具体如下文中所述。
>
>此外，还更新了多个JavaScript库，以帮助最大限度地减少虚数。 Adobe建议您升级到以下库版本（或更高版本）：
>
>* Experience Cloud 访客 ID 服务：visitorAPI.js 版本 2.3.0 或更高版本。
>* Adobe Analytics：appMeasurement.js 版本 2.1.
>* Adobe Target：at.js 版本 0.9.6 或更高版本（如果将重定向选件与 A4T 配合使用，则不包括版本 1.1.0）。

>
>  
mbox.js 库不支持将重定向选件与 A4T 配合使用。您的实施必须使用 at.js。

## 更改了哪些内容？{#section_9CCF45F5D66D48EBA88F3A178B27D986}

当使用[!DNL Adobe Analytics]测量[!DNL Target]活动（称为A4T）时， [!DNL Analytics]会收集当页面上没有[!DNL Target]活动时不可用的额外数据。 [!DNL Target]活动在页面顶部触发调用，但[!DNL Analytics]通常在页面底部触发其数据收集调用。 在迄今为止的A4T实施中，当[!DNL Target]活动处于活动状态时，Adobe将包含此附加数据。 今后，Adobe仅在[!DNL Target]和[!DNL Analytics]标签已触发时才包含此附加数据。

## 为什么 Adobe 做此更改？{#section_92380A4BD69E4B8886692DD27540C92A}

Adobe 以数据的准确性和高质量而自豪。当[!DNL Target]标记触发，但[!DNL Analytics]标记未触发时，Analytics会记录“部分数据”（有时称为“未拼接点击”）。 如果没有[!DNL Target]活动，则[!DNL Analytics]将不会捕获这些未拼接的点击。 尽管在[!DNL Analytics]报告中包含此部分数据可提供其他信息，但它也会导致与未运行[!DNL Target]活动的期间的历史数据不一致。 这种情况可能会导致[!DNL Analytics]用户在分析趋势随时间变化的问题。 为了确保[!DNL Analytics]中的数据一致性，Adobe将排除所有部分数据。

## 产生局部数据的原因是什么？{#section_C9C906BEAA7D44DAB9D3C03932A2FEB8}

Adobe在[!DNL Analytics]中遇到部分数据速率较高的客户。 部分数据的高率可能来自不当实施，但也有合理的原因。

已确定产生局部数据的原因包括：

* **未对齐报表包 ID（实施）：**&#x200B;在活动设置期间指定的报表包与交付测试的页面上的报表包不匹配。无法在[!DNL Analytics]服务器上对数据进行协调，因此它看起来像是部分数据。
* **慢速页面：** [!DNL Target] 调用位于页面顶部， [!DNL Analytics] 调用通常位于页面底部。如果页面加载缓慢，则会增加在[!DNL Target]调用触发后，但在[!DNL Analytics]调用之前，访客离开页面的可能性。 在连接速度通常较慢的移动网站上，页面速度缓慢可能特别成问题。
* **页面错** 误：如果存在JavaScript错误或其他触点未触发(Experience CloudID服务、目标和分析)的情况，则会显示部分数据结果。
* **重定向优惠 [!DNL Target] ：要** 在使用A4T的活动中重定向优惠，您的实施必须满足某些最低要求。此外，您必须了解一些重要信息。 有关更多信息，请参阅[重定向选件 - A4T 常见问题解答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#section_FA9384C2AA9D41EDBCE263FFFD1D9B58)。
* **旧版本的库：在** 过去一年中，Adobe对JavaScript库（、和） [!DNL appMeasurement.js]做了 `at.js/mbox.js` `visitorAPI.js`几项改进，以确保尽可能高效地发送数据。要了解有关实施要求的更多信息，请参阅[在实施之前](/help/c-integrating-target-with-mac/a4t/before-implement.md#concept_046BC89C03044417A30B63CE34C22543)。

## 减少局部数据的最佳实践是什么？{#section_065C38501527451C8058278054A1818D}

查看以下步骤以减少部分数据收集：

| 步骤 | 任务 |
| --- | --- |
| ![步骤 1](assets/step1_icon.png) | 确保在[!DNL Target]中选择的报表包与显示活动的页面上的报表包相同。 |
| ![步骤 2](assets/step2_icon.png) | 确保visitorAPI.js、appMeasurement.js、at.js / mbox.js库位于与A4T兼容的版本上。 要了解有关实施要求的更多信息，请参阅[在实施之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)。 |
| ![步骤 3](assets/step3_icon.png) | 确保在离开页面的所有[!DNL Target]和[!DNL Analytics]调用上设置SDID，并确保它们匹配。<br/>使用网络分析器或调试工具确保调 `mboxMCSDID` 用上 [!DNL Target] 的参数与调用中的SDID [!DNL Analytics] 参数匹配。 |
| ![步骤 4](assets/step4_icon.png) | 确认实施库在您的网站上以正确的顺序加载。有关更多信息，请参阅[Analytics for Target 实施](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)中的步骤 8。 |

## 如何查看我有多少局部数据？{#section_89B663E2824A4805AB934153508A0F4B}

尽管此信息不能直接在 [!DNL Analytics] 中获得，但您可以联系 Adobe 客户关怀团队以索取一份局部数据报表。本报表旨在为调试提供帮助。

## 如何查看不含局部数据的历史趋势？{#section_4C9DED560FAD4428B362DDA2064897C3}

此处理更改仅影响发布日期（2016年11月14日）之后的数据。 如果您要调整历史量度以匹配，Adobe建议您创建一个区段以排除部分数据。

以下与此更改相关的信息包含相关说明，可帮助您定义区段并将其应用于虚拟报表包，使该区段始终适用于您的 [!DNL Analytics] 查看次数。

在大多数情况下，每个网页上的 [!DNL Target] 点击量会与 [!DNL Analytics] 点击量拼合。如果 [!DNL Target] 和 [!DNL Analytics] 调用以及同一页面上 [!DNL Analytics] 调用中的 [!DNL Experience Cloud ID] (MCID) 均存在一致的 SDID，则会进行拼合。[!DNL Target] 通常也有MCID，但如果在访客ID返回 [!DNL Target] 之前发生调用，则由于SDID，点击仍然被拼接。此外，用户必须在页面上停留足够长的时间，才能在触发 [!DNL Target] 调用后继续触发 [!DNL Analytics] 调用。这种情况是理想的。

**局部数据点击量：**&#x200B;用户有时不会在页面上停留足够长的时间来发出 [!DNL Analytics] 调用，但 [!DNL Target] 具有适当的 MCID。此方案会导致部分数据点击(没有[!DNL Analytics]页面视图的点击)。 如果这些用户返回您的站点并视图包含[!DNL Analytics]代码的页面，则会将他们正确计为返回访客。 如果页面上只有[!DNL Analytics]代码，则这些点击会丢失。 某些客户不想拥有这些点击量的数据，因为它们会夸大某些量度（访问次数）并缩减其他量度（每次访问的页面查看次数、每次访问停留的时间等等）。您还可以看到没有任何页面视图的访问。 但是，仍有正当理由保留这些数据。

为了最大限度减少局部数据点击量，您可以加快页面加载速度，更新到最新版本的库，或者创建一个[虚拟报表包](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html)以排除这些点击量。有关分步说明，请参阅&#x200B;*分析组件指南*&#x200B;中的[创建虚拟报表包](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html)。

下图显示了该虚拟报表包的区段定义：

![](assets/ts_a4t.png)

创建虚拟报表包时，请为区段定义指定以下配置（如上图所示）：

* **显示点击：**
* Analytics for Target：存在
* “逻辑与”
* 页面查看次数：不存在
* “逻辑与”
* 自定义链接实例：不存在
* “逻辑与”
* 下载链接实例：不存在
* “逻辑与”
* 退出链接实例：不存在

**孤立点击：**&#x200B;在少数情况下，用户不会在页面上停留足够长的时间来进行 Analytics 调用，并且 Target 未获得适当的 MCID。这些点击是Adobe定义为“孤立”点击的。 这些点击代表旧访客较少，且它们不合理地夸大了访问次数和访客数量。

为了最大限度地减少这些“孤立”点击，您可以创建一个排除这些点击的[虚拟报表包](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html)，如上所述。

## 这对我的 [!DNL Target] 报表有什么影响？{#section_AAD354C722BE46D4875507F0FCBA5E36}

发生此更改后，您可能会看到新访客和实时测试访问量减少，因为[!DNL Adobe]不处理传入的部分数据。 其他 [!DNL Analytics] 量度的转化和点击量不会发生变化。
