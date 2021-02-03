---
keywords: 欢迎套件；目标欢迎套件；介绍；入门
description: Adobe Target欢迎工具包——第二章-目标一览
title: 欢迎工具包——第2章——一览表
feature: Overview
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '2510'
ht-degree: 17%

---


# 第二章：Adobe Target

在开始使用[!DNL Adobe Target]之前，获取解决方案的高级概述可能会很有帮助。 在本章中，了解该解决方案的关键功能、可用于该解决方案的品牌接触点、实施选项、重要的用户界面功能和工作流、管理功能以及它在整体[!DNL Adobe Experience Cloud]中的作用。 除非指明为[!DNL Adobe Target Premium]功能，否则本章中介绍的项目可同时用于[!DNL Adobe Target Premium]和[!DNL Adobe Target Standard]。 有关详细信息，请参阅[目标简介](/help/c-intro/intro.md)。

## 功能和活动

测试和个性化是[!DNL Target]优惠的两种广泛功能，在[!DNL Target]中创建“活动”时可以使用它们。 您可能会看到术语“测试”与“优化”互换使用，而“个性化”与“定位”互换使用。

在测试活动中，您可以将数字体验的一个变体与一个或多个其他变体进行比较，以发现导致最多访客采取所需操作的变体。 [!DNL Target] 优惠以下测试功能：A/B测试、多变量测试(MVT)和自动分配。

通过个性化活动，您可以提供针对特定访客群或各个访客定制的数字体验。 [!DNL Target] 优惠以下个性化功能：体验定位、自动目标、Automated Personalization和Recommendations。

要更深入地了解何时以及如何使用每项功能，请参阅[目标活动类型](/help/c-activities/target-activities-guide.md)。

| 活动类型 | 详细信息 |
| --- | --- |
| A/B 测试 | 在您的网站或其他数字客户接触点上比较两种或两种以上体验或优惠的变体，以了解哪种变体在预先指定的测试期内对关键业务措施的改进程度最高。 A/B测试非常适合进行大型更改，如新网页布局、不同的站点导航方法，或对数字体验中各个元素（如副本、图像和行动动员按钮）进行完全不同的处理。 [了解更多](/help/c-activities/t-test-ab/test-ab.md)。 |
| 自动分配 | 确定两种或两种以上体验中表现最佳的体验，并自动重新分配更多流量给入选方，以在测试继续运行和学习的同时提高转化率。 使用由[!DNL Adobe Sensei]提供支持的人工智能。 [了解更多](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)。 |
| 自动目标<br>（高级） | 利用[!DNL Target]中的Adobe SenseiAI，根据每位访客的用户档案和拥有相似用户档案的先前访客的行为，确定并为每位客户提供最佳体验。 自动目标支持大规模个性化。 [了解更多](/help/c-activities/auto-target/auto-target-to-optimize.md)。 |
| Automated Personalization<br>（高级） | 使用由[!DNL Adobe Sensei]提供支持的高级机器学习算法和自动化功能来检查优惠中图像、副本和其他元素的不同组合，并根据最佳实现业务目标(如提高转化率或每个访客的收入)为每个访客提供最佳组合。 [了解更多](/help/c-activities/t-automated-personalization/automated-personalization.md)。 |
| 体验定位 (XT) | 根据一组用户定义的规则和标准将内容交付到特定受众。 **[!UICONTROL 当您]** 了解受众的价值并且能够充分了解受众与其产生共鸣的体验时，Experience Targeting对于将特定体验或内容定位到特定非常有价值。[了解更多](/help/c-activities/t-experience-target/experience-target.md)。 |
| 多变量测试 (MVT) | 比较页面或数字体验中元素变量的所有可能组合，例如三种不同的背景图像、两种副本变量和两种不同的按钮颜色。 MVT确定哪些组合对特定受众的效果最佳，以及哪些元素对结果的影响最大。 [了解更多](/help/c-activities/c-multivariate-testing/multivariate-testing.md)。 |
| Recommendations<br>（高级） | 使用Adobe Sensei人工智能根据客户先前的活动和其他客户的体验自动推荐可能引起客户兴趣的产品或内容。 [了解更多](/help/c-recommendations/recommendations.md)。 |

