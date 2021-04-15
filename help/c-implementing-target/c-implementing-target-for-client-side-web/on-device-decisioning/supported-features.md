---
keywords: 实现；javascript库；js;atjs；设备上决策；设备上决策；支持的功能
description: 了解支持哪些功能进行设备上决策。
title: 设备上决策支持哪些功能
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: 5fcc5776e69222e0a232bd92ddfd10cee748e577
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 11%

---

# 支持的设备决策功能

[!DNL Adobe Target] JS SDK可让客户灵活地在数据的性能与新鲜度之间做出选择，以便作出决策。 换句话说，如果通过机器学习交付最相关、最引人入胜的个性化内容对您来说最为重要，则应进行实时服务器调用。 但是，当性能更为关键时，应该做出设备内和内存内决策。 要使设备决策正常工作，请参阅列表所支持功能的以下部分。

## 支持的活动类型

下表说明了在设备上决策支持或不支持由[基于表单的体验书写器](/help/c-experiences/form-experience-composer.md)或[可视体验书写器](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md)(VEC)创建的[活动类型](/help/c-activities/target-activities-guide.md)。

| 活动类型 | 受支持? |
| --- | --- |
| [A/B 测试](/help/c-activities/t-test-ab/test-ab.md) | 是 |
| [自动分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | 否 |
| [Auto-Target（自动定位）](/help/c-activities/auto-target/auto-target-to-optimize.md) ![Premium](/help/assets/premium.png) | 否 |
| [多变量测试](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | 否 |
| [体验定位](/help/c-activities/t-experience-target/experience-target.md) (XT) | 是 |
| [自动个](/help/c-activities/t-automated-personalization/automated-personalization.md) ![性化](/help/assets/premium.png) | 否 |
| [推荐](/help/c-recommendations/recommendations.md)  ![Premium](/help/assets/premium.png) | 否 |
| [活动使用Analytics for 目标](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | 是 |

## 受众定位

下表指示设备上决策支持或不支持哪些受众规则。

| 受众规则 | 受支持? |
| --- | --- |
| [地域](/help/c-target/c-audiences/c-target-rules/geo.md) | 是 |
| [网络](/help/c-target/c-audiences/c-target-rules/network.md) | 否 |
| [Mobile](/help/c-target/c-audiences/c-target-rules/mobile.md) | 否 |
| [自定义参数](/help/c-target/c-audiences/c-target-rules/custom-parameters.md) | 是 |
| [操作系统](/help/c-target/c-audiences/c-target-rules/operating-system.md) | 是 |
| [网页](/help/c-target/c-audiences/c-target-rules/site-pages.md) | 是 |
| [浏览器](/help/c-target/c-audiences/c-target-rules/browser.md) | 是 |
| [访客资料](/help/c-target/c-audiences/c-target-rules/visitor-profile.md) | 否 |
| [流量源](/help/c-target/c-audiences/c-target-rules/traffic-sources.md) | 否 |
| [期限](/help/c-target/c-audiences/c-target-rules/time-frame.md) | 是 |
| Adobe Experience Cloud受众<br>(来自[!DNL Adobe Analytics]、[!DNL Adobe Audience Manager]和[!DNL Adobe Experience Manager]的受众 | 否 |

### 设备上决策的地理定位

为了使具有基于地理的活动的设备上决策受众保持最低的延迟，Adobe建议您在调用[getOffers](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md)时自己提供地理值。 在请求的上下文中设置Geo对象。 这意味着从浏览器中确定每个访客位置的方法。 例如，您可以使用您配置的服务执行IP到地理查找。 某些托管提供商（如Google Cloud）通过每个`HttpServletRequest`中的自定义标题提供此功能。

（即将发布的代码）

但是，如果您无法在服务器上执行IP到地理查找，但您仍希望对包含基于地理的受众的[getOffers](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md)请求执行设备上决策，则也支持此功能。 此方法的缺点是它使用远程IP到地理查找，这会为每个`getOffers`调用增加延迟。 此延迟应比服务器端决策的`getOffers`调用低，因为它会点击靠近服务器的CDN。 在您请求SDK以检索访客IP地址的地理位置的上下文中，仅在Geo对象中提供“ipAddress”字段。 如果除“ipAddress”之外还提供了任何其他字段，则[!DNL Target] SDK将不会提取地理位置元数据以进行解析。

（即将发布的代码）

### 分配方法

下表指示设备上决策支持或不支持哪些分配方法。

| 分配方法 | 受支持? |
| --- | --- |
| 手动 | 是 |
| [自动分配到最佳体验](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | 否 |
| [自动目标，实现个性化体验](/help/c-activities/auto-target/auto-target-to-optimize.md) | 否 |
