---
keywords: 数据差异;Analytics;区别;差异;A4T;Analytics for Target;Analytics 作为报表源;差别
description: 了解不使用Adobe Target for 目标(A4T)时，Analytics与Analytics之间的预期数据差异，这可以彻底消除数据差异。
title: Analytics和A4T之间的预期数据差异是什么？
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 4abf975095c5e29eea42d67119a426a3922d8d79
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 49%

---


# 在使用和不使用A4T时，Adobe Target和Adobe Analytics之间的预期数据差异

此信息介绍了当&#x200B;*使用*&#x200B;和&#x200B;*不*&#x200B;使用 Analytics 作为报表源 (A4T) 时，[!DNL Target] 和 Adobe [!DNL Analytics] 之间的预期数据差异。A4T 可显著减小数据差异.

## 使用 A4T 时的预期数据差异 {#expected-using-a4t}

使用 A4T 时，Analytics 和 Target 活动报表都只使用 Analytics 数据，因此 Target 活动报表中的解决方案之间几乎没有差异。但是，在某些情况下，客户会将目标数据与A4T集成范围外的Analytics数据进行比较，从而体验下面描述的差异问题。

以下是一些您可以体验预期数据差异的方案：

* A4T 可能发生 Target 点击（页面顶部），但未发生 Analytics 点击（页面底部）。例如，假设访客加载页面，但在触发Analytics调用之前关闭浏览器。 在这些情况下，A4T会从数据中排除目标点击。 允许目标点击（同样是页面顶部）在没有实际Analytics调用时计为Analytics点击，会与Analytics中设置的数据(访客通胀等)产生不一致。

   如果在目标中设置重定向测试以分割流量50/50(或25/25/25/25等)，则用户行为可能不会平均分割。 如果您看到的是不均衡的拆分，这只意味着一组用户未能在登陆页上执行Analytics调用，而其他组没有。 由于未能对某组执行 Analytics 调用，导致该用户的 Target 点击被排除，从而造成不均匀性。

   Adobe希望将来在Adobe团队致力于Adobe Experience Platform上的A4T时解决这个问题。 Adobe团队正在确定如何处理页面上不同时间发生的这些不同事件。

   >[!NOTE]
   >
   >存在一个已知问题，该问题会导致将重定向与 A4T 结合使用的有限数量的客户看到较高的未经整合点击率百分比。请参阅[已知问题和已解决的问题](/help/r-release-notes/known-issues-resolved-issues.md#redirect)。

## *不使用* A4T 时的预期数据差异 {#expected-not-using-a4t}

即使是相似的数据集，有 15-20% 的差异也是正常的。采用不同计数方式的系统可能导致更高的数据差异，例如可能高达 35-50%。有时，差异可能更大。

虽然实际的数据可以有很大的不同，但其趋势通常是一致的。只要数据的差异和趋势能够保持一致，那么这些数据依然是有价值和有用的。如果数据的差异和趋势不一致，这可能说明某些配置不正确。此情况下，请联系您的客服专员以获得帮助。

[!DNL Analytics] 使用基于访问和交易的系统，而 使用基于访客的量度。[!DNL Target]每当访客打开页面时，它都计为[!DNL Analytics]中的访问，但[!DNL Target]在满足活动中设置的条件之前不会计算访问。

[!DNL Target]中的报表根据定义活动时选择的转换mbox显示性能。 但是，此转换mbox数据不会发送到[!DNL Analytics]，后者具有由[!DNL Analytics]标记实现定义的自己的转换变量。 如果您期望获得相同的数据(例如，零售商的订单确认页面同时包含转换mbox和[!DNL Analytics]购买事件)，则数据可能因这些标签的放置而有所不同。 总体而言，两种产品的报表趋势相似。

技术和业务的差异均有可能造成预期数据的差异。

### 技术差异示例 {#section_C3B50ED2E2F9416FAC91437CF1A87369}

以下可能造成技术方面的数据差异：

* [!DNL Target] 访客必须允许 Cookie 和 JavaScript
* 第一方和第三方 Cookie 的处理方式不相同，所以来自这些 Cookie 类型的数据不匹配
* 页面上标记的相对位置，以及访客在页面未完全加载前退出造成的“漏出”。
* 时区方面的因素
* 在哪些设备可以被计数上存在差异

### 业务差异示例  {#section_2E1EB5E15BB64A1A80E4CDB1A5062AEE}

以下可能造成业务方面的数据差异：

* 访客和访问量度之间的差异
* 活动的定位排除了一些访客
* 多个页面上的单个mbox，对每个页面的访客进行计数
* 活动优先级可以包括某些访客，并在页面上排除其他
* 已转换一次的访客在重新进入活动时可以再次计数
* [!DNL Analytics] 为所有访问和访客的所有转化计数，而 [!DNL Target] 则只为列入活动的访问和访客的转化计数