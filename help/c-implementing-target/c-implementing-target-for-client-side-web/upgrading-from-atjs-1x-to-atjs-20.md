---
description: 从. js1.x升级到. js2.x
keywords: at.js 发行版;at.js 版本;单页应用程序;spa
seo-description: 有关如何从 Adobe Target at.js 1.x 升级到 at.js 版本 2.0.0 的详细信息
seo-title: '从 Adobe Target at.js 版本 1.x 升级到 at.js 版本 2.0.0 '
solution: Target
subtopic: 入门指南
title: 从. js1.x升级到. js2.x
uuid: 3586af55-db15-4e68-90a7-d552338ec5e8
translation-type: tm+mt
source-git-commit: 4315e6dbec175b22fb7b321719c2f3e2d6729009

---


# 从. js1.x升级到. js2.x {#upgrading-from-atjs-1x-to-atjs-200}

. js的最新版本 [!DNL Adobe Target] 提供丰富的功能集，使您的企业能够在下一代的客户端技术上执行个性化。这个新版本着重升级了 at.js 以与单页应用程序 (SPA) 进行良性的交互。

以下是在以前版本中不提供的. js2.x的一些优点：

* 能够在页面加载时缓存所有选件，将多次服务器调用减少至一次服务器调用。
* 由于选件是通过缓存立即显示的，不存在传统服务器调用引入的任何时间延迟，因此极大地提升了最终用户在您网站上的体验。
* 通过简单的单行代码和一次性开发人员设置，您的营销人员能够通过 VEC 在 SPA 上创建和运行 A/B 和 XT 活动。

## at. js2.x系统示意图

以下示意图帮助您了解包含视图的. js2.x的工作流程及其如何增强SPA集成。要更好地介绍在. js2.x中使用的概念，请参阅 [单个页面应用程序实施](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md)。

![目标流量：js2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/system-diagram-atjs-20.png)

| 调用 | 详细信息 |
| --- | --- |
| 1 | 如果用户通过了身份验证，则调用会返回 [!DNL Experience Cloud ID]；另一调用会同步客户 ID。 |
| 2 | at.js 库会同步加载，并隐藏文档正文。<br>也可以选择预先隐藏页面上实施的代码段，以异步方式加载 at.js。 |
| 3 | 将会发出页面加载请求，其中包括已配置的所有参数（例如，MCID、SDID 和客户 ID）。 |
| 4 | 配置文件脚本在执行后进入配置文件存储区。存储区向受众库请求符合条件的受众（例如从 Adobe Analytics、Audience Management 等共享的受众）。<br>客户属性会以批量过程发送到配置文件存储区。 |
| 5 | 根据 URL 请求参数和配置文件数据，[!DNL Target] 可决定将哪些活动和体验返回给查看当前页面和未来视图的访客。 |
| 6 | 目标内容会发送回页面，其中可能包含其他个性化的配置文件值。<br>当前页面上的目标内容会在默认内容不发生闪烁的情况下尽快显示。<br>视图中作为 SPA 用户操作结果显示的目标内容会缓存在浏览器中，因此当通过 `triggerView()` 触发视图时，可以立即应用它而无需额外的服务器调用。 |
| 7 | Analytics 数据会发送到数据收集服务器。 |
| 8 | 目标数据会通过 SDID 匹配到 Analytics 数据，并且会进行相应处理以保存到 Analytics 报表存储中。之后，便可以在 Analytics 和 Target 中通过 Analytics for Target (A4T) 报表查看 <br>Analytics 数据。 |

现在，无论在 SPA 上的什么位置实施 `triggerView()`，都会从缓存中检索查看次数和操作，并在没有服务器调用的情况下显示给用户。`triggerView()` 还会向 [!DNL Target] 后端发出通知请求，以增加和记录展示次数计数。

![目标流：. js2.x TriggerView](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-triggerview.png)

