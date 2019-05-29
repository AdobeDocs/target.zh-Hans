---
description: 此信息介绍了当“不”使用 Analytics 作为报表源（A4T，可完全消除数据差异）时 Target 和 Adobe Analytics 之间的预期数据差异。
keywords: 数据差异;Analytics;区别;差异;A4T;Analytics for Target;Analytics 作为报表源;差别
seo-description: 此信息介绍了当“不”使用 Analytics 作为报表源（A4T，可完全消除数据差异）时 Target 和 Adobe Analytics 之间的预期数据差异。
seo-title: 不使用 A4T 时的预期数据差异
solution: Target
title: 不使用 A4T 时的预期数据差异
topic: 高级
uuid: 61bef460-8613-4251-b1b2-b6226ec86d9b
translation-type: tm+mt
source-git-commit: 8423f5e8468c131ba9b0a77025968e11012f57f6

---


# 使用和不使用 A4T 时，Target 和 Analytics 之间的预期数据差异{#expected-data-variances-when-not-using-a-t}

有关在使用Analytics作为报表源 [!DNL Target] (A4T) [!DNL Analytics] 时 *与Adobe*** 之间的预期数据差异的信息。A4T 可显著减小数据差异.

## 使用A4T时需要数据变化 {#expected-using-a4t}

使用 A4T 时，Analytics 和 Target 活动报表都只使用 Analytics 数据，因此 Target 活动报表中的解决方案之间几乎没有差异。但是，在某些情况下，客户可能会将 Target 数据与 A4T 集成范围之外的 Analytics 数据进行比较，这样，就会出现下面所述的差异问题。

以下是可能遇到预期数据变化的少数情况：

* A4T允许发生Target点击(页面顶部)，但不发生Analytics点击(页面底部)。例如，如果用户加载页面，但在触发Analytics调用之前关闭浏览器，则会出现这种情况。在这些情况下，A4T从我们的数据中排除Target。原因在于，允许Target点击(再次、页面顶部)在缺少实际Analytics调用的情况下计算Analytics点击会造成与Analytics中数据集的不一致(访客膨胀等)。

   如果在Target中设置重定向测试以拆分流量50/50(或25/25/25等)，则用户行为可能不会平均拆分。如果您看到一个不均匀的拆分，就意味着一组用户在登录页面上无法执行分析调用，该调用比其他用户组更多。这一未能对一个组执行Analytics调用导致Target点击该用户被排除，从而创造不熟悉。

   当我们在Adobe Experience Platform上致力于A4T时，我们希望将来能解决这一问题。我们的团队正在了解如何最好地处理页面上不同时间发生的这些不同活动。

* 假定您为特定页面创建了向所有访客开放的自动分配活动。由于自动分配活动不支持 A4T，因此 [!DNL Target] 会收集所有活动数据。您可能希望同一日期范围内 [!DNL Target] 报表中的活动访客与 [!DNL Analytics] 报表中该页面的访客相匹配。在这种情景中，预期会出现下面所述的差异。

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