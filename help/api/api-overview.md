---
keywords: api;apis;admin api;delivery api;reporting api;profile api
description: 有关Adobe TargetAPI的信息，包括管理员、投放、报告和用户档案API。
title: Adobe TargetAPI概述
topic: APIs
translation-type: tm+mt
source-git-commit: 240c0f36bf39ee16d8d8e1b66ad6bed54b4f1fed
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 1%

---


# Adobe TargetAPI概述

[!DNL Adobe Target] API可以按类型进行分组。

| API类型 | 它使您能够 | 下载链接 | 其他有用链接 |
| --- | --- | --- |--- |
| 管理员 | 创建、修改和删除活动、受众、优惠和其他对象( [!DNL Recommendations] 包括实体、标准、设计等)。 API [!DNL Recommendations] 是一种管理API类型。) | <UL><li>[目标管理员API邮递员集合](https://developers.adobetarget.com/api/#admin-postman-collection)</li><li>[RecommendationsAPI邮递员集](https://developers.adobetarget.com/api/recommendations/#section/Postman)</li></ul> | [在RecommendationsAdobe Target中](https://docs.adobe.com/content/help/en/target-learn/recommendations-api-tutorial/recs-api-overview.html) 使用 *APITutorials* |
| 交付 | 从中检索优化和个性化的 [!DNL Target] 内容，以便投放给最终用户。 | [目标投放API邮递员集合](https://developers.adobetarget.com/api/delivery-api/#section/Getting-Started/Postman-Collection) |  |
| 报表 | 导出活动结果和其他报告结果。 | 报告API包含在 [目标管理API邮递员集合中](https://developers.adobetarget.com/api/#admin-postman-collection)。 |  |
| Profile | 检索和修改存储在Adobe Target的用户用户档案。 | [目标用户档案API邮递员集合](https://developers.adobetarget.com/api/#profiles) |  |

>[!NOTE]
>
>管理API(包括 [!DNL Target] API)和投放API [!DNL Recommendations] 之间有重要 [!DNL Target] 的区别：
>
>* 管理员API允许您配置UI [!DNL Target] 中还可以配置的各个 [!DNL Target] 方面。 管理员API需要身份验证。
   >
   >
* 投放API允许您检索内容。 投放API不需要身份验证。
>
>
要使用 [!DNL Target] 管理员API，您首先需要使用AdobeI/O配置身份验证。有关详细信息，请参 [阅在Adobe TargetTutorials](https://docs.adobe.com/content/help/en/target-learn/tutorials/apis/configure-io-target-integration.html) 中配 *置身份验证*。
