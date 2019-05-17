---
description: Target 可自动收集和使用各种数据，以在自动个性化 (AP) 和自动定位 (AT) 活动中构建其个性化算法。当一名访客进入到 AP 或 AT 活动，信息快照便会被传递到一组“训练记录”（个性化算法将要学习的访客数据）中。
seo-description: Target 可自动收集和使用各种数据，以在自动个性化 (AP) 和自动定位 (AT) 活动中构建其个性化算法。当一名访客进入到 AP 或 AT 活动，信息快照便会被传递到一组“训练记录”（个性化算法将要学习的访客数据）中。
seo-title: 为 Target 个性化算法收集数据
solution: Target
title: 为 Target 个性化算法收集数据
title-outputclass: premium
topic: Premium
uuid: f5ca2d84-0016-4af5-a139-bca567a3d0e8
badge: premium
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# ![PREMIUM](/help/assets/premium.png) 为 Target 个性化算法收集数据{#data-collection-for-the-target-personalization-algorithms}

Target 可自动收集和使用各种数据，以在自动个性化 (AP) 和自动定位 (AT) 活动中构建其个性化算法。当一名访客进入到 AP 或 AT 活动，信息快照便会被传递到一组“训练记录”（个性化算法将要学习的访客数据）中。

要了解有关 Target 个性化算法的更多信息，请参阅[随机林算法](../../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA)。

下表显示了在营销人员无需执行任何操作的情况下，自动个性化默认收集的数据，以及在[个性化分析报表](../../c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767)中用于反映这些属性的命名约定。您可以随时增加输入数据集。要了解有关如何上传其他数据的更多信息，请参阅[为 Target 个性化算法上传数据](../../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6)。

| 数据类型 | 描述 | 数据类型命名约定 | 示例属性 |
|--- |--- |--- |--- |
| URL 参数 | Target 会检查 URL 以提取 URL 参数。 | `Custom - URL Parameter - [URL Parameter]` | 自定义数据 |
| 引荐 URL 参数 | 一般而言，引荐 URL 是指将访客引荐到启用了 mbox 调用的特定页面的 URL。<br>请注意，用户在您网站上的活动以及您网站的技术实施都可能会对此变量造成影响。 | `Custom - [Referring URL Parameter] - [Parameter value]` | 自定义数据 |
| 环境和会话数据 | 有关用户如何以及何时访问活动的信息。 | `Visitor Profile - [attribute name]`<br>`Browser - [browser attribute]`<br>`Operating System - [OS attribute]` | 访客配置文件 - 最近一次访问的开始时间<br>访客配置文件 - 访问总数<br>访客配置文件 - 每次访问的平均时间<br>浏览器 - 时区<br>浏览器 - 每周时间<br>浏览器 - 语言设置<br>浏览器 - 类型<br>操作系统 - 版本 |
| 地域 | 有关访客所在位置的信息。 | `Geo - [geo attribute]` | 城市<br>国家/地区<br>地区/州<br>邮政编码<br>纬度<br>经度<br>ISP 或移动运营商 |
| 设备和移动设备数据 | 特定于设备和移动设备的信息。 | `Device - [device attribute]`<br>`Mobile - [mobile attribute]` | 移动设备操作系统<br>移动设备屏幕大小 |

