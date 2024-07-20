---
keywords: 响应令牌；令牌；插件；插件；at.js；响应；平台web sdk；google analytics
description: 了解如何在 [!DNL Adobe Target] 中使用响应令牌来输出特定的信息，以便调试并与第三方工具集成。
title: 什么是响应令牌？如何使用它们？
feature: Administration & Configuration
role: Admin
exl-id: d0c1e914-3172-466d-9721-fe0690abd30b
source-git-commit: 74355ad115eba20a0078aa15970b23c5754842a4
workflow-type: tm+mt
source-wordcount: '1626'
ht-degree: 22%

---

# 响应令牌

响应令牌允许您自动将特定于[!DNL Adobe Target]的信息输出到品牌网页。 此信息可以包括有关活动、选件、体验、用户配置文件、地理信息等的详细信息。 这些详细信息提供了额外的响应数据，可用于与内部或第三方工具共享或用于调试。

响应令牌允许您选择要使用的变量（在键值对中），然后启用它们作为[!DNL Target]响应的一部分发送。 您使用开关启用一个变量，该变量将随[!DNL Target]响应一起发送，这可以在网络调用中验证。 响应令牌也可在[!UICONTROL Preview]模式下使用。

插件和响应令牌之间的主要区别在于，插件可以将JavaScript交付到在交付时执行的页面。 但是，响应令牌会传递一个对象，然后可以使用事件侦听器读取该对象并对其执行操作。 响应令牌方法更安全，并且允许更轻松地开发和维护第三方集成。

>[!NOTE]
>
>at.js版本1.1或更高版本中有响应令牌可用。

| Target SDK | 建议的操作 |
|--- |--- |
| [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank} | 确保您使用的是Platform Web SDK版本2.6.0或更高版本。 有关下载最新版Platform Web SDK的信息，请参阅&#x200B;*Platform Web SDK概述*&#x200B;指南中的[安装SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html){target=_blank}。 有关每个Platform Web SDK版本中新功能的信息，请参阅&#x200B;*Platform Web SDK概述*&#x200B;指南中的[发行说明](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html)。 |
| [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html){target=_blank} | 确保您使用的是 at.js 版本 1.1 或更高版本。有关下载最新版本at.js的信息，请参阅[下载at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-without-a-tag-manager.html?lang=en){target=_blank}。 有关每个at.js版本中新功能的信息，请参阅[at.js版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank}。<br>我们鼓励使用 at.js 的客户使用响应令牌而不是插件。某些插件依赖的内部方法在mbox.js中存在（现已弃用），但在at.js中不存在；这些插件虽然可以交付，但却会失败。 |

## 使用响应令牌 {#section_A9E141DDCBA84308926E68D05FD2AC62}

1. 确保您使用的是Platform Web SDK版本2.6.0（或更高版本）或者at.js版本1.1（或更高版本）。

   有关更多信息：

   * **Platform Web SDK**：请参阅&#x200B;*Platform Web SDK概述*&#x200B;指南中的[安装SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html)。
   * **at.js**：请参阅[下载at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-without-a-tag-manager.html){target=_blank}。

1. 在[!DNL Target]中，单击&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Response Tokens]**。

   ![response_tokens — 新图像](assets/response_tokens-new.png)

