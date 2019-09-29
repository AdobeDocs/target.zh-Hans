---
description: 从at.js 1.*x*升级到at.js 2.*x*
keywords: at.js版本；at.js版本；单页应用程序；spa；跨域；跨域
seo-description: 有关如何从Adobe Target at.js 1.*x*升级到at.js 2.0.0版的详细信息
seo-title: 从Adobe Target at.js版本1升级。*x*至at.js版本2。*x 不支持跨域跟踪*
solution: Target
subtopic: 入门指南
title: Upgrading from at.js 1.*x* to at.js 2.*x*
uuid: 3586af55-db15-4e68-90a7-d552338ec5e8
translation-type: tm+mt
source-git-commit: 8dc94ca1ed48366e6b3ac7a75b03c214f1db71d9

---


# Upgrading from at.js 1.*x* to at.js 2.*x* {#upgrading-from-atjs-1x-to-atjs-200}

[!DNL Adobe Target] 中最新版本的 at.js 提供了丰富的功能集，使您的企业能够在下一代客户端技术上实现个性化。这个新版本着重升级了 at.js 以与单页应用程序 (SPA) 进行良性的交互。

Here are some benefits of using at.js 2.*x* that are not available in previous versions:

* 能够在页面加载时缓存所有选件，将多次服务器调用减少至一次服务器调用。
* 由于选件是通过缓存立即显示的，不存在传统服务器调用引入的任何时间延迟，因此极大地提升了最终用户在您网站上的体验。
* 通过简单的单行代码和一次性开发人员设置，您的营销人员能够通过 VEC 在 SPA 上创建和运行 A/B 和 XT 活动。

## at.js 2.*x* system diagrams

The following diagrams help you understand the workflow of at.js 2.*x* with Views and how this enhances the SPA integration. To get a better introduction of the concepts used in at.js 2.*x*, see [Single Page Application implementation](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).

![使用at.js 2.*x实现目标流*](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/system-diagram-atjs-20.png)

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

![目标流at.js 2.** x triggerView](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-triggerview.png)

| 调用 | 详细信息 |
| --- | --- |
| 1 | 在 SPA 中调用 `triggerView()` 以渲染视图并应用操作来修改可视化元素。 |
| 2 | 从缓存中读取视图的目标内容。 |
| 3 | 目标内容会在默认内容不发生闪烁的情况下尽快显示。 |
| 4 | 通知请求将发送到 [!DNL Target] 配置文件存储区，以计算活动中的访客和递增量度。 |
| 5 | Analytics 数据会发送到数据收集服务器。 |
| 6 | Target 数据会通过 SDID 匹配到 Analytics 数据，并且会进行相应处理以保存到 Analytics 报表存储中。之后，便可以在 Analytics 和 Target 中通过 A4T 报表查看 Analytics 数据。 |

## 部署 at.js 2.*x* {#deploy-atjs-200}

1. 部署 at.js 2.*x* ，通过 [Adobe Launch扩展](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) 。

   >[!NOTE]
   >
   > 首选方法是使用 Adobe Launch 部署 at.js。

   或

   Manually download at.js 2.*x* using the Target UI and deploy it using the [method of your choice](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md).

## 已弃用的 at.js 函数

There are several functions that have been deprecated in at.js 2.*x*.

>[!IMPORTANT]
>
>If these deprecated functions are still used on your site when at.js 2.*x* is deployed, you will see console warnings. The recommended approach when upgrading is to test the deployment of at.js 2.*x* in a staging environment and make sure to go through each and every warning that has been logged in the console and translate the deprecated functions to new functions introduced in at.js 2.*x*.

您可以在下面找到已弃用的函数及其对应的等效函数。有关函数的完整列表，请参阅 [at.js 函数](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md)。

>[!NOTE]
>at.js 2.*x* 不再自动预隐藏 `mboxDefault` 标记的元素。因此，客户必须在网站上手动或通过标签管理器容纳预隐藏逻辑。

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

**at.js 2.*x*equivalent**

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

**at.js 2.*x*equivalent**:

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

### 转化跟踪

使用 `mboxCreate()` 进行转化跟踪的客户必须使用 `trackEvent()` 或 `getOffer()`。

### 选件交付

未使用 `getOffer()` 或 `applyOffer()` 替换 `mboxCreate()` 的客户可能无法交付选件。

### Can at.js 2.*在* at.js 1时，在某些页面上使用x。而在其他页面上使用 at.js 1.*x* 或 mbox.js？

可以，系统会使用不同版本和库保留各个页面中的访客配置文件。Cookie 格式是相同的。

### New API use in at.js 2.*x*

