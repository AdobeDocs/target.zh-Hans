---
keywords: Real-time Customer Data Platform;rtcdp;个性化;aep 受众;Adobe Experience Platform 受众
description: 了解如何使用 [!DNL Target]/[!DNL Real-time Customer Data Platform] (RTCDP) 集成提供更丰富的客户数据和更有效的个性化。
title: 如何将 [!DNL Target] 与 [!DNL Real-time Customer Data Platform] 集成？
feature: Integrations
exl-id: 1c066b62-91a2-4b8c-807a-3cc56fca7778
source-git-commit: 9bc31a2de295cdc5ea29dfb5ebf60fdf36705e98
workflow-type: tm+mt
source-wordcount: '903'
ht-degree: 22%

---

# 与 Real-time Customer Data Platform 集成

基于 [!DNL Adobe Experience Platform] 的 [!DNL Real-time Customer Data Platform] (RTCDP) 可帮助各大公司汇集来自多个企业来源的已知和匿名数据，以创建可用于实时跨所有渠道和设备提供个性化客户体验的客户档案。

有关 RTCDP 的更多信息，请参阅[ Real-time Customer Data Platform 概述](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=zh-Hans){target=_blank}.

## 使用受众 [!DNL Adobe Experience Platform] {#aep}

使用 [受众](/help/main/c-target/c-audiences/audiences.md) 创建于 [!DNL Adobe Experience Platform] 提供更丰富的客户数据，从而实现更具影响力的个性化。 的 [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=zh-Hans){target=_blank} (RTCDP)，内置于 [!DNL Adobe Experience Platform]，可帮助公司将来自多个企业来源的已知和匿名数据汇集在一起。 通过此流程，您可以创建客户配置文件，以便用于在所有渠道和设备中实时提供个性化的客户体验。

连接 [!DNL Target] 和 [!DNL Real-time Customer Data Platform] 后，客户可以通过解锁 [!DNL Target] 以前可能无法访问的新分段来丰富其 Web 个性化，从而在客户 Web 访问的第一个页面上在毫秒内实现实时个性化。使用在 [!DNL Adobe Experience Platform] 允许您扩展可用的数据点，以便进行更丰富的个性化。

此集成可通过Real-time CDP解锁关键用例：

* 同页/下次点击个性化
* 首次/未知用户个性化

### 主要功能

主要功能包括：

* 直接 [!DNL Target] 与实时CDP集成/[!DNL Adobe Experience Platform] 在边缘上(删除对 [!DNL Audience Core services] - AAM)
* [!UICONTROL Target边缘目标卡] 管理和政策执行
* 实时CDP区段和共享配置文件属性

### Real-time CDP Profile Attributes功能限制和注意事项

请考虑以下事项：

* 给定选件中的属性必须来自同一AEP沙盒。 （换言之，选件不能包含来自不同AEP沙箱的属性。）
* 给定选件内的属性可能来自不同的来源；即 [!DNL Target] 配置文件和AEP配置文件。 (换言之，无论属性来自 [!DNL Target] 或从AEP配置文件中删除。)
* 在定义选件时，您可以为实时CDP配置文件属性分配默认值，以防该属性没有明确值。 例如，如果同意或管理策略阻止在个性化服务中使用的属性，则可以改用默认值。
* 共享后，将在用于 [!UICONTROL 自动定位] 和 [!UICONTROL Automated Personalization] 活动。

>[!NOTE]
>
>Real-time CDP Profile Attributes功能目前在测试版中提供，适用于HTML选件和 [JSON选件](/help/main/c-experiences/c-manage-content/create-json-offer.md).

### 指向更多信息的链接

有关更多信息，请参阅以下主题：

