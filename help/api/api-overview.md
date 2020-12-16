---
keywords: api;apis;admin api;delivery api;reporting api;profile api
description: 有关Adobe TargetAPI的信息，包括管理员、投放、报告和用户档案API。
title: Adobe TargetAPI概述
feature: api
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 1%

---


# Adobe TargetAPI概述

[!DNL Adobe Target] API可以按类型进行分组。

| API类型 | 它使您能够 | 下载链接 | 其他有用链接 |
| --- | --- | --- |--- |
| 管理员 | 创建、修改和删除活动、受众、优惠和其他对象（包括[!DNL Recommendations]实体、标准、设计等）。 [!DNL Recommendations] API是一种管理API类型。) | <UL><li>[目标管理员API邮递员集合](https://developers.adobetarget.com/api/#admin-postman-collection)</li><li>[RecommendationsAPI邮递员集](https://developers.adobetarget.com/api/recommendations/#section/Postman)</li></ul> | [在Recommendations](https://experienceleague.adobe.com/docs/target-learn/recommendations-api-tutorial/recs-api-overview.html) Tutorials *中使用Adobe Target* |
| 交付 | 从[!DNL Target]检索优化的个性化内容，以便向最终用户投放。 | [目标投放API邮递员集合](https://developers.adobetarget.com/api/delivery-api/#section/Getting-Started/Postman-Collection) |  |
| 报表 | 导出活动结果和其他报告结果。 | 报告API包含在[目标管理API邮件收藏集](https://developers.adobetarget.com/api/#admin-postman-collection)中。 |  |
| Profile | 检索和修改存储在Adobe Target的用户用户档案。 | [目标用户档案API邮递员集合](https://developers.adobetarget.com/api/#profiles) |  |

>[!NOTE]
>
>[!DNL Target]管理API（包括[!DNL Recommendations] API）和[!DNL Target]投放API之间有重要区别：
>
>* 管理员API允许您配置[!DNL Target]的各个方面，您也可以在[!DNL Target] UI中进行配置。 管理员API需要身份验证。
   >
   >
* 投放API允许您检索内容。 投放API不需要身份验证。
>
>
要使用[!DNL Target]管理API，您首先需要使用Adobe I/O配置身份验证。有关详细信息，请参阅&#x200B;*Adobe TargetTutorials*&#x200B;中的[配置身份验证](https://experienceleague.adobe.com/docs/target-learn/tutorials/apis/configure-io-target-integration.html)。
