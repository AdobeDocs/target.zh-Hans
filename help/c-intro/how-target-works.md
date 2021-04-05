---
keywords: Adobe Experience Platform Web SDK;aep web sdk;aep sdk；搜索引擎优化；搜索引擎优化；seo;edge clusters， central clusters;at.js;mbox.js;
description: 了解Adobe Target的工作方式，包括有关目标 JavaScript库（at.js和AEP Web SDK）、Adobe数据中心和SEO测试的信息。
title: 目标的工作原理
feature: 概述
exl-id: 8a93e061-0be7-4ecc-b511-2210094547f2
translation-type: tm+mt
source-git-commit: 73053526e68e08136ab66b9d4c1aa17958cfc76e
workflow-type: tm+mt
source-wordcount: '2574'
ht-degree: 31%

---

# Adobe Target 的工作原理

了解[!DNL Adobe Target]的工作方式，包括有关[!DNL Adobe Experience Platform Web SDK]和JavaScript库（at.js和mbox.js）的信息。 本文还介绍了可以使用[!DNL Target]创建的各种活动类型。 您还可以了解[!DNL Target]边缘网络、搜索引擎优化(SEO)以及[!DNL Target]如何检测机器人程序。

## 目标 Platform Web SDK和JavaScript库{#libraries}

[!DNL Target] 与使用或JavaScript库 [!DNL AEP Web SDK] 的网站集成：

