---
keywords: implement;implementing;setting up;setup;page parameter;tomcat;url encoded;in-page profile attribute;mbox parameter;in-page profile attributes;script profile attribute;bulk profile update API;single file update API;customer attributes;data providers;dataprovider;data provider
description: 此信息介绍了可用于将数据导入 Target 的各种方法，包括页面参数、页面内配置文件属性、脚本配置文件属性、数据提供程序、批量配置文件更新 API、单个配置文件更新 API 和客户属性。
title: 将数据导入 Target 的方法
feature: implementation general
subtopic: Getting Started
topic: Standard
uuid: a6d64e39-6cdc-49fe-afe5-ecf7dcacf97d
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '1940'
ht-degree: 96%

---


# 将数据导入 Target 的方法{#methods-to-get-data-into-target}

此信息介绍了可用于将数据导入 Target 的不同方法，包括页面参数、页面内配置文件属性、脚本配置文件属性、数据提供程序、批量配置文件更新 API、单个配置文件更新 API 和客户属性。

## 页面参数（也称为“mbox 参数”）{#section_5A297816173C4FE48DC4FE03860CB42B}

页面参数是直接通过页面代码传入的名称/值对，它们未存储在访客的配置文件中供将来使用。

页面参数可用于将其他页面数据发送到 Target，这些数据不需要与访客配置文件一起存储以供将来的定位使用，而是用来描述页面或用户在特定页面上执行的操作。

### 格式

页面参数通过服务器调用作为字符串名称/值对传递给 Target。参数名称和值是可自定义的（但存在一些用于特定用途的“保留名称”）。

示例：

* `page=productPage`

* `categoryId=homeLoans`

### 使用示例

**产品页面**：发送有关已查看的特定产品的信息（这就是“推荐”的工作方式）

**订单详细信息**：发送订单 ID、orderTotal 和其他用于订单收集的信息

**类别亲和度**：将已查看的类别信息发送到 Target，以了解用户对特定站点类别的亲和度

**第三方数据**：发送来自第三方数据源的信息，例如天气定位提供程序、帐户数据（例如 DemandBase）、人口统计数据（例如 Experian）等。

### 该方法的好处

数据会被实时发送到 Target，并可用于得到该数据的同一服务器调用。

### 注意事项

