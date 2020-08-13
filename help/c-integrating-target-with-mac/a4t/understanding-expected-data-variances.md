---
keywords: data variances;analytics;differences;variance;a4t;analytics for target;analytics as the reporting source;discrepancies;discrepancy
description: 此信息介绍了当“不”使用 Analytics 作为报表源（A4T，可完全消除数据差异）时 Target 和 Adobe Analytics 之间的预期数据差异。
title: 不使用 A4T 时的预期数据差异
feature: a4t troubleshooting
topic: Advanced
uuid: 61bef460-8613-4251-b1b2-b6226ec86d9b
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '853'
ht-degree: 100%

---


# 使用和不使用 A4T 时，Target 和 Analytics 之间的预期数据差异{#expected-data-variances-when-not-using-a-t}

此信息介绍了当&#x200B;*使用*&#x200B;和&#x200B;*不*&#x200B;使用 Analytics 作为报表源 (A4T) 时，[!DNL Target] 和 Adobe [!DNL Analytics] 之间的预期数据差异。A4T 可显著减小数据差异.

## 使用 A4T 时的预期数据差异 {#expected-using-a4t}

使用 A4T 时，Analytics 和 Target 活动报表都只使用 Analytics 数据，因此 Target 活动报表中的解决方案之间几乎没有差异。但是，在某些情况下，客户可能会将 Target 数据与 A4T 集成范围之外的 Analytics 数据进行比较，这样，就会出现下面所述的差异问题。

以下是您可以会遇到预期数据差异的几种情况：

* A4T 可能发生 Target 点击（页面顶部），但未发生 Analytics 点击（页面底部）。例如，如果用户加载页面，但在触发 Analytics 调用之前关闭了浏览器。在这些情况下，A4T 会从我们的数据中排除 Target 点击。原因在于，在没有实际 Analytics 调用的情况下，如果允许将 Target 点击（同样是页面顶部）计为 Analytics 点击，则会导致与 Analytics 中的数据集不一致（访客计数夸大等）。

   如果在 Target 中设置重定向测试以拆分流量 50/50（或 25/25/25/25 等），则可能无法均匀拆分用户行为。如果您看到不均匀的拆分，这仅表示一组用户在登陆页面上未能执行 Analytics 调用的次数多于其他组。由于未能对某组执行 Analytics 调用，导致该用户的 Target 点击被排除，从而造成不均匀性。

   我们希望将来在 Adobe Experience Platform 上实现 A4T 时可以解决这个问题。我们的团队正在研究如何最好地处理页面上不同时间发生的这些不同事件。

   >[!NOTE]
   >
   >存在一个已知问题，该问题会导致将重定向与 A4T 结合使用的有限数量的客户看到较高的未经整合点击率百分比。请参阅[已知问题和已解决的问题](/help/r-release-notes/known-issues-resolved-issues.md#redirect)。

* 假设您创建了一个将向特定页面的所有访客公开的自动分配活动。由于自动分配活动不支持 A4T，因此 [!DNL Target] 会收集所有活动数据。您可能希望同一日期范围内 [!DNL Target] 报表中的活动访客与 [!DNL Analytics] 报表中该页面的访客相匹配。在这种情景中，预期会出现下面所述的差异。

   有关支持 A4T 的活动类型的完整列表，请参阅[支持的活动类型](../../c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA)。

## *不使用* A4T 时的预期数据差异 {#expected-not-using-a4t}

即使是相似的数据集，有 15-20% 的差异也是正常的。采用不同计数方式的系统可能导致更高的数据差异，例如可能高达 35-50%。而在某些情况下，差异甚至可能更大。

虽然实际的数据可以有很大的不同，但其趋势通常是一致的。只要数据的差异和趋势能够保持一致，那么这些数据依然是有价值和有用的。如果数据的差异和趋势不一致，这可能说明某些配置不正确。此情况下，请联系您的客服专员以获得帮助。

[!DNL Analytics] 使用基于访问和交易的系统，而 使用基于访客的量度。[!DNL Target]这意味着任何时候访客打开一个页面，[!DNL Analytics] 都会将此计为一次访问，但 [!DNL Target] 只有在满足活动中设置的条件时才会将此计为一次访问。

[!DNL Target] 报表根据定义活动时选择的转化 mbox 显示性能，但该转化 mbox 的数据不会发送给 [!DNL Analytics]，该产品有它自己的转化变量，这些变量由 [!DNL Analytics] 标记实施进行定义。您可能期望得到相同数据（例如，如果一个零售商的订单确认页面同时包含一个转化 mbox 和一个 [!DNL Analytics] 购买事件），但实际情况却是数据可能会因为这些标记的放置而产生差异。通常情况下，两个产品的报表中显示的趋势应当是相似的。

技术和业务的差异均有可能造成预期数据的差异。

### 技术差异示例 {#section_C3B50ED2E2F9416FAC91437CF1A87369}

以下可能造成技术方面的数据差异：

* [!DNL Target] 访客必须允许 Cookie 和 JavaScript
* 第一方和第三方 Cookie 的处理方式不相同，所以来自这些 Cookie 类型的数据不匹配
* 页面上标记的相对位置，以及访客在页面未完全加载前退出造成的“漏出”。
* 时区方面的因素
* 在哪些设备可以被计数上存在差异

### 业务差异示例 {#section_2E1EB5E15BB64A1A80E4CDB1A5062AEE}

以下可能造成业务方面的数据差异：

* 访客和访问量度之间的差异
* 活动的定位排除了一些访客
* 单个 mbox 可以设置在多个页面上，每个页面都计算访客数
* 活动优先级可能在一个页面上接受部分访客并排除其他访客
* 当已经转化过一次的访客再次进入活动时，可能被再次计数
* [!DNL Analytics] 为所有访问和访客的所有转化计数，而 [!DNL Target] 则只为列入活动的访问和访客的转化计数