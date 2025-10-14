---
keywords: Adobe Experience Platform Web SDK;aep web sdk;aep sdk;搜索引擎优化;搜索引擎优化;seo;边缘群集、中心群集;at.js;mbox.js;
description: 了解 [!DNL Adobe Target] 的工作原理，包括有关JavaScript库(AEP Web SDK at.js)、服务器调用使用策略、使用情况、Adobe数据中心、SEO测试和机器人的信息。
title: ' [!DNL Target] 的工作原理'
feature: Overview
exl-id: 8a93e061-0be7-4ecc-b511-2210094547f2
source-git-commit: 85edad5c3adb3a7b01ee6d1eaf2c30c7596d5f92
workflow-type: tm+mt
source-wordcount: '2214'
ht-degree: 24%

---

# [!DNL Adobe Target] 的工作原理

了解[!DNL Adobe Target]的工作原理，包括有关JavaScript库（[!DNL Adobe Experience Platform Web SDK]和at.js）的详细信息。 本文还介绍了您可以创建的各种活动类型、[!DNL Target]使用计数策略、[!DNL Target]Edge Network、SEO和机器人检测。

要点包括：

* **JavaScript Libraries**：了解有关[!DNL Target] JavaScript库[!DNL Adobe Experience Platform Web SDK]和at.js的信息。
* **服务器调用使用策略**：了解[!DNL Target]如何计算各种服务器调用，包括端点、单个mbox、批量mbox、执行、预获取和通知调用。
* **Edge Network**：了解[!DNL Target]如何与[!DNL Adobe Experience Platform Edge Network]交互。
* **受保护的用户体验**：了解[!DNL Adobe]如何确保其定位基础结构的可用性和性能。
* **SEO准则**：遵循最佳实践，使[!DNL Target]活动与SEO准则保持一致。
* **机器人流量**：了解Target如何处理机器人流量，以避免测试和个性化算法出现偏差。

## [!DNL Adobe Target] JavaScript 库 {#libraries}

Target使用[!DNL Experience Platform Web SDK]或at.js与网站集成：

