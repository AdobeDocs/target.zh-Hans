---
keywords: 响应令牌；令牌；插件；插件；at.js；响应
description: 了解如何在Adobe [!DNL Target] 特定于输出的信息中使用响应令牌，以用于调试和与第三方工具集成。
title: 什么是响应令牌？如何使用它们？
feature: 管理和配置
role: Administrator
exl-id: d0c1e914-3172-466d-9721-fe0690abd30b
source-git-commit: a63b123ed180a818de5338656781957931abd755
workflow-type: tm+mt
source-wordcount: '1650'
ht-degree: 27%

---

# 响应令牌

响应令牌允许您自动将特定于[!DNL Adobe Target]的信息输出到品牌的网页。 此信息可以包括有关活动、选件、体验、用户配置文件、地理信息等的详细信息。 这些详细信息可提供额外的响应数据，以便与内部或第三方工具共享或用于调试。

响应令牌允许您选择要使用的变量（键值对中），然后允许将这些变量作为[!DNL Target]响应的一部分发送。 您使用交换机启用一个变量，该变量随[!DNL Target]响应一起发送，这些响应可在网络调用中验证。 响应令牌也可在[!UICONTROL 预览]模式下使用。

插件和响应令牌之间的一个关键区别在于，插件会将JavaScript交付到交付时执行的页面。 但是，响应令牌会交付一个对象，该对象随后可以使用事件侦听器进行读取和操作。 响应令牌方法更安全，并且允许更轻松地开发和维护第三方集成。

>[!NOTE]
>
>响应令牌在at.js版本1.1或更高版本中可用。

>[!IMPORTANT]
>
>在将来的版本中，[!DNL Adobe Experience Platform Web SDK]将提供响应令牌（日期待定）。 以下关于响应令牌和Platform Web SDK的文档包含为潜在峰值。

| Target SDK | 建议的操作 |
|--- |--- |
| [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) | 确保您使用的是Platform Web SDK版本2.6.0或更高版本。 有关下载最新版Platform Web SDK的信息，请参阅&#x200B;*Platform Web SDK概述*&#x200B;指南中的[安装SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html)。 有关每个Platform Web SDK版本中新功能的信息，请参阅&#x200B;*Platform Web SDK概述*&#x200B;指南中的[发行说明](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html)。 |
| [at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) | 确保您使用的是 at.js 版本 1.1 或更高版本。有关下载最新版本 at.js 的信息，请参阅[下载 at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)。有关每个 at.js 版本新功能的信息，请参阅 [at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)。<br>我们鼓励使用 at.js 的客户使用响应令牌而不是插件。某些插件依赖的内部方法在mbox.js中存在，但在at.js中不存在，这些插件会交付但失败。 有关更多信息，请参阅 [at.js 限制](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-limitations.md)。 |

## 使用响应令牌 {#section_A9E141DDCBA84308926E68D05FD2AC62}

1. 确保您使用的是Platform Web SDK版本2.6.0（或更高版本）或at.js版本1.1（或更高版本）。

   有关更多信息：

   * **平台Web SDK**:请参 [阅平台](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html) Web SDK概 *述指南中的* 安装SDK。
   * **at.js**:请参 [阅下载at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#concept_1E1F958F9CCC4E35AD97581EFAF659E2)。

1. 在[!DNL Target]中，单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 响应令牌]**。

   ![](assets/response_tokens-new.png)

