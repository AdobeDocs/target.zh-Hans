---
keywords: QA;服务器端;预览;预览链接
description: 了解如何在服务器端交付中使用Adobe [!DNL Target] QA URL来执行简单的端到端活动QA，它提供了永不变更的预览链接、可选的受众定位以及从实时活动数据中分段的QA报表。
title: 能否在服务器端交付中执行活动QA？
feature: Activities
exl-id: eb6965be-92a6-452d-ac01-7ae1533239cc
TQID: 'https://experienceleague.adobe.com/zZJmFqpXtAigTiEWMZhRqXBJqvG3ANLussSPE3-NoDA'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0a683f6e68bb7481b9e45c91a275a46b84a1ffd8
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 18%
---
# 在服务器端交付中使用活动 QA {#qa-server-side}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何在服务器端[!DNL Adobe Target]调用中传递活动QA参数，以便在`pageUrl`不可用时测试活动。

>[!ENDSHADEBOX]

活动QA的标准实现支持通过`pageUrl`参数传递`qa_mode`参数。 此方法非常便于standard/ajax [!DNL Target]调用。 但是，它不适用于服务器到服务器调用，例如Mobile SDK实现，该实现中的`pageUrl`不可用。 在这些情况下，请在请求本身中传递QA参数，这会保留与实时活动数据分段的相同预览链接、可选受众定位和QA报表。

以下代码示例显示了服务器端调用中的活动 QA：

```json
{
  "mbox" : "orderConfirmPage",
  "clientSideAnalyticsLogging": true,
  "clicked" : true,
  "tntId" : "12121212.17_01",
  "order" : {
    ...
  },
  "profileParameters" : {
    ...
  },
  "mboxParameters" : {
    ...
  },
  "requestLocation" : {
    ...
  },
  "qaMode" : {
    "token" : "<encrypted token string>",
    "bypassEntryAudience" : true,
    "listedActivitiesOnly" : true,
    "evaluateAsTrueAudienceIds" : [audienceId1, audienceId2...],
    "evaluateAsFalseAudienceIds" : [audienceId3, audienceId4...],
    "previewIndexes" : [
       {
         "activityIndex" : 1,
         "experienceIndex" : 1
       }
     ],
  },
  "mboxTrace" : true
}
```

下表描述了服务器端请求的参数：

| 参数 | 类型 | 默认值 | 描述 |
|--- |--- |--- |--- |
| 令牌 | 加密令牌 | 无。 不能为空。 | 包含允许在活动QA中执行的活动ID列表的加密实体。<br>验证规则：令牌必须是属于[!DNL Target]请求中指定的客户端的加密令牌。 令牌中指定的所有活动都必须属于客户端。 |
| bypassEntryAudience | 布尔值 | false | 指定是评估QA活动的登入步骤目标还是将其视为匹配。 |
| listedActivitiesOnly | 布尔值 | false | 指定QA活动是单独执行，还是作为当前环境的活动活动进行计算。 |
| evaluateAsTrueAudienceIds | ID 列表 | 空列表 | 在[!DNL Target]请求的范围内始终被评估为true的受众ID列表。 |
| evaluateAsFalseAudienceIds | ID 列表 | 空列表 | 在[!DNL Target]请求的范围内始终被评估为false的受众ID列表。 |
| activityIndex | 整数 | Null. 不能为空。 | 加密令牌中的活动索引。 如果`activityIndex`为null或超出令牌中活动的边界，则会忽略它。 索引以1.<br>验证规则开头：至少需要一个活动索引，并且必须引用令牌中指定的活动。 |
| experienceIndex | 整数 | Null | 如果指定，则在活动定义中按索引选择体验。 如果未指定或超出边界，它将返回到活动的体验选择器策略。 索引以1.<br>验证规则开头：该值可以为null，或者必须引用活动中的体验。 |
