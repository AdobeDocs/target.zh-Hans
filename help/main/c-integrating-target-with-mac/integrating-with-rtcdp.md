---
keywords: Real-Time Customer Data Platform；rtcdp；个性化；aep 受众；Adobe Experience Platform 受众；轮廓属性
description: 了解如何使用 [!DNL Target]/[!DNL Real-Time Customer Data Platform] (RTCDP) 集成提供更丰富的客户数据和更有效的个性化。
title: 如何将 [!DNL Target] 与 [!DNL Real-Time Customer Data Platform] 集成？
feature: Integrations
exl-id: 1c066b62-91a2-4b8c-807a-3cc56fca7778
source-git-commit: 4104b6cb67347205c0143c9dea46dd483a8266ce
workflow-type: tm+mt
source-wordcount: '975'
ht-degree: 71%

---

# 与 [!DNL Real-Time Customer Data Platform] 集成

基于 [!DNL Adobe Experience Platform]，[!DNL Real-Time Customer Data Platform] (RTCDP) 可帮助公司汇集来自多个企业来源的已知和匿名数据。RTCDP 允许您创建轮廓，这些轮廓可用于在所有渠道和设备中实时提供个性化的客户体验。

有关RTCDP的更多信息，请参阅[Real-Time Customer Data Platform概述](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=zh-Hans){target=_blank}。

## 主要功能

主要功能包括：

* 直接与 Edge 上的[!DNL Target] Real-Time CDP/集成[!DNL Adobe Experience Platform]（消除对 [!DNL Audience Core services] 的依赖 - AAM）
* 具有治理和策略实施的[!UICONTROL Target Edge Destinations Card]
* Real-time CDP 片段和共享轮廓属性

## 实施场景

以下部分显示了在使用不同的实施方法时哪种类型的个性化用例（下一会话或同一页面）可用：

### at.js 实施

| 解决方案 | 用例已启用 |
| --- | --- |
| <ul><li>[!DNL Adobe Audience Manager] (AAM) 和[!DNL Target]</li><li>[!DNL RTCDP]（Premium 或 Ultimate）和[!DNL Target]</li><li>[!DNL RTCDP]（任何 SKU），[!DNL AAM]，和[!DNL Target]</li></ul> | 下一个会话个性化 |

### [!DNL Adobe Experience Platform Web SDK]或[!DNL Experience Platform Server-Side API]实现

| 解决方案 | 用例已启用 |
| --- | --- |
| <ul><li>[!DNL RTCDP]（任何 SKU）和 [!DNL Target]</li></ul> | <ul><li>下一个会话个性化</li><li>通过 Edge 实现同一页面个性化</li><li>共享片段时强制执行治理</li></ul> |
| <ul><li>[!DNL RTCDP]（任何 SKU），[!DNL AAM]，和[!DNL Target]</li></ul> | <ul><li>下一个会话个性化</li><ul><li>[!DNL AAM] 区段</li><li>通过 [!DNL AAM] 的第三方片段</li></ul><li>通过 Edge 实现同一页面个性化</li><ul><li>[!DNL RTCDP] 区段</li><li>共享片段时强制执行治理</li></ul> |

### [!UICONTROL at.js]和[!DNL Platform Web SDK]实现的组合

| 解决方案 | 用例已启用 |
| --- | --- |
| <ul><li>[!DNL RTCDP]（任何 SKU）和 [!DNL Target]</li></ul> | <ul><li>下一个会话个性化</li><ul><li>对于带有 [!UICONTROL at.js] 的所有页面</li></ul><li>同一页面个性化</li><ul><li>对于带有 [!DNL Platform Web SDK] 的所有页面</li></ul> |
| <ul><li>[!DNL RTCDP]（任何 SKU），[!DNL AAM]，和[!DNL Target]</li></ul> | <ul><li>下一个会话个性化</li><ul><li>对于带有 [!UICONTROL at.js] 的所有页面</li><li>[!DNL AAM] 区段</li><li>通过 [!DNL AAM] 的第三方片段</li></ul> |

## 片段评估时间

下表显示了来自不同实施场景的事件的片段评估时间：

