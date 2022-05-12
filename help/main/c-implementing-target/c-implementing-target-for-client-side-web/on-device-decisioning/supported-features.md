---
keywords: 实施；javascript库；js;atjs；设备上决策；设备上决策；支持的功能
description: 了解设备上决策支持哪些功能。
title: Which Features Are Supported in On-Device Decisioning
feature: at.js
role: Developer
exl-id: 3531ff55-c3db-44c1-8d0a-d7ec2ccb6505
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 13%

---

# 对 at.js 的设备上决策支持的功能

的 [!DNL Adobe Target] JS SDK使客户能够灵活地在性能和数据新鲜度之间进行选择，以便做出决策。 In other words, if delivering the most relevant and engaging personalized content via machine learning is most important to you, a live server call should be made. 但是，当性能更为关键时，应该做出设备内和内存内的决策。 For on-device decisioning to work, refer to the following sections that list the features that are supported.

## Supported activity types

下表指明了 [活动类型](/help/main/c-activities/target-activities-guide.md) 创建者 [基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md) 或 [可视化体验编辑器](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC)是否支持设备决策。

| 活动类型 | 受支持? |
| --- | --- |
| [A/B 测试](/help/main/c-activities/t-test-ab/test-ab.md) | 是 |
| [自动分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | 否 |
| [Auto-Target（自动定位）](/help/main/c-activities/auto-target/auto-target-to-optimize.md) ![Premium](/help/main/assets/premium.png) | 否 |
| [多变量测试](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | 否 |
| [Experience Targeting](/help/main/c-activities/t-experience-target/experience-target.md) (XT) | 是 |
| [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) ![Premium](/help/main/assets/premium.png) | 否 |
| [Recommendations](/help/main/c-recommendations/recommendations.md) ![Premium](/help/main/assets/premium.png) | 否 |
| [使用Analytics for Target的活动](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | 是 |

## Audience targeting

The following table indicates which audience rules are supported or not supported for on-device decisioning.

| Audience rule | 受支持? |
| --- | --- |
| [地域](/help/main/c-target/c-audiences/c-target-rules/geo.md) | 是 |
| [网络](/help/main/c-target/c-audiences/c-target-rules/network.md) | 否 |
| [移动设备](/help/main/c-target/c-audiences/c-target-rules/mobile.md) | 否 |
| [自定义参数](/help/main/c-target/c-audiences/c-target-rules/custom-parameters.md) | 是 |
| [操作系统](/help/main/c-target/c-audiences/c-target-rules/operating-system.md) | 是 |
| [网页](/help/main/c-target/c-audiences/c-target-rules/site-pages.md) | 是 |
| [浏览器](/help/main/c-target/c-audiences/c-target-rules/browser.md) | 是 |
| [访客资料](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md) | 否 |
| [流量源](/help/main/c-target/c-audiences/c-target-rules/traffic-sources.md) | 否 |
| [期限](/help/main/c-target/c-audiences/c-target-rules/time-frame.md) | 是 |
| Adobe Experience Cloud Audiences<br>(受众来源 [!DNL Adobe Analytics], [!DNL Adobe Audience Manager]和 [!DNL Adobe Experience Manager] | 否 |

### 设备上决策的地域定位

为了通过基于地理的受众保持设备上决策活动的最短延迟，Adobe建议您在调用 [getOffers](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md). 在请求的上下文中设置Geo对象。 这表示从浏览器中确定每个访客位置的方法。 For example, you can perform an IP-to-Geo lookup, using a service you configure. Some hosting providers, such as Google Cloud, provide this functionality via custom headers in each `HttpServletRequest`.

```javascript
window.adobe.target.getOffers({ 
	decisioningMethod: "on-device", 
	request: { 
		context: { 
			geo: { 
				city: "SAN FRANCISCO", 
				countryCode: "US", 
				stateCode: "CA", 
				latitude: 37.75, 
				longitude: -122.4 
			} 
		}, 
		execute: { 
			pageLoad: {} 
		} 
	} 
})
```

However, if you are not able to perform IP-to-Geo lookups on your server, but you still want to perform on-device decisioning for [getOffers](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) requests that contain geo-based audiences, this is also supported. The downside of this approach is that it uses a remote IP-to-Geo lookup, which adds latency to each `getOffers` call. This latency should be lower than a `getOffers` call with server-side decisioning, because it hits a CDN that is located close to your server. Provide only the &quot;ipAddress&quot; field in the Geo object in the Context of your request for the SDK to retrieve the geo-location of your visitor&#39;s IP address. 如果除了“ipAddress”之外还提供了任何其他字段，则 [!DNL Target] SDK将不会获取用于解析的地理位置元数据。

```javascript
window.adobe.target.getOffers({ 
	decisioningMethod: "on-device", 
	request: { 
		context: { 
			geo: { 
				ipAddress: "127.0.0.1" 
			} 
		}, 
		execute: { 
			pageLoad: {} 
		} 
	} 
})
```

### Allocation method

下表指示设备上决策支持或不支持哪些分配方法。

| 分配方法 | 受支持? |
| --- | --- |
| 手动 | 是 |
| [自动分配到最佳体验](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | 否 |
| [自动定位以提供个性化体验](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | 否 |