## 渠道

您可以使用[!DNL Target]随时随地测试和个性化数字体验——传统数字接触点（如您的网站、移动站点和移动应用程序），也可以在触点(如报亭、电子邮件、物联网设备、游戏机，甚至语音助理(如Alexa和小娜)上进行测试。 许多公司开始在其网站上使用[!DNL Target]。 然而，最近的研究表明，更多人通过移动设备访问品牌。 优化移动渠道现在至关重要。 理想情况下，您可以将访客的体验连接到所有接触点，以提供无缝、一致的体验。

| 渠道 | 详细信息 |
| --- | --- |
| 网站 | [!DNL Target] 可用于在多页、单页应用程序(Multivariate Testing)和移动网站的页面上运行A/B测试、SPA、体验定位、自动分配、自动目标、Automated Personalization和Recommendations活动，以提高访客和客户参与度、提高转化率并增加收入。 |
| 移动Web | [!DNL Target] 可用于运行您在移动网站页面上的网站上运行的所有相同活动类型，以同样提高访客和客户参与度、提高转化率和增加收入。 |
| 移动设备应用程序 | [!DNL Target] 可用于根据用户行为和移动上下文测试和个性化移动App体验。[!DNL Target] 使您能够通过迭代测试、体验定位和基于AI的个性化提供吸引和转化的互动。要在移动应用程序上使用[!DNL Target]，必须使用AdobeMobile Services SDK。 |
| 物联网／无处不在 | [!DNL Target] 优惠是一种服务器端实施，这样您就可以在传统网站、移动站点和移动应用程序中的电子邮件和没有浏览器或不使用JavaScript代码的接触点上使用相同的活动中使用相同的测试和个性化功能。例如，这样您就可以测试和个性化自助终端、机顶盒、游戏控制台、语音助手和其他非传统接触点。 |

## 实施

您中的许多人可能希望使用[!DNL Target]在您的许多不同的数字接触点（包括传统的Web和移动接触点）上测试和个性化，但也希望使用缺少浏览器或未使用JavaScript代码的触点。 在某些情况下，内部或外部策略要求您拥有更高级别的控制和安全性。 由于性能原因，您可能还有需要在后端服务器上运行的进程。 为了满足这种广泛的用途，我们为您提供了以不同方式实现[!DNL Target]的能力：客户端、服务器端或两者的组合。

| 实现类型 | 详细信息 |
| --- | --- |
| 客户端 | 通过此[!DNL Target]实现，[!DNL Target]将与活动相关的体验直接交付到客户端浏览器。 浏览器将决定要显示的体验，然后显示该体验。在客户端，您可以使用WYSIWYG编辑器、**[!UICONTROL 可视体验书写器]**(VEC)或非可视界面（**[!UICONTROL 基于表单的体验书写器]**）创建测试和个性化体验。 [了解更多](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)。 |
| 服务器端 | 在这种类型的[!DNL Target]实现中，客户端设备通过服务器请求体验，服务器将该请求发送到[!DNL Target],[!DNL Target]将响应发回给服务器，服务器将决定将什么体验交付给客户端设备以供其呈现。 体验不一定显示在浏览器中；它能够以电子邮件或网亭形式显示，还可以通过语音助手或者其他一些非可视化体验或不基于浏览器的设备显示。由于您的服务器位于客户端和 [!DNL Target] 之间，因此如果您需要更好地控制体验并提高其安全性，或者您希望在服务器上运行复杂的后端进程，则此类实施是最佳选择。[了解更多](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md)。 |
| 混合实现 | 在此实施中，您选择最适合给定用例的实施方法。 例如，您可以使用客户端实现在主页的英雄横幅中测试优惠，也可以使用服务器端实现来确定要在客户端浏览器中显示的内部搜索结果、在智能汽车仪表板上显示的体验，或通过语音助手发送语音响应。 |

## 活动元素

在[!DNL Target]中，您可以创建个性化活动、优化活动或优化个性化方法的活动。 每个活动都有关键元素，包括您正在测试或个性化的体验或优惠、您向其提供体验的受众或个人、衡量活动影响的指标，以及以可视方式显示影响的报告。

| 元素类型 | 详细信息 |
| --- | --- |
| 体验 | 一个页面、整个网页、可能形成购买漏斗的一组页面或一些其他逻辑序列的页面上的一个选件、图像、文本、按钮、视频，以及这些不同元素的组合。它还可以是语音助手的回复、客户服务脚本，甚至是饮料机中提供的独特口味。您可以在 [!DNL Target] 活动中测试或个性化体验。[了解更多](/help/c-experiences/experiences.md)。 |
| 选件 | 可能包含图像、文本、HTML、链接、视频、行动动员按钮、语音助手响应或任何其他类型内容的内容块。 优惠可以享受折扣、免费送货等。 优惠可以显示在网页上，但也可能在任何客户接触点（如语音助手或游戏控制台）上体验。 测试优惠时，可以与其他优惠或无优惠比较衡量其成功程度。 [了解更多](/help/c-experiences/c-manage-content/manage-content.md)。 |
| 受众 | 具有相同特征的人群，例如都是新访客、回访访客或来自中西部的回访访客。通过使用“受众”功能，您可以将不同的内容和体验定位到特定的受众，即在适当的时间向适当的人员展示恰当的信息，从而优化网站营销。如果访客被标识为目标受众的一部分，[!DNL Target]将根据在活动创建过程中定义的标准确定要显示的体验。 [了解更多](/help/c-target/target.md)。 |
| 成功量度 | 使您能够在[!DNL Target]活动中确定特定体验或优惠是否成功的关键业务度量。 例如，您可以确定新的选件是否增加了每个访客带来的收入或是否吸引访客向购物车中添加物品。成功量度可用于发现注册、订购或购买漏斗等方面的问题，也可仅仅用于提高访客或客户参与度。[了解更多](/help/c-activities/r-success-metrics/success-metrics.md)。 |
| 报表 | 有关活动进度和结果的信息，这些信息可帮助您根据数据做出决策。 报表数据可以帮助您确定何时结束测试，向您显示哪个体验或选件已入选，并提供确定后续操作所需的分析或学习数据。[了解更多](/help/c-reports/reports.md)。 |

## 活动创建工具

[!DNL Target] 为您提供了三种设置测试和个性化活动的主 [!UICONTROL 要方法] :Visual Experience Composer(VEC)、 [!UICONTROL 基于表单的Experience Composer], [!UICONTROL 以及Single Page Application(SPA) Visual Experience Composer]。这两种方法都可指导您通过三个步骤完成活动设置过程：定义体验、选择或定义受众，以及选择主要和次要成功量度，通过它们衡量活动结果。

| 工具 | 详细信息 |
| --- | --- |
| 可视化体验编辑器 (VEC) | WYSIWYG用户界面，可让您轻松创建和测试网站情境中的个性化体验和优惠。 您可以通过拖放、交换和修改网页(或优惠)或移动网页的布局和内容，为[!DNL Target]活动创建体验和优惠。 [了解更多](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md)。 |
| [!UICONTROL 基于表单的体验编辑器] | 一种非可视体验和优惠创建界面，当Visual Experience Composer不可用或无法实际使用时，该界面可用于创建用于A/B测试、体验定位、Automated Personalization和Recommendations活动的体验。 例如，您可以使用基于表单的编辑器为电子邮件、网亭和语音助手中的交付创建体验和选件。[了解更多](/help/c-experiences/form-experience-composer.md)。 |
| [!UICONTROL 单页应用程序 (SPA) 可视化体验编辑器] | 使用 SPA VEC，营销人员能够以 DIY（自己动手）方式创建测试并对 SPA 上的内容进行个性化，而无需持续依赖开发。VEC 可用于在常用框架（例如 React 和 Angular）上创建 A/B 测试和体验定位 (XT) 活动。[了解更多](/help/c-experiences/spa-visual-experience-composer.md)。 |

## 治理和控制

为了向适当的人员提供对[!DNL Target]的适当角色和相关访问级别和权限，我们拥有一个管理控制台。 对于[!UICONTROL 目标Premium]用户，我们优惠更详细的管理和控制
具有[!UICONTROL 企业权限]。

| 工具 | 详细信息 |
| --- | --- |
| [!UICONTROL 企业版 Adobe Admin Console] | 将用户添加到Adobe Target并从Adobe Admin Console分配权限。 [了解更多](/help/administrating-target/c-user-management/c-user-management/user-management.md)。 |
| [!UICONTROL 企业]权限<br>（高级） | 一种正式管理企业用户对[!DNL Target]的访问的方法。 将用户添加到[!DNL Target]，根据其角色分配权限，并根据不同部门、全局位置、渠道和其他逻辑组为团队创建工作区。 您可以为用户分配“观察者”、“编辑者”、“发布者”或“审批者”角色。 [了解更多](/help/administrating-target/c-user-management/property-channel/property-channel.md)。 |

## 集成

[!DNL Target] 可以与许多第一方、第二方和第三方系统集成。这些
集成功能对于您访问这些系统提供的访客和客户数据非常有价值，这些数据可用于创建测试和个性化受众。 作为[!DNL Adobe Experience Cloud]的一部分，[!DNL Target]与[!DNL Experience Cloud]解决方案及其核心服务紧密集成。

| 集成 | 详细信息 |
| --- | --- |
| Adobe Experience Cloud | [!DNL Target] 将嵌入的功能与其他解 [!DNL Adobe Experience Cloud] 决方案相结合，实现大规模个性化体验。将[!DNL Target]和[Adobe Analytics](/help/c-integrating-target-with-mac/a4t/a4t.md)、[Experience Cloud受众](/help/c-integrating-target-with-mac/mmp.md)、[Adobe Campaign](/help/c-integrating-target-with-mac/campaign-and-target.md)、[Adobe Audience Manager](/help/c-integrating-target-with-mac/audience-manager-target-integration.md)(AAM)和[Adobe Experience Manager](/help/c-experiences/c-manage-content/aem-experience-fragments.md)(AEM)的力量结合起来。 |
| 目标API（高级） | [!UICONTROL Targeto] 提供40多个API，可用于将Adobe Target与第一方、第二方和第三方系统集成。[了解更多](/help/api/api-overview.md)。 |

## 记住

在转到下一章之前，请考虑以下想法：“开发测试和个性化创意。”

### 优化的最佳实践

* **好的战略**:我们的目标和假设验证是什么？他们是否一致？ 例如，我们希望增加贷款申请提交，因此我们假设减少申请表单中字段的数量就能实现这一点。
* **有条** 理的方法我们是否开始在正确的位置进行测试？例如，您需要具有足够流量并影响重要指标的位置    生意上。
* **正** 确设置我们的活动是否旨在实现我们的目标？例如，如果我们试图增加贷款申请提交数量，我们应当目标对贷款感兴趣的人，并测量“提交”按钮的点击量。
* **彻底分析**:测试活动是否运行到完成？结果如何？ 运行活动，直到达到95%到99%的统计置信度。 文档您为何认为成功的体验会胜出并将学习应用到其他位置。
* **迭代测试**:我们是在以前活动的学习为基础吗？如果您发现了成功策略，请尝试改进该策略，或进行与其配合的更改以进一步改进您的成功指标。

### 意见可能会对结果产生负面影响

* 可能对您的有效性产生负面影响的意见。 Highest Paid Person’s Oppion(HIPPO)，态度，偏见。 例如， CEO希望缩小搜索框的大小，以在每页上留出更多空间。 我们应进行测试以确保不会减少搜索数量。
* 你是根据意见行事吗？ 我不喜欢测试的样子。 客户根本不喜欢这种体验。 直觉很有用，但A/B测试一再证明它并不总是触手可及。
* 还是你有优化心态？ 我很高兴看到哪种体验能取得成功。 我们是否有足够的选项可进行测试？

### 假设也可能对结果产生负面影响

* 可能对您的有效性产生负面影响的假设。 从众心理(我们的竞争对手就是这样做的)。 例如，所有竞争对手都使用带有旋转图像的英雄横幅，因此我们也应该使用。
* 假设我们知道为什么有东西起作用或无效。 假设我们不需要测试什么。 例如，我们始终以最高到最低价格作为默认列表酒店房间。
* 你是在假设下行事吗？ 我们无需测试，已检查分析。 （是的，但故事可能比分析揭示的要多。）
* 还是你有优化心态？ 我们测试一切。