| 调用 | 详细信息 |
| --- | --- |
| 1 | 在 SPA 中调用 `triggerView()` 以渲染视图并应用操作来修改可视化元素。 |
| 2 | 从缓存中读取视图的目标内容。 |
| 3 | 目标内容会在默认内容不发生闪烁的情况下尽快显示。 |
| 4 | 通知请求将发送到 [!DNL Target] 配置文件存储区，以计算活动中的访客和递增量度。 |
| 5 | Analytics 数据会发送到数据收集服务器。 |
| 6 | Target 数据会通过 SDID 匹配到 Analytics 数据，并且会进行相应处理以保存到 Analytics 报表存储中。之后，便可以在 Analytics 和 Target 中通过 A4T 报表查看 Analytics 数据。 |

## 部署到. js2.x {#deploy-atjs-200}

1. 使用目标UI下载. js2.x。

   ![“实施详细信息”对话框](/help/c-experiences/assets/imp-200.png)

   >[!NOTE]
   >
   >尚不支持通过 [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) 扩展安装. js2.x。

## 已弃用的 at.js 函数

在. js2.x中已弃用几个函数。

>[!IMPORTANT]
>
>如果在部署. js2.x时您的站点仍使用这些弃用的函数，您将看到控制台警告。升级时的建议方法是在一个stage环境中测试. js2.x的部署，确保遍历在控制台中记录的每个警告，并将弃用的函数转换为在. js2.x中引入的新函数。

您可以在下面找到已弃用的函数及其对应的等效函数。有关函数的完整列表，请参阅 [at.js 函数](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md)。

>[!NOTE]
>at. js2.x不再自动隐藏 `mboxDefault` 标记的元素。因此，客户必须在网站上手动或通过标签管理器容纳预隐藏逻辑。

### mboxCreate(mbox,params)

**描述**：

可使用 `mboxDefault` 类名称执行请求并将选件应用到最近的 DIV。

**示例**：

```
<div class="mboxDefault">
  default content to replace by offer
</div>
<script>
  mboxCreate('mboxName','param1=value1','param2=value2');
</script>
```

**at. js2.x等效键**

`mboxCreate(mbox, params)` 的替代函数是 `getOffer()` 和 `applyOffer()`。

**示例**：

```
<div class="mboxDefault"> 
  default content to replace by offer 
</div> 
<script> 
  var el = document.currentScript.previousElementSibling;
  adobe.target.getOffer({
    mbox: "mboxName",
    params: {
      param1: "value1",
      param2: "value2"
    },
    success: function(offer) {
      adobe.target.applyOffer({
        mbox: "mboxName",
        selector: el,
        offer: offer
      });
    },
    error: function(error) {
      console.error(error);
      el.style.visibility = "visible";
    }
  });
</script> 
```

### mboxDefine() 和 mboxUpdate()

**描述**：

创建元素和 mbox 名称之间的内部映射，但不执行请求。与 `mboxUpdate()` 结合使用，后者执行请求并将选件应用于 `mboxDefine()` 中 nodeId 标识的元素。也可以用来更新由 `mboxCreate` 发起的 mbox。

**示例**：

```
<div id="someId" class="mboxDefault"></div>
<script>
 mboxDefine('someId','mboxName','param1=value1','param2=value2');
 mboxUpdate('mboxName','param3=value3','param4=value4');
</script>
```

**at. js2.x等效** 项：

`mboxDefine()` 和 `mboxUpdate` 的替代项是 `getOffer()` 和 `applyOffer()`，`applyOffer()` 中会使用选择器选项。此方法允许您使用任何 CSS 选择器将选件映射到元素，而不仅仅映射到具有 ID 的元素。

**示例**：

```
<div id="someId" class="mboxDefault"> 
  default content to replace by offer 
</div> 
<script> 
  adobe.target.getOffer({
    mbox: "mboxName",
    params: {
      param1: "value1",
      param2: "value2",
      param3: "value3",
      param4: "value4" 
    },
    success: function(offer) {
      adobe.target.applyOffer({
        mbox: "mboxName",
        selector: "#someId",
        offer: offer
      });
    },
    error: function(error) {
      console.error(error);
      var el = document.getElementById("someId");
      el.style.visibility = "visible";
    }
  });
</script>
```

