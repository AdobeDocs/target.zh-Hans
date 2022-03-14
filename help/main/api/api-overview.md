---
keywords: API;API；管理API；交付API；报表API；配置文件API
description: 查找Adobe [!DNL Target] API，包括管理、交付、报表和用户档案API。
title: 在哪里可以找到 [!DNL Target] API和SDK文档？
feature: APIs/SDKs
role: Developer
exl-id: 2a0232cc-9a6a-42f4-afb6-4b3e2b13939c
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 1%

---

# Adobe [!DNL Target] API概述

[!DNL Adobe Target] API可以按类型进行分组：管理、交付、报告和用户档案API。

| API类型 | 它使您能够执行的操作 | 下载链接 | 其他有用链接 |
| --- | --- | --- |--- |
| 管理员 | 创建、修改和删除活动、受众、选件和其他对象(包括 [!DNL Recommendations] 实体、标准、设计等。 的 [!DNL Recommendations] API是一种管理员API类型。) | <UL><li>[Target管理员API Postman集合](https://developers.adobetarget.com/api/#admin-postman-collection)</li><li>[Recommendations API Postman Collection](https://developers.adobetarget.com/api/recommendations/#section/Postman)</li></ul> | [使用Recommendations API](https://experienceleague.adobe.com/docs/target-learn/recommendations-api-tutorial/recs-api-overview.html) in *Adobe TargetTutorials* |
| 交付 | 从中检索优化和个性化内容 [!DNL Target] ，以交付给最终用户。 | [Target交付API Postman收集](https://developers.adobetarget.com/api/delivery-api/#section/Getting-Started/Postman-Collection) |  |
| 报表 | 导出活动结果和其他报表结果。 | 报表API包含在 [Target管理员API Postman集合](https://developers.adobetarget.com/api/#admin-postman-collection). |  |
| Profile | 检索和修改存储在Adobe Target中的用户配置文件。 | [Target配置文件API Postman集合](https://developers.adobetarget.com/api/#profiles) |  |

>[!NOTE]
>
>两者之间有重要区别 [!DNL Target] 管理员API(包括 [!DNL Recommendations] API)和 [!DNL Target] 交付API:
>
>* 管理员API允许您配置 [!DNL Target] ，您也可以在 [!DNL Target] UI。 管理员API需要身份验证。
>
>* 交付API允许您检索内容。 交付API不需要身份验证。
>
>使用 [!DNL Target] 管理员API，您首先需要使用Adobe I/O配置身份验证。有关更多信息，请参阅 [配置身份验证](https://experienceleague.adobe.com/docs/target-learn/tutorials/apis/configure-io-target-integration.html) in *Adobe TargetTutorials*.
