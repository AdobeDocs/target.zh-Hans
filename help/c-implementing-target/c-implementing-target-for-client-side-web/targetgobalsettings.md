---
keywords: serverstate;targetGlobalSettings;targetglobalsettings;globalSettings;globalSettings;globalsettings；全局设置；at.js；函数；clientCode;serverDomain;serverCookieDomain;cookieDomain;crossDomain;crossDimain;timeout;globalMboxAutoCreate;visitorApiTimeoutContentHiddenStyle;defaultContentVisibleStyle;bodyStyle;hdyIdenIngIms;enabledMMs;secureBorgMBoxEdgeServer;overrideMboxEdgeServerTimeout;optoutEnabled;optout;optout;selectorsPollingTimeout;dataProviders；混合个性化；deviceIdLifetime
description: 将targetGlobalSettings()函数用于Adobe [!DNL Target] at.js JavaScript库来覆盖设置，而不是使用 [!DNL Target] UI或REST API。
title: 如何使用targetGlobalSettings()函数？
feature: at.js
role: Developer
exl-id: 14080cf6-6a15-4829-b95d-62c068898564
source-git-commit: 8fe168950effe60ead262c842fe9d89d1e376e57
workflow-type: tm+mt
source-wordcount: '2364'
ht-degree: 30%

---

# targetGlobalSettings()

您可以使用 `targetGlobalSettings()` 覆盖 at.js 库中的设置，而不是在 [!DNL Target] Standard/Premium UI 中或通过使用 REST API 来配置设置。

## 设置 {#section_42C759AE9B524A43B8659018677224B8}

您可以覆盖以下设置：

### bodyHiddenStyle

* **类型**：字符串
* **默认值**:body { opacity:0 }
* **描述**:仅在 `globalMboxAutocreate === true` 以尽量减少出现闪烁的情况。

   有关更多信息，请参阅 [at.js 如何管理闪烁](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md)。

### bodyHidingEnabled

* **类型**:布尔值
* **默认值**:true
* **描述**:用于在 `target-global-mbox` 用于交付在可视化体验编辑器中创建的选件，也称为可视化选件。

### clientCode

* **类型**：字符串
* **默认值**:通过UI设置的值。
* **描述**:表示客户端代码。

### cookieDomain

* **类型**：字符串
* **默认值**:如果可能，请设置为顶级域。
* **描述**:表示保存Cookie时使用的域。

### crossDomain

* **类型**：字符串
* **默认值**:通过UI设置的值。
* **描述**:指示是否启用跨域跟踪。 允许的值包括：已禁用、已启用或仅限x。

### cspScriptNonce

