---
keywords: 故障诊断;常见问题解答;FAQ;推荐;特殊字符;属性权重;内容相似度
description: 查看有关[!DNL Target Recommendations]活动的常见问题和答案的列表。
title: 可在何处找到关于[!DNL Recommendations]的问答？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: aaa52923-1c2d-44ae-bd89-671329222077
TQID: 'https://experienceleague.adobe.com/Hz37Dp21q-25Pj6mmbiaGqONY14eImVB9Ebz8VH9hMA'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '3560'
ht-degree: 10%
---
# “推荐”常见问题解答 {#recommendations-faq}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;查找有关[!DNL Adobe Target] [!DNL Recommendations]活动的常见问题解答。

>[!ENDSHADEBOX]

## 数据和API {#data-and-apis}

+++ 通过API创建的[!DNL Recommendations]对象是否显示在[!DNL Target] UI中？

是. 通过API创建的[!UICONTROL 推荐]对象（**[!UICONTROL 标准]**、**[!UICONTROL 设计]**、**[!UICONTROL 收藏集]**&#x200B;和&#x200B;**[!UICONTROL 排除项]**）在UI中可用，可以通过API或[!DNL Target]用户界面进行编辑。

+++

+++ 能否使用[!DNL Target] API管理在[!DNL Target] UI中创建的可视化选件？

否. 在[!DNL Target] UI中创建的具有可视化选件的[!DNL Recommendations]活动无法使用[!DNL Target] API进行管理。 这些活动显示在&#x200B;**[!UICONTROL 活动]**&#x200B;列表中，但无法读取或更新它们（使用GET或PUT）。

+++

+++ 要插入或更新产品的API调用的大小限制是多少？ 是否可以在一次调用中而不是在馈送中更新50,000个产品？

[!DNL Target]在应用程序级别施加了50 MB的发布限制，但仅当传递`application/x-www-form-urlencoded`内容类型标头时才会施加该限制。

可以尝试一次包含50,000个产品的调用。 如果调用失败，可将其拆分为多个批次。 Adobe建议批量处理5,000或10,000个产品，以降低因系统负载而导致超时的可能性。

+++

+++ 可用于信息源上传的 CSV 文件的最大大小是多少？

对于信息源CSV文件上传，其行数或文件大小没有硬性限制。 作为最佳实践，Adobe建议将CSV文件限制为1 GB，以避免上传期间失败。 超过1 GB的文件最好可以拆分为多个信息源文件。

自定义属性列的最大数量为100，自定义属性限制为4,096个字符。 可在 [[!DNL Target]  的“限制”页面](/help/main/r-troubleshooting-target/target-limits.md)上找到针对所需列长度的其他限制。

+++

+++ 对具有数字值的自定义属性进行搜索时，**[!UICONTROL 目录搜索]**&#x200B;为何不显示正确结果？

对具有数字值的自定义属性执行目录搜索时，结果将该属性视为字符串而非数字值。

目前没有可用的功能允许客户更改属性的类型。 若要进行更改，请[打开一个客户问题](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)，该问题引用其类型必须从字符串更改为数字的属性。

+++

## 更新计时 {#update-timing}

+++ 对目录中项目的更新需要多久才能反映在网站上？

此时间范围和结果会有所不同，具体取决于这些项目的更新方式。

| 更新 | 推荐 | 目录搜索 |
| --- | --- | --- |
| 通过mbox或API更新的项目属性 | 15分钟内 | 在目录索引之后（3-8个小时） |
| 通过信息源更新的项目属性 | 信息源提取后（2-8个小时） | 在信息源摄取（2-8个小时）和后续目录索引（3-8个小时）之后，总共在5-16个小时内完成 |
| 通过[!DNL Target] UI或API从目录中删除项目 | 15分钟内 | 在目录索引之后（3-8个小时） |
| 通过mbox或API添加到目录的项目 | 运行下一个算法后。 算法会按计划运行，1-2天的算法每12小时运行一次，7天以上的算法每24小时运行一次 | 在目录索引之后（3-8个小时） |
| 通过信息源添加到目录的项目 | 在信息源摄取（2-8小时）和后续算法运行后（1-2天的算法每12小时安排一次，7天以上的算法每24小时安排一次），总共在2-32小时内运行 | 在信息源摄取（2-8个小时）和目录索引（3-8个小时）之后，总共在5-16个小时内完成 |

