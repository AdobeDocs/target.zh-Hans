---
description: Adobe Target自动收集和使用各种数据，以在自动个性化(AP)和自动Target(AT)活动中构建个性化算法。当一名访客进入到 AP 或 AT 活动，信息快照便会被传递到一组“训练记录”（个性化算法将要学习的访客数据）中。
keywords: 环境数据；会话数据；地理数据；地理数据；设备数据；移动数据；属性；配置文件属性
seo-description: Adobe Target自动收集和使用各种数据，以在自动个性化(AP)和自动Target(AT)活动中构建个性化算法。当一名访客进入到 AP 或 AT 活动，信息快照便会被传递到一组“训练记录”（个性化算法将要学习的访客数据）中。
seo-title: Adobe Target个性化算法的数据收集
solution: Target
title: 为 Target 个性化算法收集数据
title-outputclass: premium
topic: Premium
uuid: f5ca2d84-0016-4af5-a139-bca567a3d0e8
badge: premium
translation-type: tm+mt
source-git-commit: 156587a0375fe2dbf8c461e310b2eae04b491b57

---


# ![PREMIUM](/help/assets/premium.png) 为 Target 个性化算法收集数据{#data-collection-for-the-target-personalization-algorithms}

Target 可自动收集和使用各种数据，以在自动个性化 (AP) 和自动定位 (AT) 活动中构建其个性化算法。当一名访客进入到 AP 或 AT 活动，信息快照便会被传递到一组“训练记录”（个性化算法将要学习的访客数据）中。

要了解有关 Target 个性化算法的更多信息，请参阅[随机林算法](../../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA)。

The following table shows the data collected by Automated Personalization and Auto-Target by default, without the marketer having to do anything, as well as the naming convention used to indicate these attributes in [Personalization Insights Reports](../../c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). 您可以随时增加输入数据集。要了解有关如何上传其他数据的更多信息，请参阅[为 Target 个性化算法上传数据](../../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6)。

