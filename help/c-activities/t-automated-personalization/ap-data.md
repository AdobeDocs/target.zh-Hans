---
description: Target 可自动收集和使用各种数据，以在自动个性化 (AP) 和自动定位 (AT) 活动中构建其个性化算法。当一名访客进入到 AP 或 AT 活动，信息快照便会被传递到一组“训练记录”（个性化算法将要学习的访客数据）中。
seo-description: Adobe Target自动收集和使用各种数据，以在自动个性化(AP)和自动Target(AT)活动中构建个性化算法。当一名访客进入到 AP 或 AT 活动，信息快照便会被传递到一组“训练记录”（个性化算法将要学习的访客数据）中。
seo-title: Adobe Target个性化算法的数据收集
solution: Target
title: 为 Target 个性化算法收集数据
title-outputclass: premium
topic: Premium
uuid: f5ca2d84-0016-4af5-a139-bca567a3d0e8
badge: premium
translation-type: tm+mt
source-git-commit: 1662c5e83a3712626536a659e5001cd537343883

---


# ![PREMIUM](/help/assets/premium.png) 为 Target 个性化算法收集数据{#data-collection-for-the-target-personalization-algorithms}

Target 可自动收集和使用各种数据，以在自动个性化 (AP) 和自动定位 (AT) 活动中构建其个性化算法。当一名访客进入到 AP 或 AT 活动，信息快照便会被传递到一组“训练记录”（个性化算法将要学习的访客数据）中。

要了解有关 Target 个性化算法的更多信息，请参阅[随机林算法](../../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA)。

下表显示了在营销人员无需执行任何操作的情况下，自动个性化默认收集的数据，以及在[个性化分析报表](../../c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767)中用于反映这些属性的命名约定。您可以随时增加输入数据集。要了解有关如何上传其他数据的更多信息，请参阅[为 Target 个性化算法上传数据](../../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6)。

| 数据类型 | 描述 | 数据类型命名约定 | 示例属性 |
| --- | --- | --- | --- |
| URL 参数 | Target 会检查 URL 以提取 URL 参数。 | `Custom - URL Parameter - [URL Parameter]` | 自定义数据 |
| 引荐 URL 参数 | 一般而言，引荐 URL 是指将访客引荐到启用了 mbox 调用的特定页面的 URL。<br>请注意，用户在您网站上的活动以及您网站的技术实施都可能会对此变量造成影响。 | `Custom - [Referring URL Parameter] - [Parameter value]` | 自定义数据 |
| 环境和会话数据 | 有关用户如何以及何时访问活动的信息。<br>请参见下面的“环境和会话数据”。 | `Visitor Profile - [attribute name]`<br>`Browser - [browser attribute]`<br>`Operating System - [OS attribute]` | 访客配置文件 - 最近一次访问的开始时间<br>访客配置文件 - 访问总数<br>访客配置文件 - 每次访问的平均时间<br>浏览器 - 时区<br>浏览器 - 每周时间<br>浏览器 - 语言设置<br>浏览器 - 类型<br>操作系统 - 版本 |
| 地理位置 | 有关访客所在位置的信息。<br>请参见下面的“地理数据”。 | `Geo - [geo attribute]` | CityCountRegion<br><br>/StateZip<br>CodelativeDelongItuDeISP<br><br><br>或Mobile运营商 |
| 设备和移动设备数据 | 特定于设备和移动设备的信息。<br>请参见下面的“设备和移动数据”。 | `Device - [device attribute]`<br>`Mobile - [mobile attribute]` | 移动设备OmMobile<br>屏幕大小 |

以下部分包含有关各种数据类型的详细信息，包括属性名称、描述和示例值。

>[!NOTE]
>
>以下表中的部分值已舍入到最近的整数或小时。

## 环境和会话数据

