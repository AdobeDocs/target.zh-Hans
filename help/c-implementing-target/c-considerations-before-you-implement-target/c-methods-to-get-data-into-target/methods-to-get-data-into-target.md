---
keywords: 实施;设置;设定;页面参数;tomcat;url 编码;页面内配置文件属性;mbox 参数;页面内配置文件属性;脚本配置文件属性;批量配置文件更新 API;单个文件更新 API;客户属性;数据提供程序
description: 将数据导入目标(页面参数、用户档案属性、脚本用户档案属性、数据提供商、单个和批量用户档案更新API、客户属性)。
title: 如何将数据导入目标?
feature: 实施
role: Developer
exl-id: b42eb846-d423-4545-a8fe-0b8048ab689e
translation-type: tm+mt
source-git-commit: e8c25685341319fea4381386cad1ce0c5b80face
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 61%

---

# 方法概述

有关将数据导入[!DNL Adobe Target]的不同方法的信息。

可用的方法包括：

| 方法 | 详细信息 |
| --- | --- |
| [页面参数](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/page-parameters.md)<br>（也称为“mbox参数”） | 页面参数是直接通过页面代码传入的名称/值对，它们未存储在访客的配置文件中供将来使用。<br>页面参数对于将页面数据发送到目标很有用，因为该访客无需与用户档案一起存储，以便将来进行定位。而是用来描述页面或用户在特定页面上执行的操作。 |
| [页内用户档案属性](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/in-page-profile-attributes.md)<br>(也称为“mbox内用户档案属性”) | 页面内配置文件属性是直接通过页面代码传递的名称/值对，它们存储在访客的配置文件中供将来使用。<br>页面内配置文件属性允许将特定于用户的数据存储在 Target 的配置文件中，供以后进行定位和分段。 |
| [脚本配置文件属性](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/script-profile-attributes.md) | 脚本配置文件属性是 Target 解决方案中定义的名称/值对。该值是在每个服务器调用时，通过在 Target 服务器上执行一段 JavaScript 代码来确定。<br>为访客评估受众和活动用户编写一小段代码，该代码片段会在每次 mbox 调用时、且在评估访客的受众群体和活动成员资格之前执行。 |
| [数据提供者](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/data-providers.md) | 数据提供商使您能够轻松地将数据从第三方传递到目标。 |
| [批量配置文件更新 API](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/bulk-profile-update-api.md) | 通过 API 向 Target 发送一个 .csv 文件，该文件可包含许多访客的访客配置文件更新。每个访客配置文件均可以在一次调用中通过多个页面内配置文件属性进行更新。 |
| [单个配置文件更新 API](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/single-profile-update-api.md) | 几乎与批量用户档案更新API相同，但每次更新一个访客用户档案，在API调用中排行，而不是.csv文件。 |
| [客户属性](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/customer-attributes.md) | 客户属性可让您通过 FTP 将访客配置文件数据上传到 Experience Cloud。上传后，请使用Adobe Analytics和Adobe Target中的数据。 |