### adobe.target.registerExtension()

**描述**：

可提供用于注册特定扩展的标准方法。

此函数不再受支持，不应使用。

## at.js 2.0 中已弃用、新增和受支持的函数的摘要

| 方法 | 受支持? | 新的? | 已弃用?<br>（将显示默认内容） |
| --- | --- | --- | --- |
| `getOffer()` | 是 |  |  |
| `getOffers()` |  | 是 |  |
| `applyOffer()` | 是 |  |  |
| `applyOffers()` |  | 是 |  |
| `triggerView()` |  | 是 |  |
| `trackEvent()` | 是 |  |  |
| `mboxCreate()` |  |  | 是 |
| `mboxDefine()`<br>`mboxUpdate()` |  |  | 是 |
| `targetGlobalSettings()` | 是 |  |  |
| `Data Providers` | 是 |  |  |
| `targetPageParams()` | 是 |  |  |
| `targetPageParamsAll()` | 是 |  |  |
| `registerExtension()` |  |  | 是 |
| `At.js Custom Events` | 是 |  |  |

## 限制和标注

请注意以下限制和标注：

**转化跟踪**

使用 `mboxCreate()` 进行转化跟踪的客户必须使用 `trackEvent()` 或 `getOffer()`。

**选件交付**

未使用 `getOffer()` 或 `applyOffer()` 替换 `mboxCreate()` 的客户可能无法交付选件。

**可以在. js的某些页面上使用. js2.x。而在其他页面上使用 at.js 1.*x*或 mbox.js？**

可以，系统会使用不同版本和库保留各个页面中的访客配置文件。Cookie 格式是相同的。

**Adobe Experience Cloud调试器不完全支持. js2.x**

[!DNL Adobe Experience Cloud Debugger][!UICONROL 支持“摘要”选项卡] 功能和 [!UICONTROL “禁用”和“控制台日志记录] ”工具，但在. js2.x上不支持网络请求和mboxTrace。

这是因为. js2.x中发送了一个JSON有效负荷，而不是键值对。要检查 [!DNL Target] 请求，请将浏览器开发人员工具的[!UICONTROL 网络]选项卡过滤到“交付”、“`tt.omtrdc.net`”或您的客户端代码。仍可以使用查询字符串参数和授权令牌来检查跟踪数据。有关更多信息，请参阅 [mboxTrace](/help/c-activities/c-troubleshooting-activities/content-trouble.md)。

**新API在. js2.x中使用**

at. js2.x使用新API，我们将其命名为Delivery API。为了调试 at.js 是否正确调用 [!DNL Target] 边缘服务器，您可以将浏览器开发人员工具的“网络”选项卡过滤到“交付”、“`tt.omtrdc.net`”或您的客户端代码。您还会注意到 [!DNL Target] 发送的是 JSON 有效负载而不是键值对。

**不再使用 Target 全局 Mbox**

在. js2.x中，您不再在网络调用中看到“`target-global-mbox`”灵活。我们已在发送到 [!DNL Target] 服务器的 JSON 有效负载中将“`target-global-mbox`”语法替换为的“`execute > pageLoad`”，如下所示：

```
{
  "id": {
    // ...
  },
  "context": {
    "channel": "web",
    // ...
  },
  "execute": {
    "pageLoad": {}
  }
}
```

本质上讲，我们引入全局 mbox 概念是为了告知 [!DNL Target] 在页面加载时是否要检索选件和内容。因此，我们在最新版本中更加明确了此概念。

**at.js 中的全局 mbox 名称是否无关紧要？**