在更新可用之前，将显示以下内容：

* 对于已更新或删除的项目，将显示现有的推荐和项目属性。
* 对于已添加的项目，如果添加的项目不是所请求的键，则会显示现有的推荐。 如果添加的项目是所请求的键，则会显示备用推荐。

导入信息源文件后，或者通过API或mbox收到实体更新后，将在60分钟内反映以下更改：

* 如果某个项目之前已被排除但现在应该添加，该项目将包含在下一次算法运行（12-24小时）中。

  出现此情形是因为 [!DNL Target] 会在线和离线应用排除项。 如果某个项目是新排除的，会快速应用在线排除项。 如果某个项目是新添加的，在线排除项会快速消失，但离线排除项直到下一次运行算法才会消失。

* 如果某个项目之前已添加但现在应该排除，则会根据表中的时间线排除该项目，具体取决于来源：通过mbox或API为15分钟，通过信息源为12-24小时。

在下一个算法运行后（12-24小时内），才会反映以下更改：

* 在活动的收集规则中使用的项目属性。
* 在基于属性或与活动关联的收藏集的促销活动中使用的项目属性。
* 在&#x200B;**[!UICONTROL 最畅销商品]**&#x200B;或&#x200B;**[!UICONTROL 查看次数最多]**&#x200B;算法中，项目显示为“当前类别”或“最喜爱的类别”的项目类别。
* 当更改的属性是用作算法自定义键的自定义属性时，推荐项目的排名。
* 当推荐逻辑为“具有相似属性的项目”或者当使用了“内容相似度”或“属性权重”因子时，基于一个或多个已更改属性的推荐项目排名。

>[!NOTE]
>
>当信息源文件的状态从“正在导入项目”变为“正在准备搜索索引更新”时，信息源文件会被视为已导入。 更新可能需要60分钟以上的时间才能反映在&#x200B;**[!UICONTROL 目录搜索]**&#x200B;用户界面中。 当信息源状态更改为“更新已完成”时，**[!UICONTROL 目录搜索]**&#x200B;是最新的。 即使&#x200B;**[!UICONTROL 目录搜索]**&#x200B;尚未处于最新状态，网站也会反映上方所列时间范围内的更新。 最新的&#x200B;**[!UICONTROL 目录搜索]**&#x200B;索引更新时间显示在&#x200B;**[!UICONTROL 目录搜索]**&#x200B;页面上。

+++

+++ 对[!UICONTROL 推荐]活动、优惠、促销或标准设置所做的更改需要多久才能反映在网站上？

* 对促销设置所做的更改最多可能需要五个小时才能反映在网站上。
* 对其他标准设置做出的更改到下一次算法运行时才会反映在网站上。

  * 某些标准设置（例如添加动态包含规则）会立即得到反映。
  * 其他标准设置，例如删除动态包含规则或更改回顾窗口，直到下一次算法运行才会纳入该设置。
  * 这些更改会触发算法运行，最多可能需要24小时才能完成。 算法还按计划运行，每12-24小时一次。

+++

+++ 用户的行为（例如，单击产品A并购买产品B）需要多久才能反映在该用户收到的推荐中？

