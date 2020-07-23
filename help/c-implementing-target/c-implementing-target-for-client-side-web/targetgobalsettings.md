---
keywords: serverstate;targetGlobalSettings;targetglobalsettings;globalSettings;globalsettings;global settings;at.js;functions;function;clientCode;clientcode;serverDomain;serverdomain;cookieDomain;cookiedomain;crossDomain;crossdomain;timeout;globalMboxAutoCreate;visitorApiTimeout;defaultContentHiddenStyle;defaultContentVisibleStyle;bodyHiddenStyle;bodyHidingEnabled;imsOrgId;secureOnly;overrideMboxEdgeServer;overrideMboxEdgeServerTimeout;optoutEnabled;optout;opt out;selectorsPollingTimeout;dataProviders;Hybrid Personalization;deviceIdLifetime
description: 有关 Adobe Target at.js JavaScript 库的 targetGlobalSettings() 函数的信息。
title: 有关 Adobe Target at.js JavaScript 库的 targetGlobalSettings() 函数的信息。
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: 3edb13b196240bb1918fc66edcc653936e32d3ef
workflow-type: tm+mt
source-wordcount: '1647'
ht-degree: 40%

---


# targetGlobalSettings()

您可以使用 `targetGlobalSettings()` 覆盖 at.js 库中的设置，而不是在 [!DNL Target] Standard/Premium UI 中或通过使用 REST API 来配置设置。

在某些用例中，特别是当您想要覆盖某些设置而通过 [!DNL Dynamic Tag Management] (DTM) 传递 at.js 的情况下，可执行此类操作。

## 设置 {#section_42C759AE9B524A43B8659018677224B8}

您可以覆盖以下设置：

### bodyHiddenStyle

* **类型**：字符串
* **默认值**: body { opacity: 0 }
* **描述**: 仅在将闪 `globalMboxAutocreate === true` 烁的可能性降至最低时使用。

   有关更多信息，请参阅 [at.js 如何管理闪烁](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md)。

### bodyHidingEnabled

* **类型**: 布尔值
* **默认值**: 真
* **描述**: 用于在传送在 `target-global-mbox` Visual Experience Composer中创建的优惠(也称为可视优惠)时控制闪烁。

### clientCode

* **类型**：字符串
* **默认值**: 通过UI设置的值。
* **描述**: 表示客户端代码。

### cookieDomain

* **类型**：字符串
* **默认值**: 如果可能，请设置到顶级域。
* **描述**: 表示保存Cookie时使用的域。

### crossDomain

* **类型**：字符串
* **默认值**: 通过UI设置的值。
* **描述**: 指示是否启用跨域跟踪。 允许的值包括： 禁用、启用或仅x-only。

### cspScriptNonce