1. 激活所需的响应令牌，如`activity.id`和`option.id`。

   以下参数默认可用：

   | 类型 | 参数 | 注释 |
   |--- |--- |--- |
   | 内置配置文件 | `profile.activeActivities` | 返回该访客符合条件的 `activityIds` 数组。它会随着符合条件的用户数量的增加而递增。例如，在具有两个[!DNL Target]请求来交付两个不同活动的页面上，第二个请求包含两个活动。 |
   |  | `profile.isFirstSession` | 返回“true”或“false”。 |
   |  | `profile.isNewSession` | 返回“true”或“false”。 |
   |  | `profile.daysSinceLastVisit` | 返回自该访客上次访问后已过的天数。 |
   |  | `profile.tntId` | 返回访客的 tntID |
   |  | `profile.marketingCloudVisitorId` | 返回访客的 Experience Cloud 访客 ID。 |
   |  | `profile.thirdPartyId` | 返回访客的第三方 ID。 |
   |  | `profile.categoryAffinity` | 返回访客最喜欢的类别。 |
   |  | `profile.categoryAffinities` | 将该访客排名前 5 的类别的数组作为字符串返回。 |
   | 活动 | `activity.name`<br>`activity.id`<br>`experience.name`<br>`experience.id`<br>`option.name`<br>`option.id` | 当前活动的详细信息。请注意，“option”等同于“offer”。 |
   | 地域 | `geo.country`<br>`geo.state`<br>`geo.city`<br>`geo.zip`<br>`geo.dma`<br>`geo.domainName`<br>`geo.ispName`<br>`geo.connectionSpeed`<br>`geo.mobileCarrier` | 请参阅[地域](/help/c-target/c-audiences/c-target-rules/geo.md)以了解在活动中使用地域定位的详细信息。 |
   | 流量分配方法<br>(仅适用于[!UICONTROL 自动定位]和[!UICONTROL Automated Personalization]活动。) | `experience.trafficAllocationId` | 如果访客从“控制”流量中收到体验，则返回0；如果访客从“目标”流量分发中收到体验，则返回1。 |
   |  | `experience.trafficAllocationType` | 返回“控制”或“已定位”。 |

   用户配置文件属性和客户属性也会显示在列表中。

   >[!NOTE]
   >
   >包含特殊字符的参数不会显示在列表中。只支持字母数字字符和下划线。

1. （视情况而定）要将配置文件参数用作响应令牌，但该参数尚未通过[!DNL Target]请求传递，因此未加载到[!DNL Target] UI中，您可以使用[!UICONTROL 添加响应令牌]按钮将配置文件添加到UI。

   单击&#x200B;**[!UICONTROL 添加响应令牌]**，提供令牌名称，然后单击&#x200B;**[!UICONTROL 激活]**。

   ![](assets/response_token_create.png)

1. 创建一个活动。

## 监听响应和读取响应令牌

用于侦听[!DNL Target]响应和读取响应令牌的过程会因您是使用[!DNL Platform Web SDK]还是at.js实施而异。

### ![Adobe Experience Platform Web SDK](/help/assets/platform.png) [!DNL Platform Web SDK] 使用Handle对象类标记

使用Handle对象类，该类具有元数据对象和数据对象来侦听[!DNL Target]响应并读取响应令牌。

以下响应示例将[!DNL Platform Web SDK]自定义事件处理程序直接添加到HTML页面（该表说明了代码中使用的对象）：

| 对象 | 信息 |
| --- | --- |
| 类型 — Personalization.decision | 是由[!DNL Target]还是Offer decisioning提供商做出决定。 |
| DecisionProvider - TGT | TGT-[!DNL Target]. [!DNL Target] 将响应令牌元数据和值提供到页面。 |
| Meta | 传递到页面的元数据。 |
| 数据 | 传递到页面的元数据的值。 |

```html
<html>

<head>
 ...
 <script src="alloy.js"></script>
 <script>
  {
   "requestId": "4d0a7cfd-952c-408c-b3b8-438edc38250a",
   "handle": [{
    "type": "personalization:decisions",
    "payload": [{
     "id": "....",
     "scope": "__view__",
     "scopeDetails": {
      "decisionProvider": "TGT",
      "activity": {
       "id": "..."
      },
      "experience": {
       "id": "...."
      }
     },
     "items": [{
      "id": "123",
      "schema": "https://ns.adobe.com/personalization/dom-action",
      "meta": {
       "activity.id": "...",
       "activity.name": "...",
       "profile.foo": "...",
       "profile.bar": "..."
      },
      "data": {
       "id": "123",
       "type": "setHtml",
       "selector": "#foo",
       "prehidingSelector": "#foo",
       "content": "<div>Hello world</div>"
      }
     }]
    }]
   }]
  }
  });
 </script>
</head>

<body>
 ...
</body>

</html>
```

