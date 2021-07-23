---
keywords: 欢迎套件;target 欢迎套件;简介;简介;开始使用
description: 纵览 Adobe Target。了解可用的活动、渠道、实现、集成等。
title: 可在何处找到 Target 的概括性介绍？
feature: 概述
exl-id: 19238d4c-b7e1-418d-96e5-c46a3769f7bf
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '2520'
ht-degree: 100%

---

# 第 2 章：Adobe [!DNL Target] 概览

在您开始使用 [!DNL Adobe Target] 之前，大致了解一下该解决方案可能对您有帮助。在本章中，可了解该解决方案的关键功能、可在上面使用它的品牌接触点、实现方式、重要的用户界面功能和工作流程、治理功能及其在整个 [!DNL Adobe Experience Cloud] 中的角色。除非指出本章中的某项为 [!DNL Adobe Target Premium] 功能，否则 [!DNL Adobe Target Premium] 和 [!DNL Adobe Target Standard] 均提供该功能。有关详细信息，请参阅 [Target 简介](/help/c-intro/intro.md)。

## 功能和活动

测试和个性化是 [!DNL Target] 提供的两大类功能，您在 [!DNL Target] 中创建“活动”时可使用这些功能。您可能会看到“测试”与“优化”以及“个性化”与“定位”可互换使用。

在测试活动中，您比较某种数字体验的一个变体与一个或多个其他变体，以找出使最多访客采取期望行动的那个变体。[!DNL Target] 提供以下测试功能：A/B 测试、多变量测试 (MVT) 和自动分配。

通过个性化活动，您投放一种为特定的一组访客或为每个单独的访客量身定制的数字体验。[!DNL Target] 提供这些个性化功能：体验定位、自动定位、自动个性化和推荐。

要更深入地了解何时及如何使用每种功能，请参阅 [Target 活动类型](/help/c-activities/target-activities-guide.md)。

| 活动类型 | 详细信息 |
| --- | --- |
| A/B 测试 | 比较您在网站上或其他数字客户接触点上体验或产品的两个或更多变体，以了解哪个变体在预先指定的测试期间最能改善关键业务措施。A/B 测试适合较大的变动，如新的网页布局、不同的网站导航方法或处理数字体验个别元素（如文案、图像和行动号召按钮）的方式发生重大变化。[了解更多](/help/c-activities/t-test-ab/test-ab.md)。 |
| 自动分配 | 在两个或更多个体验中找出表现最好的体验，并自动将更多流量重新分配给入选者以提高转化率，同时测试继续运行和学习。其中使用由 [!DNL Adobe Sensei] 提供的人工智能。[了解更多](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)。 |
| Auto-Target<br>(Premium) | 利用 [!DNL Target] 中的 Adobe Sensei AI，根据每位访客个别的客户个人资料和以前具有类似个人资料的访客作出的行为，确定若干体验中的最佳体验并提供给访客。自动定位可实现大规模自定义。[了解更多](/help/c-activities/auto-target/auto-target-to-optimize.md)。 |
| 自动个性化<br>(Premium) | 使用由 [!DNL Adobe Sensei] 提供的高级机器学习算法和自动化功能检查产品中的图像、文案和其他元素的各种组合，并根据哪种组合最能实现业务目标（如提高转化率或每位访客的收入）将最佳组合提供给每位访客。[了解更多](/help/c-activities/t-automated-personalization/automated-personalization.md)。 |
| 体验定位 (XT) | 根据用户定义的一组规则和标准将内容交付给特定受众。当您认识到某个受众很重要，并且该受众很了解什么体验与其产生共鸣时，**[!UICONTROL 体验定位]**&#x200B;对于让特定体验或内容锁定特定受众可发挥很大作用。[了解更多](/help/c-activities/t-experience-target/experience-target.md)。 |
| 多变量测试 (MVT) | 比较您的页面或数字体验上元素变体所有可能的组合 - 例如三个不同的背景图像、两个文案变体以及两种不同的按钮颜色。MVT 确定哪个组合对特定受众的表现最好以及哪些元素对结果影响最大。[了解更多](/help/c-activities/c-multivariate-testing/multivariate-testing.md)。 |
| 推荐<br>(Premium) | 使用 Adobe Sensei AI 根据客户以前的活动和其他客户的活动，自动推荐可能让客户感兴趣的产品或内容。[了解更多](/help/c-recommendations/recommendations.md)。 |