* **[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/zh-hans/docs/target-dev/developer/client-side/aep/aep-web-sdk-overview){target=_blank}**：此客户端JavaScript库允许[!DNL Adobe Experience Cloud]客户通过[!DNL Experience Platform Edge Network]与各种服务进行交互。 [!DNL Adobe]建议新[!DNL Target]客户实施[!DNL Experience Platform Web SDK]。
* **[at.js](https://experienceleague.adobe.com/zh-hans/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/how-to-deployatjs){target=_blank}**：此[!DNL Target]实现库可缩短Web实施的页面加载时间，并为单页应用程序提供更好的选项。 经常更新新功能，[!DNL Adobe]建议所有[at.js用户更新到最新版本](https://experienceleague-review.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank}。

>[!NOTE]
>
>mbox.js库是[!DNL Target]的旧版实施，在2021年3月31日之后不再受支持。 升级到[!UICONTROL Experience Platform Web SDK] （首选）或at.js的最新版本。

在网站的每个页面上引用[!UICONTROL Experience Platform Web SDK]或at.js。 例如，将其中一个库添加到您的全局标头。 或者，使用Adobe Experience Platform[中的](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/home){target=_blank}标记实现[!DNL Target]。

以下资源包含帮助您实施 [!DNL Experience Platform Web SDK] 或 at.js 的详细信息：

* [[!DNL Adobe Experience Platform Web SDK] 扩展](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=zh-Hans){target=_blank}
* [使用  [!DNL Adobe Experience Platform] 实施  [!DNL Target] &#x200B;](https://experienceleague.adobe.com/zh-hans/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-using-adobe-launch){target=_blank}

每次访客请求访问针对[!DNL Target]进行优化的页面时，系统都会向定位系统发送实时请求，以确定要提供的内容。 每次加载页面时都会提出并完成此请求，受营销人员控制的活动和体验的约束。 内容针对个别网站访客，可最大限度地提高响应率、客户获取率和收入。 个性化内容有助于确保访客做出响应、与之互动或进行购买。

在[!DNL Target]中，页面上的每个元素都属于单个体验，该体验可以包含多个元素。

显示的内容取决于您创建的活动类型：

### [!UICONTROL A/B Test]

在基本A/B测试中，从分配的体验中随机选择内容。 您可以为每个体验设置流量分配百分比。 起初，流量可能因随机拆分而不均匀分布，但随着流量的增加，其分布会趋于均衡。 例如，对于两种体验，会随机选择起始体验。 低流量可能会使访客百分比向某个体验倾斜，但这种情况会与更多流量相平衡。

指定每个体验的百分比目标。 将生成一个随机数以选择要显示的体验。 虽然生成的百分比可能与目标不完全匹配，但较高的流量会导致与目标目标更接近。

1. 客户向您的服务器请求一个页面，该页面会显示在客户的浏览器中。
1. 在客户的浏览器中设置第一方Cookie以存储其行为。
1. 页面调用定位系统。
1. 将根据活动规则显示内容。

有关更多信息，请参阅[创建 A/B 测试](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)。

### [!UICONTROL Auto-Allocate]

[!UICONTROL Auto-Allocate]在两个或更多选项中标识入选体验。 然后，它会自动为入选者重新分配更多流量，从而随着测试的继续运行和学习而提高转化率。

有关详细信息，请参阅[[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)。

### [!UICONTROL Auto-Target] （在）

[!UICONTROL Auto-Target]利用高级机器学习从多种由营销人员定义的体验中选择表现好的体验。 [!UICONTROL Auto-Target]根据每位访客的个人客户配置文件和具有相似配置文件的先前访客的行为，为每位访客提供量身定制的体验。 使用[!UICONTROL Auto-Target]个性化内容并促进转化。

有关更多信息，请参阅[自动锁定](/help/main/c-activities/auto-target/auto-target-to-optimize.md)。

### [!UICONTROL Automated Personalization] (AP)

[!UICONTROL Automated Personalization] (AP)将选件或消息组合在一起，并使用高级机器学习将不同的变体与每位访客相配。 AP根据个别客户个人资料对内容进行个性化以提高提升度。

有关更多信息，请参阅[自动个性化](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9)。

### [!UICONTROL Experience Targeting] (XT)

[!UICONTROL Experience Targeting] (XT)根据营销人员定义的规则和条件向特定受众提供内容。 包括地理定位在内，XT对于定义规则以将特定体验或内容定位到特定受众非常有用。 可以在活动中设置多个规则，以将不同的内容变体交付到不同的受众。 当访客查看您的网站时，XT会评估访客，以确定他们是否符合标准。 如果他们符合条件，他们将进入活动并查看为其设计的体验。 您可以在一个活动中为多个受众创建体验。

有关更多信息，请参阅[体验定位](/help/main/c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4)。

### [!UICONTROL Multivariate Test] (MVT)

[!UICONTROL Multivariate Testing] (MVT)比较页面元素中的选件组合，以确定哪个组合对特定受众表现最佳。 MVT 有助于找出哪个元素对活动取得成功影响最大。

更多信息，请参阅[多变量测试](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499)。

### [!UICONTROL Recommendations]

[!UICONTROL Recommendations]活动可根据客户先前的活动或其他算法自动显示客户可能感兴趣的产品或内容。 “推荐”有助于将客户导向到他们可能无法通过其他方式发现的相关项目。

有关更多信息，请参阅[推荐](/help/main/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0)。

<!--
## How [!DNL Target] counts server-call usage {#usage}

[!DNL Target] counts only server calls that provide value to customers. The following table shows how [!DNL Target] counts endpoints, single mbox, batch mbox calls, execute, prefetch, and notification calls.

The following information helps you understand the counting strategy used for [!DNL Target] server calls, as shown in the table below:

* **Count Once**: Counts once per API call.
* **Count the Number of mboxes**: Counts the number of mboxes under the array in the payload of a single API call.
* **Ignore**: Is not counted at all.
* **Count the Number of Views (Once)**: Counts the number of views under the array in the payload. In a typical implementation, a view notification has only one view under the notifications array, making this equivalent to counting once in most implementations.

|Endpoint|Fetch type|Options|Counting strategy|
|--- |--- |--- |-- |
|`rest//v1/mbox`|Single|[!UICONTROL execute]|Count once|
|`rest/v2/batchmbox`|Batch|[!UICONTROL execute]|Count the number of mboxes|
||Batch|[!UICONTROL prefetch]|Ignore|
||Batch|[!UICONTROL notifications]|Count the number of mboxes|
|`/ubox/[raw\|image\|page]`|Single|[!UICONTROL execute]|Count once|
|`rest/v1/delivery`<p>`/rest/v1/target-upstream`|Single|[!UICONTROL execute] > [!UICONTROL pageLoad]|Count once|
||Single|[!UICONTROL prefetch] > [!UICONTROL pageLoad]|Ignore|
||Single|[!UICONTROL prefetch] > [!UICONTROL views]|Ignore|
||Batch|[!UICONTROL execute] > [!UICONTROL mboxes]|Count the number of mboxes|
||Batch|[!UICONTROL prefetch] > [!UICONTROL mboxes]|Ignore|
||Batch|[!UICONTROL notifications] > [!UICONTROL views]|Count the number of views (once)|
||Batch|[!UICONTROL notifications] > [!UICONTROL pageLoad]|Count once|
||Batch|[!UICONTROL notifications] > type ([!UICONTROL conversions])|Count once|
||Batch|[!UICONTROL notifications] > [!UICONTROL mboxes]|Count the number of mboxes|

-->

## 边缘网络 {#concept_0AE2ED8E9DE64288A8B30FCBF1040934}

“Edge”是一种按地理位置分布的服务架构，它确保请求内容的访客无论身在何处，均可获得最佳的响应时间。

为了改善响应时间，[!DNL Target] 边缘仅存放活动逻辑、缓存的轮廓和产品建议信息。

活动和内容数据库、[!DNL Analytics]数据、API和营销人团用户界面存放在[!DNL Adobe]中心群集中。 更新将发送到[!DNL Target]边缘，这些边缘会自动与中心群集同步，以不断更新缓存的活动数据。 所有1:1建模也都存储在每个边缘上，允许本地处理复杂的请求。

每个Edge集群都包含响应访客内容请求和跟踪分析数据所需的所有信息。 访客请求被路由到最近的边缘群集。

有关更多信息，请参阅[《Adobe Target 安全概述》](https://www.adobe.com/content/dam/cc/en/security/pdfs/AdobeTargetSecurityOverview.pdf)白皮书。

[!DNL Target]托管在Adobe拥有和Adobe租用的全球数据中心上。

中心群集地点同时容纳数据收集中心和数据处理中心。 Edge群集位置仅包含数据收集中心。 每个报表包均分配给一个特定的数据处理中心。

客户网站活动数据由七个最接近的Edge群集收集。 然后，将此数据定向到预先确定的中心群集目标（俄勒冈、都柏林或新加坡）以供处理。 访客轮廓数据存储在距离网站访客最近的边缘群集。Edge群集地点包括中心群集地点以及弗吉尼亚、孟买、悉尼和东京。

Edge集群处理距离访客最近的请求，而不是从单个位置处理所有定位请求。 此方法可减轻网络和Internet旅行时间的影响。

![显示不同类型的 Target 服务器的地图](/help/main/c-intro/assets/target-servers.png)

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
>[!DNL Target]当前在中国缺少Edge群集，从而限制了该区域[!DNL Target]客户的访客性能。 防火墙和Edge群集的缺失可能会影响站点体验，导致渲染和页面加载时间变慢。 此外，营销人员在使用[!DNL Target]创作UI时可能会遇到延迟问题。

如果需要，可将 [!DNL Target] 边缘群集列入允许列表。有关更多信息，请参阅[将 Target 边缘节点列入允许列表](https://experienceleague.adobe.com/zh-hans/docs/target-dev/developer/implementation/privacy/allowlist-edges){target=_blank}。

## 受保护的用户体验 {#concept_40A5E781D90A41E4955F80EA9E5F8F96}

[!DNL Adobe]确保其定位基础设施的可用性和性能尽可能可靠。 但是，访客的浏览器与[!DNL Adobe]服务器之间的通信中断可能会中断内容交付。

为了防止发生服务中断和连接问题，所有地点均设置为包括（由客户端定义的）默认内容。如果访客的浏览器无法连接到[!DNL Target]，则显示此默认内容。

如果访客的浏览器无法在定义的超时时间段（默认值： 15秒）内连接，则不会对页面进行任何更改。 如果达到此超时阈值，则会显示默认位置内容。

[!DNL Adobe] 通过优化和保障性能来保护用户体验。

* [!DNL Adobe]确保[!UICONTROL Adobe Service Level Agreement]保证的基于行业标准的性能基准。
* 边缘网络确保及时的数据交付。
* [!UICONTROL Adobe]采用多层方法来保护其应用程序，从而为客户提供最高级别的可用性和可靠性。
* [!DNL Target] 咨询团队可提供实施帮助以及持续的产品支持。

## 搜索引擎优化 (SEO) 友好测试 {#concept_C0C865663CAB4251B66A1F250FD25E6A}

[!DNL Adobe Target]与搜索引擎准则保持一致，以进行测试。 [!DNL Google]鼓励用户测试，并声明A/B和[!UICONTROL Multivariate Testing]在遵循某些准则时不会影响自然搜索引擎排名。

[!DNL Adobe Target] 将遵循搜索引擎准则来进行测试。

有关更多信息，请参阅以下 Google 资源：

* [网站测试和 Google 搜索](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)
* [实验和伪装](https://support.google.com/analytics/answer/12979939?hl)


[Google Webmaster Central Blog](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html) 中有篇博文介绍了相关准则。尽管该帖子可追溯到2012年，但它仍是[!DNL Google]关于该问题的最新声明，并且准则仍然适用。

* **无遮蔽**：遮蔽涉及向用户显示一组内容，并通过专门识别搜索引擎机器人并向其提供不同的内容而向其显示另一组内容。

  [!DNL Target]配置为将搜索引擎机器人视为与任何用户相同。 因此，如果随机选择机器人并“看到”测试变体，则可以将机器人包含在活动中。

* **使用rel=&quot;canonical&quot;**：有时A/B测试需要不同的URL才能测试变体。 在这些情况下，所有变体都应当包含引用原始（控制）URL的rel=&quot;canonical&quot;标记。 例如，如果[!DNL Adobe]正在测试其主页，其中对每个变体使用不同的URL，则主页的以下canonical标记应放置在每个变体的`<head>`标记中：

  `<link rel="canonical" href="https://www.adobe.com" />`

* **使用302（临时）重定向**：当测试中的变体页面使用单独的URL时，[!DNL Google]建议使用302重定向将流量定向到测试变体。 302重定向会通知搜索引擎，该重定向是临时的，仅在测试运行时有效。

  302重定向是服务器端重定向，而[!DNL Target]和大多数优化提供程序使用客户端功能。 因此，[!DNL Target]不完全符合[!DNL Google]的重定向建议。 但是，这仅影响一小部分测试。 通过[!DNL Target]运行测试的标准方法涉及更改单个URL中的内容，从而无需重定向。 在测试变体需要多个URL的情况下，[!DNL Target]使用JavaScript `window.location`命令，该命令不会指定重定向是301还是302。

  [!DNL Adobe]正在积极寻找解决方案，以完全遵守搜索引擎准则。 对于需要单独的URL进行测试的客户端，[!DNL Adobe]认为正确实施规范标记可减轻相关风险。

* **仅运行试验必要时长**： [!DNL Adobe]将“必要时长”定义为达到统计显着性所需的时间。 [!DNL Target]提供最佳实践和[!DNL Adobe Target] [样本量计算器](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)来确定您的测试何时达到此点。 [!DNL Adobe]建议将入选测试的硬编码实现并入测试工作流并分配适当的资源。

  不建议使用[!DNL Target]来“发布”入选测试作为永久解决方案。 如果始终为100%的用户发布入选测试，则可以临时使用此方法硬编码入选测试。

  考虑您的测试发生了哪些变化。 次要更新（如按钮颜色）不会影响自然排名。 但是，文本更改应进行硬编码。

  此外，还要考虑您正在测试的页面的辅助功能。 如果搜索引擎无法访问页面，并且页面从未打算在自然搜索中排名，则这些注意事项不适用。 一个示例是电子邮件营销活动的专用登陆页面。

Google 指出，遵循这些准则“应会使您的测试对您的网站在搜索结果中的排名产生很小影响或不会产生任何影响”。

除了这些准则之外，Google 还在其 Content Experiments 工具的文档中提供了另外一个准则：

* “您的变体页面应保留原始页面的实质性内容。这些变体不应更改原始内容的含义或用户对原始内容的大体理解。”

Google 举例说明“如果某个网站的原始页面加载了与向用户显示的组合无关的关键词，则我们可能会从索引中删除该网站。”

[!UICONTROL Adobe]认为难以无意中改变测试变体中原始内容的含义。 但是，[!UICONTROL Adobe]建议了解页面上的关键字主题并保持这些主题。 对页面内容所做的更改，特别是添加或删除相关的关键词，可能会导致 URL 在自然搜索中的排名发生变化。[!DNL Adobe] 建议与 SEO 合作伙伴合作制定测试协议。

## 机器人 {#bots}

[!DNL Target]使用[DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester/)量度“isRobot”根据在请求标头中传递的用户代理字符串检测已知机器人。

>[!NOTE]
>
> 对于 [!DNL Server-Side] 请求，在[请求的“Context”节点](https://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API)中传递的值比用户代理字符串优先检测机器人。

标识为机器人生成的流量仍会提供内容。 机器人被视为常规用户，以确保[!DNL Target]符合SEO准则。 但是，如果按照处理普通用户流量的方式处理，机器人流量可能会扭曲A/B测试或个性化算法。 因此，您[!DNL Target]活动中的已知机器人流量处理方式不同。 删除机器人流量可更准确地衡量用户活动。

对于已知的机器人流量，[!DNL Target]不会：

* 创建或检索访客轮廓
* 记录配置文件属性或执行配置文件脚本
* 查找 [!DNL Adobe Audience Manager] (AAM) 区段（如果适用）
* 使用机器人流量为[!UICONTROL Recommendations]、[!UICONTROL Auto-Target]、[!UICONTROL Automated Personalization]或[!UICONTROL Auto-Allocate]活动建模或提供个性化内容
* 记录活动访问情况以进行报告
* 记录要发送到 [!DNL Adobe Experience Cloud] 平台的数据

对于已知的机器人流量，在使用[!UICONTROL Analytics for Target] (A4T)时，[!DNL Target]不会：

* 发送事件到 [!DNL Analytics]

对于使用`client_side`日志记录时的已知机器人流量，[!DNL Target]不会返回：

* `tnta payload`
