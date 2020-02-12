---
keywords: Overview and Reference;act
description: 此信息介绍了有助于您了解 Adobe Target 特性和功能的关键概念。
title: Target 关键概念
subtopic: Getting Started
topic: Standard
uuid: c62ac156-b4cf-494c-979f-33f889abd118
translation-type: tm+mt
source-git-commit: 65a4fd0d05ad065c9291a83dc0b3066451f7373e

---


# Target 关键概念{#target-key-concepts}

此信息介绍了有助于您了解 Adobe Target 特性和功能的关键概念。

## 活动和测试 {#section_BEA0A0C51A8847579B566060206DE7E8}

活动可决定网站访客可能遇到的体验。

例如，您可能会设计一个活动以对两个不同的登陆页面进行测试，其中一个页面着重显示夏季女鞋的相关信息，而另一个页面则重点展示更广泛的夏季服饰信息。此活动确定了用于控制这两个登陆页面分别何时显示的条件，以及用于决定哪个页面更为成功的量度。此活动配置为在满足特定条件时开始和结束，例如在具体日期开始和结束，或者在活动得到批准后开始并在活动停用后结束。

设计活动时，您应该仔细规划。首先要确定活动的开始时间及其持续时长。然后，列出您的选件并为每个选件分配一组目标顾客。

Target 包括多种活动类型。下表提供了每种活动类型的概述，其中包含可帮助您了解更多信息的链接。为了帮助您更好地选择符合要求的最佳活动类型，我们还创建了 [Adobe Target 活动指南](/help/c-activities/target-activities-guide.md)。

