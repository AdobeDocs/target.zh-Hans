---
keywords: 定位;A4T;地域;地域定位;地域定位的精准度;国家/地区;省/州;城市;邮政编码;DMA;移动设备运营商;城市代码;地区代码;国家/地区代码;大都市代码;配置文件脚本;地域定位配置文件脚本;地域定位移动设备
description: 了解如何在 [!DNL Adobe Target] 中创建受众，以根据用户的地理位置定位用户。
title: 我是否可以根据位置定位访客？
feature: 受众
solution: Target,Analytics
exl-id: e4a71a4d-e8f3-4f94-a1a7-fd250f4d5095
source-git-commit: b46966a8dbb2ff6d2efbfb8f126783f750c2f08c
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 50%

---

# Adobe Target 中的地域

在[!DNL Adobe Target]中使用受众可根据用户的地理位置来定位用户。

地理位置参数允许您根据访客的地理位置定位活动和体验。 您可以根据访客的地理位置信息（包括其国家/地区、省/自治区/直辖市、城市、邮编/邮政编码、纬度、经度、DMA 或移动设备运营商）来包含或排除访客。此数据随每个[!DNL Target]请求一起发送，并基于访客的IP地址。 选择这些参数的方式与选择其他任何定位值一样。

## 通过地域定位创建受众 {#section_49CBFFAAC8694C4AAD3DE4B2DB7B05DE}

1. 在 [!DNL Target] 界面中，单击&#x200B;**[!UICONTROL 受众]** > **[!UICONTROL 创建受众]**。
1. 为受众命名并添加可选描述。
1. 将&#x200B;**[!UICONTROL Geo]**&#x200B;拖放到受众生成器窗格中。