客户可以通过 [!UICONTROL Target &gt; 设置 &gt; 实施 &gt; 编辑 at.js 设置]来指定全局 mbox 名称。[!DNL Target] 边缘服务器使用此设置来将 execute &gt; pageLoad 转换为 [!DNL Target] UI 中显示的全局 mbox 名称。这允许客户继续使用服务器端 API、基于表单的编辑器、配置文件脚本，并使用全局 mbox 名称创建受众。我们强烈建议您还确保在[!UICONTROL 设置 &gt; 首选项]页面上配置相同的全局 mbox 名称，以防仍有使用 at.js 1*x* 或 mbox.js 的页面，如以下插图所示。

![修改 at.js 对话框](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/modify-atjs.png)

和

![自定义全局 mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/custom-global-mbox.png)

**是否需要打开自动创建全局mbox设置？js2.x？**

在大多数情况下需要。此设置告知. js2.x在页面加载时向 [!DNL Target] 边缘服务器发出请求。由于全局 mbox 被转换为 execute &gt; pageLoad，因此如果要在页面加载时触发请求，则应该启用此设置。

**现有CMS活动是否仍可继续工作，即使未从. js2.x中指定目标全局mbox名称吗？**

会，因为系统会在如 `target-global-mbox` 的 [!DNL Target] 后端处理 execute &gt; pageLoad。

**如果将我的基于表单的活动定位到`target-global-mbox`，那么这些活动是否会继续工作？**

会，因为和 `target-global-mbox` 一样，系统会在 [!DNL Target] 边缘服务器上处理 execute &gt; pageLoad。

**支持和不支持. js2.x设置**

| 设置 | 受支持? |
| --- | --- |
| X-Domain | 否 |
| 自动创建全局 Mbox | 是 |
| 全局 Mbox 名称 | 是 |

**跨域跟踪**不** 受支持

通过跨域跟踪，可以将在不同域中两个相关的站点上的会话作为单个会话查看。您可以创建一个跨越 `siteA.com` 和 `siteB.com` 的 [!DNL Target] 活动，这样访客在跨域访问时将会保持相同的体验。此功能与 Target 的第三方和第一方 Cookie 行为相关联。

在 [!DNL Target] 中，第三方 Cookie 存储在 `[CLIENTCODE].tt.omtrdc.net` 中，第一方 Cookie 存储在 `clientdomain.com` 中。第一个请求会返回尝试设置名为 `mboxSession` 和 `mboxPC` 的第三方 Cookie 的 HTTP 响应标头，而会使用额外的参数 (`mboxXDomainCheck=true`) 发送回重定向请求。如果浏览器接受第三方 Cookie，则该重定向请求将包含这些 Cookie，同时会返回选件。这个工作流程是可行的，因为我们使用的是 HTTP GET 方法。

但是，在. js2.x中，不再使用HTTP GET，而是使用HTTP POST。HTTP POST 现在通过 at.js 使用，以便将 JSON 有效负载发送到 [!DNL Target] 边缘服务器。这意味着检查浏览器是否支持第三方 Cookie 的重定向请求现在会中断。这是因为 HTTP GET 请求是幂等事务，而 HTTP POST 是非幂等事务，不能任意重复。因此，不再支持. js2.x中的跨域跟踪。

**支持自动创建全局 Mbox**

此设置告知. js2.x在页面加载时向 [!DNL Target] 边缘服务器发出请求。由于全局 mbox 已转换为 execute &gt; pageLoad，并且这由 [!DNL Target] 边缘服务器来解释，所以如果客户想要在页面加载时触发请求，则应该打开此设置。

**支持全局 Mbox 名称**

客户可以通过 [!UICONTROL Target &gt; 设置 &gt; 实施 &gt; 编辑 at.js 设置]来指定全局 mbox 名称。[!DNL Target] 边缘服务器使用此设置来将 execute &gt; pageLoad 转换为输入的全局 mbox 名称。这允许客户继续使用服务器端 API、基于表单的编辑器、配置文件脚本，并创建针对全局 mbox 的受众。

**以下 at.js 自定义事件是否适用于`triggerView()`，还是仅适用于`applyOffer()`或`applyOffers()`？**