* [目标发行说明](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=en#destinations){target=_blank} 在 *Adobe Experience Platform发行说明*
* [为同一页面和下一页面个性化配置个性化目标](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html){target=_blank} 在 *目标概述* 的双曲余切值。
* [自定义个性化连接](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/custom-personalization.html){target=_blank} 在 *目标概述* 指南
* [Adobe Target连接](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection.html){target=_blank} 在 *目标概述* 指南
* [为同一页面和下一页个性化用例配置个性化目标](https://www.adobe.com/go/destinations-edge-personalization-en){target=_blank} 在 *目标概述* 指南

### 其他详细信息

在使用 [!DNL Adobe Experience Platform]:

#### 个性化用例

下表显示了使用 [!DNL Adobe Experience Platform Web SDK] 与使用at.js:

| 实施 | 已启用解决方案/用例 |
| --- | --- |
| at.js | **解决方案**:<ul><li>[!DNL Adobe Audience Manager] (AAM)和 [!DNL Target]</li><li>[!DNL RTCDP] （Premium或Ultimate）和 [!DNL Target]</li><li>[!DNL RTCDP] （任何SKU）、 [!DNL AAM]和 [!DNL Target]</li></ul>**用例**:<ul><li>下一会话个性化</li></ul> |
| [!DNL Platform Web SDK] 或 [!DNL AEP Server-Side API] | **解决方案**:<ul><li>[!DNL RTCDP] （任何SKU）和 [!DNL Target]</li></ul>**用例**:<ul><li>下一会话个性化</li><li>通过Edge进行同页个性化</li><li>在共享区段时强制实施管理</li></ul>**解决方案**:<ul><li>[!DNL RTCDP] （任何SKU）、 [!DNL AAM]和 [!DNL Target]</li></ul>**用例**:<ul><li>下一会话个性化</li><ul><li>[!DNL AAM] 区段</li><li>通过 [!DNL AAM]</li></ul><li>通过Edge进行同页个性化</li><ul><li>[!DNL RTCDP] 区段</li><li>在共享区段时强制实施管理</li></ul> |
| 混合 [!UICONTROL at.js] 和 [!DNL Platform Web SDK] | **解决方案**:<ul><li>[!DNL RTCDP] （任何SKU）和 [!DNL Target]</li></ul>**用例**:<ul><li>下一会话个性化</li><ul><li>适用于 [!UICONTROL at.js]</li></ul><li>同页个性化</li><ul><li>适用于 [!DNL Platform Web SDK]</li></ul></ul>**解决方案**:<ul><li>[!DNL RTCDP] （任何SKU）、 [!DNL AAM]和 [!DNL Target]</li></ul>**用例**:<ul><li>下一会话个性化</li><ul><li>适用于 [!UICONTROL at.js]</li><li>[!DNL AAM] 区段</li><li>通过 [!DNL AAM]</li></ul> |

#### 区段评估时间

下表显示了来自不同实施方案的事件的区段评估时间：

| 情景 | 边缘区段（毫秒评估） | 流区段（分钟评估） | 批量区段评估 |
| --- | --- | --- | --- |
| 来自的事件/数据 [!DNL Adobe Experience Platform] SDK | 是 | 是 | 不适用 |
| 事件来自 [!UICONTROL at.js] | 否 | 是 | 不适用 |
| 事件来自 [!DNL Target Mobile] SDK | 否 | 是 | 不适用 |
| 批量上传事件 | 否 | 否 | 是 |
| 离线数据（流）中的事件 | 否 | 是 | 是 |

## 与共享Real-time CDP Profile Attributes [!DNL Target] {#rtcdp-profile-attributes}

Real-time CDP Profile Attributes可与 [!DNL Target] 用于HTML选件和 [JSON选件](/help/main/c-experiences/c-manage-content/create-json-offer.md). （请注意，此功能目前处于测试阶段。）

示例用例：作为在线营销人员，您希望AEP/统一配置文件与共享属性值 [!DNL Target] 以便提供实时个性化。 通过使用实时CDP配置文件属性，您可以在 [!DNL Target] 选件。 例如，您可以使用 `${aep.profile.favoriteColor}`，或者使用令牌的忠诚度等级和忠诚度点值 `${aep.loyalty.tier}` 和 `${aep.loyalty.points}`.

![offer-json-aep-shared-attribute图像](/help/main/c-experiences/c-manage-content/assets/offer-json-aep-shared-attribute.png)

请注意，指定默认值是可选的。

## 视频：使用实时CDP实现下一次点击的个性化，以及 [!DNL Adobe Target]{#RTCDP}

了解如何在下次点击时使用进行个性化设置 [!DNL Real-time Customer Data Platform] 和 [!DNL Adobe Target]. 的 [!DNL Adobe Target] 目标 [!DNL Real-time CDP] 允许您使用 [!DNL Experience Platform] 区段 [!DNL Adobe Target] 具有管理和隐私支持的相同页面个性化和下一页个性化。

有关更多信息，请参阅 [使用实时CDP和Adobe Target实现下一次点击的个性化](https://experienceleague.adobe.com/docs/platform-learn/tutorials/experience-cloud/next-hit-personalization.html){target=_blank} 在 *平台Tutorials* 的双曲余切值。

>[!VIDEO](https://video.tv.adobe.com/v/340091?quality=12&learn=on)

## Adobe Target博客和视频：

[[!DNL Adobe] announces Same Page Enhanced Personalization with [!DNL Adobe Target] 和 [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}