1. 单击&#x200B;**[!UICONTROL 选择]**，然后选择以下选项之一：

   * [!UICONTROL 国家/地区]
   * [!UICONTROL 省/自治区/直辖市]
   * [!UICONTROL 城市]
   * [!UICONTROL 邮政编码]
   * [!UICONTROL 经度]
   * [!UICONTROL 纬度]
   * [!UICONTROL DMA]
   * [!UICONTROL 移动设备运营商]

   访客的 IP 地址使用 mbox 请求来传递，以分析该访客的地域定位参数，每个访问（会话）进行一次。

   对于[!UICONTROL 移动设备运营商],[!DNL Target]使用IP地址注册数据（即IP地址块所有者的注册数据），通过[移动设备国家/地区代码(MCC)和移动设备网络代码(MNC)](https://www.mcc-mnc.com)来确定相应的移动设备运营商。

1. 指定运算符和相应的值。
1. （可选）为受众设置其他规则。
1. 单击&#x200B;**[!UICONTROL 完成]**。

下图展示了一个受众，它定位的是从纬度大于44°和经度小于22°访问活动的用户。

![](assets/target_geo.png)

## 精准度 {#section_D63D5FFCB49C42F9933AFD0BD7C79DF1}

地域定位的精准度取决于多个因素。与蜂窝网络相比，使用 WiFi 连接进行地域定位会更加精准。如果访客使用的是蜂窝数据连接，则地理查询的精准度可能会受到位置、提供商与 [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester) 之间的数据关系及其他因素的影响。使用基于蜂窝塔的网络连接进行地域定位可能没有使用有线或 WiFi 连接精准。此外，访客的IP地址可能会映射到访客的ISP位置，该位置可能与访客的实际位置不同。 使用[地理位置API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API)可以解决一些移动设备地理位置问题。

下表显示了使用有线或 WiFi Internet 连接时根据 IP 获取的地理位置信息的精准度，此数据由 [DigitalEnvoy](https://www.digitalelement.com/solutions/) 提供。DigitalEnvoy 能够提供业内最精准的数据。国家/地区级全局精准度超过 99.9%，城市级全局准确度高达 97%。此精准度信息不适用于基于蜂窝塔的网络。

| 国家/地区 | 省/自治区/直辖市 | 城市 | 地区 |
|--- |--- |--- |--- |
| 美国 | 99.99% | 96% | 94% |
| 加拿大 | 99.99% | 96% | 94% |
| 欧洲 | 99.99% |  |  |
| 英国 | 99.99% |  | 87% |
| 德国 | 99.99% | 95% | 93% |
| 斯堪的纳维亚半岛 | 99% | 90% - 95% | 85% 左右 |
| 西班牙 | 99.99% | 大概 90% | 95% - 99% |
| 亚洲 | 99% | 95% 左右 | 90% - 95% |
| 日本 | 99.99% | 95% 左右 | 90% - 95% |
| 澳大利亚 | 99.99% | 94% | 91% |

## 在配置文件脚本中使用地理定位 {#section_92C93138542C4A94997E3F4BE3F5DA28}

您可以将地理位置信息用于配置文件脚本。

例如，使用：

* `profile.geolocation.country`
* `profile.geolocation.state`
* `profile.geolocation.city`
* `profile.geolocation.zip`
* `profile.geolocation.dma`
* `profile.geolocation.domainName`
* `profile.geolocation.ispName`
* `profile.geolocation.connectionSpeed`
* `profile.geolocation.mobileCarrier`

因此，您可以使用以下代码编写名为“来自北美”的定位表达式：

`return profile.geolocation.country == 'united states' || profile.geolocation.country == 'canada' || profile.geolocation.country == 'mexico';`

## 将地理定位值用作令牌 {#section_E7F7FDF62C3B4934A6565D04B24655F6}

您可以在选件、插件等中直接将`profile.geolocation`值用作令牌。

例如，使用：

* `${profile.geolocation.country}`
* `${profile.geolocation.state}`
* `${profile.geolocation.city}`
* `${profile.geolocation.zip}`
* `${profile.geolocation.dma}`
* `${profile.geolocation.domainName}`
* `${profile.geolocation.ispName}`
* `${profile.geolocation.connectionSpeed}`
* `${profile.geolocation.mobileCarrier}`
* `${profile.geolocation.latitude}`
* `${profile.geolocation.longitude}`

## 地域定位常见问题解答 {#section_DD308A53AF0F48FA8C81423580561FE7}

以下是有关地域定位的常见问题：

### 如何指定纬度和经度？

* 纬度和经度的值应该是度数值。
* 纬度和经度的值最大精度可以小数位五位。
* 纬度值应介于 -90 到 90 之间。
* 经度值应介于 -180 到 180 之间。

### 地域定位在移动设备上的工作原理是什么？

大多数移动设备用户通过WiFi访问内容，这意味着[!DNL Target]基于IP的地理定位与桌面一样准确。 使用基于蜂窝塔的连接时，会根据获取信号的塔所在的位置来确定访客的 IP 地址，因此精准度可能会有所降低。使用[地理位置API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API)可以解决一些移动设备地理位置问题。

### 地域定位功能如何处理来自 AOL（美国在线公司）的访客？

由于AOL代理其流量的方式，[!DNL Target]只能在国家/地区级别定位它们。 例如，定位到法国的营销活动成功定位了法国的AOL用户。 但是，定位到巴黎的营销活动无法成功定位巴黎的AOL用户。 如果您的目的是特别定位 AOL 用户，您可以将地区字段设为“aol”。实际上，您可以通过指定以下两个定位条件来定位美国的 AOL 用户：国家/地区完全匹配“美国”，而地区完全匹配“aol”。

### 地域定位功能提供哪些位置选项？

* 国家/地区 - 全球
* 州/省/地区 - 全球
* 市 - 全球
* 邮政编码 - 美国、德国、加拿大
* DMA/ITV (UK) - 美国、英国
* 移动设备运营商 - 全球

### 我如何模拟其他位置的用户身份测试活动？

* **at.js 1.*x***:您可以使用其他位置的IP地址来覆盖您的IP地址，并使用 `mboxOverride.browserIp url` 参数。例如，如果您的公司位于英国，但您的全球营销活动定位的是奥克兰和新西兰的访客，请使用以下类型的URL（假设`60.234.0.39`是奥克兰的一个IP地址）：

   `https://www.mycompany.com?mboxOverride.browserIp=60.234.0.39`

   在测试活动之前清除Cookie。

   >[!NOTE]
   >
   >`mboxOverride.browserIp` at.js 1.*x*。at.js 2.*x* 目前不支持选择加入支持。

* **at.js 2.*x***:使用at.js 2.*x*，安装浏览器扩展/插件（例如适用于Chrome或Firefox的X-Forwarded-For Header）。此扩展允许您在页面请求中传递x-forwarded-for标头。

### 如何将波多黎各和中国香港特别行政区等区域映射到地理定位结构？

系统将波多黎各、中国香港特别行政区和其他区域视为单独的“国家/地区”值。

### 使用地理位置定位功能定位活动时，[!DNL Target]是否会捕获（并存储）邮政编码等信息？

否，[!DNL Target]仅在会话期间使用地理数据，然后丢弃该数据。

## 培训视频：创建受众![教程徽章](/help/assets/tutorial.png)

以下视频包含有关使用受众类别的信息。

* 创建受众
* 定义受众类别

>[!VIDEO](https://video.tv.adobe.com/v/17392)