* `adobe.target.event.CONTENT_RENDERING_FAILED`
* `adobe.target.event.CONTENT_RENDERING_SUCCEEDED`
* `adobe.target.event.CONTENT_RENDERING_NO_OFFERS`
* `adobe.target.event.CONTENT_RENDERING_REDIRECT`

是，at.js 自定义事件也适用于 `triggerView()`。

**上文说如果调用使用`{“page” : “true”}`的`triggerView()`时，它会向[!DNL Target]后端发送通知并增加展示次数。它是否还会导致系统执行配置文件脚本？**

当对 [!DNL Target] 后端进行预取调用时，将会执行配置文件脚本。此后，受影响的配置文件数据将被加密并传递回客户端。在调用使用 `{"page": "true"}` 的 `triggerView()` 后，将会发送通知以及加密的配置文件数据。之后，[!DNL Target] 后端将解密配置文件数据并将其存储到数据库中。

**我们是否需要在调用`triggerView()`之前添加预隐藏代码以避免闪烁？**

不需要，在调用 `triggerView()` 之前，您不需要添加预隐藏代码。at. js2.x在显示和应用视图之前管理预隐藏和闪烁逻辑。

## at.js 兼容性

以下表格介绍了 at.js. 2.0.0 与不同活动类型、集成、功能和 at.js 函数之间的兼容性。

### 活动类型 {#types}

| 类型 | 受支持? |
| --- | --- |
| A/B 测试 | 是 |
| 自动分配 | 是 |
| 自动定位 | 是 |
| 体验定位 | 是 |
| 多变量测试 | 是 |
| 自动个性化 | 是 |
| 推荐 | 是 |

>[!NOTE]
>
>当应用所有修改时，将通过at. js2.x和CMS支持自动Target活动 `Page Load Event`。当修改添加到特定视图时，仅支持A/B测试、自动分配和体验定位(XT)活动。

### 集成 {#integrations}

| 类型 | 受支持? |
| --- | --- |
| Analytics for Target (A4T) | 是 |
| 受众 | 是 |
| 客户属性 | 是 |
| AEM 体验片段 | 是 |
| Adobe Launch 扩展 | 当前不支持 |
| 调试程序 | 是 |
| 审核 | 尚未更新. js2.x的规则 |
| 动态标签管理器 (DTM) | 是 |
| 选择加入 | 否。在. js版本2.1.0中支持选择加入 [GDPR](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md)[支持](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)。 |
| 由 Adobe Target 提供支持的 AEM 增强型个性化 | 否 |

### 功能