at.js 2.*x* 使用一个新的 API，我们称之为“交付 API”。为了调试 at.js 是否正确调用 [!DNL Target] 边缘服务器，您可以将浏览器开发人员工具的“网络”选项卡过滤到“交付”、“`tt.omtrdc.net`”或您的客户端代码。您还会注意到 [!DNL Target] 发送的是 JSON 有效负载而不是键值对。

### 不再使用 Target 全局 Mbox

在 at.js 2.*x*，您不再在网络调`target-global-mbox`用中看到“”可见。 我们已在发送到 [!DNL Target] 服务器的 JSON 有效负载中将“`target-global-mbox`”语法替换为的“`execute > pageLoad`”，如下所示：

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

### at.js 中的全局 mbox 名称是否无关紧要？

客户可以通过 [!UICONTROL Target &gt; 设置 &gt; 实施 &gt; 编辑 at.js 设置]来指定全局 mbox 名称。[!DNL Target] 边缘服务器使用此设置来将 execute &gt; pageLoad 转换为 [!DNL Target] UI 中显示的全局 mbox 名称。这允许客户继续使用服务器端 API、基于表单的编辑器、配置文件脚本，并使用全局 mbox 名称创建受众。我们强烈建议您还确保在[!UICONTROL 设置 &gt; 首选项]页面上配置相同的全局 mbox 名称，以防仍有使用 at.js 1 *x* 或 mbox.js 的页面，如以下插图所示。

![修改 at.js 对话框](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/modify-atjs.png)

和

![自定义全局 mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/custom-global-mbox.png)

### Does the auto-create global mbox setting need to be turned on for at.js 2.*x*?

在大多数情况下需要。This setting tells at.js 2.*x* to fire a request to the [!DNL Target] edge servers upon page load. 由于全局 mbox 被转换为 execute &gt; pageLoad，因此如果要在页面加载时触发请求，则应该启用此设置。

### Will existing VEC activities continue to work, even though the target global mbox name is not specified from at.js 2.*x*?

会，因为系统会在如 `target-global-mbox` 的 [!DNL Target] 后端处理 execute &gt; pageLoad。

### 如果将我的基于表单的活动定位到 `target-global-mbox`，那么这些活动是否会继续工作？

会，因为和 `target-global-mbox` 一样，系统会在 [!DNL Target] 边缘服务器上处理 execute &gt; pageLoad。

### Supported and non-supported at.js 2.*x* Settings

| 设置 | 受支持? |
| --- | --- |
| X-Domain | 否 |
| 自动创建全局 Mbox | 是 |
| 全局 Mbox 名称 | 是 |

### at.js 2.x中的跨域跟踪支持 {#cross-domain}

通过跨域跟踪，可以跨不同域缝合访客。 由于必须为每个域创建新Cookie，因此很难跟踪访客在域之间导航时的情况。 要实现跨域跟踪，请 [!DNL Target] 使用第三方Cookie跨域跟踪访客。 这样，您便可以创建一个Target活动，该活动跨 `siteA.com` 独特域 `siteB.com` 进行导航时，访客将保持相同的体验。 此功能与 Target 的第三方和第一方 Cookie 行为相关联。

>[!NOTE]
>
>at.js 2中不支持跨域跟踪。*x* 不支持跨域跟踪。Cross-domain tracking is supported in at.js 2.*x* v4.3.0+通过Experience Cloud ID(ECID)库。

在Target中，第三方Cookie存储在中 `<CLIENTCODE>.tt.omtrdc.net`。 第一方Cookie存储在中 `clientdomain.com`。 第一个请求会返回尝试设置名为 `mboxSession` 和 `mboxPC` 的第三方 Cookie 的 HTTP 响应标头，而会使用额外的参数 (`mboxXDomainCheck=true`) 发送回重定向请求。If the browser accepts third-party cookies, the redirect request includes those cookies, and the experience is returned. 这个工作流程是可行的，因为我们使用的是 HTTP GET 方法。

However, in at.js 2.*x*, HTTP GET is no longer used and instead we use HTTP POST. HTTP POST现在通过at.js 2使用。*x* ，将JSON有效负载发送到目标边缘服务器。 这意味着检查浏览器是否支持第三方 Cookie 的重定向请求现在会中断。This is because HTTP GET requests are idempotent transactions, while HTTP POST is non-idempotent and must not be arbitrarily repeated. 因此，at.js 2中的跨域跟踪。*x* 不再支持开箱即用。 仅at.js 1.*x* 现成支持跨域跟踪。