| 活动类型 | 描述 |
|--- |--- |
| [A/B 测试](/help/c-activities/t-test-ab/test-ab.md) | A/B 测试可比较两个或更多版本的网站内容，以查看在预先指定的测试期间，哪个版本最能提高转化。<br>**注意：**现在，您可以[在 A/B 测试活动中包含推荐](/help/c-recommendations/recommendations-as-an-offer.md)。要使用此功能，您需要拥有[Target Premium 许可证](/help/c-intro/intro.md#premium)。 |
| [自动分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | 自动分配可在两个或更多体验中标识一个入选者，并在测试继续运行和学习期间，自动为入选者重新分配更多流量以提高转化。<br>**注意：**现在，您可以[在自动分配活动中包含推荐](/help/c-recommendations/recommendations-as-an-offer.md)。要使用此功能，您需要拥有[Target Premium 许可证](/help/c-intro/intro.md#premium)。 |
| [自动定位](/help/c-activities/auto-target-to-optimize.md)<br>![Target Premium](/help/assets/premium.png) | 自动定位可使用先进的机器学习技术从营销人员定义的多个高性能体验中进行识别，并根据每位访客的个人客户配置文件和具有相似配置文件的先前访客的行为，向每位访客提供量身定制的体验，以便个性化内容并促进转化。<br>**注意：**现在，您可以[在自动定位活动中包含推荐](/help/c-recommendations/recommendations-as-an-offer.md)。要使用此功能，您需要拥有[Target Premium 许可证](/help/c-intro/intro.md#premium)。 |
| [使用 Analytics 数据](/help/c-activities/t-test-ab/t-test-create-ab/create-a4t.md) (A4T) | 您可以将活动配置为使用 [!DNL Adobe Analytics] 作为报表源。此活动类型要求您将 [!DNL Adobe Experience Cloud] 帐户与 [!DNL Analytics] 和 [!DNL Target] 均关联。 |
| [多变量测试](/help/c-activities/c-multivariate-testing/multivariate-testing.md) | 多变量测试 (MVT) 可通过比较页面上各元素中的选件组合，来确定哪个组合对特定受众的效果最佳，以及哪个元素对活动成功的影响最大。 |
| [体验定位](/help/c-activities/t-experience-target/experience-target.md) | 体验定位 (XT) 可根据营销人员定义的一组规则和标准，将内容交付给指定的受众。<br>**注意：**现在，您可以[在体验定位活动中包含推荐](/help/c-recommendations/recommendations-as-an-offer.md)。要使用此功能，您需要拥有[Target Premium 许可证](/help/c-intro/intro.md#premium)。 |
| [自动个性化](/help/c-activities/t-automated-personalization/automated-personalization.md)<br>![Target Premium](/help/assets/premium.png) | 自动个性化 (AP) 可将各种选件或消息进行组合，并且使用先进的机器学习技术，根据每位访客的个人客户配置文件将不同的变体与其匹配，以便个性化内容并促进转化。 |
| [推荐](/help/c-recommendations/recommendations.md)<br>![Target Premium](/help/assets/premium.png) | 推荐可根据网站用户在网站上的活动来确定向该用户推广产品的方式。<br>例如，您可能想要鼓励购买了背包的人也考虑购买登山鞋和登山杖。在这种情况下，您可以使用“购买了这个项目，也购买了那个项目的人”算法，创建一个推荐来显示通常一起购买的项目。或者，您可能想要鼓励访客在您的媒体网站上停留更长的时间，为此，您可以使用“查看了这个项目，也查看了那个项目的人”算法，向访客推荐与其正在观看的视频相似的视频。<br>**注意：**现在，您可以在 A/B 测试（包括自动分配和自动定位）和体验定位 (XT) 活动中包含推荐。请参阅[“推荐”作为选件](/help/c-recommendations/recommendations-as-an-offer.md)。 |

## 位置 {#section_F18FBF1ED23340ED9F39C51971A4E874}

位置主要是指网站上的页面。它也可以指移动设备应用程序、电子邮件中的位置，或是指您运行优化的任何其他位置。

位置对于活动和体验而言是不可或缺的。您可以决定位置是可以执行以下某一操作，还是执行所有两个操作，亦或两个操作都不执行：

* 为访客显示和交换内容。
* 记录访客行为。

在 [!DNL Target Standard] 中，位置可以是页面上的任何元素，但前提是要跟踪的每个页面的 `<head>` 部分中包含一行用于启用 [!DNL Target] 的代码。这一行代码会调用所需的 JavaScript 库，以便收集信息并将定位体验交付给访客。

请参阅 [at.js 的好处](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits)，以详细了解 [!DNL Target Standard] 中的位置实施与 [!DNL Target Classic] 中的 mbox 实施之间的差异。

位置与受众相结合，可提供近乎无限数量的客户定位信息的选项。例如，如果访客以前从未访问过您的网站，您可以向这些新访客显示折扣券。同样，页面也可以更改为向回访客户显示更优化的选件。

您还可以使用位置来跟踪访客在您网站中的访问进度，或跟踪访客是否完成了特定的成功量度（例如将项目添加到购物车或完成购买）。

## 体验和页面设计 {#section_B806FB752EC1470784755C1EB3D4AC70}

体验（有时也称为方法）可定义页面上显示的内容，以及其他页面元素，例如链接。

当满足特定的定位条件时，体验会确定在特定位置显示哪些选件。例如，体验可决定当回访访客访问您的网站时，在页面顶部显示两天免运费优惠信息。体验还可决定当新访客首次访问页面时，在同一位置显示九折优惠信息。

体验包含页面上显示的选件、图像资产或其他 HTML 元素（例如链接），这些元素有助于促进访客采取相应操作以达到您所期望的结果。[!DNL Target] 将位置、选件和体验整合在一起，用于决定在特定测试期间要在您的网站上显示的内容。

体验也可以是一种不同的页面设计。例如，一个体验可能是在页面顶部提供一组链接，而另一个体验则是在相同位置提供不同的链接，或是将相同的链接按不同的顺序进行排列。您可能想要测试某个图像所产生的提升度是否高于另一个图像，或者测试某个广告位于页面顶部时被点击的可能性是否大于其他位置。

[!DNL Target] 可以在您的数字触点中优化每位访客的体验，并对不同的体验进行测试，以确定哪个体验最为成功。通过精心规划的体验定位，您可以确保在页面的适当位置向网站访客显示与其最相关的选件，从而提高成功访问的可能性。

## 选件 {#section_973D4CC4CEB44711BBB9A21BF74B89E9}

选件是在营销活动或活动期间网页上显示的内容。

测试网页时，您可以衡量每个具有不同选件的体验在您的位置的成功度。

一个选件可以包含不同类型的内容，这些内容包括：

* 图像
* 文本
* HTML
* 链接
* 按钮

例如，根据访客之前是否访问过您的网站，网页可能会显示两个选件中的其中一个选件。

An *体验*&#x200B;可决定满足特定条件时所显示的内容。

## 受众{#section_3F32DA46BDF947878DD79DBB97040D01}

可为符合特定标准的活动参加者优化目标内容。

受众定义活动的目标，在可以进行定位的任何位置都可以使用受众。

[!DNL Target] 受众是一组定义的访客标准。可以将选件定位到特定受众（或区段）。将体验定位到受众后，只有属于该受众的访客才能看到该体验。

例如，您可以将活动定位到由使用特定浏览器或操作系统的访客组成的受众。

或者，您可以将活动定位到来自某个地理区域的访客，或通过特定搜索引擎访问您页面的访客。

可以保存受众以供多个活动重复使用，也可以为特定活动创建受众。

| 受众类型 | 描述 |
|--- |--- |
| 可重用受众 | 可以为任何活动选择可重用受众。对某个可重用受众进行更改时，该受众在使用它的所有活动中也会发生相应的更改。 |
| 自定义区段 | 在 Target Classic 中，自定义区段（也称为“特定于营销活动”的区段）专门用于特定的营销活动。它们作为营销活动的一部分被创建，无法在其他营销活动中重复使用。 |
| 共享受众 | 可以在 [!DNL Adobe Experience Cloud] 解决方案之间共享受众。See [Audiences](https://docs.adobe.com/content/help/en/core-services/interface/audiences/audience-library.html) for examples. |

要了解访客配置文件如何跟踪与网站访客相关的信息，请参阅[访客配置文件](../c-target/c-visitor-profile/visitor-profile.md#concept_5E53D1A6DF224D7BAE76F4AE390B9DA1)。

## 培训视频：

以下视频包含有关本文中所讨论概念的详细信息。

### 活动类型(9:03)概 ![述徽章](/help/assets/overview.png)

以下视频介绍了 [!DNL Target Standard/Premium] 中可用的活动类型。

* 介绍 [!DNL Adobe Target] 中包含的活动类型
* 选择相应的活动类型以实现目标
* 介绍适用于所有活动类型的三步引导式工作流

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### 在Adobe Target中使用受众(6:21)概 ![述徽章](/help/assets/overview.png)

以下视频介绍了如何在 [!DNL Target Standard/Premium] 中使用受众。

* 解释术语“受众”
* 介绍使用受众进行优化的两种方式
* 在“受众”列表中查找受众
* 将活动定位到受众
* 在活动中使用受众进行被动报告

>[!VIDEO](https://video.tv.adobe.com/v/17398)
