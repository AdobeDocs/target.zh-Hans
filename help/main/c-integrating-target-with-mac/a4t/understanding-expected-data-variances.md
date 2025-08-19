---
keywords: 数据差异;Analytics;区别;差异;A4T;Analytics for Target;Analytics 作为报表源;差别
description: 了解Adobe [!DNL Target] 与Analytics之间不使用可完全消除数据差异的Analytics for [!DNL Target] (A4T)时的预期数据差异。
title: Analytics与A4T之间的预期数据差异是什么？
feature: Analytics for Target (A4T)
exl-id: 9e63f309-8ec1-4ed5-a1f9-6c3098a7b8f6
source-git-commit: 4abd24f63dd65e65a1d8b07647630eeb640e7a1d
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 45%

---

# 使用和不使用A4T时，Adobe [!DNL Target]和Adobe Analytics之间的预期数据差异

此信息介绍了当&#x200B;*使用*&#x200B;和&#x200B;*不*&#x200B;使用 Analytics 作为报表源 (A4T) 时，[!DNL Target] 和 Adobe [!DNL Analytics] 之间的预期数据差异。A4T 可显著减小数据差异.

## 使用A4T时的预期数据差异 {#expected-using-a4t}

使用 A4T 时，Analytics 和 Target 活动报表都只使用 Analytics 数据，因此 Target 活动报表中的解决方案之间几乎没有差异。但是，在某些情况下，客户会将Target数据与A4T集成范围以外的Analytics数据进行比较，这样，就会出现下面所述的差异问题。

以下是您可以体验到预期数据差异的几种情况：

* A4T 可能发生 Target 点击（页面顶部），但未发生 Analytics 点击（页面底部）。例如，假设一位访客加载了页面，但在触发Analytics调用之前关闭了浏览器。 在这些情况下，A4T会从数据中排除Target点击。 在没有实际Analytics调用的情况下，如果允许Target点击（同样是页面顶部）被计为Analytics点击，则会导致与Analytics中的数据集不一致（访客计数夸大等）。

  如果在Target中设置重定向测试以拆分流量50/50（或25/25/25/25等），则可能无法均匀拆分用户行为。 如果您看到不均匀的拆分，这仅表示一组用户在登陆页面上未能执行Analytics调用的次数多于其他组。 由于未能对某组执行 Analytics 调用，导致该用户的 Target 点击被排除，从而造成不均匀性。

  Adobe希望将来解决此问题，因为Adobe团队将努力在Adobe Experience Platform上实现A4T。 Adobe团队正在确定如何处理在页面上不同时间发生的这些不同事件。

## *不使用* A4T 时的预期数据差异 {#expected-not-using-a4t}

即使是相似的数据集，有 15-20% 的差异也是正常的。采用不同计数方式的系统可能导致更高的数据差异，例如可能高达 35-50%。有时候，差异可能更大。

虽然实际的数据可以有很大的不同，但其趋势通常是一致的。只要数据的差异和趋势能够保持一致，那么这些数据依然是有价值和有用的。如果数据的差异和趋势不一致，这可能说明某些配置不正确。此情况下，请联系您的客服专员以获得帮助。

[!DNL Analytics] 使用基于访问和交易的系统，而 使用基于访客的量度。[!DNL Target]每当访客打开页面时，它都会计为[!DNL Analytics]中的一次访问，但在满足活动中设置的条件之前，[!DNL Target]不会计为一次访问。

[!DNL Target]中的报表根据定义活动时选择的转化mbox显示性能。 但是，此转化mbox数据不会发送到[!DNL Analytics]，它有它自己的转化变量，这些变量由您的[!DNL Analytics]标记实现定义。 您希望获得相同数据的位置(例如，如果retailer的订单确认页面同时包含转化mbox和[!DNL Analytics]购买事件)，则数据可能会因这些标记的位置而有所不同。 总体而言，两种产品报表中的趋势相似。

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
* 在多个页面上使用单个mbox，对每个页面上的访客进行计数
* 活动优先级可以包括页面上的某些访客并排除其他访客
* 重新进入活动后，转化一次的访客可能会被再次计数
* [!DNL Analytics] 为所有访问和访客的所有转化计数，而 [!DNL Target] 则只为列入活动的访问和访客的转化计数
