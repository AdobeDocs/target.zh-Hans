---
keywords: 推荐;推荐标准;推荐算法;推荐活动;标准;推荐定向;推荐
description: 了解Adobe [!DNL Target] 中的Recommendations活动，它会根据先前的用户活动或其他算法自动显示可能引起客户兴趣的内容。
title: 什么是 [!DNL Target] Recommendations?
feature: Recommendations
exl-id: 0d986e17-bc99-4c08-a963-7f9a6619609a
translation-type: tm+mt
source-git-commit: cb42be6b0791711d3a9ddf5680cf6d6e32045579
workflow-type: tm+mt
source-wordcount: '929'
ht-degree: 97%

---

# ![PREMIUM](/help/assets/premium.png) Recommendations

[!DNL Adobe Target Recommendations] 活动根据以前的用户活动、偏好或其他标准，自动显示可能让访客感兴趣的产品、服务或内容。[!DNL Target Recommendations] 有助于引导访客查看在其他情况下他们可能不知道的相关项目。通过 [!DNL Recommendations]，可在正确的时间和正确的地点为访客提供相关的内容。

>[!NOTE]
>
>[!DNL Recommendations] 活动作为 [Target Premium 解决方案](/help/c-intro/intro.md#premium)的一部分提供。如果没有 [!DNL Target Premium] 许可证，它们将无法在 [!DNL Target Standard] 中使用。
>
>如果您目前拥有 [!DNL Recommendations Classic]，则请参阅 [Recommendations Classic 与 Target Premium 中的“推荐”活动](/help/c-recommendations/c-recommendations-faq/recommendations-classic-versus-recommendations-activities-target-premium.md#concept_A80223EF66634EA380580C2823A581C5)以了解有关这两种解决方案的更多信息。

[!DNL Recommendations] 可帮助您在各种渠道、应用程序、页面、电子邮件消息以及其他交付选项中优化并自定义实时建议，从而提高参与度和转化，同时简化管理工作。

[!DNL Recommendations] 可帮助您：

* 创建复杂的标准（规则）以实现自动化推荐
* 使用一些 JavaScript 代码片段来自动显示推荐
* 测试并优化推荐标准以及用于显示推荐的设计
* 报告“推荐”活动的结果

下图显示了某个网页上的推荐：

![](assets/velocity_example.png)

推荐根据访客在网站上的活动，决定如何将产品推荐给该访客。例如：

| 所需操作 | 推荐 |
|--- |--- |
| 鼓励购买了背包的人也考虑购买登山鞋和登山杖。 | 使用“购买了这个项目，也购买了那个项目的人”标准，创建一个推荐来显示通常一起购买的项目。 |
| 向访客推荐与其正在观看的媒体内容相似的内容，以增加访客在媒体网站上的停留时间。 | 使用“查看了这个项目，也查看了那个项目的人”标准，创建一个推荐来推荐其他视频。 |
| 建议查看有关银行储蓄计划信息的客户也阅读 IRA 帐户相关信息。 | 使用“查看了这个项目，但购买了那个项目的人”标准，显示人们查看某个产品后购买的其他产品，而不显示推荐中的第一个产品。 |

有关上述标准及其他 [!DNL Recommendations] 标准的更多信息，请参阅[标准](/help/c-recommendations/c-algorithms/algorithms.md)。

## 术语

在开始使用 [!DNL Recommendations] 之前，熟悉本节中使用的一些术语很有帮助。如果尚未完全理解这些术语，也不必担心，随着您设置自己的 [!DNL Recommendations] 活动，您将更加熟悉这些术语。

| 术语 | 定义 |
| --- | --- |
| 活动 | 通过 [!DNL Target] 中的活动，可针对特定受众使内容个性化并测试页面设计。[!DNL Recommendations] 只是 [!DNL Target] 中可用的许多活动类型之一。有关详细信息，请参阅 [Target 活动类型](/help/c-activities/target-activities-guide.md)。 |
| 实体 | 实体是指您想推荐的项目。实体可为产品、内容（文章、幻灯片、图像、电影和电视节目）、工作清单、餐厅等任何事物。有关详细信息，请参阅[实体](/help/c-recommendations/c-products/products.md)。 |
| 信息源 | 信息源用于获取导入到 [!DNL Recommendations] 中的实体。可以使用 CSV 文件、Google Product Search 信息源格式和 Adobe Analytics 产品分类来发送实体。有关更多信息，请参阅[信息源](/help/c-recommendations/c-products/feeds.md)。 |
| 目录 | 目录指代您的整个产品集（实体）。您的目录可包含许多收藏集 - 这是一种在逻辑存储桶中组织产品的方法。 |
| 收藏集 | 收藏集指代一组类似或相关的项目，如单个产品类别。不过，您可以将任何项目分组到一个对您的业务有意义的类别中，例如可以将属于某个价格范围内或具有某种颜色的产品分组到一个类别中，或将可能在某个特定地区引起客户关注的项目分组到一个类别中。有关详细信息，请参阅[收藏集](/help/c-recommendations/c-products/collections.md)。 |
| 标准 | 标准即规则，可根据预先确定的一组访客行为来确定要推荐的产品。<br>标准的一些示例包括： <ul><li>购买了这个项目，也购买了那个项目的人</li><li>查看了这个项目，也查看了那个项目的人</li><li>具有相似属性的项目</li><li>上次购买的项目</li><li>最喜爱类别</li></ul>  有关更多信息，请参阅[标准](/help/c-recommendations/c-algorithms/algorithms.md)。 |
| 设计 | 设计定义 [!DNL Recommendations] 活动中各个推荐的外观，如行、列、表或网格。本文顶部的插图展示一个 4 x 1 的设计。有关详细信息，请参阅[创建设计](/help/c-recommendations/c-design-overview/create-design.md)。 |
| 位置 | 位置指代网页、移动应用程序或电子邮件上的某个特定内容区域，您从中运行作个性化和优化用途的活动。 |
| 受众 | 受众是各组类似的活动参与者，他们将看到一项有针对性的活动。受众是具有相同特征的人群，例如都是新访客、回访访客或来自中西部的回访访客。通过使用“受众”功能，您可以将不同的内容和体验定位到特定的受众，即在适当的时间向适当的人员展示恰当的信息，从而优化网站营销。有关更多信息，请参阅[受众](/help/c-target/target.md)。 |
| “推荐”作为选件 | 这是一项功能，通过该功能，可在 A/B 测试（包括自动分配和自动定位）和体验定位 (XT) 活动中包括推荐。有关更多信息，请参阅[将推荐作为选件](/help/c-recommendations/recommendations-as-an-offer.md)。 |

## 培训视频：活动类型![概述徽章](/help/assets/overview.png)

以下视频介绍了 [!DNL Target Standard/Premium] 中可用的活动类型。对 [!DNL Recommendations] 的讨论开始于 7:20。

* 介绍 [!DNL Adobe Target] 中包含的活动类型
* 选择相应的活动类型以实现目标
* 介绍适用于所有活动类型的三步引导式工作流

>[!VIDEO](https://video.tv.adobe.com/v/17386)

## Adobe Target 基础知识网络研讨会：Recommendations 简介![教程徽章](/help/assets/tutorial.png) {#intro-to-recs}

**“Recommendations 简介”网络研讨会包括对如何利用 [!DNL Adobe Target Recommendations] 价值的深入探讨。了解此 [!DNL Target] 活动如何通过基于先前的访问优化实时建议来自动显示客户可能感兴趣的产品或内容。此外，深入了解 [!DNL Target] UI，获取有关如何构建 [!DNL Recommendations] 活动的分步概述。

[Recommendations 简介](https://adobecustomersuccess.adobeconnect.com/p8gt31drhs3e/?OWASP_CSRFTOKEN=4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)
