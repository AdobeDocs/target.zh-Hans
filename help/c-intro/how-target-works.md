---
keywords: Overview and Reference;SEO;search engine optimization
description: Adobe Target 可通过两个 JavaScript 库（at.js 或 mbox.js）中的任意一个与网站集成
title: Adobe Target 的工作原理
subtopic: Getting Started
topic: Standard
uuid: 01c0072d-f77d-4f14-935b-8633f220db7b
translation-type: tm+mt
source-git-commit: d8cacece5dd29416f5dd025621ce442fbb6a0518
workflow-type: tm+mt
source-wordcount: '2346'
ht-degree: 94%

---


# Adobe Target 的工作原理{#how-adobe-target-works}

有关 Adobe Target 工作方式的信息，其中包括有关 Target JavaScript（at.js 和 mbox.js）以及 Target 中所包含的各种活动类型的信息。

## Target JavaScript 库 {#libraries}

Adobe Target 可通过两个 JavaScript 库（at.js 或 mbox.js）中的任意一个与网站集成

* **at.js：**[at.js 库](../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17)是适用于 Target 的新实施库。使用 at.js 可缩短 Web 实施的页面加载时间，并为单页应用程序提供更好的实施选项。at.js 是推荐使用的实施库，会经常更新功能。我们建议所有客户都实施或迁移到[最新版本的 at.js](../c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)。
* **mbox.js：** mbox.js 库是适用于 Target 的旧版实施库。虽然现在仍支持 mbox.js 库，但是以后不会再提供此库的功能更新。

>[!IMPORTANT]
>
>因此，所有客户都应迁移到 at.js。有关更多信息，请参阅[从 mbox.js 迁移到 at.js](../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA)

您必须在网站的每个页面上引用 Target JavaScript 库文件。例如，您可以将此文件添加到全局标头。或者，请考虑使用 [Adobe Launch 标记管理器](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)

访客每次请求访问已针对 Target 进行优化的页面时，系统都会向定位系统发送请求，以确定要向访客提供哪些内容。此过程是实时进行的——每次加载页面时，系统都会发出内容请求，随后定位系统会处理此请求。内容受营销人员控制的活动和体验的规则约束，并已定位到各个网站访客。提供的内容是每个网站访客最有可能响应、与之交互并最终购买的，以便最大程度地提高响应率、购置率和收入。

在 Target 中，页面上的每个元素都是整个页面的单个体验的一部分。每个体验可包含页面上的多个元素。

向访客显示的内容取决于您创建的活动类型：

### A/B 测试

