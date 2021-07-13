---
keywords: 局部数据;部分数据;A4T;差异;analytics for target;孤立;虚拟报表包;虚拟;故障诊断;未拼合;夸大;未指定
description: 了解在使用Analytics for [!DNL Target] (A4t)时，如何最大限度地减少夸大的访问和访客计数所产生的影响。 了解“局部数据”是什么以及如何减少这些数据。
title: 如何在A4T中最大限度地减少夸大的访问和访客计数？
feature: Analytics for Target (A4T)
exl-id: 308711f7-e630-4f6b-8a6d-a1f36ed7902d
source-git-commit: 3c79b2ce70e456275ddf6774a35ae5c36f0ae99d
workflow-type: tm+mt
source-wordcount: '1346'
ht-degree: 47%

---

# 在 A4T 中最大限度地减少夸大的访问和访客计数

此信息可帮助您在使用[!DNL Adobe Analytics]作为[!DNL Adobe Target](A4T)的报表源时，最大限度地减少夸大的访问和访客计数所产生的影响。

>[!IMPORTANT]
>2016 年 11 月 14 日，Adobe Analytics 针对那些使用 A4T（适用于 Target 的 Analytics 报表）的客户，更改了某些数据的处理方式。这些更改使 Adobe Target 数据更好地与 Adobe Analytics 的数据模型保持一致，并已为所有使用 A4T 的客户推出。这些更改具体解决了某些客户发现的在运行 Target 活动时访客数量夸大的问题。
>
>此更改不具有可回溯性。如果您的历史报表显示了夸大的计数，且您希望将这部分数字从报表中排除，则可以创建虚拟报表包，具体如下文中所述。
>
>此外，还更新了多个JavaScript库，以帮助最大限度地减少夸大计数。 Adobe建议您升级到以下库版本（或更高版本）：
>
>* Experience Cloud 访客 ID 服务：visitorAPI.js 版本 2.3.0 或更高版本。
>* Adobe Analytics：appMeasurement.js 版本 2.1.
>* Adobe Target：at.js 版本 0.9.6 或更高版本（如果将重定向选件与 A4T 配合使用，则不包括版本 1.1.0）。


## 更改了哪些内容？ {#section_9CCF45F5D66D48EBA88F3A178B27D986}

当使用[!DNL Adobe Analytics]测量[!DNL Target]活动（称为A4T）时， [!DNL Analytics]会收集到页面上没有[!DNL Target]活动时不可用的额外数据。 [!DNL Target]活动在页面顶部触发调用，而[!DNL Analytics]通常在页面底部触发数据收集调用。 迄今为止，在A4T实施中，只要[!DNL Target]活动处于活动状态，Adobe便会包含此附加数据。 今后，仅当[!DNL Target]和[!DNL Analytics]标记均触发时，Adobe才会包含此附加数据。

## 为什么 Adobe 做此更改？ {#section_92380A4BD69E4B8886692DD27540C92A}

Adobe 以数据的准确性和高质量而自豪。当[!DNL Target]标记触发，但[!DNL Analytics]标记未触发时，Analytics会记录“局部数据”（有时称为“未拼合点击量”）。 如果没有[!DNL Target]活动，则不会由[!DNL Analytics]捕获这些未拼合的点击。 虽然在[!DNL Analytics]报表中包含此局部数据可提供其他信息，但这也会导致它与未运行[!DNL Target]活动期间的历史数据不一致。 这种情况可能会给正在分析随时间呈现的趋势的[!DNL Analytics]用户带来问题。 为确保[!DNL Analytics]中的数据一致性，Adobe会排除所有局部数据。

## 产生局部数据的原因是什么？ {#section_C9C906BEAA7D44DAB9D3C03932A2FEB8}

Adobe在[!DNL Analytics]中遇到了部分数据率较高的客户。 不当实施可能会导致局部数据率过高，但也存在合理的原因。

已确定产生局部数据的原因包括：

