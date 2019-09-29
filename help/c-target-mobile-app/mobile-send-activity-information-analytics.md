---
description: 本部分介绍了如何将 Target 移动设备应用程序活动信息发送到 Adobe Analytics 以进行 postAhoc 分段。
seo-description: 本部分介绍了如何将 Target 移动设备应用程序活动信息发送到 Adobe Analytics 以进行 postAhoc 分段。
seo-title: 将活动信息发送到 Adobe Analytics
title: 将活动信息发送到 Adobe Analytics
uuid: 2ca1ebfe-5008-4a73-a032-1ad81f062925
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 将活动信息发送到 Adobe Analytics{#send-activity-information-to-adobe-analytics}

本部分介绍了如何将 Target 移动设备应用程序活动信息发送到 Adobe Analytics 以进行 postAhoc 分段。

**先决条件**

* 此集成要求使用 Mobile SDK 实施 Analytics 和 Target。
* 确保您已启用报表包以从 Target 接收活动信息。

   通常，您可以通过将 Target 客户端代码添加到 Analytics 报表包来实现这一点。如果您使用的是用于 Web 活动的 SiteCatalyst-Test＆Target 集成，则可能已启用此功能。如果您对此步骤有任何疑问，请联系 Adobe 客户关怀团队。

1. 获取活动信息。

   如果您在体验内容中包含类似以下内容的字符串，则 Target 会返回您可以发送到 Analytics 的促销活动信息：

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

   在此示例中，添加具有变量“`tntVal`”的节点以获取活动信息。为其他体验添加使用相应标题和信息的类似代码。

   此字符串在来自 Target 的响应中提供一个数字（例如 115110:0:0）。该数字表示活动 ID、体验 ID 和流量类型。以下是来自 Target 的响应示例：

   ```
   { 
     "tntVal": 115110:0:0", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

1. 解析 JSON 对象。

   解析回调中从 Target 返回的响应。您可以使用 NSJSONSerialization 来解析此响应并将其存储在 dict 或数组中。

   有关详细信 [息，请参阅](https://developer.apple.com/library/ios/documentation/Foundation/Reference/NSJSONSerialization_Class/#//apple_ref/occ/clm/NSJSONSerialization/JSONObjectWithData:options:error) NSJSONSerialization文档。
1. 将数据发送到 Analytics。

   将解析后的活动信息（例如上述响应中的 `tntVal`）添加到 Analytics 调用中的上下文数据对象。这个包含上下文数据的 Analytics 调用可以立即触发，也可以等到触发下一个 Analytics 调用时触发。

   例如，此调用可以在 `targetLoadRequest` 调用的回调中触发：

   ```
   [ADBMobile trackAction:@"Welcome Screen"  
         data:@{@"&&tnt" : tntVal from response}];
   ```

   >[!NOTE]
   >
   >`&&tnt` 是 Mobile SDK 中的保留事件键。Analytics 中 `tntVal` 变量的分类后处理在 Mobile SDK 中的工作方式与在 Web (JavaScript) 中的工作方式相同。在 Analytics 中处理信息后，您应该会在 Analytics 界面中看到活动和体验名称。

