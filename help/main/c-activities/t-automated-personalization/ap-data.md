---
keywords: 环境数据；会话数据；地理数据；设备数据；移动数据；属性；配置文件属性；个性化算法；机器学习算法；机器学习算法
description: 了解哪个数据Adobe [!DNL Target] 收集并使用构建其机器学习算法。
title: 收集哪些数据来构建机器学习算法？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Automated Personalization
exl-id: 7114a6d6-4779-471e-9b91-646aa49e102a
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '2025'
ht-degree: 50%

---

# [!DNL Target]机器学习算法使用的数据

[!DNL Adobe Target] 自动收集和使用各种数据以在中构建其个性化算法 [!UICONTROL Automated Personalization] (AP)和 [!UICONTROL 自动定位] (AT)活动 当访客进入AP或AT活动时，信息快照将被传递到一组“训练记录”（个性化算法将学习的访客数据）中。

要了解有关 [!DNL Target] 个性化算法，请参见 [随机林算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md).

## 默认 [!DNL Adobe Target] 属性类别

下表显示了收集的数据 [!UICONTROL Automated Personalization] 和 [!UICONTROL 自动定位] 活动默认，无任何配置 [!DNL Target] 或其他 [!DNL Adobe] 解决方案中用于指示这些属性的命名约定 [个性化分析报表](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). 您可以随时增加输入数据集。要了解有关如何上传其他数据的更多信息，请参阅 [正在上传以下项的数据 [!DNL Target] 个性化算法](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

| 数据类别 | 系统前缀 | 描述 | 显示名称 [!UICONTROL 分析] 报告 |
| --- | --- | --- | --- |
| 环境参数 | 环境 | 有关用户环境的信息，包括操作系统、浏览器和时间/星期。 | 浏览器 —  [属性名称]<br>操作系统 —  [值] |
| 地域 | 地域 | 通过IP查找获取的用户地理位置信息。 | 地域 —  [地理属性] |
| 移动设备 | MOB | 有关用户移动设备的信息。 | 设备 —  [设备属性]<br>移动设备 —  [移动属性] |
| Target报表区段 | SEG | 在中配置的报表区段 [!DNL Target] 报告。 | 报告区段 — [区段名称] |
| 会话行为 | SES | 有关用户行为的信息，例如查看的页面数量。 | 访客资料 —  [属性名称] |

## 自定义Adobe Target属性类别

下表显示由收集的客户提供的数据 [!UICONTROL Automated Personalization] 和 [!UICONTROL 自动定位] 活动。 仅当您提供此数据时，才会收集此数据。 特定的属性名称和示例值将特定于您的系统配置。

| 数据类别 | 系统前缀 | 描述 | 显示名称 [!UICONTROL 分析] 报告 |
| --- | --- | --- | --- |
| 页面参数 | BOX | 在对的调用中传递的自定义页面参数（“mbox参数”） [!DNL Target]. | 自定义 — Mbox参数 —  [参数名称] |
| [!DNL Target] 配置文件 | PRO | 自定义配置文件属性直接上传到 [!DNL Target] 通过API或页面参数和 [!DNL Target] 配置文件脚本。 | 自定义 — 访客资料 —  [属性名称] |
| 客户属性 | CRS | 客户属性上传至 [!DNL Target] 个人资料，通过 [Adobe Experience Cloud客户属性服务](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html){target=_blank}. | 自定义 — 访客资料 —  [属性名称] |
| URL parameters（URL 参数） | URL | 当前查看的页面的URL和任何URL参数。 | 自定义 — URL参数 —  [URL参数] |
| 反向链接 URL | 参考 | 反向链接URL和任何反向链接URL参数。 | 自定义 —  [反向链接URL参数] - [参数值] |
| Adobe Experience Cloud共享受众 | AAM | 共享的所有受众 [!DNL Target] 来自其他 [!DNL Adobe Experience Cloud] 解决方案(例如， [!DNL Adobe Audience Manager] 和 [!DNL Adobe Analytics]，通过 [[!DNL Experience Cloud Audience Library]](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html){target=_blank})。 | 自定义 — Experience Cloud受众 —  [受众名称] |
| Adobe Experience Platform实时CDP受众 | UPS | 与共享的AEP实时CDP受众 [!DNL Target] 通过Destinations。 |  |
| Adobe Experience Platform Real-time CDP属性 | AEP | 与共享的AEP Real-time CDP属性 [!DNL Target] 通过Destinations。 此功能目前处于Beta测试阶段。 |  |

## 阻止功能 [!DNL Target] 机器学习算法

可以从 [!DNL Target] 机器学习算法中阻止功能，防止在任何[!UICONTROL 自动定位]或[!UICONTROL 自动个性化]模型或活动中使用它们。

有关更多信息，请参阅 [模型API(列入阻止列表)概述](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api.html){target=_blank} 在 *Adobe Target开发人员指南*.

## 设备和移动设备数据 {#device-mobile}

| 属性名称 | 属性描述 | 示例值 | 系统名称 |
| --- | --- | --- | --- |
| 移动设备 - 设备 - 品牌 | 访客用于访问活动的移动设备的品牌。 | Apple | MOB_targeting.mobile.vendor |
| 移动设备 - 设备 - 电子阅读器 | 指定设备是否为电子阅读器。 | 0 为 False，1 为 True | MOB_targeting.mobile.ereader |
| 移动设备 - 设备 - 游戏控制台 | 指定设备是否为游戏控制台。 | 0 为 False，1 为 True | MOB_targeting.mobile.gamesConsole |
| 移动设备 - 设备 - 媒体播放器 | 指定设备是否为媒体播放器。 | 0 为 False，1 为 True | MOB_targeting.mobile.mediaPlayer |
| 移动设备 - 设备 - 移动电话 | 指定设备是否为移动电话。 | 0 为 False，1 为 True | MOB_targeting.mobile.mobilePhone |
| 移动设备 - 设备 - 型号名称 | 访客用于访问活动的移动设备的型号名称。 | iPhone XS | MOB_targeting.mobile.model |
| 设备 - 机顶盒 | 指定设备是否为机顶盒。 | 0 为 False，1 为 True | MOB_targeting.mobile.setTopBox |
| 移动设备 - 设备 - 平板电脑 | 指定设备是否为平板电脑。 | 0 为 False，1 为 True | MOB_targeting.mobile.tablet |
| 移动设备 - 像素密度 (ppi) | 访客用于访问活动的移动设备的像素密度。 | 1、2、3 等 | MOB_targeting.mobile.displayPpi |
| 移动设备 - 操作系统 – OSX（Android、Windows 等） | 指定用户是否使用了 OSX（或 Android、Windows 等）设备访问活动。 | 0 为 False，1 为 True | MOB_targeting.mobile.os[操作系统]<br>例如，MOB_targeting.mobile.osOSx、MOB_targeting.mobile.osWindows、MOB_targeting.mobile.osAndroid、MOB_targeting.mobile.osLinux |
| 移动设备 - 屏幕高度 (px) | 访客用于访问活动的移动设备的屏幕高度（以像素为单位）。 | 1、2、3 等 | MOB_targeting.mobile.displayHeight |
| 移动设备 - 屏幕宽度 (px) | 访客用于访问活动的移动设备的屏幕宽度（以像素为单位）。 | 1、2、3 等 | MOB_targeting.mobile.displayWidth |

## 环境数据 {#env}

|属性名称|属性说明|示例值|系统名称| | — | — | — | — | |浏览器 — 每周时间|访客在一周中访问活动的日期。|0到6。<br>（0表示星期日）|ENV_DayOfWeek| |浏览器 — 一天中的第几个小时|访客在一天中访问活动时的第几个小时。|0到23<br>（0是午夜）|ENV_UserHour| |浏览器 — 每周时间|访客访问活动时的一周中的时间。|0到168<br>（星期日的午夜为0）|ENV_WeekHour| |浏览器 — 语言设置|访客用于访问活动的浏览器中指定的语言。|英语<br>德语环境语言 |浏览器 — 一天中的时间|访客在一天中访问活动时浏览器的时间。|0、6、12、18<br>(0表示深夜，6表示上午，<br>12表示下午， 18表示晚上)|ENV_LocalTimePeriod| |浏览器 — 时区|访客访问活动时的时区。|太平洋时间<br>东部时间<br>GMT|ENV_BrowserTimezoneOffsetMinutes| |浏览器 — 类型|访客访问活动时使用的浏览器类型。|铬黄<br>Firefox<br>Internet Explorer<br>Safari<br>其他环境浏览器 |浏览器 — 工作日/周末|访客访问活动时的工作状态（周末、工作时间或工作日休息时间）。|星期六和星期日是周末<br>星期一至星期五上午9点至下午6点为工作时间<br>1800后至0900的星期一至星期五是工作日自由时间|ENV_UserHourType| |浏览器 — 窗口高度(px)|访客用于访问活动的浏览器的窗口高度（以像素为单位）。|1、2、3等|环境_浏览器高度| |浏览器 — 窗口宽度(px)|访客用于访问活动的浏览器的窗口宽度（以像素为单位）。|1、2、3等|环境浏览器宽度| |设备 — 屏幕高度(px)|访客用于访问活动的设备的屏幕高度。|1、2、3等|环境_屏幕高度| |设备 — 屏幕宽度(px)|访客用于访问活动的设备的屏幕宽度。|1、2、3等|环境屏幕宽度| |操作系统|访客用于访问活动的设备上的操作系统。|Mac操作系统<br>Windows<br>Linux<br>搜索机器人<br>未知操作系统|ENV_OperatingSystem| |操作系统 — 版本|访客用于访问活动的操作系统的版本。|Windows 10<br>Mac操作系统10|ENV_OperatingSystemVersion| |流量源 — 引荐登陆页面URL|访客访问您的网站时看到的第一页。|`https://www.adobe.com/ecloud.html`|环境_反向链接|

## 地理数据 {#geo}

| 属性名称 | 属性描述 | 示例值 | 系统名称 |
| --- | --- | --- | --- |
| 地域 - 城市 | 访客访问活动时所在的城市。 | 旧金山 | Geo_City |
| 地域 - 国家/地区 | 访客访问活动时所在的国家/地区。 | 德国 | 地域国家/地区 |
| 地域 - DMA | 访客访问活动时所在的指定营销区域 (DMA)。 | 夏洛茨维尔 | Geo_DMA |
| 地域 - 纬度 | 访客访问活动时所在位置的纬度。 | 47.269<br>四舍五入到小数点后三位（精度约为 100 米） | 地理纬度 |
| 地域 - 经度 | 访客访问活动时所在位置的经度。 | -122.269<br>四舍五入到小数点后三位（精度约为 100 米） | GEO_Longitude |
| 地域 - 州/地区 | 访客访问活动时所在的州或地区。 | 犹他州<br>新南威尔士州 | 地理状态<br>GEO_Region |
| 地域 - 邮政编码 | 访客访问活动时所在地区的邮政编码。 | 84004 | GEO_ZipCode |
| 移动设备 - 运营商 | 访客访问活动时所使用的移动设备运营商。 | Vodafone<br>T-Mobile | GEO_mobileCarrier |
| 网络 - 连接速度 | 访客访问活动时设备的网络连接速度。 | 宽带<br>有线电视电缆<br>DSL<br>移动设备<br>无线<br>卫星 | GEO_ConnectionSpeed |
| 网络 - 域名 | 访客访问活动时所在的网络域名。 | `nnt.net` | GEO_DomainName |
| 网络 - ISP | 访客访问活动时所使用的网络。 | NNT 通信公司 | 地域_IspName |

## 会话数据 {#session}

| 属性名称 | 属性描述 | 示例值 | 系统名称 |
| --- | --- | --- | --- |
| 访客配置文件 - 活动生命周期订单值 | 指定某个特定活动的所有访问/会话中的全部订单值总和。 | 双精度 | SES_CUMULATIVE_ORDER_VALUE |
| 访客配置文件 - 活动生命周期网站停留时间 | 指定访客在网站上花费的总时间，不包括当前会话，该时间值将在会话过期时更新。 | 双精度，毫秒 | SES_TOTAL_TIME |
| 访客配置文件 - 活动期间每次访问的平均页面查看次数 | 指定每个会话的平均页面查看次数，不包括当前会话。 | 双精度 | SES_REQUESTS_PER_SESSION |
| 访客配置文件 - 每次访问平均逗留时间 | 指定每次访问/会话所花费的平均时间。不包括当前会话。 | 双精度，毫秒 | SES_TIME_PER_SESSION |
| 访客配置文件 - 首次访问 | 指定用户进行交互的首次访问的时间 [!DNL Target]. | 双精度，毫秒 | SES_PROFILE_CREATION_TIME |
| 访客配置文件 - 距上次访问的小时数 | 指定距上次访问此特定活动的小时数。 | 双精度（仅限正整数），1、2、3 等 | SES_HOURS_SINCE_LAST_VISIT |
| 访客配置文件 - 位置/内容的展示次数 | 指定某个特定位置/内容组合在特定活动中的展示次数。 | 双精度（仅限正整数），1、2、3 等 | SES_CUMULATIVE_ACTION_[LOCATION_ID]_[CONTENT_ID] |
| 访客配置文件 — 上一个 [!DNL Target] 互动 | 指定上次与交互的时间 [!DNL Target]. 交互发生于每 [!DNL Target] 请求，因为当前实现 [!DNL Target] 会更新每个请求上的配置文件。 | 双精度，毫秒 | SES_PROFILE_UPDATE_TIME |
| 访客配置文件 - 活动之前查看的页面数 | 指定访客在进入活动之前的页面查看总次数（展示次数），包括当前访问/会话。 | 双精度（仅限正整数），1、2、3 等 | SES_TOTAL_PAGE_VIEWS |
| 访客配置文件 - 当前访问中的页面查看次数 | 指定访客在进入活动之前在当前访问/会话中的页面查看次数。精度更高的展示次数。这些展示次数并不是实际的页面查看次数，而是请求到达 Target 的次数。Target 无法区分用户是因为超时还是任何其他原因而未能接收或查看内容。 | 双精度（仅限正整数） | SES_SESSION_POSITION |
| 访客配置文件 - 当前访问的开始时间 | 指定当前 Target 访问/会话开始的时间。无需进入活动即可开始访问 Target。只需要调用任何 [!DNL Target] 请求。 访客可能需要花费一些时间才能进入活动并拍摄快照。 | 双精度，毫秒 | SES_SESSION_START |
| 访客配置文件 - 最近一次访问的开始时间 | 指定上次访问/会话的时间 [!DNL Target] 已启动。 此属性将在会话过期时更新。<br>如果这是访客的第一个会话，则会导致 `LAST_SESSION_START = 0.` | 双精度，毫秒 | SES_LAST_SESSION_START |
| 访客配置文件 - 首次进入活动时距最近一次访问的时间 | 指定从上一个会话到用户进入活动并拍摄快照所经过的时间。 | 双精度，毫秒 | SES_RECENCY |
| 访客配置文件 - 进入活动前的访问时间 | 指定上次与的交互之间的差异 [!DNL Target] 以及当前访问开始的时间。 此属性可视为在用户进入活动并拍摄快照之前，访问/会话的持续时间。<br>[!DNL Target]如果会话开始时间和上次更新时间由同一个 调用触发，则会出现负值。负值应视为 0（零）。 | 双精度，毫秒 | SES_SESSION_TIME |
| 访客配置文件 - 访问总数 | 指定访问/会话的总数。不包括当前访问/会话。 | 双精度（仅限正整数），1、2、3 等 | SES_TOTAL_SESSIONS |
| 访客配置文件 - 活动访问总数 | 指定某个特定活动的访问次数。如果之前未访问过该活动，则将返回 0（零）。 | 双精度（仅限正整数），1、2、3 等 | SES_PREVIOUS_VISIT_COUNT |
| 访客配置文件 - 有转化时的活动访问总数 | 指定在访问期间至少有一次转化时某个特定活动的访问/会话数。 | 双精度 | SES_CUMULATIVE_SUCCESSATIONS |
| 访客配置文件 - 无转化时的活动访问数 | 无转化时，某个特定活动的访问/会话数。发生转化后，此值将重置为零；如果从未发生转化，此值将重置为 -1。 | 双精度（仅限正整数），1、2、3 等 | SES_SUCCESS_RECENCY |
