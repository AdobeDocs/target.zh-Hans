---
keywords: 故障诊断;常见问题解答;FAQ;推荐;特殊字符;属性权重;内容相似度
description: 查看有关 [!DNL Target Recommendations] 活动的常见问题和答案的列表。
title: 可在何处找到关于 [!DNL Recommendations]的问答？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: aaa52923-1c2d-44ae-bd89-671329222077
source-git-commit: 18f6c06aa06e9526ee65bd3cc0f9b552c91c10e7
workflow-type: tm+mt
source-wordcount: '3444'
ht-degree: 83%

---

# “推荐”常见问题解答

关于 [!DNL Adobe Target] [!DNL Recommendations] 活动的常见问题 (FAQ) 的列表。

## 通过API创建的[!DNL Recommendations]对象是否显示在[!DNL Target] UI中？

是，通过API创建的[!UICONTROL Recommendations]对象（[!UICONTROL Criteria]、[!UICONTROL Designs]、[!UICONTROL Collections]和[!UICONTROL Exclusions]）在UI中可用，可以通过API或[!DNL Target] UI进行编辑。

## 我是否可以使用[!DNL Target] API管理[!DNL Target]个UI创建的可视化选件？

否. 在[!DNL Target] UI中创建了可视化选件的[!DNL Recommendations]活动无法使用[!DNL Target] API进行管理。 尽管这些活动显示在[!UICONTROL Activities]列表中，但您无法读取或更新它们(使用GET/PUT)。

## 对具有数字值的自定义属性进行搜索时，为什么[!UICONTROL Catalog Search]不显示正确结果？

对具有数字值的自定义属性执行目录搜索时，结果将该自定义属性视为字符串类型，而非数字值。

当前，没有可用的功能允许客户更改属性的类型。要作出改变，请[提出客户问题](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)，其中引用需要将类型从字符串变为数字的属性。

## 对目录中项目的更新耗时多久才能反映在网站上？

此时间范围和结果会有所不同，具体取决于这些项目的更新方式。

| 来源 | 详细信息 |
| --- | --- |
| 通过 mbox 或 API 更新的项目属性 | <ul><li>推荐会在 15 分钟内更新。</li><li>现有推荐和项目属性会一直显示到更新可用时为止。</li><li>目录搜索会在目录索引后更新（3-8 个小时）。</li></ul> |
| 通过信息源更新的项目属性 | <ul><li>推荐会在信息源提取后更新（2-8 个小时）。</li><li>现有推荐和项目属性会一直显示到更新可用时为止。</li><li>目录搜索会在信息源提取后（2-8 个小时）以及后续目录索引后（3-8 个小时）更新。目录搜索会在 5-16 个小时内更新。</li></ul> |
| 通过 [!DNL Target] UI 或 API 从目录删除的项目 | <ul><li>推荐会在 15 分钟内更新。</li><li>现有推荐和项目属性会一直显示到更新可用时为止。</li><li>目录搜索会在目录索引后更新（3-8 个小时）。</li></ul> |
| 通过 mbox 或 API 添加到目录的项目 | <ul><li>推荐会在算法运行后更新。算法会按计划运行，1-2 天的算法每 12 小时运行一次，7 天以上的算法每 24 小时运行一次。</li><li>现有推荐会一直显示到更新可用时为止（如果添加的项目不是所请求的键）。</li><li>备份推荐会一直显示到更新可用时为止（如果添加的项目是所请求的键）。</li><li>目录搜索会在目录索引后更新（3-8 个小时）。</li></ul> |
| 通过信息源添加到目录的项目 | <ul><li>推荐会在信息源提取后更新（2-8 个小时）。后续算法会按计划运行，1-2 天的算法每 12 小时运行一次，7 天以上的算法每 24 小时运行一次。推荐会在 2-32 个小时内更新。</li><li>现有推荐会一直显示到更新可用时为止（如果添加的项目不是所请求的键）。</li><li>备份推荐会一直显示到更新可用时为止（如果添加的项目是所请求的键）。</li><li>目录搜索会在信息源提取后（2-8 个小时）以及目录索引后（3-8 个小时）更新。目录搜索会在 5-16 个小时内更新。</li></ul> |