* 当前查看或购买的产品或内容会影响用户在同一页面查看或[!DNL Target]内容请求中收到的推荐。
* 历史用户行为（例如“上次查看过的产品”、“查看次数最多的产品”）以及总体查看和购买历史记录会与该请求一起更新。 它会影响用户在下一个页面查看或内容请求中收到的推荐。 例如，**[!UICONTROL 最近查看的项目]**&#x200B;和&#x200B;**[!UICONTROL 为您推荐的项目]**&#x200B;算法会随每次产品查看或购买而更新，并且更新会反映在后续的内容请求中。

+++

+++ 用户的行为需要多久才能反映在其他用户收到的推荐中？

用户的行为汇总会纳入离线算法处理中。 每次运行算法时，即每12-24小时进行一次此处理。

+++

+++ 根据最近查看过的项目提供的推荐是否会保留在单个访客的多个设备中？

当访客启动会话时，会话ID会绑定到一台边缘计算机，并且临时配置文件缓存会存储在这台计算机上。 来自同一会话的后续请求会读取此配置文件缓存，包括最近查看过的项目。

会话结束时（通常会在处于非活动状态30分钟后到期），会话状态（包括最近查看过的项目）会永久保存到同一地理位置边缘的更永久的配置文件存储中。 然后，来自不同设备的后续会话可以访问这些最近查看过的项目，但前提是新会话通过同一Marketing Cloud ID (MCID)、Experience Cloud ID (ECID)或CustomerID或`mbox3rdPartyId`关联到客户个人资料。

如果某位访客同时具有两个活动会话，那么除非强制这些设备共享会话ID，否则一台设备上最近查看过的项目不会更新另一台设备上最近查看过的项目。 存在可能的解决方法，但[!DNL Target]不直接支持在多个设备上共享会话ID。 客户必须管理此ID共享。

当访客在一个设备上处于活动状态并在几分钟后另一个设备上处于活动状态时，也会发生此行为。 第一个设备的会话不会在30分钟内过期，并且在配置文件状态写入永久状态并进行处理之前，最多可能会出现五分钟的延迟。 测试此行为时，请等待35分钟以使会话过期并存储配置文件。

如果访客并非同时具有两个活动会话，那么只要会话已结束，一台设备上最近查看过的项目就会更新另一台设备上最近查看过的项目。 测试此行为时，请等待35分钟以使会话过期。

+++

## 标准、设计和促销 {#criteria-designs-promotions}

+++ 创建[!DNL Recommendations]活动时，为何不是所有条件都可供选择，包括自定义条件？

可用的标准取决于当前类别。 创建推荐选件时，算法选取器根据类别ID显示标准。 如果应用标准的位置不包含类别ID，则算法选择器中不会提供某些标准。 如果使用了mbox中存在类别ID的位置，则标准选取器包含所有适用的标准。

[!DNL Target]具有[筛选不兼容的标准](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank}设置，该设置控制算法选取器的智能筛选。 要访问&#x200B;**[!UICONTROL 筛选不兼容的标准]**&#x200B;设置，请单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 推荐]**。

将“筛选不兼容的标准”选项突出显示的![Recommendations设置页面](assets/recs_settings_filter.png)

* 如果未启用&#x200B;**[!UICONTROL 筛选不兼容的标准]**&#x200B;设置，则[!DNL Target]不会筛选算法选取器中的算法，并且会显示所有算法。
* 如果启用此设置，则在[!UICONTROL 可视化体验编辑器] (VEC)活动中，[!DNL Target]会从所选位置读取实体ID和类别ID。 然后，如果该位置中存在相应的值，则它根据`currentItem|currentCategory`显示算法。 因此，默认情况下，算法选择器中仅显示与所选位置兼容的算法。 通过选择条件时清除&#x200B;**[!UICONTROL 兼容]**&#x200B;复选框，仍可以查看不兼容的算法。

  ![Select的“标准”屏幕中突出显示了兼容复选框](assets/compatible_checkbox.png)

[!DNL Target]在以下特殊情况下不显示&#x200B;**[!UICONTROL 兼容]**&#x200B;复选框：