### ![at.js使用](/help/assets/atjs.png) 自定义事件的badgeat.js

使用 [at.js 自定义事件](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md)来监听 响应并读取响应令牌。[!DNL Target]

以下代码示例可将一个 [!DNL at.js] 自定义事件处理程序直接添加到 HTML 页面：

```html
<html> 
  <head> 
    .... 
    <script src="at.js"></script> 
    <script> 
      document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(e) { 
        console.log("Request succeeded", e.detail); 
      }); 
    </script> 
  <head> 
  <body> 
  ... 
  </body> 
</html>
```

## 响应令牌常见问题解答 {#section_3DD5F32C668246289CDF9B4CDE1F536D}

**激活或停用响应令牌需要使用哪个角色？**

响应令牌只能由具有[!DNL Target] [!UICONTROL 管理员]角色的用户激活或停用。

**如果我运行的是[!DNL Platform Web SDK] 2.6.0（或更早版本），会发生什么情况？

您无权访问响应令牌。

**如果我运行的是at.js 1.0（或更早版本），会发生什么情况？**

您会看到响应令牌，但at.js无法使用它们。

**[!DNL Target Classic]我是否可以同时使用 插件和响应令牌？**

插件和响应令牌可并行使用；但是，插件将来会被弃用。

**响应令牌是通过所有响应 [!DNL Target] 交付，还是仅通 [!DNL Target] 过交付活动的响应交付？**

响应令牌仅通过传递活动的[!DNL Target]响应来传递。

**我的 [!DNL Target Classic] 插件包含JavaScript。如何使用响应令牌复制其功能？**

迁移到响应令牌时，此类JavaScript必须保留在您的代码库或标签管理解决方案中。 您可以使用[!DNL Platform Web SDK]或[!DNL at.js]自定义事件触发此代码，并将响应令牌值传递给您的JavaScript函数。

**为什么我的配置文件/客户属性参数不会显示在响应令牌列表中？**

[!DNL Target] 通常每15分钟刷新一次参数。此刷新取决于用户操作，并且仅在您查看响应令牌页面时才会刷新数据。 如果您的参数未显示在响应令牌列表中，则[!DNL Target]尚未刷新数据。

此外，如果参数包含非字母数字字符或除下划线以外的任何符号以外的任何内容，则该参数不会显示在列表中。 目前，仅支持字母数字和下划线字符。

**如果响应令牌使用的是已删除的配置文件脚本或配置文件参数，该令牌是否仍会交付内容？**

响应令牌从用户配置文件中提取信息，然后交付该信息。如果删除配置文件脚本或参数，并不意味着该信息已从用户配置文件中删除。用户配置文件仍具有与配置文件脚本对应的数据。 响应令牌可继续交付内容。 对于未在其配置文件中保存该信息的用户，或者对于新访客，由于该数据不存在于其配置文件中，因此不会交付该令牌。

[!DNL Target] 不会自动关闭令牌。如果您要删除配置文件脚本并且不再希望交付该令牌，则必须自行关闭该令牌。

**我重命名了我的配置文件脚本，但为什么使用该脚本的令牌仍使用旧名称？**

如上所述，响应令牌处理的是为用户保存的配置文件信息。即使您重命名了配置文件脚本，访问过您网站的用户的配置文件脚本值也会保存在他们的配置文件中。 令牌将继续选取用户配置文件中已保存的旧值。 如果您现在想要以新名称交付内容，则必须关闭以前的令牌，然后打开新令牌。

**如果我的属性发生更改，何时会从列表中删除它们？**

[!DNL Target] 会定期刷新属性。任何未打开的属性都将在下次刷新时删除。 但是，如果您有一个已打开且已删除的属性，则该脚本在您将其关闭之前不会从属性列表中删除。 例如，您删除了用作令牌的配置文件脚本。 [!DNL Target]如果删除或重命名属性， 只会从列表中删除已关闭的属性。

## 将数据发送到Google Analytics

以下各节介绍如何将[!DNL Target]数据发送到Google Analytics。 通过响应令牌发送的数据也可以发送到其他第三方集成。