导入信息源文件后，或者通过 API 或 mbox 接收实体更新后，将在 60 分钟内反映以下更改：

* 如果某个项目之前已被排除但现在应该添加，该项目将包含在下一次算法运行（12-24 个小时）中。

  出现此情形是因为 [!DNL Target] 会在线和离线应用排除项。如果某个项目是新排除的，会快速应用在线排除项。如果某个项目是新添加的，在线排除项会快速消失，但离线排除项一直到下一次运行算法时才会消失。

* 如果某个项目之前已添加但现在应该排除，则会按照上文讨论的“项目属性已更新...”时间线排除该项目，具体取决于信息源来源（通过 mbox/API 为 15 分钟，通过信息源为 12-24 个小时）。

在下一个算法运行后（12-24 小时内），才会反映以下更改：

* 在用于活动的收藏集规则中使用的项目属性。
* 在基于与活动关联的属性或收藏集的促销活动中使用的项目属性。
* 项目在其中显示为“最畅销商品”或“查看次数最多”算法中的“当前类别”或“最喜爱的类别”的项目类别。
* 当更改的属性是用作算法自定义键的自定义属性时的推荐项目排名。
* 当推荐逻辑为“具有相似属性的项目”、使用“内容相似度”加权系数或使用“属性权重”系数时，基于一个或多个更改的属性的推荐项目的排名。

>[!NOTE]
>
>当信息源文件的状态从“正在导入项目”变为“正在准备搜索索引更新”时，信息源文件会被视为已导入。更新可能耗时 60 分钟以上才能反映在目录搜索用户界面中；当信息源状态变为“更新已完成”时，目录搜索即为最新。即使目录搜索并非最新，您的网站也会反映上方所列时间范围内的更新。最新的“目录搜索”索引更新时间将显示在“目录搜索”页面上。

## 对我的[!UICONTROL Recommendations]活动、优惠、促销或标准设置做出的更改需要多久才能反映在我的网站上？

* 对促销设置做出的更改最多需要五个小时才能反映在网站上。
* 对其他标准设置做出的更改到下一次算法运行时才会反映在网站上。

   * 某些标准设置（例如“添加动态包含规则”）会立即得到反映。
   * 其他标准设置（例如“删除动态包含规则”、更改回顾窗口等）直到下一次算法运行才会纳入其中。
   * 算法运行由这些更改触发，但最多需要 24 小时才能完成。算法还按计划运行，每 12-24 小时一次。

## 用户的行为（例如，单击产品A并购买产品B）需要多久才能反映在&#x200B;*用户收到的推荐*&#x200B;中？

* 目前查看/购买过的产品/内容会影响用户在同一次页面浏览/[!DNL Target] 内容请求中收到的推荐。
* 历史用户行为（例如“上次查看过的产品”、“最常查看的产品”）以及总体查看/购买历史记录会与该请求一起更新，并影响用户在下一次页面浏览/[!DNL Target]内容请求中收到的推荐。 例如，“最近查看过的项目”和“为您推荐”算法会随每次产品查看/购买而更新，并反映在后续内容请求中。

## 用户的行为（例如，单击产品A并购买产品B）需要多久才能反映在&#x200B;*其他*&#x200B;用户收到的推荐中？

用户行为汇总会纳入离线算法处理中，每个算法每隔 12-24 个小时运行一次。

## 如果特殊字符破坏了数组，我应该怎么做？ {#section_D27214116EE443638A60887C7D1C534E}

在 JavaScript 中使用转义值。引号 (&quot;) 可能会破坏数组。以下代码片段是一个转义值示例：

