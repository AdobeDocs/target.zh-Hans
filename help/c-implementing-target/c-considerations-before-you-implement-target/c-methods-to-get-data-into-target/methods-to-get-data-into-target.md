---
keywords: 实施;设置;设定;页面参数;tomcat;url 编码;页面内配置文件属性;mbox 参数;页面内配置文件属性;脚本配置文件属性;批量配置文件更新 API;单个文件更新 API;客户属性;数据提供程序
description: 将数据导入目标(页面参数、用户档案属性、脚本用户档案属性、数据提供商、单个和批量用户档案更新API、客户属性)。
title: 如何将数据导入目标?
feature: 实施
role: Developer
exl-id: b42eb846-d423-4545-a8fe-0b8048ab689e
translation-type: tm+mt
source-git-commit: 70d4c5b4166081751246e867d90d43b67efa5469
workflow-type: tm+mt
source-wordcount: '1082'
ht-degree: 84%

---

# 方法概述

有关将数据导入[!DNL Adobe Target]的不同方法的信息。

可用的方法包括：

| 方法 | 详细信息 |
| --- | --- |
| [](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/page-parameters.md)<br>页面参数（也称为“mbox 参数”） | 页面参数是直接通过页面代码传入的名称/值对，它们未存储在访客的配置文件中供将来使用。<br>页面参数可用于将其他页面数据发送到 Target，这些数据不需要与访客配置文件一起存储以供将来的定位使用，而是用来描述页面或用户在特定页面上执行的操作。 |
| [](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/in-page-profile-attributes.md)<br>页面内配置文件属性（也称为“in-mbox”配置文件属性） | 页面内配置文件属性是直接通过页面代码传递的名称/值对，它们存储在访客的配置文件中供将来使用。<br>页面内配置文件属性允许将特定于用户的数据存储在 Target 的配置文件中，供以后进行定位和分段。 |
| [脚本配置文件属性](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/script-profile-attributes.md) | 脚本配置文件属性是 Target 解决方案中定义的名称/值对。该值是在每个服务器调用时，通过在 Target 服务器上执行一段 JavaScript 代码来确定。<br>为访客评估受众和活动用户编写一小段代码，该代码片段会在每次 mbox 调用时、且在评估访客的受众群体和活动成员资格之前执行。 |
| [数据提供者](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/data-providers.md) | 数据提供商是一项功能，使您能够轻松地将数据从第三方传递到目标。 |
| 批量配置文件更新 API | 通过 API 向 Target 发送一个 .csv 文件，该文件可包含许多访客的访客配置文件更新。每个访客配置文件均可以在一次调用中通过多个页面内配置文件属性进行更新。 |
| 单个配置文件更新 API | 几乎与批量用户档案更新API相同，但每次更新一个访客用户档案，在API调用中排行，而不是.csv文件。 |
| 客户属性 | 客户属性可让您通过 FTP 将访客配置文件数据上传到 Experience Cloud。上传后，即可在 Adobe Analytics 和 Adobe Target 中利用这些数据。 |







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

几乎与批量用户档案更新API相同，但每次更新一个访客用户档案，在API调用中排行，而不是.csv文件。

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

有关详细信息，请参阅[创建客户属性源并上传数据文件](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html)。

### 相关信息链接

[创建客户属性来源并上传数据文件](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).
