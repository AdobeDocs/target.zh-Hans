---
keywords: mobile;tntVal;analytics;adobe分析；集成；sdk;mobile sdk;
description: 本节介绍如何将Adobe Target移动应用程序活动信息发送到Adobe Analytics以便进行临时细分。
title: 将Adobe Target活动信息发送到Adobe Analytics
uuid: 2ca1ebfe-5008-4a73-a032-1ad81f062925
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 将活动信息发送到 Adobe Analytics{#send-activity-information-to-adobe-analytics}

This section describes how to send [!DNL Target] mobile app activity information to Adobe [!DNL Analytics] for post hoc segmentation.

**先决条件**

* This integration requires that [!DNL Analytics] and [!DNL Target] are implemented using the mobile SDK.
* Ensure that your report suite is enabled to receive activity information from [!DNL Target].

   This is usually done by adding the [!DNL Target] client code to the [!DNL Analytics] report suite. 如果您使用的是用于 Web 活动的 SiteCatalyst-Test＆Target 集成，则可能已启用此功能。如果您对此步骤有任何疑问，请联系 Adobe 客户关怀团队。

1. 获取活动信息。

   If you include a string like the following in your experience content, [!DNL Target] returns the activity information that you can send to [!DNL Analytics]:

   ```
   ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}
   ```

   将体验 json 代码中的文本替换为类似于以下示例的内容：

   ```
   { 
     "tntVal": ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

   In this example, a node with the variable `tntVal` is added to obtain the activity information. 为其他体验添加使用相应标题和信息的类似代码。

   This string delivers a number (such as 115110:0:0) in the response from [!DNL Target]. 这表示活动ID、体验ID和流量类型。 The following is a sample response from [!DNL Target]:

   ```
   { 
     "tntVal": 115110:0:0", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

1. 解析 JSON 对象。

   Parse the response that came back from [!DNL Target] in the callback. You can use `NSJSONSerialization` to parse this response and store it in a dictionary or an array.

   有关详细信 [息，请参阅](https://developer.apple.com/library/ios/documentation/Foundation/Reference/NSJSONSerialization_Class/#//apple_ref/occ/clm/NSJSONSerialization/JSONObjectWithData:options:error) NSJSONSerialization文档。

1. 将数据发送到 [!DNL Analytics].

   将解析后的活动信息（例如上述响应中的 `tntVal`）添加到 调用中的上下文数据对象。[!DNL Analytics]This [!DNL Analytics] call containing the context data can be fired immediately or it can wait until the next [!DNL Analytics] call is fired.

   例如，此调用可以在 `targetLoadRequest` 调用的回调中触发：

   ```
   [ADBMobile trackAction:@"Welcome Screen"  
         data:@{@"&&tnt" : tntVal from response}];
   ```

   >[!NOTE]
   >
   >`&&tnt` 是 Mobile SDK 中的保留事件键。The post-classification of the `tntVal` variable in [!DNL Analytics] works in the same way in the mobile SDK as it does on the web (JavaScript). After the information is processed in [!DNL Analytics], you should see activity and experience names in the [!DNL Analytics] interface.

