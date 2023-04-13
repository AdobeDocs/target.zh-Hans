---
keywords: Real-time Customer Data Platform;RTCDP；个性化；AEP受众；Adobe Experience Platform受众；配置文件属性
description: 了解如何使用 [!DNL Target]/[!DNL Real-Time Customer Data Platform] (RTCDP) 集成提供更丰富的客户数据和更有效的个性化。
title: 如何将 [!DNL Target] 与 [!DNL Real-Time Customer Data Platform] 集成？
feature: Integrations
exl-id: 1c066b62-91a2-4b8c-807a-3cc56fca7778
source-git-commit: ab4afd18d55a2b44bb31787360cec6089250c69a
workflow-type: tm+mt
source-wordcount: '936'
ht-degree: 9%

---

# 集成对象 [!DNL Real-Time Customer Data Platform]

内置 [!DNL Adobe Experience Platform], [!DNL Real-Time Customer Data Platform] (RTCDP)帮助公司将来自多个企业来源的已知和匿名数据汇集在一起。 RTCDP让您能够创建客户配置文件，这些配置文件可用于实时提供跨所有渠道和设备的个性化客户体验。

有关RTCDP的更多信息，请参阅 [Real-time Customer Data Platform概述](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=zh-Hans){target=_blank}.

## 主要功能

主要功能包括：

* 直接 [!DNL Target] 与Real-Time CDP集成/[!DNL Adobe Experience Platform] 在边缘上(删除对 [!DNL Audience Core services] - AAM)
* [!UICONTROL Target边缘目标卡] 管理和政策执行
* 实时CDP区段和共享配置文件属性

## 实施方案

以下部分显示了在使用不同的实施方法时，可用的个性化用例类型（下一会话或同一页面）：

### at.js 实施

| 解决方案 | 启用用例 |
| --- | --- |
| <ul><li>[!DNL Adobe Audience Manager] (AAM)和 [!DNL Target]</li><li>[!DNL RTCDP] （Premium或Ultimate）和 [!DNL Target]</li><li>[!DNL RTCDP] （任何SKU）、 [!DNL AAM]和 [!DNL Target]</li></ul> | 下一会话个性化 |

### [!DNL Adobe Experience Platform Web SDK] 或 [!DNL Experience Platform Server-Side API] 实施

| 解决方案 | 启用用例 |
| --- | --- |
| <ul><li>[!DNL RTCDP] （任何SKU）和 [!DNL Target]</li></ul> | <ul><li>下一会话个性化</li><li>通过Edge进行同页个性化</li><li>在共享区段时强制实施管理</li></ul> |
| <ul><li>[!DNL RTCDP] （任何SKU）、 [!DNL AAM]和 [!DNL Target]</li></ul> | <ul><li>下一会话个性化</li><ul><li>[!DNL AAM] 区段</li><li>通过 [!DNL AAM]</li></ul><li>通过Edge进行同页个性化</li><ul><li>[!DNL RTCDP] 区段</li><li>在共享区段时强制实施管理</li></ul> |

### 混合 [!UICONTROL at.js] 和 [!DNL Platform Web SDK] 实施

| 解决方案 | 启用用例 |
| --- | --- |
| <ul><li>[!DNL RTCDP] （任何SKU）和 [!DNL Target]</li></ul> | <ul><li>下一会话个性化</li><ul><li>适用于 [!UICONTROL at.js]</li></ul><li>同页个性化</li><ul><li>适用于 [!DNL Platform Web SDK]</li></ul> |
| <ul><li>[!DNL RTCDP] （任何SKU）、 [!DNL AAM]和 [!DNL Target]</li></ul> | <ul><li>下一会话个性化</li><ul><li>适用于 [!UICONTROL at.js]</li><li>[!DNL AAM] 区段</li><li>通过 [!DNL AAM]</li></ul> |

## 区段评估时间

下表显示了来自不同实施方案的事件的区段评估时间：

| 情景 | 边缘区段（毫秒评估） | 流区段（分钟评估） | 批量区段评估 |
| --- | --- | --- | --- |
| 来自的事件/数据 [!DNL Adobe Experience Platform] SDK | 是 | 是 | 不适用 |
| 事件来自 [!UICONTROL at.js] | 否 | 是 | 不适用 |
| 事件来自 [!DNL Target Mobile] SDK | 否 | 是 | 不适用 |
| 批量上传事件 | 否 | 否 | 是 |
| 离线数据（流）中的事件 | 否 | 是 | 是 |