```
#set($String='') 
#set($escaper=$String.class.forName('org.apache.commons.lang.StringEscapeUtils')) 
<script type="text/javascript"> 
console.log("$escaper.escapeJavaScript($entity1.name)") 
console.log("$escaper.escapeJavaScript($entity2.name)") 
console.log('$escaper.escapeJavaScript($entity3.name)') 
names.push("$escaper.escapeJavaScript($entity4.name)") 
</script>
```

## 创建“推荐”活动时，为何并不是所有标准（包括自定义标准）都可选择？ {#section_B2265AC8B8A94E0298D495A05C5D817F}

可用的标准依据当前类别而定。在创建推荐产品建议时，算法选取器根据类别 ID 显示标准。

如果要应用标准的位置不包含类别 ID，则算法选择器中不会提供相应的标准。

如果使用 mbox 中存在类别 ID 的位置，则标准选取器包含所有适用的标准。

[!DNL Target]具有[筛选不兼容的标准](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=zh-Hans){target=_blank}设置以控制算法选取器的智能筛选。

>[!NOTE]
>
>此设置仅适用于在[!UICONTROL Visual Experience Composer] (VEC)中创建的活动。 此设置不适用于在基于表单的体验编辑器中创建的活动（[!DNL Target] 没有位置上下文）。

要访问[!UICONTROL Filter Incompatible Criteria]设置，请单击[!UICONTROL Recommendations] > [!UICONTROL Settings]：

![recs_settings_filter图像](assets/recs_settings_filter.png)

如果未启用[!UICONTROL Filter Incompatible Criteria]设置，则[!DNL Target]不会筛选算法选择器中的算法，并且会显示所有算法。

如果[!UICONTROL Filter Incompatible Criteria]设置已启用，则在VEC活动中，[!DNL Target]会从选定的位置中读取实体ID和类别ID，然后根据`currentItem|currentCategory`显示算法（前提是该位置中存在相应的值）。 因此，默认情况下，算法选择器中仅会显示选定位置的兼容算法。

如果启用了[!UICONTROL Filter Incompatible Criteria]设置，您仍可以通过取消选中条件时勾选[!UICONTROL Compatible]复选框来查看不兼容的算法。

![compatible_checkbox图像](assets/compatible_checkbox.png)

以下列表包含[!DNL Target]不显示[!UICONTROL Compatible]复选框的特殊情况：

* 位置中同时存在实体 ID 和类别 ID，在这种情况下将不进行任何筛选。
* 您使用的是 [!DNL mbox.js] 版本 55 或更低版本。
* 未从页面触发任何 mbox 调用 (!config.isAutoCreateGlobalMbox &amp;&amp; !config.isRegionalMbox)
* 未定义 [!DNL Target] 参数。

## 如果“推荐”中的某个收藏集变为零 (0)，我应该怎么做？ {#section_E2DB2FE67CF24EEC81412BFF3FA6385D}

如果您看到某个之前不为零的收藏集变为零，请考虑以下信息：