1. 激活所需的响应令牌，如`activity.id`和`offer.id`。

   以下参数默认可用：

   | 类型 | 参数 | 注释 |
   |--- |--- |--- |
   | 内置配置文件 | `profile.activeActivities` | 返回该访客符合条件的 `activityIds` 数组。它会随着符合条件的用户数量的增加而递增。例如，在包含两个交付两个不同活动的[!DNL Target]请求的页面上，第二个请求包含这两个活动。 |
   |  | `profile.isFirstSession` | 返回“true”或“false”。 |
   |  | `profile.isNewSession` | 返回“true”或“false”。 |
   |  | `profile.daysSinceLastVisit` | 返回自该访客上次访问后已过的天数。 |
   |  | `profile.tntId` | 返回访客的 tntID |
   |  | `profile.marketingCloudVisitorId` | 返回访客的 Experience Cloud 访客 ID。 |
   |  | `profile.thirdPartyId` | 返回访客的第三方 ID。 |
   |  | `profile.categoryAffinity` | 返回访客最喜欢的类别。 |
   |  | `profile.categoryAffinities` | 将该访客排名前 5 的类别的数组作为字符串返回。 |
   | 活动 | `activity.name`<br>`activity.id`<br>`experience.name`<br>`experience.id`<br>`offer.name`<br>`offer.id` | 当前活动的详细信息。<br>请注意，优惠参数的值是在体验级别上评估的。 |
   | 地域 | `geo.country`<br>`geo.state`<br>`geo.city`<br>`geo.zip`<br>`geo.dma`<br>`geo.domainName`<br>`geo.ispName`<br>`geo.connectionSpeed`<br>`geo.mobileCarrier` | 请参阅[地域](/help/main/c-target/c-audiences/c-target-rules/geo.md)以了解在活动中使用地域定位的详细信息。 |
   | 流量分配方法<br>（仅适用于[!UICONTROL Auto-Target]和[!UICONTROL Automated Personalization]活动。） | `experience.trafficAllocationId` | 如果访客因处于“control”流量中而获得体验，则返回0；如果访客从“targeted”流量分配获得体验，则返回1。 |
   |  | `experience.trafficAllocationType` | 返回“control”或“targeted”。 |

   用户配置文件属性和客户属性也会显示在列表中。

   >[!NOTE]
   >
   >包含特殊字符的参数不会显示在列表中。只支持字母数字字符和下划线。

1. （视情况而定）要将配置文件参数用作响应令牌，但该参数尚未通过[!DNL Target]请求传递，因此尚未加载到[!DNL Target] UI中，您可以使用[!UICONTROL Add Response Token]按钮将该配置文件添加到UI。

   单击&#x200B;**[!UICONTROL Add Response Token]**，提供令牌名称，然后单击&#x200B;**[!UICONTROL Activate]**。

   ![response_token_create image](assets/response_token_create.png)

1. 创建一个活动。

## 侦听响应并读取响应令牌

根据您是[!DNL Platform Web SDK]还是at.js实施，用于侦听[!DNL Target]响应和读取响应令牌的进程会有所不同。

### 使用Handle对象类的![Adobe Experience Platform Web SDK徽章](/help/main/assets/platform.png) [!DNL Platform Web SDK] {#platform-web-sdk}

使用Handle对象类，该对象类具有元数据对象和数据对象，用于侦听[!DNL Target]响应并读取响应令牌。

以下响应示例将[!DNL Platform Web SDK]自定义事件处理程序直接添加到HTML页面（该表说明了代码中使用的对象）：

| 对象 | 信息 |
| --- | --- |
| 类型 — Personalization.decision | 是否由[!DNL Target]或Offer decisioning提供程序做出决定。 |
| DecisionProvider - TGT | TGT-[!DNL Target]。 [!DNL Target]为页面提供响应令牌元数据和值。 |
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

### 使用自定义事件的![at.js徽章](/help/main/assets/atjs.png) at.js

使用[at.js自定义事件](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/atjs-custom-events.html?lang=en){target=_blank}监听[!DNL Target]响应并读取响应令牌。

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

响应令牌只能由具有[!DNL Target] [!UICONTROL Administrator]角色的用户激活或停用。

**如果我运行的是[!DNL Platform Web SDK] 2.6.0（或更早版本），会发生什么情况？**

您无权访问响应令牌。

**如果我运行的是at.js 1.0（或更早版本），会发生什么情况？**

您可以看到响应令牌，但at.js不能使用它们。

**我是否可以同时使[!DNL Target Classic]插件和响应令牌处于活动状态？**

插件和响应令牌可并行使用；但是，未来将弃用插件。

**响应令牌是通过所有[!DNL Target]响应还是仅通过[!DNL Target]响应交付活动？**

响应令牌仅通过交付活动的[!DNL Target]响应来交付。

**我的[!DNL Target Classic]插件包含JavaScript。 如何使用响应令牌复制其功能？**

迁移到响应令牌时，必须将此类型的JavaScript保留在代码库或标签管理解决方案中。 您可以使用[!DNL Platform Web SDK]或[!DNL at.js]自定义事件触发此代码，并将响应令牌值传递给您的JavaScript函数。

**为什么我的配置文件/客户属性参数不会显示在响应令牌列表中？**

[!DNL Target]通常每15分钟刷新一次参数。 此刷新取决于用户操作，仅当查看响应令牌页面时才刷新数据。 如果您的参数未显示在响应令牌列表中，[!DNL Target]尚未刷新数据。