| 属性名称 | 属性描述 | 示例值 |
| --- | --- | --- |
| 浏览器 - 每周时间 | 访客访问活动的一周中的一天。 | 到6。<br>(0为星期日) |
| 浏览器-时段 | 访客访问活动的那一天。 | 至23<br>(0为午夜) |
| 浏览器-每周一小时 | 访客访问活动的那一周的时间。 | 到168<br>(周日午夜为0) |
| 浏览器 - 语言设置 | 访客浏览器中用于访问活动的语言。 | Englishman<br> |
| 浏览器-屏幕高度(px) | 用于访问活动的设备的浏览器屏幕高度(以像素为单位)。 | 1、2、3等 |
| 浏览器-一天的时间 | 浏览器在访客访问活动时的时间。 | 0、6、12、18<br>(0为晚上，6为上午，12为下午，18为晚上) |
| 浏览器 - 时区 | 访问活动时访客的时区。 | 太平洋时间东部<br>时间<br> |
| 浏览器 - 类型 | 访客访问活动时使用的浏览器类型。 | ChromeFirefoxInternet<br><br>Expreshers其他<br><br> |
| 浏览器-工作日/周末 | 访客访问活动(周末、工作时间或工作日免费)时的工作状态。 | 星期六和星期日是周末至<br>星期五，到星期五0900至1800年，<br>时间为1800至0900，直到0900为工作日免费时间 |
| 浏览器-窗口高度(px) | 用于访问活动的浏览器的窗口高度(以像素为单位)。 | 1、2、3等 |
| 浏览器-窗口宽度(px) | 用于访问活动的浏览器的窗口宽度(以像素为单位)。 | 1、2、3等 |
| 设备-屏幕高度 | 访客用来访问活动的设备的屏幕高度。 | 1、2、3等 |
| 设备-屏幕宽度 | 访客用来访问活动的设备的屏幕宽度。 | 1、2、3等 |
| “移动”&gt;“像素密度”(ppi) | 访客访问活动所使用的移动设备像素密度。 | 1、2、3等 |
| 操作系统 | 访客设备上用于访问活动的操作系统。 | Mac OSWindowsLinuxSearch<br><br><br>BotTunknown<br>OS |
| 操作系统-版本 | 访客用于访问活动的操作系统版本。 | Windows10<br>Mac OS10 |
| 流量源-引用登陆页面URL | 访客访问您的站点时看到的第一页。 | `https://www.adobe.com/ecloud.html` |

## 地理数据

| 属性名称 | 属性描述 | 示例值 |
| --- | --- | --- |
| 地理-城市 | 访客从中访问活动的城市。 | San Francisco |
| 地域-国家 | 访客访问活动的国家/地区。 | 德国 |
| 地理- DMA | 访客从中访问活动的指定营销区域(DMA)。 | Charlottesville |
| 地理-纬度 | 访客从中访问活动的纬度。 | 47.269<br>舍入到个小数位(约100米精度) |
| 地域-发行商 | 访客从中访问活动的longitude。 | -122.269<br>舍入到个小数位(约100米精度) |
| 地域-州/地区 | 访客访问活动的州或地区。 | UtahNew<br>South Wales |
| 地理-邮政编码 | 访客访问活动的Zip代码。 | 84004 |
| 移动-运营商 | 访问活动时使用的访客的移动运营商。 | Vodafone<br>T-Mobile |
| 网络-连接速度 | 访客访问活动时设备的网络连接速度。 | BroadbandCabedSlMobileWiress卫星<br><br><br><br><br> |
| 网络-域名 | 访客访问活动的网络域的名称。 | `nnt.net` |
| 网络- ISP | 访客访问活动的网络。 | nnt Communications Corporation |

## 设备和移动数据

| 属性名称 | 属性描述 | 示例值 |
| --- | --- | --- |
| 移动-设备-品牌 | 访客用于访问活动的移动设备的品牌。 | Apple |
| 移动-设备-模型名称 | 访客用来访问活动的移动设备的型号名称。 | iPhone XS |
| Mobile- OS- OSX | 指定用户是否使用OSX设备访问活动。 | 0为False，1为True |
| 移动-屏幕高度(px) | 用于访问活动的移动设备的屏幕高度(以像素为单位)。 | 1、2、3等 |
| 移动-屏幕宽度(px) | 用于访问活动的移动设备的屏幕宽度(以像素为单位)。 | 1、2、3等 |