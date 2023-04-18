---
keywords: Real-time Customer Data Platform;RTCDP；个性化；AEP受众；Adobe Experience Platform受众；配置文件属性
description: 了解如何使用 [!DNL Target]/[!DNL Real-Time Customer Data Platform] (RTCDP) 集成提供更丰富的客户数据和更有效的个性化。
title: 如何将 [!DNL Target] 与 [!DNL Real-Time Customer Data Platform] 集成？
feature: Integrations
exl-id: 1c066b62-91a2-4b8c-807a-3cc56fca7778
source-git-commit: 08422323607f7238a7cf9bac5b863032ce734662
workflow-type: tm+mt
source-wordcount: '936'
ht-degree: 49%

---

# 集成对象 [!DNL Real-Time Customer Data Platform]

内置 [!DNL Adobe Experience Platform], [!DNL Real-Time Customer Data Platform] (RTCDP)帮助公司将来自多个企业来源的已知和匿名数据汇集在一起。 RTCDP让您能够创建客户配置文件，这些配置文件可用于实时提供跨所有渠道和设备的个性化客户体验。

有关RTCDP的更多信息，请参阅 [Real-time Customer Data Platform概述](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=zh-Hans){target=_blank}.

## 主要功能

主要功能包括：

* 直接 [!DNL Target] 与Real-Time CDP集成/[!DNL Adobe Experience Platform] 在边缘上(删除对 [!DNL Audience Core services] - AAM)
* [!UICONTROL Target Edge Destinations Card] 具有治理和政策执行功能
* Real-time CDP 片段和共享个人资料属性

## 实施方案

以下部分显示了在使用不同的实施方法时，可用的个性化用例类型（下一会话或同一页面）：

### at.js 实施

| 解决方案 | 启用用例 |
| --- | --- |
| <ul><li>[!DNL Adobe Audience Manager] (AAM) 和[!DNL Target]</li><li>[!DNL RTCDP]（Premium 或 Ultimate）和[!DNL Target]</li><li>[!DNL RTCDP]（任何 SKU），[!DNL AAM]，和[!DNL Target]</li></ul> | 下一个会话个性化 |

### [!DNL Adobe Experience Platform Web SDK] 或 [!DNL Experience Platform Server-Side API] 实施

| 解决方案 | 启用用例 |
| --- | --- |
| <ul><li>[!DNL RTCDP]（任何 SKU）和 [!DNL Target]</li></ul> | <ul><li>下一个会话个性化</li><li>通过 Edge 实现同一页面个性化</li><li>共享片段时强制执行治理</li></ul> |
| <ul><li>[!DNL RTCDP]（任何 SKU），[!DNL AAM]，和[!DNL Target]</li></ul> | <ul><li>下一个会话个性化</li><ul><li>[!DNL AAM] 区段</li><li>通过 [!DNL AAM] 的第三方片段</li></ul><li>通过 Edge 实现同一页面个性化</li><ul><li>[!DNL RTCDP] 区段</li><li>共享片段时强制执行治理</li></ul> |

### 混合 [!UICONTROL at.js] 和 [!DNL Platform Web SDK] 实施

| 解决方案 | 启用用例 |
| --- | --- |
| <ul><li>[!DNL RTCDP]（任何 SKU）和 [!DNL Target]</li></ul> | <ul><li>下一个会话个性化</li><ul><li>对于带有 [!UICONTROL at.js] 的所有页面</li></ul><li>同一页面个性化</li><ul><li>对于带有 [!DNL Platform Web SDK] 的所有页面</li></ul> |
| <ul><li>[!DNL RTCDP]（任何 SKU），[!DNL AAM]，和[!DNL Target]</li></ul> | <ul><li>下一个会话个性化</li><ul><li>对于带有 [!UICONTROL at.js] 的所有页面</li><li>[!DNL AAM] 区段</li><li>通过 [!DNL AAM] 的第三方片段</li></ul> |

## 片段评估时间

下表显示了来自不同实施场景的事件的片段评估时间：

| 场景 | Edge 片段（毫秒评估） | 流式处理片段（分钟评价） | 批次片段评估 |
| --- | --- | --- | --- |
| 来自 [!DNL Adobe Experience Platform] SDK 的事件/数据 | 是 | 是 | 不适用 |
| 来自 [!UICONTROL at.js] 的事件 | 否 | 是 | 不适用 |
| 来自 [!DNL Target Mobile] SDK 的事件 | 否 | 是 | 不适用 |
| 批次上传事件 | 否 | 否 | 是 |
| 来自离线数据的事件（流） | 否 | 是 | 是 |

## 使用来自 [!DNL Adobe Experience Platform] 的受众 {#aep}

使用在 [!DNL Adobe Experience Platform] 中创建的[受众](/help/main/c-target/c-audiences/audiences.md)可提供更丰富的客户数据，从而带来更强大的个性化功能。 的 [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=zh-Hans){target=_blank} (RTCDP)，内置于 [!DNL Adobe Experience Platform]，可帮助公司将来自多个企业来源的已知和匿名数据汇集在一起。 此过程允许您创建配置文件，这些资料可用于在所有渠道和设备中实时提供个性化的客户体验。