* 位置中同时存在实体ID和类别ID，因此不会过滤任何内容。
* 已使用[!DNL mbox.js]版本55或更低版本。
* 未从页面(`!config.isAutoCreateGlobalMbox && !config.isRegionalMbox`)触发任何mbox调用。
* 未定义 [!DNL Target] 参数。

>[!NOTE]
>
>**[!UICONTROL 筛选不兼容的标准]**&#x200B;设置仅适用于在[!UICONTROL 可视化体验编辑器] (VEC)中创建的活动。 此设置不适用于在&#x200B;**[!UICONTROL 基于表单的体验编辑器]**&#x200B;中创建的活动，因为[!DNL Target]没有位置上下文。

+++

+++ 一般的属性权重与特定于内容相似度的属性权重之间有何区别？

属性权重存在两种形式：“标准属性权重”和“内容相似度属性权重”。

* “标准属性权重”适用于大多数标准类型，而不仅仅是&#x200B;**[!UICONTROL 内容相似度]**。 此类权重会为某些属性值赋予更大的权重。 在以下示例中，输出推荐中增加了耐克产品。

  ![品牌属性设置为以Nike开头且滑块为25%的“属性权重”部分](assets/attribute_weighting_example.png)

* “内容相似度属性权重”仅适用于&#x200B;**[!UICONTROL 内容相似度]**&#x200B;条件。 此类权重比较动态，并且基于当前“推荐键”（当前查看的项目）。 在以下示例（品牌x 16）中，与竞争对手的运动鞋相比，查看耐克运动鞋的访客更有可能推荐其他Nike产品（不一定只是运动鞋）。 更有可能向查看阿迪达斯运动鞋的访客推荐阿迪达斯产品。

  ![具有品牌属性和权重滑块且位于16x](assets/content_similarity_example.png)的“内容相似度”部分

+++

+++ 创建[!DNL Recommendations]标准、促销或模板测试规则时是否必须指定mbox名称？

根据mbox参数创建[!DNL Recommendations]标准、促销活动或模板测试规则时，`mboxParameter`不再提示`mboxName`。 mbox 名称现在是可选的。 此更改允许使用多个mbox中的参数，或对尚未记录到边缘上的参数的引用。

要选择所需的参数，请使用以下方法之一：

* 在创建标准、促销或模板测试规则时，请从列表选择参数名称。 开始键入参数名称的前几个字符或键入全名。
* 如果mbox名称是已知的，而参数名称不是，请使用该复选框来筛选传递所需参数的已知mbox。

无论使用哪种方法，mbox和参数之间都没有链接。 标准、促销或模板测试规则在所有传递该参数的mbox中根据参数工作。

编辑现有标准、促销活动或模板测试规则时，筛选条件将显示创建期间提供的mbox名称。

+++

+++ 当特殊字符破坏了数组时，可以做些什么？

在 JavaScript 中使用转义值。 引号 (&quot;) 可能会破坏数组。 以下代码片段是一个转义值示例：

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

+++

+++ 是否可以动态排除实体？

是. 要从推荐中排除的实体的实体ID可以在查询字符串中传递。 例如，可以排除购物车中已有的商品。

要启用排除功能，请使用 `excludedIds` mbox 参数。 此参数指向逗号分隔的实体ID列表，例如`mboxCreate(..., "excludedIds=1,2,3,4,5")`。 当请求推荐时会发送该值。

仅对当前[!DNL Target]调用执行排除。 除非再次传递`excludedIds`值，否则后续[!DNL Target]调用时不排除这些项。 要从每个页面的推荐中排除购物车中的商品，请继续在每个页面上传递`excludedIds`值。

要排除`entityIds`，请将`&excludes=${mbox.excludedIds}`令牌附加到选件内容URL。 在提取了内容URL后，所需参数将替换为当前的mbox请求参数。

默认情况下，新创建的推荐将启用此功能。 现有推荐必须进行保存才能支持动态排除的实体。