| 场景 | Edge 片段（毫秒评估） | 流式处理片段（分钟评价） | 批次片段评估 |
| --- | --- | --- | --- |
| 来自 [!DNL Adobe Experience Platform] SDK 的事件/数据 | 是 | 是 | 不适用 |
| 来自[!UICONTROL at.js]的事件 | 否 | 是 | 不适用 |
| 来自 [!DNL Target Mobile] SDK 的事件 | 否 | 是 | 不适用 |
| 批次上传事件 | 否 | 否 | 是 |
| 来自离线数据的事件（流） | 否 | 是 | 是 |

## 使用来自 [!DNL Adobe Experience Platform] 的受众 {#aep}

使用在 [!DNL Adobe Experience Platform] 中创建的[受众](/help/main/c-target/c-audiences/audiences.md)可提供更丰富的客户数据，从而带来更强大的个性化功能。 [Real-Time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=zh-Hans){target=_blank} (RTCDP)构建于[!DNL Adobe Experience Platform]之上，可帮助企业整合来自多个企业来源的已知和匿名数据。 此过程允许您创建轮廓，这些轮廓可用于在所有渠道和设备中实时提供个性化的客户体验。

通过连接 [!DNL Target] 到 [!DNL Real-Time Customer Data Platform]，客户可以丰富他们的网络个性化。这种集成让您可以解锁以前 [!DNL Target] 可能无法访问的新分段，从而在客户 Web 访问的第一个页面上在毫秒内实现实时个性化。使用在 [!DNL Adobe Experience Platform] 中创建的受众和轮廓属性，可以扩展可用的数据点，以实现更丰富的个性化内容。

这种集成解锁了 Real-Time CDP 的关键用例：

* “同一页面”/“下一个点击”个性化
* 首次/未知用户个性化

## 与 [!DNL Target] 共享 Real-Time CDP 轮廓属性 {#rtcdp-profile-attributes}

Real-Time CDP 轮廓属性可以共享给 [!DNL Target]，用于 HTML 产品建议和 [JSON 产品建议](/help/main/c-experiences/c-manage-content/create-json-offer.md)。

### Real-Time CDP 轮廓属性功能限制和考虑 {#limitations}

请考虑以下事项：

* 给定选件中的属性必须来自同一[!UICONTROL Experience Platform]沙盒。 （换句话说，选件不能包含来自不同[!UICONTROL Experience Platform]沙盒的属性。）
* 给定选件中的属性可以来自不同的源；即[!DNL Target]配置文件和[!UICONTROL Experience Platform]配置文件。 （换句话说，您可以组合属性，无论它们来自[!DNL Target]还是来自[!UICONTROL Experience Platform]配置文件。）
* 定义选件时，您可以为[!UICONTROL Real-Time CDP Profile Attributes]分配默认值，以防属性没有显式值。 例如，如果同意或治理策略阻止个性化服务中使用的属性，则可以使用默认值。
* [!DNL Target]仅支持要在选件中使用的[!DNL Adobe Experience Platform]配置文件属性的“string”数据类型。 尚不支持“Map”和“Array”类型属性。

### JSON 示例用例

作为在线营销人员，您希望 AEP/统一轮廓与 [!DNL Target] 共享属性值来实现实时个性化。通过使用[!UICONTROL Real-Time CDP Profile Attributes]，您可以使用令牌替换显示[!DNL Target]选件中[!UICONTROL Experience Platform]属性的值。 例如，您可以使用 `${aep.profile.favoriteColor}` 根据客户最喜欢的颜色进行个性化设置，或者使用标记 `${aep.loyalty.tier}` 和 `${aep.loyalty.points}` 根据他们的忠诚度等级和忠诚度积分值进行个性化设置。

创建 JSON 产品建议以共享 AEP/统一轮廓属性 [!DNL Target]：

1. 在[创建JSON选件](/help/main/c-experiences/c-manage-content/create-json-offer.md)时，从&#x200B;**[!UICONTROL Select a source]**&#x200B;列表中选择&#x200B;**[!UICONTROL Adobe Experience Platform]**。
1. 从&#x200B;**[!UICONTROL Select a profile sandbox name]**&#x200B;列表中，选择所需的沙盒。
1. 从&#x200B;**[!UICONTROL Select a profile attribute]**&#x200B;列表中，选择所需的属性。
1. （可选）从&#x200B;**[!UICONTROL Insert a default value]**&#x200B;列表中，选择所需的值。
1. 单击 **[!UICONTROL Add]**。