有关更多信息，请参阅[创建 A/B 测试](../c-activities/t-test-ab/t-test-create-ab/test-create-ab.md#task_68C8079BF9FF4625A3BD6680D554BB72)。

根据您为每个体验选择的百分比，将会从您为活动分配的资产中随机选出要在 A/B 基础测试中显示的内容。由于对流量的这种随机划分，可能会耗用许多初始流量，才能使百分比达到均衡。例如，如果您创建了两个体验，则会随机选取起始体验。如果流量很少，访客的百分比可能会偏向其中一个体验。随着流量增加，百分比应该会更为均等。

您可以为每个体验指定百分比定位。在这种情况下，会生成随机编号，这个编号用于选择要显示的体验。最终的百分比可能与指定定位不完全匹配，但是流量越多，体验的划分应越接近定位目标。

1. 客户向您的服务器请求一个页面，然后该页面显示在浏览器中。
2. 在客户的浏览器中设置第一方 Cookie，以保存该客户的行为。
3. 页面调用定位系统。
4. 根据您的活动的规则显示内容。

### 自动分配

有关更多信息，请参阅[自动分配](../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)。

自动分配可在两个或更多体验中标识一个入选者，并在测试继续运行和学习期间，自动为入选体验重新分配更多流量以提高转化。

### 自动定位 (AT)

有关更多信息，请参阅[自动定位](../c-activities/auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3)。

自动定位可使用先进的机器学习技术从营销人员定义的多个高性能体验中进行选择，并根据每位访客的个人客户配置文件和具有相似配置文件的先前访客的行为，向每位访客提供量身定制的体验，以便个性化内容并促进转化。

### 自动个性化 (AP)

有关更多信息，请参阅[自动个性化](../c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9)。

自动个性化 (AP) 可将各种选件或消息进行组合，并且使用先进的机器学习技术，根据每位访客的个人客户配置文件将不同的选件变体与其匹配，以便个性化内容并促进提升。

### 体验定位 (XT)

[体验定位](../c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4)

体验定位 (XT) 可根据营销人员定义的一组规则和标准，将内容交付给指定的受众。

体验定位（包括地理定位）对于定义规则以将特定体验或内容定位到特定受众非常有用。可以在活动中定义多个规则，以将不同的内容变体交付到不同的受众。访客在访问您的网站时，体验定位 (XT) 会对其进行评估以判断他们是否符合您所设定的标准。如果他们符合标准，则可以进入活动，并会看到专为符合条件的受众设计的体验。您可以在一个活动中为多个受众创建体验。

### 多变量测试 (MVT)

更多信息，请参阅[多变量测试](../c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499)。

多变量测试 (MVT) 可通过比较页面上各元素中的选件组合，来确定哪个组合对特定受众的效果最佳，以及哪个元素对活动成功的影响最大。

### 推荐

有关更多信息，请参阅[推荐](../c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0)。

“推荐”活动可根据以往用户活动或其他算法自动显示客户可能感兴趣的产品或内容。“推荐”有助于将客户导向到他们可能还不知道的相关项目。

## 边缘网络 {#concept_0AE2ED8E9DE64288A8B30FCBF1040934}

“边缘”是分布在各个地理位置的服务架构，不论请求内容的最终用户位于何处，均可确保为这些用户提供最佳响应时间，

为了缩短响应时间，边缘环境仅托管活动逻辑以及缓存的配置文件和选件信息。活动数据库、内容数据库、[!DNL Analytics] 数据、API 以及营销人员用户界面都存储在 Adobe 的中心数据环境中。更新随后被发送到边缘节点。中心环境和边缘节点会自动同步，以持续更新缓存的活动数据。1:1 建模也会存储在每个边缘，因此这些更加复杂的请求也能在边缘上处理。

每个边缘节点均具有响应用户内容请求和针对该请求跟踪分析数据所需的全部信息。用户请求被路由到最近的边缘节点。

![包含核心边缘站点和边缘站点的地图](assets/edge_network.png)

此图像的来源是Adobe [目标安全概述](https://www.adobe.com/content/dam/acom/en/security/pdfs/AdobeTargetSecurityOverview.pdf) 白皮书。

Adobe Target 解决方案托管在全球范围内 Adobe 自有和 Adobe 租用的数据中心上。管理服务器完全托管在位于伦敦、新加坡和美国多个地方（包括俄勒冈和弗吉尼亚）的 Adobe 自有数据中心内。Edge Server托管在位于伦敦、中国香港特别行政区、新加坡、东京和悉尼的Amazon AWS数据中心的Adobe自有和Adobe租赁的服务器上。

管理服务器位置同时包含一个数据收集中心和一个数据处理中心。而其他边缘站点位置则仅包含一个数据收集中心。每个报表包均分配给一个特定的数据处理中心。

从距离访客最近的边缘环境来处理请求（而不是从一处位置响应所有定位请求）可以降低网络/Internet 传输时间的影响。

>[!IMPORTANT]
>
>[!DNL Adobe Target] 目前在中国没有边缘网络，因此，对于中国的 [!DNL Target] 客户，其最终用户性能将继续受限。Because of the firewall and the lack of Edge nodes within the country, the experiences of sites with [!DNL Target] deployed will be slow to render and page loads will be affected. Also, marketers might experience latency when using the [!DNL Target] authoring UI.

如果需要，可以允许列出目标边注释。 有关详细信息，请参 [阅allowlist目标边节点](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md)。

## 受保护的用户体验 {#concept_40A5E781D90A41E4955F80EA9E5F8F96}

Adobe 确保定位基础设施的可用性和性能尽可能可靠。但是，最终用户浏览器与 Adobe 服务器之间的通信划分可能会导致内容交付中断。

为了避免出现服务中断和连接问题，所有位置都设置为包含默认内容（由客户端定义），当用户的浏览器无法连接到 [!DNL Target] 时，将会显示默认内容。

如果用户的浏览器无法连接服务器，则在定义的超时时间段（默认为 15 秒）内，页面不会发生任何更改。如果达到此超时阈值，则会显示默认位置内容。

Adobe 通过优化和保障性能来保护用户体验。

* Adobe 通过 Adobe 服务级别协议来确保基于行业标准的性能基准。
* 边缘网络确保及时的数据交付。
* Adobe 采用多层方法来保护其应用程序，以便为客户提供最高级别的可用性和可靠性。
* [!DNL Target] 咨询团队可提供实施帮助以及持续的产品支持。

## 搜索引擎优化 (SEO) 友好测试 {#concept_C0C865663CAB4251B66A1F250FD25E6A}

[!DNL Adobe Target] 将遵循搜索引擎准则来进行测试。

Google 鼓励用户进行测试，并在其文档中指出只要遵循一些简单的准则，A/B 测试和多变量测试便不会对自然搜索引擎排名造成任何不利影响。

有关更多信息，请参阅以下 Google 资源：

* [网站测试和 Google 搜索](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)
* [实验和伪装](https://support.google.com/analytics/answer/2576845?hl=en&amp;ref_topic=1745207)

[Google Webmaster Central Blog](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html) 中有篇博文介绍了相关准则。虽然该博文是在 2012 年发布的，但它是 Google 对此问题的最近说明，而且其中的准则仍然适用。

* **无伪装** - 伪装是指向用户显示一组内容，而向搜索引擎机器人显示另一组内容（使用特定方式来识别搜索引擎机器人，并有意向其提供不同的内容）。

   作为一个平台，Target 已被配置为采用相同的方式对待搜索引擎机器人和任何用户。这意味着如果随机选择的话，搜索引擎机器人也可能会包含在您运行的测试中，而且会“看到”测试变体。

* **使用 rel=&quot;canonical&quot;** - 有时，设置 A/B 测试时需要对各个变体使用不同的 URL。在这些情况下，所有变体都应当包含一个引用了原始（控制）URL 的 `rel="canonical"` 标记。例如，如果 Adobe 在测试其主页时对每个变体分别使用不同的 URL，则每个变体的 `<head>` 标记中将包含以下主页 canonical 标记：

   `<link rel="canonical" href="https://www.adobe.com" />`

* **使用 302（临时）重定向** - 在某些情况下，测试中的各个变体页面需要使用不同的 URL，为此 Google 建议使用 302 重定向将流量定向到各个测试变体。这样，搜索引擎便可以知晓重定向是临时性的，将只会在测试运行期间处于活动状态。

   302 重定向是一种服务器端重定向，而 Target 及大多数优化服务提供程序使用的是客户端功能。因此，在这方面，Target 并未完全遵循 Google 的建议。但是，这只会对一小部分测试造成影响。通过 Target 运行测试的标准方法要求在单个 URL 中更改内容，因此不需要使用重定向。但在某些情况下，客户需要使用多个 URL 来表示其测试变体。对于这些情况，Target 会使用 JavaScript `window.location` 命令将用户定向到测试变体，此方法不会明确指示使用的是 301 还是 302 重定向。

   虽然我们在不断寻找完全符合搜索引擎准则的可行解决方案，但对于那些在测试中必须使用多个不同的 URL 的客户而言，我们确信正确实施上述 Canonical 标记可以缓解此方法所产生的相关风险。

* **仅将实验运行所需的时间** - 我们认为“所需的时间”是指达到统计意义所需的时间。至于如何确定测试何时到达此时间点，Target [提供了最佳实践](https://docs.adobe.com/content/target-microsite/testcalculator.html)。我们建议您将入选测试的硬编码实施合并到测试工作流中，并分配适当的资源。

   我们不建议将使用 Target 平台“发布”入选测试作为一种永久性解决方案，但如果是在 100% 的时间内向 100% 的用户发布入选测试，则可以在对入选测试进行硬编码的过程完成后使用此方法。

   考虑您的测试做出了哪些更改也很重要。如果只是更新了按钮或页面上其他不基于文本的次要项目的颜色，这不会对您的自然排名产生任何影响。但是，对文本所做的更改应当进行硬编码。

   此外，还应务必考虑所测试的页面的可访问性。如果搜索引擎无法访问页面，而且之前从未将页面设计为在自然搜索排名中占据首位（例如专门用于电子邮件营销活动的登陆页面），则上述考虑事项均不适用。

Google 指出，遵循这些准则“应会使您的测试对您的网站在搜索结果中的排名产生很小影响或不会产生任何影响”。

除了这些准则之外，Google 还在其 Content Experiments 工具的文档中提供了另外一个准则：

* “您的变体页面应保留原始页面的实质性内容。这些变体不应更改原始内容的含义或用户对原始内容的大体理解。”

Google 举例说明“如果某个网站的原始页面加载了与向用户显示的组合无关的关键词，则我们可能会从索引中删除该网站。”

我们认为无意中在测试变体内更改原始内容的含义不太容易发生，但是我们仍建议您注意页面上的关键词主题，并保留这些主题。对页面内容所做的更改，特别是添加或删除相关的关键词，可能会导致 URL 在自然搜索中的排名发生变化。我们建议您与 SEO 合作伙伴协作并将此内容包含在您的测试协议中。

## 机器人 {#bots}

Adobe Target uses [DeviceAtlas](https://deviceatlas.com/) to detect known bots. 被标识为由机器人生成的流量仍会像普通用户生成的流量那样提供内容，以确保其符合 SEO 准则。如果按照处理普通用户流量的方法来处理机器人流量，则使用机器人流量可能会使 A/B 测试或个性化算法产生偏差。因此，如果在 Target 活动中检测到已知机器人，则对流量的处理方式略有不同。删除机器人流量可以更准确地测量用户活动。

具体而言，对于已知机器人流量，Target 不会：

* 创建或检索访客配置文件
* 记录任何配置文件属性或执行配置文件脚本
* 查找 Adobe Audience Manager (AAM) 区段（如果适用）
* 在为“推荐”、自动定位、自动个性化或自动分配活动建模和提供个性化内容时使用机器人流量
* 记录活动访问情况以进行报告
* 记录要发送到 Adobe Experience Cloud 平台的数据