此外，如果参数包含非字母数字字符或下划线以外的任何符号，则该参数不会出现在列表中。 目前，仅支持字母数字和下划线字符。

**如果响应令牌使用已删除的配置文件脚本或配置文件参数，它是否仍会交付内容？**

响应令牌从用户配置文件中提取信息，然后交付该信息。如果删除配置文件脚本或参数，并不意味着该信息已从用户配置文件中删除。用户配置文件仍然具有与配置文件脚本对应的数据。 响应令牌将继续交付内容。 对于未在配置文件中保存该信息的用户或者新访客，不会交付该令牌，因为数据不存在于其配置文件中。

[!DNL Target]不会自动关闭令牌。 如果您要删除配置文件脚本并且不再希望交付该令牌，则必须自行关闭该令牌。

**我重命名了我的配置文件脚本，但为什么使用该脚本的令牌仍使用旧名称？**

如上所述，响应令牌处理的是为用户保存的配置文件信息。即使您重命名了配置文件脚本，但访问过您网站的用户会在其配置文件中保存旧的配置文件脚本值。 令牌会继续选取已保存在用户配置文件中的旧值。 如果您现在想要以新名称交付内容，则必须关闭以前的令牌，然后打开新令牌。

**如果我的属性已更改，何时将其从列表中移除？**

[!DNL Target]定期执行属性刷新。 任何未切换的属性将在下次刷新时删除。 但是，如果您具有已打开并已删除的属性，则在将其关闭之前，不会将该脚本从属性列表中删除。 例如，您删除了用作令牌的配置文件脚本。 删除或重命名[!DNL Target]时，只从列表中删除已切换的属性。

## 向Google Analytics发送数据

以下各节介绍如何将[!DNL Target]数据发送到Google Analytics4。 由响应令牌发送的数据也可以发送到其他第三方集成。

### ![AEP徽章](/help/main/assets/platform.png)通过Platform Web SDK向Google Analytics发送数据

通过在HTML页面中添加以下代码，可以通过Platform Web SDK版本2.6.0（或更高版本）发送Google Analytics数据。

>[!NOTE]
>
>确保响应令牌键值对位于`alloy("sendEvent"`对象下。

```javascript
<script async src="https://www.googletagmanager.com/gtag/js?id=TAG_ID"></script>
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
 
        gtag('config', 'TAG_ID');
        gtag('event', 'action_name', {'eventCategory': 'target',
            'eventAction': experienceNames, 'eventLabel': activityNames
        });
    });
</script>
```

### ![at.js徽章](/help/main/assets/atjs.png)通过at.js向Google Analytics发送数据 {#section_04AA830826D94D4EBEC741B7C4F86156}

通过在 HTML 页面中添加以下代码，即可通过 at.js 向 Google Analytics 发送数据：

```javascript
<script async src="https://www.googletagmanager.com/gtag/js?id=TAG_ID"></script>

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

        gtag('config', 'TAG_ID');
        gtag('event', 'action_name', {'eventCategory': 'target',
            'eventAction': experienceNames, 'eventLabel': activityNames
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

### ![at.js徽章](/help/main/assets/atjs.png)Google Analytics和调试

以下代码允许您使用Google Analytics进行调试：

```javascript
<script async src="https://www.googletagmanager.com/gtag/js?id=TAG_ID"></script>
  
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
  
      gtag('config', 'TAG_ID');
      gtag('event', 'action_name', {'eventCategory': 'target',
          'eventAction': experienceNames, 'eventLabel': activityNames
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

### 使用ttMeta插件的等效插件进行调试

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
        'OfferId': token["offer.id"], 
        'OfferName': token["offer.name"], 
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

## ![at.js](/help/main/assets/atjs.png)培训视频：响应令牌和at.js自定义事件 {#section_3AA0A6C8DBD94A528337A2525E3E05D5}

以下视频介绍如何使用响应令牌和at.js自定义事件将[!DNL Target]中的配置文件信息共享到第三方系统。

>[!NOTE]
>
>[!DNL Target] [!UICONTROL Administration]菜单UI（以前为[!UICONTROL Setup]）已重新设计，以提供更好的性能、缩短发布新功能时所需的维护时间并改善整个产品的用户体验。 以下视频中的信息正确；但是，选项的位置略有不同。
>
>视频提及了`option.name`和`option.id`，它们已分别替换为`offer.name`和`offer.id`。

>[!VIDEO](https://video.tv.adobe.com/v/23253/)