* **Adobe Experience Platform Web SDK:** AEP  [Web ](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) SDK是一个新的客户端JavaScript库。AEP Web SDK允许[!DNL Adobe Experience Cloud]的客户通过[!DNL AEP]边缘网络与[!DNL Experience Cloud]（包括[!DNL Target]）中的各种服务交互。 Adobe建议所有新的[!DNL Target]客户实施[!DNL AEP Web SDK]。
* **at.js:at.** js [库是](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17) 用于的实现库 [!DNL Target]。使用 at.js 可缩短 Web 实施的页面加载时间，并为单页应用程序提供更好的实施选项。at.js经常使用新功能进行更新。 Adobe建议使用at.js的所有客户将其实施更新到at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)的[最新版本。
* **mbox.js:** mbox. [js库](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md) 是旧版实施库 [!DNL Target]。在2021年3月31日之前，支持mbox.js库；但是，将不会有功能更新。

>[!IMPORTANT]
>
>所有客户应迁移到[!DNL AEP Web SDK]或最新版本的at.js。 有关详细信息，请参阅[Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)或[从mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA)迁移到at.js。

在网站的每个页面上引用[!DNL AEP Web SDK]或at.js。 例如，您可以将其中一个库添加到全局标题中。 或者，也可以考虑使用[AdobePlatform launch](https://experienceleague.adobe.com/docs/launch/using/overview.html)实现[!DNL Target]。

以下资源包含帮助您实施AEP Web SDK或at.js的详细信息：

* [Adobe Experience Platform Web SDK扩展](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html?lang=en#configure-the-aep-web-sdk-extension)
* [使用Adobe Experience Platform Launch实施目标](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)

每次访客请求已针对[!DNL Target]优化的页面时，都会向定位系统发送请求。 请求有助于确定为该访客提供哪些内容。 此过程实时发生。 每次加载页面时，系统都会对内容发出请求并满足这些请求。 内容受营销人员控制的活动和体验的规则约束，并已定位到各个网站访客。每个网站访客最可能响应、交互或最终购买内容。 个性化内容有助于最大限度地提高响应率、赢取率和收入。

在[!DNL Target]中，页面上的每个元素都是整个页面单个体验的一部分。 每个体验都可以在页面上包含多个元素。

向访客显示的内容取决于您创建的活动类型：

### A/B 测试

基本A/B测试中显示的内容是从您分配给活动的体验中随机选择的。 您可以为每个体验分配流量分配百分比。 由于流量的随机分割，它可能需要大量初始流量才能使百分比均衡。 例如，如果您创建了两个体验，则会随机选取起始体验。如果流量很少，访客的百分比可能会偏向其中一个体验。随着流量的增加，百分比会相等。

您可以为每个体验指定百分比定位。在这种情况下，会生成随机编号，这个编号用于选择要显示的体验。最终的百分比可能与指定定位不完全匹配，但是流量越多，体验的划分应越接近定位目标。

1. 客户向您的服务器请求一个页面，然后该页面显示在浏览器中。
1. 在客户的浏览器中设置第一方Cookie以存储客户行为。
1. 页面调用定位系统。
1. 根据您的活动的规则显示内容。

有关更多信息，请参阅[创建 A/B 测试](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)。

### 自动分配

“自动分配”可在两种或多种体验中确定优胜者。 “自动分配”会自动将更多流量重新分配给入选体验，这有助于在测试继续运行和学习的同时提高转化率。

有关更多信息，请参阅[自动分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)。

### 自动定位 (AT)

自动目标使用高级机器学习从多个高性能营销人员定义的体验中进行选择。 自动目标为每位访客提供量身定制的体验。 体验投放基于个别客户用户档案和以前具有相似用户档案的访客的行为。 使用自动目标来个性化内容并推动转化。

有关更多信息，请参阅[自动定位](/help/c-activities/auto-target/auto-target-to-optimize.md)。

### 自动个性化 (AP)

Automated Personalization(AP)结合了优惠或消息，并使用高级机器学习将不同的优惠变量与每个访客相匹配。 体验投放基于个人客户用户档案，实现内容个性化并推动提升。

有关更多信息，请参阅[自动个性化](/help/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9)。

### 体验定位 (XT)

体验定位 (XT) 可根据营销人员定义的一组规则和标准，将内容交付给指定的受众。

体验定位（包括地理定位）对于定义规则以将特定体验或内容定位到特定受众非常有用。可以在活动中定义多个规则，以将不同的内容变体交付到不同的受众。访客在访问您的网站时，体验定位 (XT) 会对其进行评估以判断他们是否符合您所设定的标准。如果他们符合标准，则可以进入活动，并会看到专为符合条件的受众设计的体验。您可以在一个活动中为多个受众创建体验。

有关详细信息，请参阅[体验定位](/help/c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4)。

### 多变量测试 (MVT)

Multivariate Testing(MVT)比较页面上元素中的优惠组合，以确定哪种组合最适合特定受众。 MVT可帮助确定最影响活动成功的元素。

更多信息，请参阅[多变量测试](/help/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499)。

### Recommendations

“推荐”活动可根据以往用户活动或其他算法自动显示客户可能感兴趣的产品或内容。“推荐”有助于将客户导向到他们可能还不知道的相关项目。

有关更多信息，请参阅[推荐](/help/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0)。

## 边缘网络{#concept_0AE2ED8E9DE64288A8B30FCBF1040934}

“Edge”是一种地理上分布的服务架构，可确保请求内容的访客的最佳响应时间，而不管他们位于世界各地。

要缩短响应时间，[!DNL Target]边缘仅托管活动逻辑、缓存用户档案和优惠信息。

活动和内容数据库、[!DNL Analytics]数据、API和营销人员用户界面都存放在Adobe的中央群集中。 然后，更新会发送到[!DNL Target]边缘。 Central群集和Edge群集会自动同步以持续更新缓存的活动数据。 所有1:1建模也存储在每个边上，因此这些更复杂的请求也可以在边缘上处理。

每个边缘群集都具有响应访客内容请求和跟踪该请求的分析数据所需的所有信息。 访客请求将路由到最近的边缘群集。

有关更多信息，请参阅[《Adobe Target 安全概述》](https://www.adobe.com/content/dam/cc/en/security/pdfs/AdobeTargetSecurityOverview.pdf)白皮书。

[!DNL Target]解决方案托管于全球Adobe拥有和Adobe租用的数据中心。

中央群集位置同时包含数据收集中心和数据处理中心。 边缘群集位置仅包含数据收集中心。 每个报表包均分配给一个特定的数据处理中心。

客户站点活动数据由七个边缘群集中最接近的群集收集。 此数据将指向客户预定的中央群集目标(以下三个位置之一：（俄勒冈、都柏林、新加坡）。 访客用户档案数据存储在最靠近站点访客的边缘群集上。 边缘群集位置包括中央群集位置和弗吉尼亚、阿姆斯特丹、悉尼、东京和香港。

与响应来自单个位置的所有定位请求不同，请求由最接近访客的边缘群集处理。 此过程有助于减轻网络/Internet旅行时间的影响。

![显示不同类型目标服务器的映射](/help/c-intro/assets/target-servers.png)

[!DNL Target] 托管在Amazon Web Services(AWS)上的Central Clusters包括：

* 美国俄勒冈州
* 爱尔兰都柏林
* 新加坡共和国

[!DNL Target] Edge Clusters，托管在AWS上，包括：

* 印度孟买
* 日本东京
* 美国弗吉尼亚州
* 美国俄勒冈州
* 澳大利亚悉尼
* 爱尔兰都柏林
* 新加坡共和国

[!DNL Target Recommendations]服务托管在俄勒冈州的[!DNL Adobe]数据中心。

>[!IMPORTANT]
>
>[!DNL Adobe Target] 目前，中国没有Edge Cluster，中国客户的访客性能仍 [!DNL Target] 然有限。由于防火墙和国内缺少边缘群集，部署[!DNL Target]的站点的体验可能会受到影响。 体验的渲染速度可能会很慢，页面加载可能会受到影响。 此外，营销人员在使用[!DNL Target]创作UI时可能会遇到延迟。

如果需允许列表要，可以[!DNL Target]边缘群集。 有关详细信息，请参阅[允许列表目标边节点](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md)。

## 受保护的用户体验{#concept_40A5E781D90A41E4955F80EA9E5F8F96}

Adobe 确保定位基础设施的可用性和性能尽可能可靠。但是，访客浏览器与Adobe服务器之间的通信故障可能会导致内容投放中断。

为了防止服务中断和连接问题，所有位置都设置为包括默认内容（由客户端定义）。 如果用户的浏览器无法连接到[!DNL Target]，则显示此默认内容。

如果用户的浏览器无法连接服务器，则在定义的超时时间段（默认为 15 秒）内，页面不会发生任何更改。如果达到此超时阈值，则会显示默认位置内容。

Adobe 通过优化和保障性能来保护用户体验。

* Adobe 通过 Adobe 服务级别协议来确保基于行业标准的性能基准。
* 边缘网络确保及时的数据交付。
* Adobe 采用多层方法来保护其应用程序，以便为客户提供最高级别的可用性和可靠性。
* [!DNL Target] 咨询团队可提供实施帮助以及持续的产品支持。

## 搜索引擎优化 (SEO) 友好测试 {#concept_C0C865663CAB4251B66A1F250FD25E6A}

[!DNL Adobe Target] 将遵循搜索引擎准则来进行测试。

谷歌鼓励用户进行测试。 Google在其文档中称，如果您遵循某些准则，A/B和Multivariate Testing不会损害有机搜索引擎排名。

有关更多信息，请参阅以下 Google 资源：

* [网站测试和 Google 搜索](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)
* [实验和伪装](https://support.google.com/analytics/answer/2576845?hl=en&amp;ref_topic=1745207)

[Google Webmaster Central Blog](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html) 中有篇博文介绍了相关准则。虽然该博文是在 2012 年发布的，但它是 Google 对此问题的最近说明，而且其中的准则仍然适用。

* **不要遮盖**:遮盖功能向用户显示一组内容，向搜索引擎机器人程序显示另一组内容。遮盖通过具体识别机器人并有意地喂给它们不同的内容来实现。

   [!DNL Target]作为一个平台， 已被配置为采用相同的方式对待搜索引擎机器人和任何用户。因此，如果随机选择机器人并“查看”测试变量，则机器人可以包含在活动中。

* **Use rel=&quot;canonical&quot;**:有时，必须使用不同的URL设置A/B测试。在这些情况下，所有变体都应当包含一个引用了原始（控制）URL 的 `rel="canonical"` 标记。例如，假设Adobe正在使用每个变体的不同URL测试其主页。 每个变量的`<head>`标签中将包含以下主页的规范标签：

   `<link rel="canonical" href="https://www.adobe.com" />`

* **使用302（临时）重定向**:在测试中的变体页面使用单独的URL的实例中，Google建议使用302重定向将流量引导至测试变体。302重定向告诉搜索引擎该重定向是临时的，并且仅在测试运行时才处于活动状态。

   302重定向是服务器端重定向，[!DNL Target]与大多数优化提供程序一起使用客户端功能。 因此，重定向是一个[!DNL Target]不完全符合Google建议的区域。 然而，这种做法只影响了一小部分测试。 通过[!DNL Target]运行测试的标准方法调用在单个URL中更改内容，因此无需重定向。 有时客户端必须使用多个URL来表示其测试变量。 在这些情况下，[!DNL Target]使用JavaScript `window.location`命令。 此命令指示用户测试变量，这并不明确表示重定向是301还是302。

   Adobe继续寻找能够完全符合搜索引擎指南的可行解决方案。 对于必须使用单独URL进行测试的客户端，Adobe确信正确实施规范标记能够降低与此方法相关的风险。

* **只要需要，就可以运行实验**:Adobe认为，只要达到统计意义，“只要有必要”。[!DNL Target][至于如何确定测试何时到达此时间点， 提供了最佳实践](https://docs.adobe.com/content/target-microsite/testcalculator.html)。Adobe建议您将入选测试的硬编码实施集成到测试工作流程中并分配相应的资源。

   不建议将[!DNL Target]平台用于“发布”入选测试作为永久解决方案。 如果100%的用户在100%的时间内发布了入选测试，则可在完成对入选测试进行硬编码的过程时使用此方法。

   考虑您的测试做出了哪些更改也很重要。只更新页面上按钮或其他次要非文本项目的颜色不会影响您的自然排名。 但是，对文本所做的更改应当进行硬编码。

   此外，还应务必考虑所测试的页面的可访问性。如果搜索引擎无法访问页面，且最初从未设计为在有机搜索中排名，则上述注意事项均不适用。 例如，电子邮件登陆页的专用活动。

Google 指出，遵循这些准则“应会使您的测试对您的网站在搜索结果中的排名产生很小影响或不会产生任何影响”。

除了这些准则之外，Google 还在其 Content Experiments 工具的文档中提供了另外一个准则：

* “您的变体页面应保留原始页面的实质性内容。这些变体不应更改原始内容的含义或用户对原始内容的大体理解。”

Google 举例说明“如果某个网站的原始页面加载了与向用户显示的组合无关的关键词，则我们可能会从索引中删除该网站。”

Adobe认为，很难在测试变量中无意中更改原始内容的含义。 但是，Adobe建议注意页面上的关键字主题并维护这些主题。 对页面内容所做的更改，特别是添加或删除相关的关键词，可能会导致 URL 在自然搜索中的排名发生变化。Adobe建议您与SEO合作伙伴进行交互，作为测试协议的一部分。

## 机器人 {#bots}

Adobe [!DNL Target]使用[DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester/)量度“isRobot”根据在请求标头中传递的用户代理字符串检测已知机器人程序。

>[!NOTE]
>
> 对于[!DNL Server-Side]请求，在[请求的“Context”节点](https://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API)中传递的值优先于用户代理字符串以进行机器人检测。

标识为由机器人生成的流量仍提供内容。 机器人会像常规用户一样处理，以确保[!DNL Target]符合SEO准则。 如果按照处理普通用户流量的方法来处理机器人流量，则使用机器人流量可能会使 A/B 测试或个性化算法产生偏差。因此，如果在[!DNL Target]活动中检测到已知bot，则对流量的处理会略有不同。 删除机器人流量可以更准确地测量用户活动。

具体而言，对于已知的bot通信[!DNL Target]不：

* 创建或检索访客配置文件
* 记录任何配置文件属性或执行配置文件脚本
* 查找 Adobe Audience Manager (AAM) 区段（如果适用）
* 使用机器人流量为Recommendations、自动目标、Automated Personalization或自动分配活动建模和提供个性化内容
* 记录活动访问情况以进行报告
* 要发送到[!DNL Adobe Experience Cloud]平台的日志数据
