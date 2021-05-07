---
keywords: Adobe Experience Platform Web SDK;aep web sdk;aep sdk;搜索引擎优化;搜索引擎优化;seo;边缘群集、中心群集;at.js;mbox.js;
description: 了解Adobe [!DNL Target] works, including information about the [!DNL Target] JavaScript库（at.js和AEP Web SDK）、Adobe数据中心和SEO测试。
title: 如何 [!DNL Target] 工作？
feature: 概述
exl-id: 8a93e061-0be7-4ecc-b511-2210094547f2
translation-type: tm+mt
source-git-commit: b673a925bd16c9f786b884dc36fbd7155f26f51c
workflow-type: tm+mt
source-wordcount: '2563'
ht-degree: 97%

---

# Adobe [!DNL Target]的工作方式

了解 [!DNL Adobe Target] 的工作原理，包括关于 [!DNL Adobe Experience Platform Web SDK] 和 JavaScript 库（at.js 和 mbox.js）的信息。本文还介绍可使用 [!DNL Target] 创建的各种活动类型。还可了解 [!DNL Target] 边缘网络、搜索引擎优化 (SEO) 以及 [!DNL Target] 如何检测机器人。

## [!DNL Target] 平台 Web SDK 和 JavaScript 库{#libraries}

[!DNL Target] 使用 [!DNL AEP Web SDK] 或 JavaScript 库与网站集成：

* **Adobe Experience Platform Web SDK：**[AEP Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) 是一个新的客户端 JavaScript 库。AEP Web SDK 使 [!DNL Adobe Experience Cloud] 的客户可通过 [!DNL AEP] 边缘网络与 [!DNL Experience Cloud] 中的各种服务（包括 [!DNL Target]）进行交互。Adobe 建议所有新 [!DNL Target] 客户均实现 [!DNL AEP Web SDK]。
* **at.js：**[at.js 库](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17)是 [!DNL Target] 的一个实现库。使用 at.js 可缩短 Web 实施的页面加载时间，并为单页应用程序提供更好的实施选项。经常更新 at.js 以增加新功能。Adobe 建议所有使用 at.js 的客户都将其实现更新到 [at.js 的最新版本](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)。
* **mbox.js：**[mbox.js 库](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)是 [!DNL Target] 旧版实现库。我们支持 mbox.js 库直到 2021 年 3 月 31 日；但是，将不再有功能更新。

>[!IMPORTANT]
>
>所有客户都应迁移到 [!DNL AEP Web SDK] 或 at.js 的最新版本。有关详细信息，请参阅 [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) 或[从 mbox.js 迁移到 at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA)。

