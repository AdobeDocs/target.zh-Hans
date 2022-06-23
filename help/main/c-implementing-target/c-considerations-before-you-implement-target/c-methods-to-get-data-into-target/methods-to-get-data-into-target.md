---
keywords: 实施;设置;设定;页面参数;tomcat;url 编码;页面内配置文件属性;mbox 参数;页面内配置文件属性;脚本配置文件属性;批量配置文件更新 API;单个文件更新 API;客户属性;数据提供程序
description: 将数据导入 [!DNL Target] （页面参数、配置文件属性、脚本配置文件属性、数据提供程序、单个和批量配置文件更新API、客户属性）。
title: 如何将数据导入Target?
feature: Implementation
role: Developer
exl-id: b42eb846-d423-4545-a8fe-0b8048ab689e
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 56%

---

# 方法概述

有关可用于将数据导入的不同方法的信息 [!DNL Adobe Target].

可用的方法包括：

| 方法 | 详细信息 |
| --- | --- |
| [页面参数](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/page-parameters/)<br>（也称为“mbox参数”） | 页面参数是直接通过页面代码传入的名称/值对，它们未存储在访客的配置文件中供将来使用。<br>页面参数可用于将页面数据发送到Target，而无需与访客的配置文件一起存储以供将来定位使用。 而是用来描述页面或用户在特定页面上执行的操作。 |
| [页面内配置文件属性](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/in-page-profile-attributes/)<br>（也称为“mbox内配置文件属性”） | 页面内配置文件属性是直接通过页面代码传递的名称/值对，它们存储在访客的配置文件中供将来使用。<br>页面内配置文件属性允许将特定于用户的数据存储在 Target 的配置文件中，供以后进行定位和分段。 |
| [脚本配置文件属性](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/script-profile-attributes/) | 脚本配置文件属性是 Target 解决方案中定义的名称/值对。该值是在每个服务器调用时，通过在 Target 服务器上执行一段 JavaScript 代码来确定。<br>为访客评估受众和活动用户编写一小段代码，该代码片段会在每次 mbox 调用时、且在评估访客的受众群体和活动成员资格之前执行。 |
| [数据提供程序](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/data-providers/) | 通过数据提供商，您可以轻松将数据从第三方传递到Target。 |
| [批量配置文件更新 API](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/bulk-profile-update-api/) | 通过 API 向 Target 发送一个 .csv 文件，该文件可包含许多访客的访客配置文件更新。每个访客配置文件均可以在一次调用中通过多个页面内配置文件属性进行更新。 |
| [单个配置文件更新 API](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/single-profile-update-api/) | 与批量配置文件更新API几乎相同，只是一次更新一个访客配置文件，这与API调用中的一行相同，而不是与.csv文件相同。 |
| [客户属性](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/customer-attributes/) | 客户属性可让您通过 FTP 将访客配置文件数据上传到 Experience Cloud。上传后，使用Adobe Analytics和Adobe Target中的数据。 |