## 渠道

几乎可随处使用 [!DNL Target] 测试数字体验并使其个性化 - 不仅是您的网站、移动网站和移动应用程序等传统的数字接触点，还可在信息亭、电子邮件、物联网设备、游戏主机甚至是 Alexa 和 Cortana 等语音助手这样的接触点上。许多公司都开始在其网站上使用 [!DNL Target]。然而，最近的研究表明，人们越来越多地从其移动设备访问各个品牌。优化您的移动渠道现在至关重要。理想情况下，您将访客在您所有接触点上的体验联系起来以投放一种无缝、一致的体验。

| 渠道 | 详细信息 |
| --- | --- |
| 网站 | [!DNL Target] 可用于对您的多页面、单页面应用程序 (SPA) 和移动网站的页面运行 A/B 测试、多变量测试、体验定位、自动分配、自动定位、自动个性化和推荐活动，以提高访客和客户参与程度、提高转化率并增加收入。 |
| 移动 Web | [!DNL Target] 可用于在您的移动网站页面上运行与在您的网站上运行的相同的所有活动类型，以便类似地提高访客和客户参与程度、提高转化率并增加收入。 |
| 移动设备应用程序 | [!DNL Target] 可用于根据用户行为和移动上下文测试移动应用程序体验并使其个性化。[!DNL Target] 让您可通过迭代测试以及体验定位和 AI 驱动的个性化，投放有吸引力并产生转化的交互。要在您的移动应用程序上使用 [!DNL Target]，必须使用 Adobe Mobile Services SDK。 |
| 物联网/各处 | [!DNL Target] 提供一种服务器端实现，以使您可在电子邮件中和缺乏浏览器或不使用 JavaScript 代码的接触点上在活动中使用与您在传统网站、移动网站和移动应用程序上使用的相同的测试和个性化功能。例如，您因此可测试信息亭、机顶盒、游戏主机、语音助手和其他非传统接触点并使其个性化。 |

## 实施

你们中有许多人可能要使用 [!DNL Target] 在多种不同的数字接触点上进行测试和个性化，其中不仅包括传统的 Web 和移动接触点，还包括缺乏浏览器或不使用 JavaScript 代码的接触点。在某些情况下，内部或外部策略要求另设几层控制和安全。出于性能原因，可能还需要在后端服务器上运行一些进程。为了满足这些多种多样的用途，我们让您可按几种不同的方式实现 [!DNL Target]：客户端、服务器端或两者的组合。

| 实现类型 | 详细信息 |
| --- | --- |
| 客户端 | 对于 [!DNL Target] 的这种实现，[!DNL Target] 将与某个活动关联的体验直接提供给客户端浏览器。浏览器将决定要显示的体验，然后显示该体验。对于客户端，可使用所见即所得编辑器&#x200B;**[!UICONTROL 可视体验编辑器]** (VEC) 或非可视界面&#x200B;**[!UICONTROL 基于表格的体验编辑器]**&#x200B;创建您的测试和个性化体验。[了解更多](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)。 |
| 服务器端 | 在此类型的 [!DNL Target] 实现中，客户端设备通过您的服务器提出体验请求，您的服务器将该请求发送给 [!DNL Target]，[!DNL Target] 将响应发回您的服务器，然后您的服务器决定将什么体验提供给客户端设备以供其呈现。体验不一定显示在浏览器中；它能够以电子邮件或网亭形式显示，还可以通过语音助手或者其他一些非可视化体验或不基于浏览器的设备显示。由于您的服务器位于客户端和 [!DNL Target] 之间，因此如果您需要更好地控制体验并提高其安全性，或者您希望在服务器上运行复杂的后端进程，则此类实施是最佳选择。[了解更多](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md)。 |
| 混合实现 | 在此实现中，您选择最适合给定用例的实现方法。例如，您可能会使用客户端实现对主页上巨型横幅中的选件进行 A/B 测试，但还可能会使用服务器端实现确定要在客户端浏览器上显示的内部搜索结果、要在智能汽车仪表板上显示的体验或要从语音助手发出的语音响应。 |

## 活动元素

在 [!DNL Target] 中，可创建个性化活动、优化活动或优化个性化方法的活动。每项活动都有若干关键的元素 - 所测试或个性化的体验或选件、要为其投放体验的受众或个人、按其衡量活动影响的指标以及用视觉方式展现该影响的报表。