| 功能 | 受支持? |
| --- | --- |
| X-Domain | 否 |
| 属性/工作区 | 是 |
| QA 链接 | 是 |
| 基于表单的体验编辑器 | 是 |
| 可视化体验编辑器 (VEC) | 是 |
| 自定义代码 | 是 |
| 响应令牌 | [是](#response-tokens) |
| 点击跟踪 | 是 |
| 多活动交付 | 是 |
| targetGlobalSettings | 是（但不支持 x 域） |
| at.js 方法 | 除了会显示默认内容的 <br>`mboxCreate()`<br>`mboxUpdate()`<br>`mboxDefine()`<br>之外，其他所有方法均受支持。 |

### 查询字符串参数

| 参数 | 受支持? |
| --- | --- |
| `?mboxDisable` | 是 |
| `?mboxDisable` | 是 |
| `?mboxTrace` | 是 |
| `?mboxSession` | 否 |
| `?mboxOverride.browserIp` | 否 |

## 响应令牌 {#response-tokens}

at.js 2.*x*，就像在. js中一样。*x*，使用自定义事件 `at-request-succeeded` 来显示响应令牌。有关使用 `at-request-succeeded` 自定义事件的代码示例，请参阅 [响应令牌](/help/administrating-target/response-tokens.md)。

## at. js1.x参数到. js2.x有效负荷映射 {#payload-mapping}

本节概述. js之间的映射。*x* 和at. js2.x。

在将参数映射到参数映射之前，这些库版本所使用的端点已发生更改：

* at.js 1.*x* - `http://<client code>.tt.omtrdc.net/m2/<client code>/mbox/json`
* at. js2.x- `http://<client code>.tt.omtrdc.net/rest/v1/delivery`

另一个重要区别是：

* at.js 1.*x* -客户端代码是路径的一部分
* at. js2.x-客户端代码作为查询字符串参数发送，如：
   `http://<client code>.tt.omtrdc.net/rest/v1/delivery?client=democlient`

以下部分列出每个. js1。*x* 参数、其描述和对应的2.0.0JSON有效负荷(如果适用)：

### at_ property

(at.js 1.*x* 参数)

用于 [企业用户权限](/help/administrating-target/c-user-management/property-channel/property-channel.md)。

```
{
  ....
  "property": {
    "token": "1213213123122313121"
  }
  ....
}
```

### browserHeight

(at.js 1.*x* 参数)

访客浏览器窗口的高度。

at. js2.x JSON有效负荷：

```
{
  "context": {
    "window": {
       "height": 200
    }
  }
}
```

### browserWidth

(at.js 1.*x* 参数)

访客浏览器窗口的宽度。

at. js2.x JSON有效负荷：

```
{
  "context": {
    "window": {
       "width": 200
    }
  }
}
```

### browserTimeOffset

(at.js 1.*x* 参数)

时区偏移。

at. js2.x JSON有效负荷：

```
{
  "context": {
    "timeOffsetInMinutes": -480
  }
}
```

### screenHeight

(at.js 1.*x* 参数)

访客屏幕的高度。

at. js2.x JSON有效负荷：

```
{
  "context": {
    "screen": {
       "height": 200
    }
  }
}
```

### screenWidth

(at.js 1.*x* 参数)

访客屏幕的宽度。

at. js2.x JSON有效负荷：

```
{
  "context": {
    "screen": {
       "width": 200
    }
  }
}
```

### colorDepth

(at.js 1.*x* 参数)

访客屏幕的颜色深度。

at. js2.x JSON有效负荷：

```
{
  "context": {
    "screen": {
       "colorDepth": 24
    }
  }
}
```

### mboxHost

(at.js 1.*x* 参数)

目标库运行的页面的域。

at. js2.x JSON有效负荷：

```
{
  "context": {
    "browser": {
       "host": "test.com"
    }
  }
}
```

### webGLRenderer

(at.js 1.*x* 参数)

浏览器的WEB GL渲染器功能。我们的设备检测机制用于确定访问者设备是桌面、iPhone、Android设备等。

at. js2.x JSON有效负荷：

```
{
  "context": {
    "browser": {
       "webGLRenderer": "AMD Radeon Pro 560X OpenGL Engine"
    }
  }
}
```

### mboxURL

(at.js 1.*x* 参数)

页面URL。

at. js2.x JSON有效负荷：

```
{
  "context": {
    "address": {
       "url": "http://test.com"
    }
  }
}
```

### mboxReferrer

(at.js 1.*x* 参数)

页面引用程序。

at. js2.x JSON有效负荷：

```
{
  "context": {
    "address": {
       "referringUrl": "http://google.com"
    }
  }
}
```

### mbox(the name)等于全局mbox

(at.js 1.*x* 参数)

交付API不再具有全局mbox概念。在JSON有效负荷中，您必须使用 `execute > pageLoad`。

at. js2.x JSON有效负荷：

```
{
  "execute": {
    "pageLoad": {
       "parameters": ....
       "profileParameters": ...
       .....
    }
  }
}
```

### mbox(the name)不 ** 等于全局mbox

(at.js 1.*x* 参数)

要使用mbox名称，请将其传递 `execute > mboxes`到。mbox需要一个索引和名称。

at. js2.x JSON有效负荷：

```
{
  "execute": {
    "mboxes": [{
       "index": 0,
       "name": "some-mbox",
       "parameters": ....
       "profileParameters": ...
       .....
    }]
  }
}
```

### mboxID

(at.js 1.*x* 参数)

已不再使用。

### mboxCount

(at.js 1.*x* 参数)

已不再使用。

### mboxGrid

(at.js 1.*x* 参数)

下游系统用来帮助调试的请求ID。

at. js2.x JSON有效负荷：

```
{
  "requestId": "2412234442342"
  ....
}
```

### mboxTime

(at.js 1.*x* 参数)

已不再使用。

### mboxSession

(at.js 1.*x* 参数)

会话ID作为查询字符串参数(`sessionId`)发送到交付API端点。

### mboxPC

(at.js 1.*x* 参数)

TNT ID被传入 `id > tntId`。

at. js2.x JSON有效负荷：

```
{
  "id": {
    "tntId": "ca5ddd7e33504c58b70d45d0368bcc70.21_3"
  }
  ....
}
```

### mboxMCGVID

(at.js 1.*x* 参数)

Marketing Cloud访客ID已传入 `id > marketingCloudVisitorId`。

at. js2.x JSON有效负荷：

```
{
  "id": {
    "marketingCloudVisitorId": "797110122341429343505"
  }
  ....
}
```

### vst. aaa. id和vst. aaa. authState

(at.js 1.*x* 参数)

应将客户ID传递进去 `id > customerIds`。

at. js2.x JSON有效负荷：

```
{
  "id": {
    "customerIds": [{
       "id": "1232131",
       "integrationCode": "aaaa",
       "authenticatedState": "....."
     }]
  }
  ....
}
```

### mbox3rdPartyId

(at.js 1.*x* 参数)

客户第三方ID，用于链接不同的目标ID。

at. js2.x JSON有效负荷：

```
{
  "id": {
    "thirdPartyId": "1232312323123"
  }
  ....
}
```

### mboxMcSID

(at.js 1.*x* 参数)

SSID，也称为补充数据ID。`experienceCloud > analytics > supplementalDataId`应有尽有。

at. js2.x JSON有效负荷：

```
{
  "experienceCloud": {
    "analytics": {
      "supplementalDataId": "1212321132123131"
    }
  }
  ....
}
```

### vst. tk

(at.js 1.*x* 参数)

Analytics跟踪服务器。`experienceCloud > analytics > trackingServer`应有尽有。

at. js2.x JSON有效负荷：

```
{
  "experienceCloud": {
    "analytics": {
      "trackingServer": "analytics.test.com"
    }
  }
  ....
}
```

### vst. tracks

(at.js 1.*x* 参数)

分析跟踪服务器安全。`experienceCloud > analytics > trackingServerSecure`应有尽有。

at. js2.x JSON有效负荷：

```
{
  "experienceCloud": {
    "analytics": {
      "trackingServerSecure": "secure-analytics.test.com"
    }
  }
  ....
}
```

### mboxMCGLH

(at.js 1.*x* 参数)

Audience Manager位置提示。`experienceCloud > audienceManager > locationHint`应有尽有。

at. js2.x JSON有效负荷：

```
{
  "experienceCloud": {
    "audienceManager": {
      "locationHint": 9
    }
  }
  ....
}
```

### mboxAAMB

(at.js 1.*x* 参数)

Audience Manager blob.`experienceCloud > audienceManager > blob`应有尽有。

at. js2.x JSON有效负荷：

```
{
  "experienceCloud": {
    "audienceManager": {
      "blob": "2142342343242342"
    }
  }
  ....
}
```

### mboxVersion

(at.js 1.*x* 参数)

版本通过版本参数作为查询字符串参数发送。

## 培训视频：at. js2.x建筑图

at. js2.x增强了Adobe Target对SPA的支持并与其他Experience Cloud解决方案集成。该视频介绍了如何将所有内容结合到一起。

>[!VIDEO](https://video.tv.adobe.com/v/26250?captions=chi_hans)

请参阅 [了解. js2.x的工作](https://helpx.adobe.com/target/kt/using/atjs20-diagram-technical-video-understand.html) 原理以了解更多信息。