* 可重新保存该收藏集，然后查看它是否更新数字。通过重新保存，该收藏集重新运行所有使用该收藏集的算法。
* 您所查看的环境是否正确？请转到 [!DNL /target/products.html#recsSettings] 进行复查（如下所示）。

  ![product_catalog图像](assets/product_catalog.png)

* 索引是否为最新？转到[!DNL /target/products.html#productSearch]并检查索引存在了多少个小时（例如，“3小时前编制了索引”）。 如有需要，您可以刷新索引。
* 您是否更改过信息源或数据层，从而导致实体不再匹配收藏集规则？请确保大小写匹配（区分大小写）。
* 信息源是否已成功运行？是否有人更改了 FTP 目录、密码等？
* [!DNL Target]会尽可能在最短的时间内生成交付更新（在客户的页面/应用程序中）。 但是，[!DNL Target] 还必须在 UI 中为营销人员提供某种表现方式。[!DNL Target] 并不推迟投放更新以等待 UI 更新变为同步。您可以使用 [mboxTrace](/help/main/c-activities/c-troubleshooting-activities/content-trouble.md) 来查看收到请求时系统中包含哪些内容。

## 一般的属性权重与特定于内容相似度的属性权重之间有何区别？ {#section_FCD96598CBB44B16A4C6C084649928FF}

属性权重存在两种形式：“标准属性权重”和“内容相似度属性权重”。

“标准属性权重”适用于大部分（如果不是适用于全部）标准类型（不仅仅包括内容相似度）。此类型的权重会赋予某些属性值较高的权重。在以下示例中，输出推荐中增加了耐克产品。

![attribute_weighting_example图像](assets/attribute_weighting_example.png)

“内容相似度属性权重”仅适用于内容相似度标准。

此类权重比较动态，并且基于当前“推荐键”（当前查看的项目）。 在以下示例（品牌x 16）中，如果访客正在查看Nike运动鞋，则更有可能向该访客推荐其他Nike产品（不一定只是运动鞋）而不是竞争对手的运动鞋。 如果访客正在查看阿迪达斯运动鞋，则更有可能为该访客推荐阿迪达斯产品。

![content_similarity_example图像](assets/content_similarity_example.png)

## [!DNL Target] 为何有时无法显示推荐？ {#section_DB3F40673AED42228E407C05437D99E9}

[!DNL Target] 有时无法显示推荐，原因在于可用推荐的数量过低。

为每个标准生成的值的数量是在设计中指定的实体数量的三倍。运行时筛选（例如库存和 mbox 属性匹配）将在生成 3 倍的值后进行应用，因此有可能在交付时最终生成的值不足 3 倍。要缓解此情况，请通过隐藏其他实体而提高设计中的实体数量。

可在设计开始时使用以下 JavaScript 来增加请求实体的数量。在此示例中，请求的实体计数将为 30 (3x10)。

```
#foreach($entity in $entities) 
 #if( $foreach.count > 10 ) 
  #break 
 #end 
 #set ($foo = $entity.id) 
#end 
```

## 用于插入/更新产品的 API 调用的大小限制是多少？我能否使用 API 而不是信息源在一次调用中更新 50,000 个产品？ {#section_434FE1F187B7436AA39B7C14C7895168}

[!DNL Target] 在应用程序级别施加 50 MB 的发布限制；但是，仅在传递 `application/x-www-form-urlencoded` 内容类型标题时施加该限制。

您当然可以尝试在一次调用中发送 50,000 个产品。如果失败，可将其分几批发送。Adobe 建议客户将其调用分解为 5000 或 10000 件产品的批次，以降低因系统负载而导致超时的可能性。

## 在创建推荐标准、促销或模板测试规则时，是否必须指定 mbox 名称？ {#section_FFA42ABCC5954B48A46526E32A3A88A2}

在基于 mbox 参数创建推荐标准、促销活动或模板测试规则时，`mboxParameter` 不再提示您输入 `mboxName`。mbox 名称现在是可选的。通过这项更改，您可以使用多个 mbox 中的参数或引用尚未记录到 Edge 的参数。

要选择所需的参数，请执行以下操作：

* 在创建标准、促销或模板测试规则时，请从列表选择参数名称。开始键入所需参数名称的前几个字符，或键入所需参数名称的全名。
* 如果您记得 mbox 名称而不记得参数名称，则使用复选框筛选传递所需参数的已知 mbox。

无论使用哪种方法，mbox 和参数之间均没有链接。标准、促销或模板测试规则依据参数在所有传递该参数的 mbox 间工作。

如果您编辑现有标准、促销活动或模板测试规则，则会显示筛选标准以及在创建期间提供的 mbox 名称。

## 在定义新受众后，为什么我无法保存旧版“推荐”活动？ {#section_1E47C40B1FE7479BAC3EE0F50CE7C2C4}

确保受众具有唯一的名称。如果您为受众指定了与现有受众相同的名称，则无法保存旧版“推荐”活动（在 2016 年 10 月之前创建的“推荐”活动）。

## 可用于信息源上传的 CSV 文件的最大大小是多少？ {#section_20F1AF4839A447B9889B246D6E873538}

对于上传信息源的 CSV 文件，其行数或文件大小没有硬性限制。但是，作为最佳实践，Adobe 建议将 CSV 文件的大小限制为最大 1 GB，以免在文件上传过程中失败。如果文件大小超过 1 GB，则最好能将其拆分为多个信息源文件。自定义属性列的最大数量为 100，自定义属性限制为 4,096 个字符。可在 [[!DNL Target]  的“限制”页面](/help/main/r-troubleshooting-target/target-limits.md#reference_BEFE60C3AAA442FF94D4EBFB9D3CC9B1)上找到针对所需列长度的其他限制。

## 我可以动态排除实体吗？ {#exclude}

在查询字符串中，您可以传递要从推荐中排除的实体 ID。例如，可排除购物车中已有的商品。

要启用排除功能，请使用 `excludedIds` mbox 参数。此参数指向一个以逗号分隔的实体 ID 列表。例如，`mboxCreate(..., "excludedIds=1,2,3,4,5")`。该值将在请求推荐时发送。

仅对当前 [!DNL Target] 调用执行排除；除非再次传递 `excludedIds` 值，否则后续 [!DNL Target] 调用时不排除项目。要从每页上的推荐都排除购物车中的商品，请继续在每页上都传递 `excludedIds` 值。

>[!NOTE]
>
>如果排除的实体过多，则推荐所表现出的行为就像是没有足够的实体来填充推荐模板。

要排除 `entityIds`，请将 `&excludes=${mbox.excludedIds}` 令牌追加到产品建议内容 URL。在提取了内容 URL 之后，所需参数将使用当前的 mbox 请求参数替代。

默认情况下，新创建的推荐将启用此功能。现有推荐必须进行保存才能支持动态排除的实体。

## 有时在推荐内容跟踪中返回的 NO_CONTENT 响应表示什么意思？

当所请求的算法和键组合无推荐可用时，返回 NO_CONTENT。一般而言，对该算法禁用了备份，并且以下一项或多项也属实时发生此情况：

* 结果尚未准备好。

  一般在首次保存新创建的活动时或在对该活动中使用的收藏集、标准或促销作出配置更改之后发生此情况。

* 所请求的算法/键组合的结果已准备好，但尚未缓存到最近的边缘服务器上。

  该请求发起缓存操作，因此在重新加载几页和/或经过几分钟后，此问题应自行解决。

* 结果已准备好，但所提供的键值无结果可用。

  一般在算法最近运行之后为添加到目录的项目请求推荐时发生此情况，并将在算法下次运行之后自行解决。

* 禁用了部分模板渲染，因此没有足够多的结果可填入模板。

  一般在具有动态包含规则时发生此情况，该规则积极地从可能得出的结果中筛选掉许多项目。为避免发生此情况，请启用备份并且不要将包含规则应用于备份，或者按顺序使用不那么积极筛选的标准。

## 根据最近查看过的项目提供的推荐是否会保留在单个访客的多个设备中？ {#persist-across-devices}

当访客启动会话时，会话 ID 会绑定到一台边缘计算机，并且临时轮廓缓存会存储在这台边缘计算机上。来自同一会话的后续请求会读取此轮廓缓存，包括最近查看过的项目。

会话结束时（通常会在处于非活动状态 30 分钟后终止），会话状态（包括最近查看过的项目）会永久保存到同一地理位置边缘的更多永久轮廓存储中。

然后，来自不同设备的后续会话能够访问这些最近查看过的项目，但前提是新会话通过同一 Marketing Cloud ID (MCID)、Experience Cloud ID (ECID) 或 CustomerID/mbox3rdPartyId 关联到客户轮廓。

如果某位访客同时具有两个活动会话，那么除非强制这些设备共享会话 ID，否则一台设备上最近查看过的项目不会更新另一台设备上最近查看过的项目。这是针对此问题的可能解决方法，但[!DNL Target] 不会直接支持在多个设备上共享会话 ID。客户必须自己管理此 ID 共享。

如果某位访客在一个设备上处于活动状态，然后在几分钟后又在另一台设备上处于活动状态，仍然会发生此行为。第一个设备的会话不会在 30 分钟内过期，并且在将轮廓状态写入永久状态并进行处理之前，最多可能会有五分钟的延迟。测试此行为时，请等待 35 分钟以使会话过期并存储轮廓。

如果该访客并非同时具有两个活动会话，那么只要会话已结束，一台设备上最近查看过的项目就会更新另一台设备上最近查看过的项目。测试此行为时，请等待 35 分钟以使会话过期。

## 我是否可以在 [!DNL Recommendations Premium] 中使用在 [!DNL Adobe Recommendations Classic] 中创建的算法？

[!DNL Recommendations Premium] 不支持 [!DNL Recommendations Classic] 中创建的算法。您或许可以使用 [!DNL Target Premium] 中的旧算法；但是，在 [!DNL Target Premium] UI 中停用或删除活动时，该算法可能会产生同步问题。有关这两种解决方案之间差异的更多信息，请参阅 [!DNL Target Premium][&#128279;](/help/main/c-recommendations/c-recommendations-faq/recommendations-classic-versus-recommendations-activities-target-premium.md)中的[!DNL Recommendations Classic] 与 [!DNL Recommendations] 活动。

## 如何只推荐新文章或视频？ {#recommend-new-articles}

媒体和出版行业中的一些客户希望确保推荐项目仅包含最新的文章或视频。例如，[!DNL Target] 客户使用了以下方法推荐存在时间少于 60 天的文章：

1. 以 YYMMDDD 格式传递文章发布日期作为自定义实体属性。
1. 创建一个日期为今天日期减去60天的配置文件脚本，同样采用YYYYMMDD格式。
1. 在条件中使用动态包含过滤器，以便`publish date > today's date minus 60 days`。

### 传递作为自定义实体属性的发布日期：

| 实体属性 | 示例 |
| --- | --- |
| issueDate | 2021218 |
| lastViewDate | 2021701 |
| parentCategory | 注释 |
| publishDate | 20210113 |
| publishDateDisplay | 2021 年 1 月 13 日 |

### 配置轮廓脚本：

![示例轮廓脚本](/help/main/c-recommendations/c-recommendations-faq/assets/sample-profile-script.png)

### 配置包含规则：

![示例包含规则](/help/main/c-recommendations/c-recommendations-faq/assets/sample-inclusion-rule.png)

>[!NOTE]
>
>此示例还可以使用匹配 `priorDate60` 值并将其作为 mbox 参数进行传递的参数来完成。

### 使用[!DNL Recommendations]活动时出现哪些已知问题？

以下是[!UICONTROL Recommendations]活动的已知问题：

* 当 [!DNL Target] 用 getOffer() 返回 JSON 产品建议时，它返回的是 JSON 类型。但是，如果您返回 JSON 推荐设计，则它返回的是 HTML 类型。
* 60 天未通过信息源或 API 收到更新之后，已到期的实体可正确地到期；但是，在到期后并不从目录搜索的索引中删除已到期的实体。当前也不从目录搜索的索引中删除通过信息源或 API 删除的实体。(IRI-857)
* A/B 活动和体验定位活动中的推荐产品建议不显示推荐栏的可视预览 (TGT-33426)
* 通过 API 创建的推荐活动可在用户界面中查看，但只能通过 API 进行编辑。
* “标准”列表（卡片）视图中显示的“自定义标准”信息源状态每十分钟刷新一次，在极少情况下可能会超过十分钟。在“自定义标准”编辑视图中显示的状态是实时获取的，因此始终为最新。(TGT-35896、TGT-36173)
