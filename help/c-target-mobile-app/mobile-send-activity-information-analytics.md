---
keywords: mobile;tntVal;analytics;adobe analytics;integration;sdk;mobile sdk;
description: 了解如何将Adobe [!DNL Target] 移动应用程序活动信息发送到Adobe Analytics以进行临时后细分。
title: 能否将移动应用活动信息发送到Analytics?
feature: 实施移动
role: Developer
exl-id: 33812f14-320f-40c3-8234-d6006fb4d6bc
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 30%

---

# 将活动信息发送到 Adobe Analytics

本节介绍如何将[!DNL Target]移动应用程序活动信息发送到Adobe [!DNL Analytics]以进行即席后分段。

**先决条件**

* 此集成要求使用移动SDK实现[!DNL Analytics]和[!DNL Target]。
* 确保您的报表包已启用，可从[!DNL Target]接收活动信息。

   这通常通过将[!DNL Target]客户端代码添加到[!DNL Analytics]报表包来完成。 如果您使用的是用于 Web 活动的 SiteCatalyst-Test＆Target 集成，则可能已启用此功能。如果您对此步骤有任何疑问，请联系 Adobe 客户关怀团队。

1. 获取活动信息。

   如果您的体验内容中包含如下字符串，[!DNL Target]将返回可发送到[!DNL Analytics]的活动信息：

   ```javascript
   ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}
   ```

   将体验 json 代码中的文本替换为类似于以下示例的内容：

   ```javascript
   { 
     "tntVal": ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

   在此示例中，添加变量`tntVal`的节点以获取活动信息。 为其他体验添加使用相应标题和信息的类似代码。

   此字符串在[!DNL Target]的响应中传递一个数字(如115110:0:0)。 这表示活动ID、体验ID和流量类型。 以下是[!DNL Target]的示例响应：

   ```javascript
   { 
     "tntVal": 115110:0:0", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

1. 解析 JSON 对象。

   解析从回调中的[!DNL Target]返回的响应。 可以使用`NSJSONSerialization`分析此响应并将其存储在字典或数组中。

   有关详细信息，请参阅[NSJSONSerialization文档](https://developer.apple.com/library/ios/documentation/Foundation/Reference/NSJSONSerialization_Class/#//apple_ref/occ/clm/NSJSONSerialization/JSONObjectWithData:options:error)。

1. 将数据发送到 [!DNL Analytics].

   将解析后的活动信息（例如上述响应中的 `tntVal`）添加到 调用中的上下文数据对象。[!DNL Analytics]包含上下文数据的此[!DNL Analytics]调用可以立即触发，也可以等到下一个[!DNL Analytics]调用被触发。

   例如，此调用可以在 `targetLoadRequest` 调用的回调中触发：

   ```javascript
   [ADBMobile trackAction:@"Welcome Screen"  
         data:@{@"&&tnt" : tntVal from response}];
   ```

   >[!NOTE]
   >
   >`&&tnt` 是 Mobile SDK 中的保留事件键。[!DNL Analytics]中`tntVal`变量的后分类在移动SDK中的工作方式与在Web上相同(JavaScript)。 在[!DNL Analytics]中处理信息后，您应会在[!DNL Analytics]界面中看到活动和体验名称。