>[!NOTE]
>
>如果排除的实体过多，则Recommendations所表现出的行为就像是没有足够的实体来填充推荐模板。

+++

+++ 为什么在定义新受众后无法保存旧版[!DNL Recommendations]活动？

确保受众具有唯一的名称。 如果受众与现有受众具有相同的名称，则无法保存旧版[!DNL Recommendations]活动（在2016年10月之前创建的[!DNL Recommendations]活动）。

+++

+++ 在[!DNL Adobe Recommendations Classic]中创建的算法能否在[!DNL Recommendations Premium]中使用？

[!DNL Recommendations Premium] 不支持 [!DNL Recommendations Classic] 中创建的算法。 旧算法可能在[!DNL Target Premium]中可用，但在[!DNL Target Premium] UI中停用或删除活动时，它可能会产生同步问题。 有关这两种解决方案之间差异的更多信息，请参阅 [!DNL Target Premium]&#x200B;[&#128279;](/help/main/c-recommendations/c-recommendations-faq/recommendations-classic-versus-recommendations-activities-target-premium.md)中的[!DNL Recommendations Classic] 与 [!DNL Recommendations] 活动。

+++

+++ 如何只推荐新文章或视频？

媒体和出版业客户通常希望推荐项目仅包含最新的文章或视频。 例如，[!DNL Target]客户使用以下方法推荐存在时间少于60天的文章：

1. 以YYYYMMDD格式传递文章发布日期作为自定义实体属性。 例如：

   | 实体属性 | 示例 |
   | --- | --- |
   | issueDate | 2021218 |
   | lastViewDate | 2021701 |
   | parentCategory | 注释 |
   | publishDate | 20210113 |
   | publishDateDisplay | 2021 年 1 月 13 日 |

1. 创建一个配置文件脚本，该脚本返回今天的日期减去60天，同样采用YYYYMMDD格式。

   ![名为priorDate60的配置文件脚本，描述为YYYYYMMDD格式的今天日期减去60天，该脚本用于计算日期](/help/main/c-recommendations/c-recommendations-faq/assets/sample-profile-script.png)

1. 在条件中使用动态包含规则，以便`publish date > today's date minus 60 days`。

   ![包含规则部分，该部分具有配置文件属性匹配规则，用于将publishDate与user.priorDate60](/help/main/c-recommendations/c-recommendations-faq/assets/sample-inclusion-rule.png)中存储的值进行比较

此示例还可以通过参数匹配来完成，方法是将`priorDate60`值作为mbox参数进行传递。

+++

## 故障排除 {#troubleshooting}

+++ [!DNL Target] 为何有时无法显示推荐？

[!DNL Target]有时无法显示推荐，因为可用推荐的数量过低。

为每个标准生成的值的数量是在设计中指定的实体数量的三倍。 运行时筛选（例如，库存或mbox属性匹配）将在生成3倍的值后进行应用，因此交付时可以保留的值少于3倍。 要缓解此情况，请通过隐藏其他实体而提高设计中的实体数量。

可在设计开始时使用以下 JavaScript 来增加请求实体的数量。 在此示例中，请求的实体计数为30 (3x10)。

```
#foreach($entity in $entities) 
 #if( $foreach.count > 10 ) 
  #break 
 #end 
 #set ($foo = $entity.id) 
#end 
```

+++

+++ 有时在[!DNL Recommendations]内容跟踪中返回的NO_CONTENT响应表示什么意思？

当所请求的算法和键组合无推荐可用时，返回 NO_CONTENT。 此情况通常发生在算法禁用了备份，并且以下一个或多个条件也为true时：

* 结果尚未准备好。

  一般在首次保存新创建的活动时，或者在对该活动中使用的收藏集、标准或促销进行配置更改之后发生此情况。