* **未对齐报表包 ID（实施）：**&#x200B;在活动设置期间指定的报表包与交付测试的页面上的报表包不匹配。无法在[!DNL Analytics]服务器上协调数据，因此它看起来像是局部数据。
* **慢速页面：** [!DNL Target] 调用位于页面顶部， [!DNL Analytics] 调用通常位于页面底部。如果页面加载缓慢，则访客在[!DNL Target]调用触发后但在[!DNL Analytics]调用触发之前离开页面的可能性会增加。 在连接速度通常较慢的移动设备网站上，页面速度慢可能会特别成问题。
* **页面错误：** 如果存在JavaScript错误或每个接触点未触发的其他情况(Experience CloudID服务、Target和Analytics)，则会生成局部数据结果。
* **活动中的重 [!DNL Target] 定向选件：** 对于使用A4T的活动中的重定向选件，您的实施必须满足某些最低要求。此外，您还必须了解一些重要信息。 有关更多信息，请参阅[重定向选件 - A4T 常见问题解答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#section_FA9384C2AA9D41EDBCE263FFFD1D9B58)。
* **库的旧版本：** 过去一年，Adobe对JavaScript库( [!DNL appMeasurement.js]、 `at.js`和 `visitorAPI.js`)进行了多项改进，以确保尽可能高效地发送数据。要了解有关实施要求的更多信息，请参阅[在实施之前](/help/c-integrating-target-with-mac/a4t/before-implement.md#concept_046BC89C03044417A30B63CE34C22543)。

## 减少局部数据的最佳实践是什么？ {#section_065C38501527451C8058278054A1818D}

请查看以下步骤以减少局部数据收集：

| 步骤 | 任务 |
| --- | --- |
| ![步骤 1](assets/step1_icon.png) | 确保在[!DNL Target]中选择的报表包与显示活动的页面上的报表包相同。 |
| ![步骤 2](assets/step2_icon.png) | 确保visitorAPI.js、appMeasurement.js和at.js库位于与A4T兼容的版本上。 要了解有关实施要求的更多信息，请参阅[在实施之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)。 |
| ![步骤 3](assets/step3_icon.png) | 确保在所有离开页面的[!DNL Target]和[!DNL Analytics]调用上设置了SDID，且它们匹配。<br/>使用网络分析器或调试工具确保调用 `mboxMCSDID` 中的 [!DNL Target] 参数与调用中的SDID参数 [!DNL Analytics] 匹配。 |
| ![步骤 4](assets/step4_icon.png) | 确认实施库在您的网站上以正确的顺序加载。有关更多信息，请参阅[Analytics for Target 实施](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)中的步骤 8。 |

## 如何查看我有多少局部数据？ {#section_89B663E2824A4805AB934153508A0F4B}

尽管此信息不能直接在 [!DNL Analytics] 中获得，但您可以联系 Adobe 客户关怀团队以索取一份局部数据报表。本报表旨在为调试提供帮助。

## 如何查看不含局部数据的历史趋势？ {#section_4C9DED560FAD4428B362DDA2064897C3}

此处理更改仅会在发行日期（2016年11月14日）之后影响数据。 如果要调整历史量度以匹配，则Adobe建议您创建一个区段以排除局部数据。

以下与此更改相关的信息包含相关说明，可帮助您定义区段并将其应用于虚拟报表包，使该区段始终适用于您的 [!DNL Analytics] 查看次数。

在大多数情况下，每个网页上的 [!DNL Target] 点击量会与 [!DNL Analytics] 点击量拼合。如果 [!DNL Target] 和 [!DNL Analytics] 调用以及同一页面上 [!DNL Analytics] 调用中的 [!DNL Experience Cloud ID] (MCID) 均存在一致的 SDID，则会进行拼合。[!DNL Target] 通常也具有MCID，但如果在访客ID返回 [!DNL Target] 之前发生对的调用，则由于SDID，点击仍会拼合。此外，用户必须在页面上停留足够长的时间，才能在触发 [!DNL Target] 调用后继续触发 [!DNL Analytics] 调用。这种情况是理想的。

**局部数据点击量：**&#x200B;用户有时不会在页面上停留足够长的时间来发出 [!DNL Analytics] 调用，但 [!DNL Target] 具有适当的 MCID。此方案会生成局部数据点击量（没有[!DNL Analytics]页面查看的点击量）。 如果这些用户返回您的网站并查看包含[!DNL Analytics]代码的页面，则他们将被正确计为回访访客。 如果页面上只有[!DNL Analytics]代码，则这些点击量将会丢失。 某些客户不想拥有这些点击量的数据，因为它们会夸大某些量度（访问次数）并缩减其他量度（每次访问的页面查看次数、每次访问停留的时间等等）。您还会看到没有任何页面查看的访问。 但是，仍有正当理由保留这些数据。

为了最大限度减少局部数据点击量，您可以加快页面加载速度，更新到最新版本的库，或者创建一个[虚拟报表包](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html)以排除这些点击量。有关分步说明，请参阅《Analytics组件指南》*中的[创建虚拟报表包](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html) 。*

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

## 这对我的 [!DNL Target] 报表有什么影响？ {#section_AAD354C722BE46D4875507F0FCBA5E36}

发生此更改后，您可能会看到上线测试的新访客数和访问次数减少，因为[!DNL Adobe]不处理传入的局部数据。 其他 [!DNL Analytics] 量度的转化和点击量不会发生变化。