下图显示了两个轮廓属性：`loyalty.tier` 和 `loyalty.points` 已添加到 JSON 产品建议中。

![offer-json-aep-shared-attribute 图像](/help/main/c-experiences/c-manage-content/assets/offer-json-aep-shared-attribute.png)

## 更多信息的链接

有关更多信息，请参阅以下主题：

* *Adobe Experience Platform发行说明中的[目标发行说明](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=zh-Hans#destinations){target=_blank}*
* 在&#x200B;*目标概述*&#x200B;指南中[为同一页面和下一页面个性化配置个性化目标](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=zh-Hans){target=_blank}。
* *目标概述*&#x200B;指南中的[Adobe Target连接](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection.html?lang=zh-Hans){target=_blank}
* *目标概述*&#x200B;指南中的[映射属性](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/activate-profile-request-destinations.html?lang=zh-Hans#map-attributes){target=_blank}。
* 在&#x200B;*目标概述*&#x200B;指南中[将受众激活到边缘个性化目标](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/activate-edge-personalization-destinations.html?lang=zh-Hans){target=_blank}。
* 通过&#x200B;*目标概述*&#x200B;指南中“常见问题”下的 [!DNL Adobe Target] 和自定义Personalization目标[&#128279;](https://experienceleague.adobe.com/docs/experience-platform/destinations/destinations-faq.html?lang=zh-Hans#same-next-page-personalization){target=_blank}进行同一页面和下一页面个性化。

## 视频和博客帖子 {#videos-blogs}

以下视频和博客帖子提供了有关使用 Target 和 RTCDP 增强个性化的更多信息：

### 视频：使用 Real-Time CDP 和 [!DNL Adobe Target] 实现下一个点击个性化{#RTCDP}

了解如何使用 [!DNL Real-Time Customer Data Platform] 和 [!DNL Adobe Target] 对下一次点击进行个性化。[!DNL Real-Time CDP] 中的 [!DNL Adobe Target] 目标允许您使用 [!DNL Adobe Target] 中的 [!DNL Experience Platform] 片段进行相同页面个性化和下一页面个性化，同时提供数据治理和隐私支持。

有关详细信息，请参阅&#x200B;*Platform教程*&#x200B;指南中的[使用Real-Time CDP和Adobe Target进行下一次点击个性化](https://experienceleague.adobe.com/docs/platform-learn/tutorials/experience-cloud/next-hit-personalization.html?lang=zh-Hans){target=_blank}。

>[!VIDEO](https://video.tv.adobe.com/v/340091?quality=12&learn=on)

### 视频：配置 [!DNL Real-Time Customer Data Platform] 中的 [!DNL Adobe Target] 目标

了解如何配置 [!DNL Real-Time Customer Data Platform] 中的 [!DNL Adobe Target] 目标以开始从 [!DNL Real-Time CDP] 到 [!DNL Target] 发送区段和轮廓属性。

>[!VIDEO](https://video.tv.adobe.com/v/3449803/?learn=on&captions=chi_hans)

### 视频：激活区段和轮廓属性

了解如何从 [!DNL Adobe Real-Time Customer Data Platform] 到 [!DNL Adobe Target] 激活区段和轮廓属性，以在您的网站、移动应用程序和其他数字资产中显示实时个性化内容。

>[!VIDEO](https://video.tv.adobe.com/v/3447365/?learn=on&captions=chi_hans)

### 视频：在 [!DNL Target] 中使用 [!DNL Real-Time CDP] 区段

了解如何在 [!DNL Adobe Target] 中使用 [!DNL Real-Time Customer Data Platform] 区段，以在您的网站和移动应用程序上提供个性化体验。

>[!VIDEO](https://video.tv.adobe.com/v/3446837/?learn=on&captions=chi_hans)

### 视频：在 [!DNL Adobe Target] 中使用 [!DNL Real-Time CDP] 轮廓属性

了解如何在 [!DNL Adobe Target] 中使用 [!DNL Adobe Real-Time Customer Data Platform] 轮廓属性，以在您的网站和移动应用程序上提供个性化体验。

>[!VIDEO](https://video.tv.adobe.com/v/3451903/?learn=on&captions=chi_hans)

### [!DNL Adobe Target]博文和视频：同一页面增强的个性化

[[!DNL Adobe] 通过 [!DNL Adobe Target] 和 [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}发布同页增强型Personalization