* 结果已准备好，但尚未缓存到最近的边缘服务器上，以查看所请求的算法和键组合。

  该请求会启动缓存操作，因此在重新加载几页或几分钟后，此问题得到解决。

* 结果已准备好，但所提供的键值无结果可用。

  通常情况下，当请求对最近算法运行之后添加到目录中的项目进行推荐时，会发生此情况。 它会在下一次算法运行后解析。

* 禁用了部分模板渲染，因此没有足够多的结果可填入模板。

  此情况通常发生在动态包含规则中，该规则积极地从可能得出的结果中筛选掉许多项目。 要避免出现这种情况，请启用备份，并且不要将包含规则应用于备份，或者按顺序使用不那么积极筛选的标准。

+++

+++ 当[!DNL Recommendations]中的集合变为零(0)时，应该做什么？

当之前不为零的集合变为零时，请考虑以下事项：

* 重新保存收藏集，并检查号码是否更新。 重新保存会重新运行所有使用该收藏集的算法。
* 检查是否显示了正确的环境。 单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 推荐]**，然后检查&#x200B;**[!UICONTROL 产品目录]**&#x200B;部分中的&#x200B;**[!UICONTROL 默认主机组]**&#x200B;设置。

  “管理”选项卡的![推荐页面，其中的“产品目录”部分突出显示了默认主机组”下拉列表](../assets/reco_faq_1.png)

* 检查索引是否为最新版本。 单击&#x200B;**[!UICONTROL 推荐]** > **[!UICONTROL 目录搜索]**，然后检查索引存在了多少个小时（例如，“已在3小时前编入索引”）。 可以根据需要刷新索引。
* 检查馈送或数据层中的某些内容是否发生了更改，从而导致实体不再匹配收集规则。 确保大小写匹配（规则区分大小写）。
* 检查信息源是否已成功运行，或者是否有人更改了FTP目录、密码等。
* [!DNL Target]会尽快更新投放（在客户页面或应用程序上），并且还必须在UI中为营销人员提供表示法。 [!DNL Target] 并不推迟投放更新以等待 UI 更新变为同步。 使用[mboxTrace](/help/main/c-activities/c-troubleshooting-activities/content-trouble.md)查看请求传入时系统中包含哪些内容。

+++

+++ 为什么&#x200B;**[!UICONTROL 下载数据]**&#x200B;操作在[!DNL Recommendations]活动中失败？

单击[!DNL Recommendations]活动的&#x200B;**[!UICONTROL 活动概述]**&#x200B;页面上的&#x200B;**[!UICONTROL 下载数据]**&#x200B;时，[!DNL Target]用户界面可能显示错误`Error while fetching recommendation data file.`

此错误通常在活动具有非常大的结果集时发生。 生成的CSV超过了单次下载中可以通过用户界面返回的响应大小。 推荐数据本身是完整的。 只有浏览器中的下载路径无法投放该大小的文件。

+++

## 已知问题 {#known-issues}

以下是[!UICONTROL 推荐]活动的已知问题：

* 当[!DNL Target]返回带有`getOffer()`的JSON选件时，它返回JSON类型。 但是，JSON [!DNL Recommendations]设计返回HTML类型。
* 如果通过信息源或API未收到更新，则经过60天后，已到期的实体可正确到期。 但是，过期后不会从&#x200B;**[!UICONTROL 目录搜索]**&#x200B;索引中删除过期的实体。 通过信息源或API删除的实体当前也不会从&#x200B;**[!UICONTROL 目录搜索]**&#x200B;索引中删除。 (IRI-857)
* A/B活动和体验定位活动中的[!DNL Recommendations]选件不显示[!DNL Recommendations]托盘的可视预览。 (TGT-33426)
* 标准列表（卡片）视图中显示的“自定义标准”信息源状态每十分钟刷新一次，在极少情况下可能会超过十分钟。 在“自定义标准”编辑视图中显示的状态是实时获取的，因此始终为最新。 (TGT-35896、TGT-36173)