通过连接 [!DNL Target] 到 [!DNL Real-Time Customer Data Platform]，客户可以丰富其Web个性化。 此集成允许您解锁之前可能无法访问的新区段 [!DNL Target] 用于在客户的Web访问首页上实时进行毫秒个性化。 使用在 [!DNL Adobe Experience Platform] 中创建的受众和个人资料属性，可以扩展可用的数据点，以实现更丰富的个性化内容。

此集成可解锁Real-Time CDP的关键用例：

* “同一页面”/“下一个点击”个性化
* 首次/未知用户个性化

## 与共享Real-Time CDP配置文件属性 [!DNL Target] {#rtcdp-profile-attributes}

Real-Time CDP配置文件属性可以与 [!DNL Target] 用于HTML选件和 [JSON选件](/help/main/c-experiences/c-manage-content/create-json-offer.md).

### Real-Time CDP配置文件属性功能限制和注意事项

>[!NOTE]
>
>在测试版中，提供了Real-Time CDP配置文件属性功能，用于HTML选件和 [JSON选件](/help/main/c-experiences/c-manage-content/create-json-offer.md).

请考虑以下事项：

* 给定选件中的属性必须来自相同的 [!UICONTROL Experience Platform] 沙盒。 (换言之，选件不能包含来自不同 [!UICONTROL Experience Platform] 沙盒。)
* 给定选件内的属性可能来自不同的来源；即 [!DNL Target] 用户档案和 [!UICONTROL Experience Platform] 配置文件。 (换言之，无论属性来自 [!DNL Target] 或 [!UICONTROL Experience Platform] 配置文件。)
* 在定义选件时，您可以为 [!UICONTROL Real-Time CDP配置文件属性]，则属性没有显式值。 例如，如果同意或治理策略阻止个性化服务中使用的属性，则可以使用默认值。

### JSON示例用例

作为在线营销人员，您希望AEP/统一配置文件与共享属性值 [!DNL Target] 提供实时个性化。 使用 [!UICONTROL Real-Time CDP配置文件属性]，则可以显示 [!UICONTROL Experience Platform] 属性 [!DNL Target] 选件。 例如，您可以使用 `${aep.profile.favoriteColor}` 根据客户最喜欢的颜色进行个性化设置，或者使用标记 `${aep.loyalty.tier}` 和 `${aep.loyalty.points}` 根据他们的忠诚度等级和忠诚度积分值进行个性化设置。

创建JSON选件以与共享AEP/统一配置文件属性 [!DNL Target]:

1. While [创建JSON选件](/help/main/c-experiences/c-manage-content/create-json-offer.md)，从 **[!UICONTROL 选择源]** 列表，选择 **[!UICONTROL Adobe Experience Platform]**.
1. 从 **[!UICONTROL 选择用户档案沙盒名称]** 列表中，选择所需的沙盒。
1. 从 **[!UICONTROL 选择配置文件属性]** 列表中，选择所需的属性。
1. （可选）从 **[!UICONTROL 插入默认值]** 列表中，选择所需的值。
1. 单击&#x200B;**[!UICONTROL 添加]**。

下图显示了两个配置文件属性： `loyalty.tier` 和 `loyalty.points` 已添加到JSON选件中。

![offer-json-aep-shared-attribute 图像](/help/main/c-experiences/c-manage-content/assets/offer-json-aep-shared-attribute.png)

## 更多信息的链接

有关更多信息，请参阅以下主题：

* *Adobe Experience Platform 发行说明*&#x200B;中的[目标发行说明](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=zh-Hans#destinations){target=_blank}
* 在&#x200B;*目标概述*&#x200B;指南中[为同一页面和下一个页面个性化配置个性化目标](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html){target=_blank}。
* *目标概述*&#x200B;指南中的 [Adobe Target 连接](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection.html){target=_blank}
* [映射属性](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/activate-profile-request-destinations.html?lang=en#map-attributes){target=_blank} 在 *目标概述* 的双曲余切值。

## 视频和博客帖子

以下视频和博客帖子提供了有关使用 Target 和 RTCDP 增强个性化的更多信息：

### 视频：使用Real-Time CDP和 [!DNL Adobe Target]{#RTCDP}

了解如何使用 [!DNL Real-Time Customer Data Platform] 和 [!DNL Adobe Target] 对下一次点击进行个性化。[!DNL Real-Time CDP] 中的 [!DNL Adobe Target] 目标允许您使用 [!DNL Adobe Target] 中的 [!DNL Experience Platform] 片段进行相同页面个性化和下一页面个性化，同时提供数据治理和隐私支持。

有关更多信息，请参阅 [使用Real-Time CDP和Adobe Target进行下一次点击的个性化](https://experienceleague.adobe.com/docs/platform-learn/tutorials/experience-cloud/next-hit-personalization.html){target=_blank} 在 *平台Tutorials* 的双曲余切值。

>[!VIDEO](https://video.tv.adobe.com/v/340091?quality=12&learn=on)

### [!DNL Adobe Target] 博客和视频：同页增强的个性化

[[!DNL Adobe] announces Same-Page Enhanced Personalization with [!DNL Adobe Target] 和 [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}
