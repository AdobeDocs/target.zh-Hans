---
description: '有关 at.js 的 targetGlobalSettings() 函数的信息。 '
keywords: targetGlobalSettings;targetglobalsettings;globalSettings;globalsettings;global settings;at.js;function;clientCode;clientDomain;serverdomain;cookieDomain;cookieDomain;crossDomain;crossDomain;timeout;globalMboxAutoCreate;visitorAtAteContCeut;defaultContContCeContChentCeCeCedCe;defaultContentVisibleStyle;bodyHiddenStyle;bodyHidingEnabled;imsOrgId;secureOnly;overrideMboxEdgeServer;overrideMboxEdgeServerTimeout;optoutEnabled;optout;selectorsPollingTimeout;dataProviders
seo-description: 有关 Adobe Target at.js JavaScript 库的 targetGlobalSettings() 函数的信息。
seo-title: 有关 Adobe Target at.js JavaScript 库的 targetGlobalSettings() 函数的信息。
solution: Target
subtopic: 入门指南
title: targetGlobalSettings()
topic: Standard
translation-type: tm+mt
source-git-commit: bc5acc09c1bc8e412929ad9a0ede8a80b6405d5d

---


# targetGlobalSettings()

您可以使用 `targetGlobalSettings()` 覆盖 at.js 库中的设置，而不是在 [!DNL Target] Standard/Premium UI 中或通过使用 REST API 来配置设置。

在某些用例中，特别是当您想要覆盖某些设置而通过 [!DNL Dynamic Tag Management] (DTM) 传递 at.js 的情况下，可执行此类操作。

## 设置 {#section_42C759AE9B524A43B8659018677224B8}

您可以覆盖以下设置：

| 设置 | 类型 | 默认值 | 描述 |
|--- |--- |--- |--- |
| clientCode | 字符串 | 通过 UI 设置的值 | 表示客户端代码 |
| serverDomain | 字符串 | 通过 UI 设置的值 | 表示 Target 边缘服务器 |
| cookieDomain | 字符串 | 如果可能的话，设置为顶级域 | 表示保存 Cookie 时使用的域 |
| crossDomain | 字符串 | 通过 UI 设置的值 | 指示是否启用跨域跟踪。<br>允许的值是：<ul><li>已禁用</li><li>已启用</li><li>仅第三方</li></ul> |
| timeout | 数值 | 通过 UI 设置的值 | 表示 Target 边缘请求超时 |
| globalMboxAutoCreate | 布尔值 | 通过 UI 设置的值 | 指示是否应触发全局 mbox 请求 |
| visitorApiTimeout | 数值 | 2000 毫秒 = 2 秒 | 表示访客 API 请求超时 |
| enabled | 布尔值 | true | 指示是否将 at.js 作为库启用，这意味着它是否应执行任何内容。此设置的主要用例是选择退出 Cookie 或其他自定义决定，这些决定会禁用 at.js 功能 |
| defaultContentHiddenStyle | 字符串 | 可见性：隐藏 | 仅用于封装使用类名为“mboxDefault”且通过 `mboxCreate()`、`mboxUpdate()` 或 `mboxDefine()` 执行的 DIV 的 mbox 以隐藏默认内容 |
| defaultContentVisibleStyle | 字符串 | 可见性：显示 | 仅用于封装使用类名为“mboxDefault”且通过 `mboxCreate()`、`mboxUpdate()` 或 `mboxDefine()` 执行的 DIV 的 mbox 以显示应用的选件（如果有）或默认内容 |
| bodyHiddenStyle | 字符串 | body { opacity: 0 } | 仅在 `globalMboxAutocreate === true` 时使用，以尽量减少出现闪烁的情况。<br>有关更多信息，请参阅 [at.js 如何管理闪烁](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md)。 |
| bodyHidingEnabled | 布尔值 | true | 当使用 `target-global-mbox` 来传递在可视化体验编辑器中创建的选件（也称为可视化选件）时，用于控制闪烁 |
| imsOrgId | 字符串 | IMS 组织 ID | 表示 IMS 组织 ID |
| secureOnly | 布尔值 | false | 指示 at.js 应仅使用 HTTPS 还是允许基于页面协议在 HTTP 和 HTTPS 之间切换。 |
| overrideMboxEdgeServer | 布尔值 | true （从 at.js 版本 1.6.2 开始为 true） | 指示我们是应使用 `<clientCode>.tt.omtrdc.net` 域还是 `mboxedge<clusterNumber>.tt.omtrdc.net` 域。<br>如果此值为 true，`mboxedge<clusterNumber>.tt.omtrdc.net` 域将被保存到 Cookie 中 |
| overrideMboxEdgeServerTimeout | 数值 | 1860000 =&gt; 31 分钟 | 指示包含 `mboxedge<clusterNumber>.tt.omtrdc.net` 值的 Cookie 生命周期。 |
| optoutEnabled | 布尔值 | false | 指示 Target 是否应调用访客 API `isOptedOut()` 函数。这是启动设备图形的一部分。 |
| selectorsPollingTimeout | 数值 | 5000 毫秒 = 5 秒 | 在 at.js 0.9.6 中，Target 引入了这个新设置，它可通过 `targetGlobalSettings` 覆盖。<br>`selectorsPollingTimeout` 表示客户端愿意等待多长时间，让选择器标识的所有元素都显示在页面上。<br>通过可视化体验编辑器 (VEC) 创建的活动具有包含选择器的选件。 |
| dataProviders | 请参阅下面的“数据提供程序”。 | 请参阅下面的“数据提供程序”。 | 请参阅下面的“数据提供程序”。 |

## 使用情况 {#section_9AD6FA3690364F7480C872CB55567FB0}

此函数可在 at.js 加载之前或在&#x200B;**[!UICONTROL 设置]** &gt; **[!UICONTROL 实施]** &gt; **[!UICONTROL 编辑 at.js 设置]** &gt; **[!UICONTROL 代码设置]** &gt; **[!UICONTROL 库标头]**&#x200B;中进行定义。

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
| [在 Adobe Target 中使用数据提供程序](https://helpx.adobe.com/target/kt/using/dataProviders-atjs-feature-video-use.html) | 数据提供程序是一项功能，允许您轻松地将数据从第三方传递到 Target。第三方可以是气象服务、DMP，甚至是您自己的 Web 服务。然后，您可以使用这些数据来构建受众、定位内容并丰富访客配置文件。 |
| [在 Adobe Target 中实施数据提供程序](https://helpx.adobe.com/target/kt/using/dataProviders-atjs-technical-video-implement.html) | 有关如何使用 Adobe Target 的 dataProviders 功能从第三方数据提供程序中检索数据，并将该数据传递到 Target 请求的实施详细信息和示例。 |

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