## 使用受众 [!DNL Adobe Experience Platform] {#aep}

使用 [受众](/help/main/c-target/c-audiences/audiences.md) 创建于 [!DNL Adobe Experience Platform] 提供更丰富的客户数据，从而实现更具影响力的个性化。 的 [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=zh-Hans){target=_blank} (RTCDP)，内置于 [!DNL Adobe Experience Platform]，可帮助公司将来自多个企业来源的已知和匿名数据汇集在一起。 通过此流程，您可以创建客户配置文件，以便用于在所有渠道和设备中实时提供个性化的客户体验。

通过连接 [!DNL Target] 到 [!DNL Real-Time Customer Data Platform]，客户可以丰富其Web个性化。 此集成允许您解锁之前可能无法访问的新区段 [!DNL Target] 用于在客户的Web访问首页上实时进行毫秒个性化。 使用在 [!DNL Adobe Experience Platform] 允许您扩展可用的数据点，以便进行更丰富的个性化。

此集成可解锁Real-Time CDP的关键用例：

* 同页/下次点击个性化
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
* 在定义选件时，您可以为 [!UICONTROL Real-Time CDP配置文件属性]，则属性没有显式值。 例如，如果同意或管理策略阻止在个性化服务中使用的属性，则可以改用默认值。

### JSON示例用例

作为在线营销人员，您希望AEP/统一配置文件与共享属性值 [!DNL Target] 提供实时个性化。 使用 [!UICONTROL Real-Time CDP配置文件属性]，则可以显示 [!UICONTROL Experience Platform] 属性 [!DNL Target] 选件。 例如，您可以使用 `${aep.profile.favoriteColor}`，或者使用令牌的忠诚度等级和忠诚度点值 `${aep.loyalty.tier}` 和 `${aep.loyalty.points}`.

创建JSON选件以与共享AEP/统一配置文件属性 [!DNL Target]:

1. While [创建JSON选件](/help/main/c-experiences/c-manage-content/create-json-offer.md)，从 **[!UICONTROL 选择源]** 列表，选择 **[!UICONTROL Adobe Experience Platform]**.
1. 从 **[!UICONTROL 选择用户档案沙盒名称]** 列表中，选择所需的沙盒。
1. 从 **[!UICONTROL 选择配置文件属性]** 列表中，选择所需的属性。
1. （可选）从 **[!UICONTROL 插入默认值]** 列表中，选择所需的值。
1. 单击&#x200B;**[!UICONTROL 添加]**。

下图显示了两个配置文件属性： `loyalty.tier` 和 `loyalty.points` 已添加到JSON选件中。

![offer-json-aep-shared-attribute图像](/help/main/c-experiences/c-manage-content/assets/offer-json-aep-shared-attribute.png)

### 指向更多信息的链接

有关更多信息，请参阅以下主题：

* [目标发行说明](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=en#destinations){target=_blank} 在 *Adobe Experience Platform发行说明*
* [为同一页面和下一页面个性化配置个性化目标](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html){target=_blank} 在 *目标概述* 的双曲余切值。
* [Adobe Target连接](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection.html){target=_blank} 在 *目标概述* 指南
* [映射属性](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/activate-profile-request-destinations.html?lang=en#map-attributes){target=_blank} 在 *目标概述* 的双曲余切值。

## 视频和博客帖子

以下视频和博客文章提供了有关使用Target和RTCDP增强个性化的更多信息：

### 视频：使用Real-Time CDP和 [!DNL Adobe Target]{#RTCDP}

了解如何在下次点击时使用进行个性化设置 [!DNL Real-Time Customer Data Platform] 和 [!DNL Adobe Target]. 的 [!DNL Adobe Target] 目标 [!DNL Real-Time CDP] 允许您使用 [!DNL Experience Platform] 区段 [!DNL Adobe Target] 具有管理和隐私支持的相同页面个性化和下一页个性化。

有关更多信息，请参阅 [使用Real-Time CDP和Adobe Target进行下一次点击的个性化](https://experienceleague.adobe.com/docs/platform-learn/tutorials/experience-cloud/next-hit-personalization.html){target=_blank} 在 *平台Tutorials* 的双曲余切值。

>[!VIDEO](https://video.tv.adobe.com/v/340091?quality=12&learn=on)

### [!DNL Adobe Target] 博客和视频：同页增强的个性化

[[!DNL Adobe] announces Same-Page Enhanced Personalization with [!DNL Adobe Target] 和 [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}