* **类型**: 请参 [阅下面的内容安全](#content-security) 策略。
* **默认值**: 请参 [阅下面的内容安全](#content-security) 策略。
* **描述**: 请参 [阅下面的内容安全](#content-security) 策略。

### cspStyleNonce

* **类型**: 请参 [阅下面的内容安全](#content-security) 策略。
* **默认值**: 请参 [阅下面的内容安全](#content-security) 策略。
* **描述**: 请参 [阅下面的内容安全](#content-security) 策略。

### dataProviders

* **类型**: 请参 [阅下面的](#data-providers) “数据提供者”。
* **默认值**: 请参 [阅下面的](#data-providers) “数据提供者”。
* **描述**: 请参 [阅下面的](#data-providers) “数据提供者”。

### defaultContentHiddenStyle

* **类型**：字符串
* **默认值**: 可见性： 隐藏
* **描述**: 仅用于包装使用类名为“mboxDefault”的DIV并通过、或隐藏默认 `mboxCreate()`内 `mboxUpdate()`容执 `mboxDefine()` 行的mbox。

### defaultContentVisibleStyle

* **类型**：字符串
* **默认值**: 可见性： 可见
* **描述**: 仅用于包装使用类名为“mboxDefault”的DIV并通过、或 `mboxCreate()`显示 `mboxUpdate()`应用的 `mboxDefine()` 优惠（如果有或默认内容）的mbox。

### deviceIdLifetime

* **类型**: 数字
* **默认值**: 63244800000 ms = 2年
* **描述**: Cookie中保 `deviceId` 留的时间。

>[!NOTE]
>
>在at.js版本2.3.1或更高版本中，deviceIdLifetime设置可覆盖。

### 已启用

* **类型**: 布尔值
* **默认值**: 真
* **描述**: 启用后，将自 [!DNL Target] 动执行检索体验的请求和呈现体验的DOM操作。 此外， [!DNL Target] 可通过／手动执 `getOffer(s)` 行调用 `applyOffer(s)`。

   禁用时 [!DNL Target] ，不自动或手动执行请求。

### globalMboxAutoCreate

* **类型**: 数字
* **默认值**: 通过UI设置的值。
* **描述**: 指示是否应触发全局mbox请求。

### imsOrgId

* **类型**: Sting
* **默认值**: 真
* **描述**: 表示IMS组织ID。

### optoutEnabled

* **类型**: 布尔值
* **默认值**: 假
* **描述**: 指示目标是否应调用访客API `isOptedOut()` 函数。 这是启动设备图形的一部分。

### overrideMboxEdgeServer

* **类型**: 布尔值
* **默认值**: true（以at.js版本1.6.2开头，为true）
* **描述**: 指示我们是否应 `<clientCode>.tt.omtrdc.net` 使用域 `mboxedge<clusterNumber>.tt.omtrdc.net` 或域。

   如果此值为 true，`mboxedge<clusterNumber>.tt.omtrdc.net` 域将被保存到 Cookie 中. 当前不使用 [CNAME](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md)

### overrideMboxEdgeServerTimeout

* **类型**: 数字
* **默认值**: 1860000 => 31分钟
* **描述**: 指示包含该值的Cookie生 `mboxedge<clusterNumber>.tt.omtrdc.net` 存期。

### pageLoadEnabled

* **类型**: 布尔值
* **默认值**: 真
* **描述**: 启用后，将自动检索页面加载时必须返回的体验。

### secureOnly

* **类型**: 布尔值
* **默认值**: 假
* **描述**: 指示at.js应仅使用HTTPS，还是允许根据页面协议在HTTP和HTTPS之间切换。

### selectorsPollingTimeout

* **类型**: 数字
* **默认值**: 5000 ms = 5 s
* **描述**: 在at.js 0.9.6中，引 [!DNL Target] 入了可通过覆盖的新设置 `targetGlobalSettings`。

   The `selectorsPollingTimeout` setting represents how long the client is willing to wait for all the elements identified by selectors to appear on the page.

   通过可视化体验编辑器 (VEC) 创建的活动具有包含选择器的选件。

### serverDomain

* **类型**：字符串
* **默认值**: 通过UI设置的值。
* **描述**: 表示目标边缘服务器。

### serverState

* **类型**: 请参 [阅以下混合](#server-state) 个性化。
* **默认值**: 请参 [阅以下混合](#server-state) 个性化。
* **描述**: 请参 [阅以下混合](#server-state) 个性化。

### timeout

* **类型**: 数字
* **默认值**: 通过UI设置的值。
* **描述**: 表示边缘 [!DNL Target] 请求超时。

### viewsEnabled

* **类型**: 布尔值
* **默认值**: 真
* **描述**: 启用后，将自动检索页面加载时必须返回的视图。 视图在at.js 2中受支持。*x*。

### visitorApiTimeout

* **类型**: 数字
* **默认值**: 2000 ms = 2 s
* **描述**: 表示 [!UICONTROL 访客API] 请求超时。

## 使用情况 {#section_9AD6FA3690364F7480C872CB55567FB0}

This function can be defined before at.js is loaded or in **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** > **[!UICONTROL Edit at.js Settings]** > **[!UICONTROL Code Settings]** > **[!UICONTROL Library Header]**.

“库标头”字段允许您输入自由格式的 JavaScript。自定义代码应与以下示例类似：

```
window.targetGlobalSettings = {  
   timeout: 200, // using custom timeout  
   visitorApiTimeout: 500, // using custom API timeout  
   enabled: document.location.href.indexOf('https://www.adobe.com') >= 0 // enabled ONLY on adobe.com  
};
```

## 数据提供程序 {#data-providers}

通过此设置，客户可以从第三方数据提供程序收集数据，例如 Demandbase、BlueKai 和自定义服务，并将这些数据作为全局 mbox 请求中的 mbox 参数传递给 Target。支持通过异步和同步请求从多个提供程序收集数据。使用这种方法可以轻松管理默认页面内容的闪烁，同时包含每个提供程序的独立超时时间以限制对页面性能的影响

>[!NOTE]
>
>数据提供程序需要使用 [!DNL at.js] 1.3 或更高版本。

以下视频包含更多信息：

| 视频 | 描述 |
|--- |--- |
| [在 Adobe Target 中使用数据提供程序](https://helpx.adobe.com/cn/target/kt/using/dataProviders-atjs-feature-video-use.html) | 数据提供程序是一项功能，允许您轻松地将数据从第三方传递到 Target。第三方可以是气象服务、DMP，甚至是您自己的 Web 服务。然后，您可以使用这些数据来构建受众、定位内容并丰富访客配置文件。 |
| [在 Adobe Target 中实施数据提供程序](https://helpx.adobe.com/cn/target/kt/using/dataProviders-atjs-technical-video-implement.html) | 有关如何使用 Adobe Target 的 dataProviders 功能从第三方数据提供程序中检索数据，并将该数据传递到 Target 请求的实施详细信息和示例。 |

`window.targetGlobalSettings.dataProviders` 设置是一个数据提供程序数组。

每个数据提供程序具有以下结构：

| 键值 | 类型 | 描述 |
|--- |--- |--- |
| name | 字符串 | 提供程序的名称。 |
| version | 字符串 | 提供程序版本。此键值将用于提供程序的版本演变。 |
| timeout | 数值 | 如果这是网络请求，则表示提供程序超时。此键值是可选的。 |
| provider | 函数 | 包含提供程序数据提取逻辑的函数。<br>该函数有一个必需的参数：`callback`。callback 参数是一个函数，只有在成功获取数据或发生错误时才应调用该函数。<br>callback 应有两个参数：<ul><li>error：指示是否发生错误。如果一切正常，则应将此参数设置为空。</li><li>params：一个 JSON 对象，表示将在 Target 请求中发送的参数。</li></ul> |

以下示例显示数据提供程序使用同步执行的位置：

```
var syncDataProvider = { 
  name: "simpleDataProvider", 
  version: "1.0.0", 
  provider: function(callback) { 
    callback(null, {t1: 1}); 
  } 
}; 
  
window.targetGlobalSettings = { 
  dataProviders: [ 
    syncDataProvider 
  ] 
};
```

在 at.js 处理 `window.targetGlobalSettings.dataProviders` 之后，Target 请求将包含一个新参数：`t1=1`。

如果您要添加到 Target 请求的参数是从第三方服务（如 Bluekai、Demandbase 等）获取的，则参考以下示例：

```
var blueKaiDataProvider = { 
   name: "blueKai", 
   version: "1.0.0", 
   provider: function(callback) { 
      // simulating network request 
     setTimeout(function() { 
       callback(null, {t1: 1, t2: 2, t3: 3}); 
     }, 1000); 
   } 
} 
  
window.targetGlobalSettings = { 
   dataProviders: [ 
      blueKaiDataProvider 
   ] 
};
```

在 at.js 处理 `window.targetGlobalSettings.dataProviders` 之后，Target 请求将包含其他参数：`t1=1`、`t2=2` 和 `t3=3`。

以下示例使用数据提供程序收集气候 API 数据，并将其作为参数发送到 Target 请求中。Target 请求将具有其他参数，例如 `country` 和 `weatherCondition`。

```
var weatherProvider = { 
      name: "weather-api", 
      version: "1.0.0", 
      timeout: 2000, 
      provider: function(callback) { 
        var API_KEY = "caa84fc6f5dc77b6372d2570458b8699"; 
        var lat = 44.426767399999996; 
        var lon = 26.1025384; 
        var url = "//api.openweathermap.org/data/2.5/weather?lang=en"; 
        var data = { 
          lat: lat, 
          lon: lon, 
          appId: API_KEY 
        } 
 
        $.ajax({ 
          type: "GET", 
                url: url, 
          dataType: "json", 
          data: data, 
          success: function(data) { 
            console.log("Weather data", data); 
            callback(null, { 
              country: data.sys.country, 
              weatherCondition: data.weather[0].main 
            }); 
          }, 
          error: function(err) { 
            console.log("Error", err); 
            callback(err); 
          } 
        });         
      } 
    }; 
 
    window.targetGlobalSettings = { 
      dataProviders: [weatherProvider] 
    };
```

使用 `dataProviders` 设置时请考虑以下事项：

* 如果数据提供程序异步添加到 `window.targetGlobalSettings.dataProviders`，则将并行执行。访客 API 请求将与添加到 `window.targetGlobalSettings.dataProviders` 的函数并行执行，以将等待时间最小化。
* at.js 不会尝试缓存数据。如果数据提供程序仅提取一次数据，则应确保数据已缓存，并且在调用提供程序函数时为第二次调用提供缓存的数据。

## Content Security Policy {#content-security}

at.js 2.3.0+支持在应用交付的目标优惠时，对附加到页面DOM的SCRIPT和STYLE标记设置内容安全策略不可用性。

在加载at.js 2.3.0+之前， `targetGlobalSettings.cspScriptNonce` 应在 `targetGlobalSettings.cspStyleNonce` 中并相应地设置SCRIPT和STYLE动作。 请参阅以下示例：

```
...
<head>
 <script nonce="<script_nonce_value>">
window.targetGlobalSettings = {
  cspScriptNonce: "<csp_script_nonce_value>",
  cspStyleNonce: "<csp_style_nonce_value>"
};
 </script>
 <script nonce="<script_nonce_value>" src="at.js"></script>
...
</head>
...
```

指定 `cspScriptNonce` 和 `cspStyleNonce` 设置后，at.js 2.3.0+会将这些属性设置为应用目标优惠时附加到DOM的所有SCRIPT和STYLE标签上的nonce属性。

## 混合个性化 {#server-state}

`serverState` 是at.js v2.2+中提供的设置，在实施目标的混合集成时，可用于优化页面性能。 混合集成意味着您在客户端同时使用at.js v2.2+和服务器端的投放API或目标SDK来提供体验。 `serverState` 赋予at.js v2.2+直接应用从服务器端获取的内容中获取的体验并作为所服务页面的一部分返回到客户端的能力。

### 先决条件

您必须具有混合集成 [!DNL Target]。

* **服务器端**:  必须使用新的 [投放API](https://developers.adobetarget.com/api/delivery-api/) 或 [目标SDK](https://developers.adobetarget.com/api/delivery-api/#section/SDKs)。
* **客户端**: 必须使用 [at.js版本2.2或更高版本](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)。

### 代码范例

为了更好地了解其工作原理，请参见下面的代码示例，您将在您的服务器上找到这些示例。 代码假定您正在使 [用目标Node.js SDK](https://github.com/adobe/target-nodejs-sdk)。

```
// First, we fetch the offers via Target Node.js SDK API, as usual
const targetResponse = await targetClient.getOffers(options);
// A successfull response will contain Target Delivery API request and response objects, which we need to set as serverState
const serverState = {
  request: targetResponse.request,
  response: targetResponse.response
};
// Finally, we should set window.targetGlobalSettings.serverState in the returned page, by replacing it in a page template, for example
const PAGE_TEMPLATE = `
<!doctype html>
<html>
<head>
  ...
  <script>
    window.targetGlobalSettings = {
      overrideMboxEdgeServer: true,
      serverState: ${JSON.stringify(serverState, null, " ")}
    };
  </script>
  <script src="at.js"></script>
</head>
...
</html>
`;
// Return PAGE_TEMPLATE to the client ...
```

视图预 `serverState` 取的示例对象JSON如下所示：

```
{
 "request": {
  "requestId": "076ace1cd3624048bae1ced1f9e0c536",
  "id": {
   "tntId": "08210e2d751a44779b8313e2d2692b96.21_27"
  },
  "context": {
   "channel": "web",
   "timeOffsetInMinutes": 0
  },
  "experienceCloud": {
   "analytics": {
    "logging": "server_side",
    "supplementalDataId": "7D3AA246CC99FD7F-1B3DD2E75595498E"
   }
  },
  "prefetch": {
   "views": [
    {
     "address": {
      "url": "my.testsite.com/"
     }
    }
   ]
  }
 },
 "response": {
  "status": 200,
  "requestId": "076ace1cd3624048bae1ced1f9e0c536",
  "id": {
   "tntId": "08210e2d751a44779b8313e2d2692b96.21_27"
  },
  "client": "testclient",
  "edgeHost": "mboxedge21.tt.omtrdc.net",
  "prefetch": {
   "views": [
    {
     "name": "home",
     "key": "home",
     "options": [
      {
       "type": "actions",
       "content": [
        {
         "type": "setHtml",
         "selector": "#app > DIV.app-container:eq(0) > DIV.page-container:eq(0) > DIV:nth-of-type(2) > SECTION.section:eq(0) > DIV.container:eq(1) > DIV.heading:eq(0) > H1.title:eq(0)",
         "cssSelector": "#app > DIV:nth-of-type(1) > DIV:nth-of-type(1) > DIV:nth-of-type(2) > SECTION:nth-of-type(1) > DIV:nth-of-type(2) > DIV:nth-of-type(1) > H1:nth-of-type(1)",
         "content": "<span style=\"color:#FF0000;\">Latest</span> Products for 2020"
        }
       ],
       "eventToken": "t0FRvoWosOqHmYL5G18QCZNWHtnQtQrJfmRrQugEa2qCnQ9Y9OaLL2gsdrWQTvE54PwSz67rmXWmSnkXpSSS2Q==",
       "responseTokens": {
        "profile.memberlevel": "0",
        "geo.city": "dublin",
        "activity.id": "302740",
        "experience.name": "Experience B",
        "geo.country": "ireland"
       }
      }
     ],
     "state": "J+W1Fq18hxliDDJonTPfV0S+mzxapAO3d14M43EsM9f12A6QaqL+E3XKkRFlmq9U"
    }
   ]
  }
 }
}
```

页面加载到浏览器中后，at.js将立即应用所 [!DNL Target] 有优惠 `serverState` ，而不会对边缘触发任何网络 [!DNL Target] 调用。 此外，at.js仅预隐藏在获取的内容服务器端 [!DNL Target] 中具有优惠的DOM元素，因此会积极影响页面加载性能和最终用户体验。

### 重要说明

Consider the following when using `serverState`:

* 目前，at.js v2.2仅支持通过serverState提供体验，以满足：

   * 在页面加载时执行的VEC创建的活动。
   * 预取的视图。

      如果SPA使用 [!DNL Target] 视图 `triggerView()` ，并且在at.js API中，at.js v2.2会缓存服务器端预取的所有视图的内容，并在通过触发每个视图时立即应用这些内容，同 `triggerView()`样不会向目标发出任何其他内容提取调用。

   * **注意**:  目前，不支持在服务器端检索的mbox `serverState`。

* 应用 `serverState `优惠时，at.js会考虑 `pageLoadEnabled` 和 `viewsEnabled` 设置，例如，如果设置为false，则不会应 `pageLoadEnabled` 用页面加载优惠。

   要打开这些设置，请在“UICONTROL管理”>“实 **[施”>“编辑”>“启用页面加载”中启用切换]**。

   ![启用页面加载设置](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/page-load-enabled-setting.png)

### 其他资源

要了解更多工 `serverState` 作方式，请查看以下资源：

* [示例代码](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/advanced-atjs-integration-serverstate).
* [包含的单页应用程序(SPA)范例应 `serverState`](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/react-shopping-cart-demo)用。
