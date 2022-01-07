---
keywords: 环境数据；会话数据；地理数据；设备数据；移动设备数据；属性；配置文件属性；个性化算法；机器学习算法
description: 了解哪些数据Adobe [!DNL Target] 收集并使用以在 [!UICONTROL Automated Personalization] （美联社）和 [!UICONTROL 自动定位] (AT)活动。
title: 收集哪些数据来构建机器学习算法？
feature: Automated Personalization
exl-id: 7114a6d6-4779-471e-9b91-646aa49e102a
source-git-commit: e830bd2de96884b6dd0c1f56b380874e1e1f7c04
workflow-type: tm+mt
source-wordcount: '2114'
ht-degree: 47%

---

# ![PREMIUM](/help/assets/premium.png) 使用的数据 [!DNL Target] 机器学习算法

[!DNL Adobe Target] 自动收集和使用各种数据，以在 [!UICONTROL Automated Personalization] （美联社）和 [!UICONTROL 自动定位] (AT)活动。 当访客进入AP或AT活动时，信息快照会被传递到一组“培训记录”（个性化算法将学习的访客数据）中。

要进一步了解 [!DNL Target] 个性化算法，请参阅 [随机林算法](/help/c-activities/t-automated-personalization/algo-random-forest.md).

## 默认 [!DNL Adobe Target] 属性类别