### ![AEP徽](/help/assets/platform.png) 章通过Platform Web SDK向Google Analytics发送数据

Google Analytics可以通过Platform Web SDK版本2.6.0（或更高版本）通过在HTML页面中添加以下代码来发送数据。

>[!NOTE]
>
>确保响应令牌键值对位于`alloy(“sendEvent”`对象下。

```
<script type="text/javascript"> 
   (function(i, s, o, g, r, a, m) { 
   i['GoogleAnalyticsObject'] = r; 
   i[r] = i[r] || function() { 
   (i[r].q = i[r].q || []).push(arguments) 
   }, i[r].l = 1 * new Date(); 
   
   
   a = s.createElement(o), 
   m = s.getElementsByTagName(o)[0]; 
   a.async = 1; 
   a.src = g; 
   m.parentNode.insertBefore(a, m) 
   })(window, document, 'script', 'https://www.google-analytics.com/analytics.js', 'ga'); 
   ga('create', 'Google Client Id', 'auto'); 
</script> 
<script type="text/javascript">
   alloy("sendEvent", {
   
   
   })
   .then(({ renderedPropositions, nonRenderedPropositions }) => {
   // concatenate all the propositions
   const propositions = [...renderedPropositions, ...nonRenderedPropositions];
   // extractResponseTokens() extract the meta from item -> meta
   const tokens = extractResponseTokens(propositions);
   const activityNames = []; 
   const experienceNames = []; 
   const uniqueTokens = distinct(tokens); 
   
   
   uniqueTokens.forEach(token => { 
   activityNames.push(token["activity.name"]); 
   experienceNames.push(token["experience.name"]); 
   }); 
   
   
   ga('send', 'event', { 
   eventCategory: "target", 
   eventAction: experienceNames, 
   eventLabel: activityNames 
   }); 
   
   
   });
</script>
```

### ![at.js徽](/help/assets/atjs.png) 章通过at.js向Google Analytics发送数据 {#section_04AA830826D94D4EBEC741B7C4F86156}

通过在 HTML 页面中添加以下代码，即可通过 at.js 向 Google Analytics 发送数据：

```javascript
<script type="text/javascript"> 
  (function(i, s, o, g, r, a, m) { 
    i['GoogleAnalyticsObject'] = r; 
    i[r] = i[r] || function() { 
      (i[r].q = i[r].q || []).push(arguments) 
    }, i[r].l = 1 * new Date(); 
    a = s.createElement(o), 
      m = s.getElementsByTagName(o)[0]; 
    a.async = 1; 
    a.src = g; 
    m.parentNode.insertBefore(a, m) 
  })(window, document, 'script', 'https://www.google-analytics.com/analytics.js', 'ga'); 
  ga('create', 'Google Client Id', 'auto'); 
</script> 
 
<script type="text/javascript"> 
  document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(e) { 
    var tokens = e.detail.responseTokens; 
 
    if (isEmpty(tokens)) { 
      return; 
    } 
 
    var activityNames = []; 
    var experienceNames = []; 
    var uniqueTokens = distinct(tokens); 
 
    uniqueTokens.forEach(function(token) { 
      activityNames.push(token["activity.name"]); 
      experienceNames.push(token["experience.name"]); 
    }); 
 
    ga('send', 'event', { 
      eventCategory: "target", 
      eventAction: experienceNames, 
      eventLabel: activityNames 
    }); 
  }); 
 
  function isEmpty(val) { 
    return (val === undefined || val == null || val.length <= 0) ? true : false; 
  } 
 
  function key(obj) { 
     return Object.keys(obj) 
    .map(function(k) { return k + "" + obj[k]; }) 
    .join(""); 
  } 
 
  function distinct(arr) { 
    var result = arr.reduce(function(acc, e) { 
      acc[key(e)] = e; 
      return acc; 
    }, {}); 
   
    return Object.keys(result) 
    .map(function(k) { return result[k]; }); 
  } 
</script>
```

## 调试

以下部分提供了有关调试响应令牌的信息：

### ![at.js徽](/help/assets/atjs.png) 章Google Analytics和调试