| 数据类型 | 描述 | 数据类型命名约定 | 示例属性 |
| --- | --- | --- | --- |
| [设备和移动数据](#device-mobile) | 特定于设备和移动设备的信息。<br>请参见下面的“设备和移动数据”。 | `Device - [device attribute]`<br>`Mobile - [mobile attribute]` | Mobile Device OS<br>Mobile Screen Size |
| [环境数据](#env) | 有关访客操作系统以及访客访问活动的方式和时间的信息。 | `Browser - / Operating System] - [Attribute Name]` | 浏览器 - 类型 |
| Experience Cloud部分 | 在Audience Manager或Analytics中创建的受众，并在Experience Cloud中共享 | `Custom - Experience Cloud Audience - [Audience Name]` | 自定义数据 |
| [地理数据](#geo) | 有关访客所在位置的信息。<br>请参见下面的“地理数据”。 | `Geo - [geo attribute]` | City<br>Country<br>Region/State<br>Zip Code<br>Latitude<br>Longitude<br>ISP or Mobile Carrier |
| 配置文件属性 | 通过更新API直接将个人资料脚本或属性上传到目标配置文件 | `Custom - Visitor Profile - [attribute name]` | 自定义数据 |
| 引用URL参数 | 一般而言，引荐 URL 是指将访客引荐到启用了 mbox 调用的特定页面的 URL。<br>请注意，用户在您网站上的活动以及您网站的技术实施都可能会对此变量造成影响。 | `Custom - [Referring URL Parameter] - [Parameter value]` | 自定义数据 |
| 报告区段 | 在活动设置中设置的任何区段。 | `Reporting Segment -[Segment Name]` | 自定义数据 |
| [会话数据](#session) | 有关访客访问活动时会话中的行为的信息。 | `Visitor Profile - [Attribute Name]` | 访客配置文件 - 最近一次访问的开始 |
| URL parameters（URL 参数） | Target 会检查 URL 以提取 URL 参数。 | `Custom - URL Parameter - [URL Parameter]` | 自定义数据 |

以下部分包含有关各种数据类型的详细信息，包括属性名称、描述和示例值。

## Device and Mobile data {#device-mobile}

| 属性名称 | 属性描述 | 示例值 |
| --- | --- | --- |
| 移动-设备-品牌 | 访客用于访问活动的移动设备的品牌。 | Apple |
| 移动-设备- eReader | 指定设备是否为eReader。 | 0为False，1为True |
| 移动-设备-游戏控制台 | 指定设备是否为游戏控制台。 | 0为False，1为True |
| 移动-设备-媒体播放器 | 指定设备是否为媒体播放器。 | 0为False，1为True |
| 移动-设备-移动电话 | 指定设备是否为手机。 | 0为False，1为True |
| 移动-设备-模型名称 | 访客用来访问活动的移动设备的型号名称。 | iPhone XS |
| 设备-机顶盒 | 指定设备是否为机顶盒。 | 0为False，1为True |
| 移动-设备-平板电脑 | 指定设备是否为平板电脑。 | 0为False，1为True |
| 移动-像素密度(ppi) | 访客访问活动所使用的移动设备像素密度。 | 1、2、3等 |
| Mobile- OS- OSX(Android、Windows等) | 指定用户是否使用OSX(或Android、Windows等)device to access the activity. | 0为False，1为True |
| 移动-屏幕高度(px) | 用于访问活动的移动设备的屏幕高度(以像素为单位)。 | 1、2、3等 |
| 移动-屏幕宽度(px) | 用于访问活动的移动设备的屏幕宽度(以像素为单位)。 | 1、2、3等 |

## Environmental data {#env}

| 属性名称 | 属性描述 | 示例值 |
| --- | --- | --- |
| 浏览器 - 每周时间 | 访客访问活动的一周中的一天。 | 到6。<br>(0为星期日) |
| 浏览器-时段 | 访客访问活动的那一天。 | 0 to 23<br>(0 is midnight) |
| 浏览器-每周一小时 | 访客访问活动的那一周的时间。 | 0 to 168<br>(Sunday midnight is 0) |
| 浏览器 - 语言设置 | 访客浏览器中用于访问活动的语言。 | English<br>German |
| 浏览器-屏幕高度(px) | 用于访问活动的设备的浏览器屏幕高度(以像素为单位)。 | 1、2、3等 |
| 浏览器-一天的时间 | 浏览器在访客访问活动时的时间。 | 0, 6, 12, 18<br>(0 is night, 6 is morning,<br>12 is afternoon, 18 is evening) |
| 浏览器 - 时区 | 访问活动时访客的时区。 | Pacific Time<br>Eastern Time<br>GMT |
| 浏览器 - 类型 | 访客访问活动时使用的浏览器类型。 | Chrome<br>Firefox<br>Internet Explorer<br>Safari<br>Other |
| 浏览器-工作日/周末 | 访客访问活动(周末、工作时间或工作日免费)时的工作状态。 | Saturday and Sunday is weekend<br>Monday-Friday 0900 to 1800 is work time<br>Monday-Friday after 1800 until 0900 is weekday free time |
| 浏览器-窗口高度(px) | 用于访问活动的浏览器的窗口高度(以像素为单位)。 | 1、2、3等 |
| 浏览器-窗口宽度(px) | 用于访问活动的浏览器的窗口宽度(以像素为单位)。 | 1、2、3等 |
| 设备-屏幕高度 | 访客用来访问活动的设备的屏幕高度。 | 1、2、3等 |
| 设备-屏幕宽度 | 访客用来访问活动的设备的屏幕宽度。 | 1、2、3等 |
| 操作系统 | 访客设备上用于访问活动的操作系统。 | Mac OS<br>Windows<br>Linux<br>Search Bot<br>Unknown OS |
| 操作系统-版本 | 访客用于访问活动的操作系统版本。 | Windows 10<br>Mac OS 10 |
| 流量源-引用登陆页面URL | 访客访问您的站点时看到的第一页。 | `https://www.adobe.com/ecloud.html` |

## Geographical data {#geo}

| 属性名称 | 属性描述 | 示例值 |
| --- | --- | --- |
| 地理-城市 | 访客从中访问活动的城市。 | San Francisco |
| 地域-国家 | 访客访问活动的国家/地区。 | 德国 |
| 地理- DMA | 访客从中访问活动的指定营销区域(DMA)。 | Charlottesville |
| 地理-纬度 | 访客从中访问活动的纬度。 | 47.269<br>Rounded to 3 decimal places (approximately 100 meters accuracy) |
| 地域-发行商 | 访客从中访问活动的longitude。 | -122.269<br>Rounded to 3 decimal places (approximately 100 meters accuracy) |
| 地域-州/地区 | 访客访问活动的州或地区。 | Utah<br>New South Wales |
| 地理-邮政编码 | 访客访问活动的Zip代码。 | 84004 |
| 移动-运营商 | 访问活动时使用的访客的移动运营商。 | Vodafone<br>T-Mobile |
| 网络-连接速度 | 访客访问活动时设备的网络连接速度。 | Broadband<br>Cable<br>DSL<br>Mobile<br>Wireless<br>Satellite |
| 网络-域名 | 访客访问活动的网络域的名称。 | `nnt.net` |
| 网络- ISP | 访客访问活动的网络。 | nnt Communications Corporation |

## Session data {#session}

| 属性名称 | 属性描述 | 示例值 |
| --- | --- | --- |
| 访客个人资料-活动生命周期订单值 | 指定所有访问/会话中所有访问/会话的总和的总和。 | 双线 |
| 访客个人资料-活动生命周期停留时间 | 指定访客在站点上花费的总时间，不包括当前会话，并在会话过期时更新。 | 两次，毫秒 |
| 访客个人资料-活动期间每个访问的平均页面查看次数 | 指定每个会话的平均页面查看次数，不包括当前会话。 | 双线 |
| 访客配置文件 - 每次访问平均逗留时间 | 指定每次访问/会话所花费的平均时间。此操作不包括当前会话。 | 两次，毫秒 |
| 访客个人资料-首次访问 | 指定首次访问时用户与Target交互的时间。 | 两次，毫秒 |
| 访客个人资料-上次访问后的时间 | 指定自上次访问此特定活动起的时间。 | 双精度(仅限整数正数)1、2、3等。 |
| 访客个人资料-位置/内容的印象 | 指定特定活动中特定位置/内容组合的次数。 | 双精度(仅限整数正数)1、2、3等。 |
| 访客个人资料-上次目标交互 | 指定上次与Target交互的时间。每次mbox请求都发生交互，因为Target的当前实施会在每个请求上更新配置文件。 | 两次，毫秒 |
| 访问者个人资料-活动之前查看的页面 | 指定页面查看次数(展示次数)，包括当前访问/会话，直到访客进入活动为止。 | 双精度(仅限整数正数)1、2、3等。 |
| 访客配置文件-当前访问中的页面查看次数 | 指定当前访问/会话中的页面查看次数，直到访客进入活动为止。更精确的展示次数。这些印象并非真实的页面查看次数，而是请求到达Target的次数。Target无法识别超时或用户未收到或查看内容的任何其他原因。 | 双精度(仅限整数正数) |
| 访客个人资料-当前访问开始 | 指定当Target的当前访问/会话开始时的时间。无需进入活动即可启动Target访问。所有这一切都是对任何mbox的调用。访客可能需要花费一段时间才能进入活动并拍摄快照。 | 两次，毫秒 |
| 访客配置文件 - 最近一次访问的开始 | 指定当Target上次访问/会话开始时的时间。此属性在会话过期时更新。<br>如果这是访客的第一个会话，则会导致 `LAST_SESSION_START = 0.` | 两次，毫秒 |
| 访客个人资料-自首次进入活动后最近访问的时间 | 指定上一个会话与用户进入活动的时间及快照的执行时间。 | 两次，毫秒 |
| 访客个人资料-进入活动前访问的时间 | 指定上次与Target交互和当前访问开始时的区别。在用户进入活动并执行快照之前，此属性可以被视为访问/会话持续时间。<br>当会话开始和上次更新时间由同一mbox调用触发时，负值会发生。基元值应视为0(零)。 | 两次，毫秒 |
| 访客配置文件 - 访问总数 | 指定访问/会话的总数。不包括当前访问/会话。 | 双精度(仅限整数正数)1、2、3等。 |
| 访客个人资料-活动总访问量 | 指定特定活动的访问次数。如果没有以前的访问，则返回0(零)。 | 双精度(仅限整数正数)1、2、3等。 |
| 访客个人资料-转化的访问总次数 | 指定在访问期间至少有一次转化的特定活动的访问/会话数。 | 双线 |
| 访客个人资料-无转化率的访问活动 | 访问次数/会话数量，不会转换为特定活动。转换后将此值重置为零，如果转换从未发生，则将此值重置为-1。 | 双精度(仅限整数正数)1、2、3等。 |