| 元素类型 | 详细信息 |
| --- | --- |
| 体验 | 一个页面、整个网页、可能形成购买漏斗的一组页面或一些其他逻辑序列的页面上的一个选件、图像、文本、按钮、视频，以及这些不同元素的组合。它还可以是语音助手的回复、客户服务脚本，甚至是饮料机中提供的独特口味。您可以在 [!DNL Target] 活动中测试或个性化体验。[了解更多](/help/c-experiences/experiences.md)。 |
| 选件 | 一块内容，其中可能包含图像、文本、HTML、链接、视频、行动号召按钮、语音助手响应或任何其他类型的内容。选件可用于打折、免运费等。可在网页上显示选件，但也可在语音助手或游戏主机等任何客户接触点上体验选件。当您测试某个选件时，你衡量它与其他选件或无选件相比是否取得成功。[了解更多](/help/c-experiences/c-manage-content/manage-content.md)。 |
| 受众 | 具有相同特征的人群，例如都是新访客、回访访客或来自中西部的回访访客。通过使用“受众”功能，您可以将不同的内容和体验定位到特定的受众，即在适当的时间向适当的人员展示恰当的信息，从而优化网站营销。如果将访客视为目标受众的一部分，则 [!DNL Target] 根据在活动创建期间定义的标准决定要显示何种体验。[了解更多](/help/c-target/target.md)。 |
| 成功量度 | 使您可确定给定体验或选件在 [!DNL Target] 活动中取得成功的关键业务度量。例如，您可以确定新的选件是否增加了每个访客带来的收入或是否吸引访客向购物车中添加物品。成功量度可用于发现注册、订购或购买漏斗等方面的问题，也可仅仅用于提高访客或客户参与度。[了解更多](/help/c-activities/r-success-metrics/success-metrics.md)。 |
| 报表 | 关于您的活动进展和结果的信息，帮助您根据自身数据作出决策。报表数据可以帮助您确定何时结束测试，向您显示哪个体验或选件已入选，并提供确定后续操作所需的分析或学习数据。[了解更多](/help/c-reports/reports.md)。 |

## 活动创建工具

[!DNL Target] 为您提供三种设置测试和个性化活动的主要方式：[!UICONTROL 可视体验编辑器] (VEC)、[!UICONTROL 基于表格的体验编辑器] 和[!UICONTROL 单页面应用程序 (SPA) 可视体验编辑器]。所有这些方式都指导您在三步中完成活动设置过程 - 定义体验、选择或定义受众并选择按其衡量活动结果的主要和次要成功指标。

| 工具 | 详细信息 |
| --- | --- |
| 可视化体验编辑器 (VEC) | 一个所见即所得界面，从中可轻松地在网站上下文中创建和测试个性化体验和选件。可通过拖放、调换和修改网页（或选件）或移动网页的布局和内容，为 [!DNL Target] 活动创建体验和选件。[了解更多](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md)。 |
| [!UICONTROL 基于表单的体验编辑器] | 一个以非可视方式创建体验和选件的界面，当可视体验编辑器不可用或无法切实可行地使用时，它在创建体验以供用于 A/B 测试、体验定位、自动个性化和推荐活动方面很有用。例如，您可以使用基于表单的编辑器为电子邮件、网亭和语音助手中的交付创建体验和选件。[了解更多](/help/c-experiences/form-experience-composer.md)。 |
| [!UICONTROL 单页应用程序 (SPA) 可视化体验编辑器] | 使用 SPA VEC，营销人员能够以 DIY（自己动手）方式创建测试并对 SPA 上的内容进行个性化，而无需持续依赖开发。VEC 可用于在常用框架（例如 React 和 Angular）上创建 A/B 测试和体验定位 (XT) 活动。[了解更多](/help/c-experiences/spa-visual-experience-composer.md)。 |

## 治理和控制

为了将适当的角色和相关级别的 [!DNL Target] 访问和权限提供给适当的人，我们建立了一个管理控制台。对于 [!UICONTROL Target Premium] 用户，我们通过
[!UICONTROL 企业权限]提供更详细的治理和控制。