如果要使用跨域跟踪，则必须将 [ECID库v4.3.0+与at.js 2](https://docs.adobe.com/content/help/en/id-service/using/release-notes/release-notes.html) 一起安装。*x* 不支持跨域跟踪。ECID库用于管理永久ID，这些ID用于识别访客，甚至跨域。 安装ECID库v4.3.0+和at.js 2后。*x*，您将能够创建跨唯一域的活动并跟踪用户。

### 支持自动创建全局 Mbox

This setting tells at.js 2.*x* to fire a request to the [!DNL Target] edge servers on page-load. 由于全局 mbox 已转换为 execute &gt; pageLoad，并且这由 [!DNL Target] 边缘服务器来解释，所以如果客户想要在页面加载时触发请求，则应该打开此设置。

### 支持全局 Mbox 名称

客户可以通过 [!UICONTROL Target &gt; 设置 &gt; 实施 &gt; 编辑 at.js 设置]来指定全局 mbox 名称。[!DNL Target] 边缘服务器使用此设置来将 execute &gt; pageLoad 转换为输入的全局 mbox 名称。这允许客户继续使用服务器端 API、基于表单的编辑器、配置文件脚本，并创建针对全局 mbox 的受众。

### 以下 at.js 自定义事件是否适用于 `triggerView()`，还是仅适用于 `applyOffer()` 或 `applyOffers()`？

* `adobe.target.event.CONTENT_RENDERING_FAILED`
* `adobe.target.event.CONTENT_RENDERING_SUCCEEDED`
* `adobe.target.event.CONTENT_RENDERING_NO_OFFERS`
* `adobe.target.event.CONTENT_RENDERING_REDIRECT`

是，at.js 自定义事件也适用于 `triggerView()`。

### 上文说如果调用使用 `triggerView()` 的 `{“page” : “true”}` 时，它会向 [!DNL Target] 后端发送通知并增加展示次数。它是否还会导致系统执行配置文件脚本？

当对 [!DNL Target] 后端进行预取调用时，将会执行配置文件脚本。此后，受影响的配置文件数据将被加密并传递回客户端。在调用使用 `{"page": "true"}` 的 `triggerView()` 后，将会发送通知以及加密的配置文件数据。之后，[!DNL Target] 后端将解密配置文件数据并将其存储到数据库中。

### 我们是否需要在调用 `triggerView()` 之前添加预隐藏代码以避免闪烁？

不需要，在调用 `triggerView()` 之前，您不需要添加预隐藏代码。at.js 2.*x* 会在显示和应用视图之前管理预隐藏和闪烁逻辑。

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
>Auto-Target activities are supported through at.js 2.*x* and the VEC when all modifications are applied to the `Page Load Event`. 将修改添加到特定视图时，仅支持 A/B 测试、自动分配和体验定位 (XT) 活动。

### 集成 {#integrations}

| 类型 | 受支持? |
| --- | --- |
| Analytics for Target (A4T) | 是 |
| 受众 | 是 |
| 客户属性 | 是 |
| AEM 体验片段 | 是 |
| Adobe Launch 扩展 | [是](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) |
| 调试程序 | 是 |
| 审核 | Rules have not yet been updated for at.js 2.*x* |
| 动态标签管理器 (DTM) | 是 |
| 选择加入 | 否。[at.js 版本 2.1.0](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) 支持满足 [GDPR](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) 要求的选择加入支持。 |
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

at.js 2.*x*（与 at.js 1.*x* 一样）使用自定义事件 `at-request-succeeded` 来显示响应令牌。有关使用 `at-request-succeeded` 自定义事件的代码示例，请参阅[响应令牌](/help/administrating-target/response-tokens.md)。

## at.js 1.*x* at.js 2的参数。*x* payload映射 {#payload-mapping}

本节概述了 at.js 1.*x* and at.js 2.*x*。

在深入研究参数映射之前，这些库版本当前使用的端点已发生更改：

* at.js 1.*x* - `http://<client code>.tt.omtrdc.net/m2/<client code>/mbox/json`
* at.js 2.*x* - `http://<client code>.tt.omtrdc.net/rest/v1/delivery`

另一个重要区别是：

* at.js 1.*x* - 客户端代码是路径的一部分
* at.js 2.*x* - 客户端代码将作为查询字符串参数发送，例如：
   `http://<client code>.tt.omtrdc.net/rest/v1/delivery?client=democlient`

以下部分列出了每个 at.js 1.*x* 参数、其描述以及相应的 2.0.0 JSON 有效负载（如果适用）：

### at_property

（at.js 1.*x* 参数）

用于[企业用户权限](/help/administrating-target/c-user-management/property-channel/property-channel.md)。

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

（at.js 1.*x* 参数）

访客浏览器窗口的高度。

at.js 2.*x* JSON有效负荷：

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

（at.js 1.*x* 参数）

访客浏览器窗口的宽度。

at.js 2.*x* JSON payload:

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

（at.js 1.*x* 参数）

时区偏移。

at.js 2.*x* JSON payload:

```
{
  "context": {
    "timeOffsetInMinutes": -480
  }
}
```

### screenHeight

（at.js 1.*x* 参数）

访客屏幕的高度。

at.js 2.*x* JSON payload:

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

（at.js 1.*x* 参数）

访客屏幕的宽度。

at.js 2.*x* JSON payload:

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

（at.js 1.*x* 参数）

访客屏幕的颜色深度。

at.js 2.*x* JSON payload:

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

（at.js 1.*x* 参数）

Target 库运行的页面的域。

at.js 2.*x* JSON payload:

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

（at.js 1.*x* 参数）

浏览器的 WEB GL 渲染器功能。我们的设备检测机制使用此参数来确定访客的设备是桌面设备、iPhone、Android 设备，还是其他设备。

at.js 2.*x* JSON payload:

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

（at.js 1.*x* 参数）

页面 URL。

at.js 2.*x* JSON payload:

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

（at.js 1.*x* 参数）

页面反向链接。

at.js 2.*x* JSON payload:

```
{
  "context": {
    "address": {
       "referringUrl": "http://google.com"
    }
  }
}
```

### mbox（名称）等于全局 mbox

（at.js 1.*x* 参数）

交付 API 不再具有全局 mbox 概念。在 JSON 有效负载中，您必须使用 `execute > pageLoad`。

at.js 2.*x* JSON payload:

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

### mbox（名称）*不*&#x200B;等于全局 mbox

（at.js 1.*x* 参数）

要使用 mbox 名称，请将其传递到 `execute > mboxes`。mbox 需要索引和名称。

at.js 2.*x* JSON payload:

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

### mboxId

（at.js 1.*x* 参数）

已不再使用。

### mboxCount

（at.js 1.*x* 参数）

已不再使用。

### mboxRid

（at.js 1.*x* 参数）

下游系统用来帮助进行调试的请求 ID。

at.js 2.*x* JSON payload:

```
{
  "requestId": "2412234442342"
  ....
}
```

### mboxTime

（at.js 1.*x* 参数）

已不再使用。

### mboxSession

（at.js 1.*x* 参数）

会话 ID 作为查询字符串参数 (`sessionId`) 发送到交付 API 端点。

### mboxPC

（at.js 1.*x* 参数）

TNT ID 被传递到 `id > tntId`。

at.js 2.*x* JSON有效负荷：

```
{
  "id": {
    "tntId": "ca5ddd7e33504c58b70d45d0368bcc70.21_3"
  }
  ....
}
```

### mboxMCGVID

（at.js 1.*x* 参数）

Marketing Cloud 访客 ID 被传递到 `id > marketingCloudVisitorId`。

at.js 2.*x* JSON payload:

```
{
  "id": {
    "marketingCloudVisitorId": "797110122341429343505"
  }
  ....
}
```

### `vst.aaaa.id` 和 `vst.aaaa.authState`

（at.js 1.*x* 参数）

客户 ID 应被传递到 `id > customerIds`。

at.js 2.*x* JSON payload:

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

（at.js 1.*x* 参数）

用于链接不同 Target ID 的客户第三方 ID。

at.js 2.*x* JSON有效负荷：

```
{
  "id": {
    "thirdPartyId": "1232312323123"
  }
  ....
}
```

### mboxMCSDID

（at.js 1.*x* 参数）

SDID，也称为补充数据 ID。应被传递到 `experienceCloud > analytics > supplementalDataId`。

at.js 2.*x* JSON payload:

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

### vst.trk

（at.js 1.*x* 参数）

Analytics 跟踪服务器。应被传递到 `experienceCloud > analytics > trackingServer`。

at.js 2.*x* JSON有效负荷：

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

### vst.trks

（at.js 1.*x* 参数）

Analytics 跟踪服务器的安全性。应被传递到 `experienceCloud > analytics > trackingServerSecure`。

at.js 2.*x* JSON有效负荷：

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

（at.js 1.*x* 参数）

Audience Manager 位置提示。应被传递到 `experienceCloud > audienceManager > locationHint`。

at.js 2.*x* JSON有效负荷：

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

（at.js 1.*x* 参数）

Audience Manager Blob。应被传递到 `experienceCloud > audienceManager > blob`。

at.js 2.*x* JSON有效负荷：

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

（at.js 1.*x* 参数）

版本将通过 version 参数作为查询字符串参数发送。

## Training video: at.js 2.*x* architectural diagram

at.js 2.*x* 增强了 Adobe Target 对 SPA 的支持，并与其他 Experience Cloud 解决方案集成。该视频介绍了如何将所有内容结合到一起。

>[!VIDEO](https://video.tv.adobe.com/v/26250?captions=chi_hans)

请参 [阅了解at.js 2的使用方法。*x适用*](https://helpx.adobe.com/target/kt/using/atjs20-diagram-technical-video-understand.html) ，以获取更多信息。