---
keywords: QA;服务器端;预览;预览链接
description: 了解如何在服务器端交付中使用Adobe [!DNL Target] QA URL来执行简单的端到端活动QA，它提供了永不变更的预览链接、可选的受众定位以及从实时活动数据中分段的QA报表。
title: 能否在服务器端交付中执行活动QA？
feature: Activities
exl-id: eb6965be-92a6-452d-ac01-7ae1533239cc
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 59%

---

# 在服务器端交付中使用活动 QA

在[!DNL Adobe Target]中使用服务器端交付的QA URL来执行简单的端到端活动QA，它提供了永不变更的预览链接、可选的受众定位以及从实时活动数据中分段的QA报表。

活动QA的标准实现支持通过`pageUrl`参数传递`qa_mode`参数。 此方法非常便于standard/ajax [!DNL Target]调用。 但是，对于服务器到服务器调用，当 `pageUrl` 不可用时，这不是实施 Mobile SDK 案例的最佳方法。

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

下表说明了服务器端请求的详细信息：

| 参数 | 类型 | 默认值 | 描述 |
|--- |--- |--- |--- |
| 令牌 | 加密令牌 | 无.<br>不能为空。 | 一种加密实体，其中包含允许在活动 QA 中执行的活动 ID 列表。<br>验证规则：应为属于[!DNL Target]请求中指定的客户端的加密令牌。 令牌中指定的所有活动都应属于客户端。 |
| bypassEntryAudience | 布尔值 | false | 指定是否应评估 QA 活动的参加步骤目标，或是否应将它们视为匹配。 |
| listedActivitiesOnly | 布尔值 | false | 指定是否应单独执行 QA 活动，或是否应将它们视为当前环境中的有效活动。 |
| evaluateAsTrueAudienceIds | ID 列表 | 空列表。 | 在[!DNL Target]请求的范围内应始终评估为true的受众ID列表。 |
| evaluateAsFalseAudienceIds | ID 列表 | 空列表。 | 在[!DNL Target]请求的范围内应始终评估为false的受众ID列表。 |
| activityIndex | 整数 | 空。<br>不能为空。 | 加密令牌中的活动索引。如果 activityIndex 超过了令牌中的活动界限或者为空，则会被忽略。索引从 1 开始。<br>验证规则：应至少有一个活动索引，且应引用令牌中指定的活动。 |
| experienceIndex | 整数 | 空。 | 如果指定，则在活动定义中按索引选择体验。如果未指定或超过了界限，它将回退到活动的体验选择器策略。索引从1个验证规则开始：可以为null，或者应该引用活动中的体验。 |