* 需要更新页面代码（直接或通过标记管理系统）。
* 如果要在后续页面/服务器调用中将数据用于定位，则需要将其转换为配置文件脚本。
* 查询字符串只能包含符合 [Internet 工程任务组 (IETF) 标准](https://www.ietf.org/rfc/rfc3986.txt)的字符。

   除了 IETF 站点上提到的那些字符之外，Target 还允许在查询字符串中使用以下字符：

   `&lt; > # % &quot; { } | \\ ^ \[\] \``

   其他所有字符都必须采用 URL 编码。The standard specifies the following format ( [https://www.ietf.org/rfc/rfc1738.txt](https://www.ietf.org/rfc/rfc1738.txt) ), as illustrated below:

   ![](assets/ietf1.png)

   或者，简单显示完整列表：

   ![](assets/ietf2.png)

### 代码示例

targetPageParamsAll（将参数附加到页面上的所有 mbox 调用）：

`function targetPageParamsAll() { return "param1=value1&param2=value2&p3=hello%20world";`

targetPageParams（将参数附加到页面上的全局 mbox）：

`function targetPageParams() { return "param1=value1&param2=value2&p3=hello%20world";`

mboxCreate 代码中的参数：

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','param1=value1','param2=value2'); </script>`

### 相关信息链接

推荐：[按照页面类型实施](/help/c-recommendations/plan-implement.md#reference_DE38BB07BD3C4511B176CDAB45E126FC)

订单确认：[跟踪转化](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053)

类别亲和度：[类别亲和度](/help/c-target/c-visitor-profile/category-affinity.md#concept_75EC1E1123014448B8B92AD16B2D72CC)

## 页面内配置文件属性（也称为“in-mbox”配置文件属性）{#section_57E1C161AA7B444689B40B6F459302B6}

页面内配置文件属性是直接通过页面代码传递的名称/值对，它们存储在访客的配置文件中供将来使用。

页面内配置文件属性允许将特定于用户的数据存储在 Target 的配置文件中，供以后进行定位和分段。

### 格式

页面内配置文件属性作为成对的字符串名称/值，通过服务器调用进行传递，且在属性名称前带有前缀“profile.”。

属性名称和值是可自定义的（但存在一些用于特定用途的“保留名称”）。

示例：

* `profile.membershipLevel=silver`
* `profile.visitCount=3`

### 使用示例

**登录信息**：根据用户的登录信息，将非 PII（个人身份信息）数据共享到 Target。该数据可能是成员资格状态、订单历史记录或其他信息。

**存储信息**：跟踪哪个商店是该用户最喜欢的位置。

**以前的互动**：跟踪用户以前在该网站上的操作，以便为其将来的个性化提供参考依据。

### 该方法的好处

数据会被实时发送到 Target，并可用于得到该数据的同一服务器调用。

### 注意事项

需要更新页面代码（直接或通过标记管理系统）。

属性和值在服务器调用中可见，因此访客可以查看这些值。如果要共享诸如信用等级或其他潜在的私人信息等内容，这可能不是最佳方法。

### 代码示例

targetPageParamsAll（将属性附加到页面上的所有 mbox 调用）：

`function targetPageParamsAll() { return "profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

targetPageParams（将属性附加到页面上的全局 mbox）：

`function targetPageParams() { return profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

mboxCreate 代码中的属性：

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','profile.param1=value1','profile.param2=value2'); </script>`

### 相关信息链接

[配置文件属性](/help/c-target/c-visitor-profile/profile-parameters.md#concept_01A30B4762D64CD5946B3AA38DC8A201)

[访客资料](/help/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)

## 脚本配置文件属性 {#section_3E27B58C841448C38BDDCFE943984F8D}

脚本配置文件属性是 Target 解决方案中定义的名称/值对。该值是在每个服务器调用时，通过在 Target 服务器上执行一段 JavaScript 代码来确定。

为访客评估受众和活动用户编写一小段代码，该代码片段会在每次 mbox 调用时、且在评估访客的受众群体和活动成员资格之前执行。

### 格式

脚本配置文件属性在 Target 的“受众”区域中创建。任何属性名称都是有效的，其属性值是由 Target 用户编写的 JavaScript 函数所产生的结果。该属性名称自动在 Target 中添加“user. ”作为前缀，以便与页面内配置文件属性区分开。

代码片段以 Rhino JS 语言编写，可引用令牌和其他值。

### 使用示例

**购物车放弃**：当访客到达购物车时，将配置文件脚本设为 1。当访客转化后，将其重置为 0。如果值 = 1，则访客在购物车中有一个商品。

**访问计数**：每新增一次访问，计数将增加 1，以跟踪访客返回网站的频率。

### 该方法的好处

不需要更新页面代码。

在受众和活动成员资格决策之前执行，这样这些配置文件脚本属性会影响单个服务器调用的成员资格。

此方法操作容量非常大。每个脚本可以执行多达 2,000 条指令。

### 注意事项

需要 JavaScript 知识。

无法保证配置文件脚本的执行顺序，因此它们不能相互依赖。

可能很难调试。

### 代码示例

配置文件脚本非常灵活：

`user.purchase_recency: var dayInMillis = 3600 * 24 * 1000; if (mbox.name == 'orderThankyouPage') {  user.setLocal('lastPurchaseTime', new Date().getTime()); } var lastPurchaseTime = user.getLocal('lastPurchaseTime'); if (lastPurchaseTime) {  return ((new Date()).getTime()-lastPurchaseTime)/dayInMillis; }`

### 相关信息链接

[配置文件脚本属性](/help/c-target/c-visitor-profile/profile-parameters.md#concept_8C07AEAB0A144FECA8B4FEB091AED4D2)

## 数据提供程序 {#section_14FF3BE20DAA42369E4812D8D50FBDAE}

数据提供程序是一项功能，允许您轻松地将数据从第三方传递到 Target。

注意：数据提供程序需要使用 at.js 1.3 或更高版本。

### 格式

`window.targetGlobalSettings.dataProviders` 设置是一个数据提供程序数组。

有关每个数据提供程序的结构的更多信息，请参阅[数据提供程序](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)。

### 使用示例

从第三方收集数据，例如气象服务、DMP，甚至您自己的 Web 服务。然后，您可以使用这些数据来构建受众、定位内容并丰富访客配置文件。

### 该方法的好处

通过此设置，客户可以从第三方数据提供程序收集数据，例如 Demandbase、BlueKai 和自定义服务，并将这些数据作为全局 mbox 请求中的 mbox 参数传递给 Target。

支持通过异步和同步请求从多个提供程序收集数据。

使用这种方法可以轻松管理默认页面内容的闪烁，同时包含每个提供程序的独立超时时间以限制对页面性能的影响

### 注意事项

如果数据提供程序异步添加到 `window.targetGlobalSettings.dataProviders`，则将并行执行。访客 API 请求将与添加到 `window.targetGlobalSettings.dataProviders` 的函数并行执行，以将等待时间最小化。

at.js 不会尝试缓存数据。如果数据提供程序仅提取一次数据，则应确保数据已缓存，并且在调用提供程序函数时为第二次调用提供缓存的数据。

### 代码示例

在[数据提供程序](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)中可以找到几个示例。

### 相关信息链接

文档：[数据提供程序](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)

### 培训视频：

* [在 Adobe Target 中使用数据提供程序](https://helpx.adobe.com/cn/target/kt/using/dataProviders-atjs-feature-video-use.html)
* [在 Adobe Target 中实施数据提供程序](https://helpx.adobe.com/cn/target/kt/using/dataProviders-atjs-technical-video-implement.html)

## 批量配置文件更新 API {#section_92AB4820A5624C669D9A1F1B6220D4FA}

通过 API 向 Target 发送一个 .csv 文件，该文件可包含许多访客的访客配置文件更新。每个访客配置文件均可以在一次调用中通过多个页面内配置文件属性进行更新。

此选项与“客户属性”非常相似，但也存在一些区别：

* 客户属性使用 FTP 上传，而 Target 批量配置文件更新 API 则使用 HTTP POST API。
* 客户属性数据可以与 Analytics 共享。批量配置文件更新只能在 Target 中使用。
* 客户属性支持为尚未使用 Target 的用户创建配置文件。批量配置文件更新 API 仅更新现有的 Target 配置文件。
* 客户属性需要使用 Experience Cloud ID (ECID)。批量配置文件更新 API 需要 TNT ID 或 `mbox3rdPartyId`。
* 不能在 `mbox3rdPartyID` 中发送下列字符：加号 (+) 和正斜线 (/)。

### 格式

.csv 文件必须通过访客的 Target PCID 或 mboxThirdPartyId 对每个访客进行引用。不支持 Experience Cloud ID (ECID)。所有配置文件属性/值都可通过 API 创建和更新。格式详细信息可在 API 文档中找到。

### 使用示例

您在 CRM 或其他内部系统中存储那些要持续更新到 Target 的有关访客的宝贵数据，从而无需在您的页面实施中暴露配置文件数据。

### 该方法的好处

配置文件属性的数量没有限制。

通过该站点发送的配置文件属性可以通过 API 进行更新，反之亦然。

### 注意事项

批处理文件必须小于 50 MB。另外，每次上传的总行数不应超过 500,000 行。

在后续的批处理中，您在 24 小时内上传的数量或行数不受限制。但是，为了确保其他进程能够高效运行，这些数据的吸收过程在工作时间可能会受到节流限制。

对于相同 thirdPartyId，如果连续的 [V2 批量更新调用](https://developers.adobetarget.com/api/#updating-profiles)之间没有 mbox 调用，则会覆盖在第一次批量更新调用中更新的属性。

### 代码示例

请参阅[更新配置文件](https://developers.adobetarget.com/api/#updating-profiles)。

### 相关信息链接

[更新配置文件](https://developers.adobetarget.com/api/#updating-profiles)

## 单个配置文件更新 API {#section_5D7A9DD7019F40E9AEF2F66F7F345A8D}

与批量配置文件更新 API 几乎相同，但是它一次只能更新一个访客配置文件，且它通过 API 调用进行更新，而不是使用 .csv 文件。

### 格式

必须通过 Target mboxPC 值或 mboxThirdPartyId 值对访客进行标识。不支持 Experience Cloud ID (ECID)。

### 使用示例

您想要在访客执行一些离线操作，例如当访客呼叫客服中心、获得贷款、在店内使用会员卡、使用自助服务终端时，实时更新 Target。

### 该方法的好处

配置文件属性的数量没有限制。

通过该站点发送的配置文件属性可以通过 API 进行更新，反之亦然。

### 注意事项

每 24 小时限制 1,000,000（100 万）次 API 调用

仅限配置文件更新。无法为尚未使用 Target 的潜在用户创建配置文件。

### 代码示例

支持 GET 和 POST。 `https://CLIENT.tt.omtrdc.net/m2/client/profile/update?mboxPC=1368007744041-575948.01_00&profile.attr1=0&profile.attr2=1...`

### 相关信息链接

[更新配置文件](https://developers.adobetarget.com/api/#updating-profiles)

## 客户属性{#section_C47FC7980A9A4608BD1A5F0BD900FA70}

客户属性可让您通过 FTP 将访客配置文件数据上传到 Experience Cloud。上传后，即可在 Adobe Analytics 和 Adobe Target 中利用这些数据。

Target Standard 客户可以使用 5 个属性，Target Premium 客户可以使用 200 个属性。

### 格式

使用 Experience Cloud ID (ECID) 和属性名称/值对的 .csv 文件，可通过 FTP 或手动上传到 Experience Cloud UI 中。

### 使用示例

您在 CRM 或其他内部系统中存储那些要与 Adobe Experience Cloud（包括 Target 和 Analytics）共享的宝贵信息。

### 该方法的好处

即使访客尚未使用 Target，通过上传客户数据也会为该访客在 Target 中创建一个配置文件条目。

会在 Target 和 Analytics 中自动提供相同的数据。

与 API 相比，FTP 的实施方法可能更简单。

### 注意事项

Target Standard 客户可以使用 5 个属性，Target Premium 客户可以使用 200 个属性

只能通过客户属性而不是在页面上来更新值。

需要 Experience Cloud ID (ECID) 实施。

### 代码示例

Details can be found in [Create a customer attribute source and upload the data file](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html).

### 相关信息链接

[创建客户属性来源并上传数据文件](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html).