| 工具 | 详细信息 |
| --- | --- |
| [!UICONTROL 企业版 Adobe Admin Console] | 从 Adobe Admin Console 将用户添加到 Adobe Target 并分配权限。[了解更多](/help/administrating-target/c-user-management/c-user-management/user-management.md)。 |
| [!UICONTROL 企业权限]<br>(Premium) | 正式管理整个企业中用户访问 [!DNL Target] 的一种方法。将用户添加到 [!DNL Target]、根据其角色分配权限、根据不同部门、全球地点、渠道和其他逻辑分组为团队创建工作区。可为用户分配观察者、编辑者、发布者或审批者的角色。[了解更多](/help/administrating-target/c-user-management/property-channel/property-channel.md)。 |

## 集成

[!DNL Target] 可与第一方、第二方和第三方系统集成。这些
集成对于让您可访问这些系统产生的用于创建受众以供测试和个性化的访客和客户数据可发挥很大作用。作为 [!DNL Adobe Experience Cloud] 的一部分，[!DNL Target] 与 [!DNL Experience Cloud] 解决方案及其核心服务紧密集成。

| 集成 | 详细信息 |
| --- | --- |
| Adobe Experience Cloud | [!DNL Target] 将多种功能嵌入其他 [!DNL Adobe Experience Cloud] 解决方案以大规模地使体验个性化。可将 [!DNL Target] 的强大功能与 [Adobe Analytics](/help/c-integrating-target-with-mac/a4t/a4t.md)、[Experience Cloud Audiences](/help/c-integrating-target-with-mac/mmp.md)、[Adobe Campaign](/help/c-integrating-target-with-mac/campaign-and-target.md)、[Adobe Audience Manager](/help/c-integrating-target-with-mac/audience-manager-target-integration.md) (AAM) 和 [Adobe Experience Manager](/help/c-experiences/c-manage-content/aem-experience-fragments.md) (AEM) 相结合。 |
| Target API (Premium) | [!UICONTROL Target] 提供 40 多种 API，可使用它们将 Adobe Target 与第一方、第二方和第三方系统集成。[了解更多](/help/api/api-overview.md)。 |

## 请牢记

在我们进入下一章“形成您的测试和个性化想法”之前，请考虑以下各种想法。

### 优化的最佳实践

* **良好的策略**：我们的目标和假设是什么？二者是否相符？例如，我们希望提高贷款申请提交量，于是我们假设减少申请表中字段的数量可做到这一点。
* **严谨的方法**：我们是否在适当的地方开始测试？例如，需要这些地点具有充足的流量并影响对业务要紧的指标。
* **适当的设置**：我们的活动是否设置为实现我们的目标？例如，如果我们尝试提高贷款申请提交量，那么我们应锁定有意贷款的人，并衡量“提交”按钮的点击量。
* **深入的分析**：测试活动是否运行到结束？结果怎样？运行您的活动，直至其达到 95% 至 99% 的统计置信度。记载您认为入选的体验之所以入选的原因，并将学识应用于别处。
* **迭代测试**：我们是否延续以往活动的经验教训？如果您找到入选的策略，请尝试改进它或作出适合它的更改以进一步提高您的成功指标。

### 可能对您的结果产生负面影响的意见

* 可能对您的效率产生负面影响的意见。最高薪人士的意见 (HIPPO)、态度、偏见。例如，CEO 想要缩小搜索框以在每个页面上腾出更多空间。我们应进行测试以确保这样做不会减少搜索次数。
* 您是否根据意见开展行动？我不喜欢这个测试的方式。客户根本不会喜欢这种体验。虽然直觉很有帮助，但 A/B 测试一再证明它并不总是准确无误。
* 另外，您是否拥有优化的思维模式？我很想看看哪种体验入选。我们是否拥有足够多的选项可供测试？

### 也可能对结果产生负面影响的假设

* 可能对您的效率产生负面影响的假设。从众心理（这是指我们竞争对手的行为方式）。例如，我们的所有竞争对手都使用巨型横幅配合轮换的图像，所以我们也应该这样做。
* 假设我们了解某件事正常或不正常的原因。假设我们不需要测试某些东西。例如，我们总是将从最高价到最低价的顺序列出酒店房间作为默认情况。
* 您是否根据假设开展行动？我们不需要测试，我们已经检查过 Analytics。（没错，但 Story 揭示的信息可能比 Analytics 揭示的更多）。
* 另外，您是否拥有优化的思维模式？我们测试一切。