请在您网站上的每个页面上都引用 [!DNL AEP Web SDK] 或 at.js。例如，可将这些库之一添加到您的全局头部。或者，考虑使用 [Adobe Platform Launch](https://experienceleague.adobe.com/docs/launch/using/overview.html?lang=zh-Hans) 实现 [!DNL Target]。

以下资源包含帮助您实现 AEP Web SDK 或 at.js 的详细信息：

* [Adobe Experience Platform Web SDK 扩展](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html?lang=zh-Hans#configure-the-aep-web-sdk-extension)
* [实 [!DNL Target] 施使用Adobe Experience Platform Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)

每次访客请求已针对 [!DNL Target] 优化的页面时，都将一个请求发送到定位系统。该请求有助于确定要向该访客提供什么内容。实时进行此过程。每次加载页面时，系统都提出并履行对内容的请求。内容受营销人员控制的活动和体验的规则约束，并已定位到各个网站访客。其中提供每个网站访客最有可能作出响应、与其交互或最终购买的内容。个性化的内容有助于充分提高响应率、获客率和收入。

在 [!DNL Target] 中，页面上的每个元素都是整个页面单次体验的一部分。每个体验均可在页面上包括多个元素。

向访客显示的内容取决于您创建的活动类型：

### [!UICONTROL A/B 测试]

从您分配给活动的体验中随机选择在基本 A/B 测试中显示的内容。可分配每个体验的流量分配百分比。流量的这种随机分摊导致可能耗费大量初始流量后，百分比才能趋于稳定。例如，如果您创建了两个体验，则会随机选取起始体验。如果流量很少，访客的百分比可能会偏向其中一个体验。随着流量增加，百分比逐渐均衡。

您可以为每个体验指定百分比定位。在这种情况下，会生成随机编号，这个编号用于选择要显示的体验。最终的百分比可能与指定定位不完全匹配，但是流量越多，体验的划分应越接近定位目标。

1. 客户向您的服务器请求一个页面，然后该页面显示在浏览器中。
1. 在客户的浏览器中设置第一方 Cookie 以存储客户行为。
1. 页面调用定位系统。
1. 根据您的活动的规则显示内容。

有关更多信息，请参阅[创建 A/B 测试](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)。

### [!UICONTROL Auto-Allocate（自动分配）]

[!UICONTROL 自动分配在两个或更多体验中找出入选的体验。][!UICONTROL 自动分配自动将更多流量重新分配给入选的体验，这样有助于在测试继续运行和学习的同时提高转化率。]

有关更多信息，请参阅[[!UICONTROL 自动分配]](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)。

### [!UICONTROL 自动定位] (AT)

自动定位使用高级机器学习从多种由营销人员定义的体验中选择表现好的体验。自动定位提供最适合每位访客的体验。体验投放基于个别客户个人资料以及个人资料相似的以往访客的行为。使用自动定位使内容个性化并促进转化。

有关更多信息，请参阅[自动定位](/help/c-activities/auto-target/auto-target-to-optimize.md)。

### [!UICONTROL 自动个性化] (AP)

自动个性化 (AP) 将选件或消息组合在一起，并使用高级机器学习将不同的选件变体与每位访客相配。体验投放基于个别客户个人资料以使内容个性化并促进提升。

有关更多信息，请参阅[自动个性化](/help/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9)。

### [!UICONTROL 体验定位] (XT)

体验定位 (XT) 可根据营销人员定义的一组规则和标准，将内容交付给指定的受众。

体验定位（包括地理定位）对于定义规则以将特定体验或内容定位到特定受众非常有用。可以在活动中定义多个规则，以将不同的内容变体交付到不同的受众。访客在访问您的网站时，体验定位 (XT) 会对其进行评估以判断他们是否符合您所设定的标准。如果他们符合标准，则可以进入活动，并会看到专为符合条件的受众设计的体验。您可以在一个活动中为多个受众创建体验。

有关详细信息，请参阅[体验定位](/help/c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4)。

### [!UICONTROL 多变量测试] (MVT)

多变量测试 (MVT) 比较页面上各元素中选件的不同组合以确定哪个组合对特定受众的表现最好。MVT 有助于找出哪个元素对活动取得成功影响最大。

更多信息，请参阅[多变量测试](/help/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499)。

### [!UICONTROL 推荐]

“推荐”活动可根据以往用户活动或其他算法自动显示客户可能感兴趣的产品或内容。“推荐”有助于将客户导向到他们可能还不知道的相关项目。

有关更多信息，请参阅[推荐](/help/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0)。

## 边缘网络{#concept_0AE2ED8E9DE64288A8B30FCBF1040934}

“边缘”是一种按地理位置分布的服务架构，它确保请求内容的访客无论身在世界各地的何处，均可获得最佳的响应时间。

为了改善响应时间，[!DNL Target] 边缘仅存放活动逻辑、缓存的个人资料和选件信息。

活动和内容数据库、[!DNL Analytics] 数据、API 和营销人团用户界面存放在 Adobe 的中心群集中。然后将更新发送到 [!DNL Target] 边缘。中心群集和边缘群集自动同步以不断更新已缓存的活动数据。所有 1:1 建模也都存储在每个边缘上，因此也可在边缘上处理那些更加复杂的请求。

每个边缘群集都具有响应访问者的内容请求并跟踪该请求的分析数据所需的所有信息。访客请求被路由到最近的边缘群集。

有关更多信息，请参阅[《Adobe Target 安全概述》](https://www.adobe.com/cn/content/dam/cc/en/security/pdfs/AdobeTargetSecurityOverview.pdf)白皮书。

[!DNL Target] 解决方案托管在世界各地的 Adobe 自有和 Adobe 租赁的数据中心内。

中心群集地点包含数据收集中心和数据处理中心。边缘群集地点仅包含数据收集中心。每个报表包均分配给一个特定的数据处理中心。

七个边缘群集中距离最近的那个群集收集客户网站活动数据。这些数据被引向客户预先确定的中心群集目标（以下三个地点之一：俄勒冈、都柏林、新加坡）以供处理。访客个人资料数据存储在距离网站访客最近的边缘群集。边缘群集地点包括中心群集地点以及弗吉尼亚、阿姆斯特丹、悉尼、东京和香港。

距离访客最近的边缘群集处理请求，而非从单个地点响应所有定向请求。此过程有助于减轻穿行网络/Internet 的时间所造成的影响。

![显示不同类型目标服务器的映射](/help/c-intro/assets/target-servers.png)

[!DNL Target] 中心群集，托管在 Amazon Web Services (AWS) 上，其中包括：

* 美国俄勒冈
* 爱尔兰都柏林
* 新加坡共和国

[!DNL Target] 边缘集群，托管在 AWS 上，其中包括：

* 印度孟买
* 日本东京
* 美国弗吉尼亚
* 美国俄勒冈
* 澳大利亚悉尼
* 爱尔兰都柏林
* 新加坡共和国

[!DNL Target Recommendations] 服务托管在俄勒冈的一个 [!DNL Adobe] 数据中心内。

>[!IMPORTANT]
>
>[!DNL Adobe Target] 目前在中国没有边缘群集，因此中国 [!DNL Target] 客户的访客表现仍然受限。由于该国存在防火墙和缺乏边缘群集，因此部署了 [!DNL Target] 的网站的体验可能受影响。体验可能呈现得较慢，并且页面加载可能受影响。此外，营销人员可能在使用 [!DNL Target] 创作 UI 时经历延迟的情况。

如果需要，可将 [!DNL Target] 边缘群集列入允许列表。有关详细信息，请参阅[将 Target 边缘节点列入允许列表](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md)。

## 受保护的用户体验{#concept_40A5E781D90A41E4955F80EA9E5F8F96}

Adobe 确保定位基础设施的可用性和性能尽可能可靠。但是，访客的浏览器与 Adobe 的服务器之间通信中断可能会导致内容投放中断。

为了防止发生服务中断和连接问题，所有地点均设置为包括（由客户端定义的）默认内容。如果用户的浏览器无法连接到 [!DNL Target]，则显示此默认内容。

如果用户的浏览器无法连接服务器，则在定义的超时时间段（默认为 15 秒）内，页面不会发生任何更改。如果达到此超时阈值，则会显示默认位置内容。

Adobe 通过优化和保障性能来保护用户体验。

* Adobe 通过 Adobe 服务级别协议来确保基于行业标准的性能基准。
* 边缘网络确保及时的数据交付。
* Adobe 采用多层方法来保护其应用程序，以便为客户提供最高级别的可用性和可靠性。
* [!DNL Target] 咨询团队可提供实施帮助以及持续的产品支持。

## 搜索引擎优化 (SEO) 友好测试 {#concept_C0C865663CAB4251B66A1F250FD25E6A}

[!DNL Adobe Target] 将遵循搜索引擎准则来进行测试。

Google 提倡用户测试。Google 在其文档中声明，只要遵循特定准则，A/B 和多变量测试就不会影响自然搜索引擎排名。

有关更多信息，请参阅以下 Google 资源：

* [网站测试和 Google 搜索](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)
* [实验和伪装](https://support.google.com/analytics/answer/2576845?hl=en&amp;ref_topic=1745207)

[Google Webmaster Central Blog](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html) 中有篇博文介绍了相关准则。虽然该博文是在 2012 年发布的，但它是 Google 对此问题的最近说明，而且其中的准则仍然适用。

* **无遮蔽**：遮蔽是将一组内容显示给用户，而将一组不同的内容显示给搜索引擎机器人。通过专门识别机器人并有意地向其投喂不同的内容而实现遮蔽。

   [!DNL Target]作为一个平台， 已被配置为采用相同的方式对待搜索引擎机器人和任何用户。因此，如果随机选择机器人，并且机器人可“看到”测试变体，则可在活动中包括这些机器人。

* **使用 rel=&quot;canonical&quot;**：有时必须将 A/B 测试设置为对变体使用不同的 URL。在这些情况下，所有变体都应当包含一个引用了原始（控制）URL 的 `rel="canonical"` 标记。例如，假设 Adobe 正在测试其主页，其中对每个变体使用不同的 URL。主页的以下 canonical 标记将放入每个变体的 `<head>` 标签：

   `<link rel="canonical" href="https://www.adobe.com" />`

* **使用 302（临时）重定向**：在将单独的 URL 用于测试中的变体页面的情况下，Google 建议使用 302 重定向将流量定向到测试变体中。302 重定向告知搜索引擎，该重定向为临时行为，仅在测试运行时有效。

   302 重定向是服务器端重定向，而 [!DNL Target] 和大多数优化提供者都使用客户端功能。因此，重定向是一个 [!DNL Target] 不完全遵循 Google 建议的方面。但是，这种做法仅影响一小部分测试。通过 [!DNL Target] 运行测试的标准方法要求在单个 URL 中更改内容，因此无需重定向。在有些情况下，客户端必须使用多个 URL 表示其测试变体。在这些情况下，[!DNL Target] 使用 JavaScript `window.location` 命令。此命令指示用户测试变体，这样就不会明确表示重定向是 301 还是 302。

   Adobe 不断寻找可行的解决方案以完全遵循搜索引擎准则。对于那些必须使用单独的 URL 进行测试的客户端，Adobe 确信恰当地实现 canonical 标签可减轻与此方法有关的风险。

* **仅运行试验必要时长**：Adobe 认为“必要时长”就是实现统计学意义所需的时间。[!DNL Target][至于如何确定测试何时到达此时间点， 提供了最佳实践](https://docs.adobe.com/content/target-microsite/testcalculator.html)。Adobe 建议将入选测试的硬编码实现并入测试工作流程并分配适当的资源。

   建议不要将使用 [!DNL Target] 平台“发布”入选测试作为永久解决方案。如果在 100% 的时间内为 100% 的用户发布入选测试，则可在完成为入选测试进行硬编码的同时使用此方法。

   考虑您的测试做出了哪些更改也很重要。仅仅更新按钮的颜色或页面上其他次要的非文本项不影响您的自然排名。但是，对文本所做的更改应当进行硬编码。

   此外，还应务必考虑所测试的页面的可访问性。如果搜索引擎无法访问页面，并且页面从未旨在从自然搜索中排名第一，那么上述注意事项均不适用。一个示例是电子邮件营销活动的专用登陆页面。

Google 指出，遵循这些准则“应会使您的测试对您的网站在搜索结果中的排名产生很小影响或不会产生任何影响”。

除了这些准则之外，Google 还在其 Content Experiments 工具的文档中提供了另外一个准则：

* “您的变体页面应保留原始页面的实质性内容。这些变体不应更改原始内容的含义或用户对原始内容的大体理解。”

Google 举例说明“如果某个网站的原始页面加载了与向用户显示的组合无关的关键词，则我们可能会从索引中删除该网站。”

Adobe 认为难以无意中改变测试变体中原始内容的含义。但是，Adobe 建议了解页面上的关键字主题并保持这些主题。对页面内容所做的更改，特别是添加或删除相关的关键词，可能会导致 URL 在自然搜索中的排名发生变化。Adobe 建议与 SEO 合作伙伴合作制定测试协议。

## 机器人 {#bots}

Adobe [!DNL Target] 使用 [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester/) 指标“isRobot”根据在请求标头中传递的用户代理字符串检测已知的机器人。

>[!NOTE]
>
> 对于 [!DNL Server-Side] 请求，在[请求的“Context”节点](https://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API)中传递的值比用户代理字符串优先检测机器人。

仍向被视为机器人生成的流量提供内容。对待机器人如同对待正常用户一样，以确保 [!DNL Target] 符合 SEO 准则。如果按照处理普通用户流量的方法来处理机器人流量，则使用机器人流量可能会使 A/B 测试或个性化算法产生偏差。因此，如果在 [!DNL Target] 活动中检测到已知的机器人，则对待该流量的方式略有不同。删除机器人流量可以更准确地测量用户活动。

具体而言，对于已知的机器人流量，[!DNL Target] 不执行以下操作：

* 创建或检索访客配置文件
* 记录任何配置文件属性或执行配置文件脚本
* 查找 Adobe Audience Manager (AAM) 区段（如果适用）
* 在为Recommendations、自动目标、Automated Personalization或[!UICONTROL 自动分配]活动建模和提供个性化内容时使用机器人流量
* 记录活动访问情况以进行报告
* 记录要发送到 [!DNL Adobe Experience Cloud] 平台的数据