* **类型**:请参阅 [内容安全策略](#content-security) 下。
* **默认值**:请参阅 [内容安全策略](#content-security) 下。
* **描述**:请参阅 [内容安全策略](#content-security) 下。

### cspStyleNonce

* **类型**:请参阅 [内容安全策略](#content-security) 下。
* **默认值**:请参阅 [内容安全策略](#content-security) 下。
* **描述**:请参阅 [内容安全策略](#content-security) 下。

### dataProviders

* **类型**:请参阅 [数据提供程序](#data-providers) 下。
* **默认值**:请参阅 [数据提供程序](#data-providers) 下。
* **描述**:请参阅 [数据提供程序](#data-providers) 下。

### 决策方法 {#on-device-decisioning}

* **类型**：字符串
* **默认值**:服务器端
* **其他值**:设备内，混合
* **描述**:请参阅下面的决策方法。

   **决策方法**

   通过设备内决策，Target引入了一个名为 [!UICONTROL 决策方法] 这就决定了at.js如何提供您的体验。 的 `decisioningMethod` 具有三个值：仅限服务器端、仅限设备内和混合。 When `decisioningMethod` 在 `targetGlobalSettings()`，它充当所有 [!DNL Target] 决策。

   **[!UICONTROL 仅服务器端]**:

   [!UICONTROL 仅服务器端] 是开箱即用的默认决策方法，在您的Web资产上实施和部署at.js 2.5及更高版本时。

   使用 [!UICONTROL 仅限服务器端] 作为默认配置，表示所有决策都是在 [!DNL Target] 边缘网络，涉及阻止服务器调用。 这种方法可以引入增量延迟，但也会带来显着好处，例如让您能够应用Target的机器学习功能，这些功能包括 [Recommendations](/help/c-recommendations/recommendations.md), [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) （美联社）和 [自动定位](/help/c-activities/auto-target/auto-target-to-optimize.md) 活动。

   此外，使用Target的用户配置文件（跨会话和渠道保留）增强您的个性化体验，可以为您的业务提供强大的结果。

   最后， [!UICONTROL 仅限服务器端] 允许您使用Adobe Experience Cloud并微调可通过Audience Manager和Adobe Analytics区段针对的受众。

   **[!UICONTROL 仅限设备内]**:

   [!UICONTROL 仅限设备内] 是at.js 2.5+中必须设置的决策方法，因为设备上决策只能在您的整个网页中使用。

   设备上决策可以以惊人的速度提供您的体验和个性化活动，因为决策是根据缓存的规则对象做出的，该对象包含符合设备上决策资格条件的所有活动。

   要进一步了解哪些活动符合设备上决策的条件，请参阅受支持的功能部分。

   仅当性能在所有需要做出决策的页面中都非常关键时，才应使用此决策方法 [!DNL Target]. 此外，请记住，当选择此决策方法时，您的 [!DNL Target] 不符合设备上决策条件的活动将不会交付或执行。 at.js库2.5及更高版本配置为仅查找缓存的规则对象以做出决策。

   **混合**:

   [!UICONTROL 混合] 是at.js 2.5+中必须设置的决策方法，当必须执行设备上决策和需要网络调用Adobe Target边缘网络的活动时。

   如果您同时管理设备上的决策活动和服务器端活动，那么在思考如何部署和配置时，这可能会有些复杂且繁琐 [!DNL Target] 在您的页面上。 以混合决策方法， [!DNL Target] 知道何时必须对Adobe Target边缘网络进行服务器调用，以执行需要服务器端执行的活动，以及何时只执行设备上的决策。

   JSON规则对象包含元数据，用于通知at.jsmbox是运行服务器端活动还是设备决策活动。 此决策方法可确保您打算快速交付的活动通过设备决策完成；对于需要更强大的ML驱动个性化的活动，这些活动会通过Adobe Target边缘网络完成。

### defaultContentHiddenStyle

* **类型**：字符串
* **默认值**:可见性：隐藏
* **描述**:仅用于封装使用类名为“mboxDefault”且通过执行的DIV的mbox `mboxCreate()`, `mboxUpdate()`或 `mboxDefine()` 来隐藏默认内容。

### defaultContentVisibleStyle

* **类型**：字符串
* **默认值**:可见性：可见
* **描述**:仅用于封装使用类名为“mboxDefault”且通过执行的DIV的mbox `mboxCreate()`, `mboxUpdate()`或 `mboxDefine()` 显示已应用的选件（如果有）或默认内容。

### deviceIdLifetime

* **类型**:数值
* **默认值**:63244800000毫秒= 2年
* **描述**:时间量 `deviceId` 将保留在cookie中。

>[!NOTE]
>
>at.js版本2.3.1或更高版本中的deviceIdLifetime设置可覆盖。

### 已启用

* **类型**:布尔值
* **默认值**:true
* **描述**:启用后， [!DNL Target] 将自动执行检索体验的请求和呈现体验的DOM操作。 此外， [!DNL Target] 可以通过手动执行调用 `getOffer(s)` / `applyOffer(s)`.

   禁用后， [!DNL Target] 请求不会自动或手动执行。

### globalMboxAutoCreate

* **类型**:数值
* **默认值**:通过UI设置的值。
* **描述**:指示是否应触发全局mbox请求。

### imsOrgId

* **类型**:字符串
* **默认值**:true
* **描述**:表示IMS组织ID。

### optinEnabled

* **类型**:布尔值
* **默认值**:false
* **描述**: [!DNL Target] 通过 [!DNL Adobe Experience Platform] 以帮助支持您的同意管理策略。 选择加入功能让客户可自行决定如何以及何时触发 [!DNL Target] 标记。还有一个选项，即通过 [!DNL Adobe Experience Platform] 预批准 [!DNL Target] 标记。启用在 [!DNL Target] at.js库中， `optinEnabled=true` 设置。 在 [!DNL Adobe Experience Platform] 您必须从 [!UICONTROL GDPR选择加入] 扩展安装视图中的下拉列表。 请参阅 [Adobe Experience Platform文档](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) 以了解更多详细信息。 有关此设置的更多信息，包括与隐私和数据保护法规(包括欧盟的《通用数据保护条例》(GDPR)和《加州消费者隐私法案》(CCPA))相关的信息，请参阅 [隐私和数据保护法规](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md).

### optoutEnabled

* **类型**:布尔值
* **默认值**:false
* **描述**:指示Target是否应调用访客API `isOptedOut()` 函数。 这是启动设备图形的一部分。

### overrideMboxEdgeServer

* **类型**:布尔值
* **默认值**:true（从at.js版本1.6.2开始为true）
* **描述**:指示我们是否应使用 `<clientCode>.tt.omtrdc.net` 域或 `mboxedge<clusterNumber>.tt.omtrdc.net` 域。

   如果此值为 true，`mboxedge<clusterNumber>.tt.omtrdc.net` 域将被保存到 Cookie 中. 当前不使用 [CNAME](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) 在使用at.js 1.8.2和at.js 2.3.1之前的at.js版本时，如果您遇到此问题，请考虑 [更新at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) 到支持的新版本。

### overrideMboxEdgeServerTimeout

* **类型**:数值
* **默认值**:1860000 => 31分钟
* **描述**:指示包含 `mboxedge<clusterNumber>.tt.omtrdc.net` 值。

### pageLoadEnabled

* **类型**:布尔值
* **默认值**:true
* **描述**:启用后，将自动检索页面加载时必须返回的体验。

### secureOnly

* **类型**:布尔值
* **默认值**:false
* **描述**:指示at.js是应仅使用HTTPS，还是可以根据页面协议在HTTP和HTTPS之间进行切换。 当设置为true时，secureOnly还会将Secure和SameSite属性设置为mbox Cookie。

### selectorsPollingTimeout

* **类型**:数值
* **默认值**:5000毫秒= 5秒
* **描述**:在at.js 0.9.6中， [!DNL Target] 引入了这个新设置，该设置可通过 `targetGlobalSettings`.

   的 `selectorsPollingTimeout` 设置表示客户端愿意等待多长时间，让选择器标识的所有元素都显示在页面上。

   通过可视化体验编辑器 (VEC) 创建的活动具有包含选择器的选件。

### serverDomain

* **类型**：字符串
* **默认值**:通过UI设置的值。
* **描述**:表示Target边缘服务器。

### serverState

* **类型**:请参阅 [混合个性化](#server-state) 下。
* **默认值**:请参阅 [混合个性化](#server-state) 下。
* **描述**:请参阅 [混合个性化](#server-state) 下。

### 遥测已启用 {#telemetry}

* **类型**:布尔值
* **默认值**:true
* **描述**:启用后， [!DNL Adobe] 收集SDK功能使用情况和性能遥测数据。 不会收集个人数据。

### timeout

* **类型**:数值
* **默认值**:通过UI设置的值。
* **描述**:表示 [!DNL Target] 边缘请求超时。

### viewsEnabled

* **类型**:布尔值
* **默认值**:true
* **描述**:启用后，将自动检索页面加载时必须返回的视图。 at.js 2.*x*。

### visitorApiTimeout

* **类型**:数值
* **默认值**:2000毫秒= 2秒
* **描述**:表示 [!UICONTROL 访客API] 请求超时。

## 使用情况 {#section_9AD6FA3690364F7480C872CB55567FB0}

此函数可在at.js加载之前或在 **[!UICONTROL 管理]** > **[!UICONTROL 实施]** > **[!UICONTROL 编辑at.js设置]** > **[!UICONTROL 代码设置]** > **[!UICONTROL 库标题]**.

“库标头”字段允许您输入自由格式的 JavaScript。自定义代码应与以下示例类似：

```javascript
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
| 超时 | 数值 | 如果这是网络请求，则表示提供程序超时。此键值是可选的。 |
| provider | 函数 | 包含提供程序数据提取逻辑的函数。<br>该函数有一个必需的参数：`callback`。callback 参数是一个函数，只有在成功获取数据或发生错误时才应调用该函数。<br>callback 应有两个参数：<ul><li>error：指示是否发生错误。如果一切正常，则应将此参数设置为空。</li><li>params：一个 JSON 对象，表示将在 Target 请求中发送的参数。</li></ul> |

以下示例显示数据提供程序使用同步执行的位置：

```javascript
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

```javascript
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

```javascript
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

## 内容安全策略 {#content-security}

at.js 2.3.0及更高版本支持在应用交付的Target选件时，在附加到页面DOM的脚本和STYLE标记上设置内容安全策略选项。

应在 `targetGlobalSettings.cspScriptNonce` 和 `targetGlobalSettings.cspStyleNonce` 相应地，在加载at.js 2.3.0+之前。 请参阅以下示例：

```javascript
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

之后 `cspScriptNonce` 和 `cspStyleNonce` 指定了设置，at.js 2.3.0及更高版本会将这些设置设置为在应用Target选件时附加到DOM的所有SCRIPT和STYLE标记上的nonce属性。

## 混合个性化 {#server-state}

`serverState` 是at.js v2.2+中提供的一项设置，在实施Target的混合集成时，可使用此设置来优化页面性能。 混合集成指的是在客户端使用 at.js 2.2 和更高版本，在服务器端使用交付 API 或 Target SDK，二者相结合以交付体验。`serverState` 让 at.js 2.2 和更高版本可直接从在服务器端获取并作为所提供的页面的一部分返回客户端的内容应用体验。

### 先决条件

您必须具有 [!DNL Target].

* **服务器端**:您必须使用新 [交付API](https://developers.adobetarget.com/api/delivery-api/) 或 [Target SDK](https://developers.adobetarget.com/api/delivery-api/#section/SDKs).
* **客户端**:您必须使用 [at.js版本2.2或更高版本](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

### 代码示例

为了更好地了解这种方法的工作原理，请参阅下面的代码示例，您将在服务器上看到这些示例。 该代码假定您使用 [Target Node.js SDK](https://github.com/adobe/target-nodejs-sdk).

```javascript
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

示例 `serverState` 用于视图预取的对象JSON如下所示：

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

在浏览器中加载页面后，at.js会应用所有 [!DNL Target] 选件 `serverState` 立即，不会针对任何网络调用触发 [!DNL Target] 边缘。 此外，at.js仅会预隐藏其 [!DNL Target] 在服务器端获取的内容中提供了选件，因此对页面加载性能和最终用户体验有积极影响。

### 重要说明

使用 `serverState`:

* 目前，at.js v2.2仅支持通过serverState交付以下体验：

   * 在页面加载时执行的VEC创建的活动。
   * 预取的视图。

      如果SPA使用 [!DNL Target] 视图和 `triggerView()` 在at.js API中，at.js v2.2会缓存服务器端预取的所有视图的内容，并在通过触发每个视图后立即应用这些内容 `triggerView()`，不会再触发对Target的任何其他内容获取调用。

   * **注意**:目前，不支持在服务器端检索的mbox `serverState`.

* 应用 `serverState `选件，at.js会考虑 `pageLoadEnabled` 和 `viewsEnabled` 设置(例如，如果 `pageLoadEnabled` 设置为false。

   要打开这些设置，请在 **[!UICONTROL 管理] > [!UICONTROL 实施] > [!UICONTROL 编辑] > [!UICONTROL 页面加载已启用]**.

   ![“启用页面加载”设置](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/page-load-enabled-setting.png)

* 如果您使用 `serverState` 和使用 `<script>` 标记，请确保您的HTML内容使用 `<\/script>` 而不是 `</script>`. 如果您使用 `</script>`，浏览器解释 `</script>` 作为内联脚本的结尾，可能会破坏HTML页面。

### 其他资源

了解详情 `serverState` 工作时，请查看以下资源：

* [示例代码](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/advanced-atjs-integration-serverstate).
* [单页应用程序(SPA)示例应用程序，其中 `serverState`](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/react-shopping-cart-demo).