下表显示了 [!UICONTROL Automated Personalization] 和 [!UICONTROL 自动定位] 默认情况下，不配置任何活动 [!DNL Target] 或其他 [!DNL Adobe] 解决方案，以及用于在 [个性化分析报表](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). 您可以随时增加输入数据集。要了解有关如何上传其他数据的更多信息，请参阅 [上传 [!DNL Target] 个性化算法](/help/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

| 数据类别 | 系统前缀 | 描述 | 中的显示名称 [!UICONTROL 分析] 报告 |
| --- | --- | --- | --- |
| 环境参数 | ENV | 有关用户环境的信息，包括操作系统、浏览器以及每周时间/每天。 | 浏览器 —  [属性名称]<br>操作系统 —  [值] |
| 地域 | 地域 | 通过IP查找获取的有关用户地理位置的信息。 | 地域 —  [地理属性] |
| 移动设备 | MOB | 有关用户移动设备的信息。 | 设备 —  [设备属性]<br>移动设备 —  [移动属性] |
| Target报表区段 | SEG | 中配置的报表区段 [!DNL Target] 报表。 | 报表区段 — [区段名称] |
| 会话行为 | SES | 有关用户行为的信息，如查看的页面数量。 | 访客资料 —  [属性名称] |

## 自定义Adobe Target属性类别

下表显示了由 [!UICONTROL Automated Personalization] 和 [!UICONTROL 自动定位] 活动。 仅当您提供此数据时，才会收集此数据。 特定属性名称和示例值将特定于您的系统配置。

| 数据类别 | 系统前缀 | 描述 | 中的显示名称 [!UICONTROL 分析] 报告 |
| --- | --- | --- | --- |
| 页面参数 | 框 | 在对的调用中传递的自定义页面参数（“mbox参数”） [!DNL Target]. | 自定义 — Mbox参数 —  [参数名称] |
| [!DNL Target] 配置文件 | PRO | 自定义配置文件属性直接上传到 [!DNL Target] 配置文件，以及 [!DNL Target] 配置文件脚本。 | 自定义 — 访客资料 —  [属性名称] |
| 客户属性 | CRS | 上传到 [!DNL Target] 通过 [Adobe Experience Cloud客户属性服务](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html){target=_blank}。 | 自定义 — 访客资料 —  [属性名称] |
| URL parameters（URL 参数） | URL | 当前查看的页面的URL和任何URL参数。 | 自定义 — URL参数 —  [URL参数] |
| 反向链接 URL | 参考 | 引荐URL和引荐URL的任何URL参数。 | 自定义 —  [引荐URL参数] - [参数值] |
| Adobe Experience Cloud共享受众 | AAM | 与共享的所有受众 [!DNL Target] 其他 [!DNL Adobe Experience Cloud] 解决方案(例如， [!DNL Adobe Audience Manager] 和 [!DNL Adobe Analytics]，通过 [[!DNL Experience Cloud Audience Library]](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html){target=_blank})。 | 自定义 — Experience Cloud受众 —  [受众名称] |
| Adobe Experience Platform RTCDP受众 | UPS | 与共享的AEP RTCDP受众 [!DNL Target] 通过目标。<br>请注意，此功能尚未在 [!DNL Target] 但将在未来实施。 |  |

## 阻止功能 [!DNL Target] 机器学习算法

功能可以从 [!DNL Target] 机器学习算法，防止它们被用于任何 [!UICONTROL 自动定位] 或 [!UICONTROL Automated Personalization] 模型或活动。

要阻止 [!DNL Target] 机器学习算法，联系人 [Adobe客户关怀](/help/cmp-resources-and-contact-information.md#section_CC8B206F58D6495C9372D5C0D4055CF6) 并使用上述提供的系统前缀指定要阻止的功能类别。

阻止 [!DNL Target] 机器学习算法，联系人 [Adobe客户关怀](/help/cmp-resources-and-contact-information.md#section_CC8B206F58D6495C9372D5C0D4055CF6) 并使用以下提供的系统名称指定应阻止的特定功能名称。 以下部分包含各种数据类型的详细信息，包括属性名称、属性描述和示例值。

## 设备和移动设备数据 {#device-mobile}

| 属性名称 | 属性描述 | 示例值 | 系统名称 |
| --- | --- | --- | --- |
| 移动设备 - 设备 - 品牌 | 访客用于访问活动的移动设备的品牌。 | Apple | MOB_targeting.mobile.vendor |
| 移动设备 - 设备 - 电子阅读器 | 指定设备是否为电子阅读器。 | 0 为 False，1 为 True | MOB_targeting.mobile.ereader |
| 移动设备 - 设备 - 游戏控制台 | 指定设备是否为游戏控制台。 | 0 为 False，1 为 True | MOB_targeting.mobile.gamesConsole |
| 移动设备 - 设备 - 媒体播放器 | 指定设备是否为媒体播放器。 | 0 为 False，1 为 True | MOB_targeting.mobile.mediaPlayer |
| 移动设备 - 设备 - 移动电话 | 指定设备是否为移动电话。 | 0 为 False，1 为 True | MOB_targeting.mobile.mobilePhone |
| 移动设备 - 设备 - 型号名称 | 访客用于访问活动的移动设备的型号名称。 | iPhone XS | MOB_targeting.mobile.modelName |
| 设备 - 机顶盒 | 指定设备是否为机顶盒。 | 0 为 False，1 为 True | MOB_targeting.mobile.setTopBox |
| 移动设备 - 设备 - 平板电脑 | 指定设备是否为平板电脑。 | 0 为 False，1 为 True | MOB_targeting.mobile.tablet |
| 移动设备 - 像素密度 (ppi) | 访客用于访问活动的移动设备的像素密度。 | 1、2、3 等 | MOB_targeting.mobile.displayPpi |
| 移动设备 - 操作系统 – OSX（Android、Windows 等） | 指定用户是否使用了 OSX（或 Android、Windows 等）设备访问活动。 | 0 为 False，1 为 True | MOB_targeting.mobile.os[操作系统]<br>例如， MOB_targeting.mobile.osOSx、MOB_targeting.mobile.osAndroid、MOB_targeting.mobile.osLinux |
| 移动设备 - 屏幕高度 (px) | 访客用于访问活动的移动设备的屏幕高度（以像素为单位）。 | 1、2、3 等 | MOB_targeting.mobile.displayHeight |
| 移动设备 - 屏幕宽度 (px) | 访客用于访问活动的移动设备的屏幕宽度（以像素为单位）。 | 1、2、3 等 | MOB_targeting.mobile.displayWidth |

## 环境数据 {#env}

|属性名称|属性描述|示例值|系统名称| | — | — | — | — | |浏览器 — 每周日期|访客在一周中访问活动的日期。|0到6。<br>（0表示星期日）|ENV_DAY_OF_WEEK_HOUR| |浏览器 — 每天的小时|访客在一天中访问活动的小时。|0至23<br>（0表示午夜）|ENV_USER_HOUR| |浏览器 — 每周时间|访客在一周中访问活动的时间。|0 - 168<br>（星期日的午夜为0）|ENV_WeekHour| |浏览器 — 语言设置|访客用于访问活动的浏览器中指定的语言。|英语<br>德语|ENV_Language| |浏览器 — 屏幕宽度(px)|访客用于访问活动的设备的浏览器屏幕宽度（以像素为单位）。|1、2、3等|ENV_browserWidth| |浏览器 — 时间|访客访问活动时浏览器在一天中的哪个时间。|0、6、12、18<br>(0表示深夜，6表示上午，<br>12表示下午，18表示晚上)|ENV_LOCAL_TIME_PERIOD| |浏览器 — 时区|访客访问活动时所在的时区。|太平洋时间<br>东部时间<br>GMT|ENV_BrowserTimezoneOffsetMinutes| |浏览器 — 类型|访客访问活动时使用的浏览器类型。|Chrome<br>Firefox<br>Internet Explorer<br>Safari<br>其他|ENV_Browser| |浏览器 — 工作日/周末|访客访问活动时的工作状态（周末、工作时间或工作日休息时间）。|星期六和星期日为周末<br>星期一至星期五上午9时至下午6时为工作时间<br>1800到900的星期一 — 星期五是工作日自由时间|ENV_USER_HOUR_TYPE| |浏览器 — 窗口高度(px)|访客用于访问活动的浏览器的窗口高度（以像素为单位）。|1、2、3等|ENV_BrowserHeight| |浏览器 — 窗口宽度(px)|访客用于访问活动的浏览器的窗口宽度（以像素为单位）。|1、2、3等|ENV_BrowserWidth| |设备 — 屏幕高度|访客用于访问活动的设备屏幕高度。|1、2、3等|ENV_SCREEN_HEIGHT| |设备 — 屏幕宽度|访客用于访问活动的设备的屏幕宽度。|1、2、3等|ENV_SCREEN_WIDTH| |操作系统|访客设备上用于访问活动的操作系统。|Mac OS<br>Windows<br>Linux<br>搜索机器人<br>未知的OS|ENV_OperatingSystem| |操作系统 — 版本|访客用于访问活动的操作系统版本。|Windows 10<br>Mac OS 10|ENV_OPERATING_SYSTEM_VERSION| |流量源 — 引荐登陆页面URL|访客访问您的网站时看到的第一个页面。|`https://www.adobe.com/ecloud.html`|ENV_REFERRER|

## 地理数据 {#geo}

| 属性名称 | 属性描述 | 示例值 | 系统名称 |
| --- | --- | --- | --- |
| 地域 - 城市 | 访客访问活动时所在的城市。 | 旧金山 | Geo_City |
| 地域 - 国家/地区 | 访客访问活动时所在的国家/地区。 | 德国 | 地域县 |
| 地域 - DMA | 访客访问活动时所在的指定营销区域 (DMA)。 | 夏洛茨维尔 | Geo_DMA |
| 地域 - 纬度 | 访客访问活动时所在位置的纬度。 | 47.269<br>四舍五入到小数点后三位（精度约为 100 米） | GEO_Latitude |
| 地域 - 经度 | 访客访问活动时所在位置的经度。 | -122.269<br>四舍五入到小数点后三位（精度约为 100 米） | GEO_Longitude |
| 地域 - 州/地区 | 访客访问活动时所在的州或地区。 | 犹他州<br>新南威尔士州 | GEO_State<br>GEO_Region |
| 地域 - 邮政编码 | 访客访问活动时所在地区的邮政编码。 | 84004 | GEO_ZipCode |
| 移动设备 - 运营商 | 访客访问活动时所使用的移动设备运营商。 | Vodafone<br>T-Mobile | GEO_mobileCarrier |
| 网络 - 连接速度 | 访客访问活动时设备的网络连接速度。 | 宽带<br>有线电视电缆<br>DSL<br>移动设备<br>无线<br>卫星 | GEO_ConnectionSpeed |
| 网络 - 域名 | 访客访问活动时所在的网络域名。 | `nnt.net` | GEO_DomainName |
| 网络 - ISP | 访客访问活动时所使用的网络。 | NNT 通信公司 | GEO_IspName |

## 会话数据 {#session}

| 属性名称 | 属性描述 | 示例值 | 系统名称 |
| --- | --- | --- | --- |
| 访客配置文件 - 活动生命周期订单值 | 指定某个特定活动的所有访问/会话中的全部订单值总和。 | 双精度 | SES_CUMULATIVE_ORDER_VALUE |
| 访客配置文件 - 活动生命周期网站停留时间 | 指定访客在网站上花费的总时间，不包括当前会话，该时间值将在会话过期时更新。 | 双精度，毫秒 | SES_TOTAL_TIME |
| 访客配置文件 - 活动期间每次访问的平均页面查看次数 | 指定每个会话的平均页面查看次数，不包括当前会话。 | 双精度 | SES_REQUESTS_PER_SESSION |
| 访客配置文件 - 每次访问平均逗留时间 | 指定每次访问/会话所花费的平均时间。不包括当前会话。 | 双精度，毫秒 | SES_TIME_PER_SESSION |
| 访客配置文件 - 首次访问 | 指定用户首次访问时与之交互的时间 [!DNL Target]. | 双精度，毫秒 | SES_PROFILE_CREATION_TIME |
| 访客配置文件 - 距上次访问的小时数 | 指定距上次访问此特定活动的小时数。 | 双精度（仅限正整数），1、2、3 等 | SES_HOURS_SINCE_LAST_VISIT |
| 访客配置文件 - 位置/内容的展示次数 | 指定某个特定位置/内容组合在特定活动中的展示次数。 | 双精度（仅限正整数），1、2、3 等 | SES_CUMULATIVE_ACTION_[LOCATION_ID]_[CONTENT_ID] |
| 访客配置文件 — 最后一个 [!DNL Target] 互动 | 指定上次与 [!DNL Target]. 每次 [!DNL Target] 请求，因为 [!DNL Target] 会根据每个请求更新用户档案。 | 双精度，毫秒 | SES_PROFILE_UPDATE_TIME |
| 访客配置文件 - 活动之前查看的页面数 | 指定访客在进入活动之前的页面查看总次数（展示次数），包括当前访问/会话。 | 双精度（仅限正整数），1、2、3 等 | SES_TOTAL_PAGE_VIEWS |
| 访客配置文件 - 当前访问中的页面查看次数 | 指定访客在进入活动之前在当前访问/会话中的页面查看次数。精度更高的展示次数。这些展示次数并不是实际的页面查看次数，而是请求到达 Target 的次数。Target 无法区分用户是因为超时还是任何其他原因而未能接收或查看内容。 | 双精度（仅限正整数） | SES_SESSION_POSITION |
| 访客配置文件 - 当前访问的开始时间 | 指定当前 Target 访问/会话开始的时间。无需进入活动即可开始访问 Target。只需调用任何 [!DNL Target] 请求。 访客可能需要花费一些时间才能进入活动并拍摄快照。 | 双精度，毫秒 | SES_SESSION_START |
| 访客配置文件 - 最近一次访问的开始时间 | 指定上次访问/会话的时间 [!DNL Target] 开始。 此属性将在会话过期时更新。<br>如果这是访客的第一个会话，则会导致 `LAST_SESSION_START = 0.` | 双精度，毫秒 | SES_LAST_SESSION_START |
| 访客配置文件 - 首次进入活动时距最近一次访问的时间 | 指定从上一个会话到用户进入活动并拍摄快照所经过的时间。 | 双精度，毫秒 | SES_RECENCY |
| 访客配置文件 - 进入活动前的访问时间 | 指定上次交互与 [!DNL Target] 和当前访问开始时。 此属性可视为在用户进入活动并拍摄快照之前，访问/会话的持续时间。<br>[!DNL Target]如果会话开始时间和上次更新时间由同一个 调用触发，则会出现负值。负值应视为 0（零）。 | 双精度，毫秒 | SES_SESSION_TIME |
| 访客配置文件 - 访问总数 | 指定访问/会话的总数。不包括当前访问/会话。 | 双精度（仅限正整数），1、2、3 等 | SES_TOTAL_SESSIONS |
| 访客配置文件 - 活动访问总数 | 指定某个特定活动的访问次数。如果之前未访问过该活动，则将返回 0（零）。 | 双精度（仅限正整数），1、2、3 等 | SES_PREVIOUS_VISIT_COUNT |
| 访客配置文件 - 有转化时的活动访问总数 | 指定在访问期间至少有一次转化时某个特定活动的访问/会话数。 | 双精度 | SES_CUMULATIVE_SUCCESS |
| 访客配置文件 - 无转化时的活动访问数 | 无转化时，某个特定活动的访问/会话数。发生转化后，此值将重置为零；如果从未发生转化，此值将重置为 -1。 | 双精度（仅限正整数），1、2、3 等 | SES_SUCCESS_RECENCY |