以下代码允许您使用Google Analytics进行调试：

```javascript
<script type="text/javascript"> 
  (function(i, s, o, g, r, a, m) { 
    i['GoogleAnalyticsObject'] = r; 
    i[r] = i[r] || function() { 
      (i[r].q = i[r].q || []).push(arguments) 
    }, i[r].l = 1 * new Date(); 
    a = s.createElement(o), 
      m = s.getElementsByTagName(o)[0]; 
    a.async = 1; 
    a.src = g; 
    m.parentNode.insertBefore(a, m) 
  })(window, document, 'script', 'https://www.google-analytics.com/analytics.js', 'ga'); 
  ga('create', 'Google Client Id', 'auto'); 
</script> 
 
<script type="text/javascript"> 
  document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(e) { 
    var tokens = e.detail.responseTokens; 
 
    if (isEmpty(tokens)) { 
      return; 
    } 
 
    var activityNames = []; 
    var experienceNames = []; 
    var uniqueTokens = distinct(tokens); 
 
    uniqueTokens.forEach(function(token) { 
      activityNames.push(token["activity.name"]); 
      experienceNames.push(token["experience.name"]); 
    }); 
 
    ga('send', 'event', { 
      eventCategory: "target", 
      eventAction: experienceNames, 
      eventLabel: activityNames 
    }); 
  }); 
 
  function isEmpty(val) { 
    return (val === undefined || val == null || val.length <= 0) ? true : false; 
  } 
 
  function key(obj) { 
     return Object.keys(obj) 
    .map(function(k) { return k + "" + obj[k]; }) 
    .join(""); 
  } 
 
  function distinct(arr) { 
    var result = arr.reduce(function(acc, e) { 
      acc[key(e)] = e; 
      return acc; 
    }, {}); 
   
    return Object.keys(result) 
    .map(function(k) { return result[k]; }); 
  } 
```

### 使用ttMeta插件的等效函数进行调试

通过向 HTML 页面添加以下代码，可以创建与 ttMeta 插件等效的调试工具：

```javascript
<script type="text/javascript" > 
  document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function (e) { 
    window.ttMETA= typeof(window.ttMETA)!="undefined" ? window.ttMETA : []; 
 
    var tokens=e.detail.responseTokens; 
 
    if (isEmpty(tokens)) { 
      return; 
    } 
     
    var uniqueTokens = distinct(tokens); 
 
    uniqueTokens.forEach(function(token) { 
      window.ttMETA.push({ 
        'CampaignName': token["activity.name"], 
        'CampaignId' : token["activity.id"], 
        'RecipeName': token["experience.name"], 
        'RecipeId': token["experience.id"], 
        'OfferId': token["option.id"], 
        'OfferName': token["option.name"], 
        'MboxName': e.detail.mbox}); 
      console.log(ttMETA); 
    }); 
  }); 
 
  function isEmpty(val){ 
    return (val === undefined || val == null || val.length <= 0) ? true : false; 
  } 
 
  function key(obj) { 
     return Object.keys(obj) 
    .map(function(k) { return k + "" + obj[k]; }) 
    .join(""); 
  } 
 
  function distinct(arr) { 
    var result = arr.reduce(function(acc, e) { 
      acc[key(e)] = e; 
      return acc; 
    }, {}); 
   
    return Object.keys(result) 
    .map(function(k) { return result[k]; }); 
  } 
</script>
```

## ![at.js](/help/assets/atjs.png) 培训视频：响应令牌和at.js自定义事件 {#section_3AA0A6C8DBD94A528337A2525E3E05D5}

以下视频介绍如何使用响应令牌和at.js自定义事件将配置文件信息从[!DNL Target]共享到第三方系统。

>[!NOTE]
>
>[!DNL Target] [!UICONTROL 管理]菜单UI（以前称为[!UICONTROL 设置]）经过重新设计，可提供更高的性能、减少发布新功能时所需的维护时间，并改善整个产品的用户体验。 以下视频中的信息正确；但是，选项的位置略有不同。

>[!VIDEO](https://video.tv.adobe.com/v/23253/)
