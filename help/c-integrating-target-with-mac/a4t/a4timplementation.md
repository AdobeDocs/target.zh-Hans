---
keywords: A4T;Adobe Analytics;Analytics-based activity;Analytics report suite;report suite;Analytics Target integration;configure report suite
description: 在实施 Adobe Analytics 作为 Target 报表源 (A4T) 时，需要执行几个步骤。
title: Analytics for Target 实施
uuid: da6498c8-1549-4c36-ae42-38c731a28f08
translation-type: tm+mt
source-git-commit: 3edb13b196240bb1918fc66edcc653936e32d3ef
workflow-type: tm+mt
source-wordcount: '879'
ht-degree: 63%

---


# Analytics for Target 实施{#analytics-for-target-implementation}

Several steps are required when implementing [!DNL Adobe Analytics] as the reporting source for [!DNL Target] (A4T).

## Implementation steps {#section_73961BAD5BB4430A95E073DE5C026277}

以下各节介绍了将此集成部署到站点所需的步骤。

## 步骤 1：请求配置 Analytics 和 Target。

After you implement [!DNL Analytics] as the reporting source for [!DNL Target], you must be provisioned for [!DNL Analytics] and [!DNL Target]. [使用此表单请求设置](http://www.adobe.com/go/audiences)。

## 步骤 2：设置用户权限

User account requirements must be met before you can create an [!DNL Analytics]-based activity in [!DNL Target]. 请参阅[用户权限要求](/help/c-integrating-target-with-mac/a4t/account-reqs.md)。

## 步骤 3：实施 Experience Cloud 访客 ID 服务。

通过访客 ID 服务，您可以在各个 [!DNL Adobe Experience Cloud] 解决方案中识别用户。您必须实施或迁移到所需版本的 Experience Cloud 访客 ID 服务。有关更多信息，请参阅[实施之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

See [Implement the Experience Cloud ID Service for Target](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/setup-target.html) in the *Experience Cloud Visitor ID Service* documentation.

## 步骤 4：更新 AppMeasurement for JavaScript 或 s_code

您必须实施或迁移到所需版本的 appMeasurement.js。有关更多信息，请参阅[实施之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

有关新的实现，请参 [阅《Analytics实施指南](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/javascript-implementation-overview.html) 》中 *的JavaScript实现概述*。

有关迁移，请参 [阅《Analytics实施指南](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs-migrate.html) 》中 *的迁移到AppMeasurement for JavaScript*。

## 步骤 5：下载并更新 at.js 或 mbox.js

您必须使用生产帐户实施或迁移到所需版本的 at.js 或 mbox.js。无需对代码进行修改。

有关更多信息，请参阅[实施之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

## 步骤 6：托管 at.js 或 mbox.js

如果您之前已部署 at.js 或 mbox.js，则可以将现有文件替换为更新版本。有关更多信息，请参阅[实施之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

如果不替换，则可以将此文件与访客 ID 服务文件和 AppMeasurement for JavaScript 文件一起托管。这些文件必须托管在可从您网站上的所有页面进行访问的 Web 服务器上。下一步需要使用这些文件的路径。

## 步骤 7：在所有网站页面上引用 at.js 或 mbox.js {#step7}

通过在每个页面的标记中添加下面一行代码，将 at.js 或 mbox.js 包含在 VisitorAPI.js 下：

对于 at.js：

```
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

对于 mbox.js：

```
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/mbox.js"></script>
```

必须先加载 VisitorAPI.js，然后再加载 at.js 或 mbox.js。如果您要更新现有的 at.js 或 mbox.js 文件，请务必确认加载顺序。

The way the out-of-the-box settings are configured for [!DNL Target] and [!DNL Analytics] integration from an implementation perspective is to use the SDID that is passed from the page to stitch the [!DNL Target] and [!DNL Analytics] request together on the backend automatically for you.

However, if you want more control on how and when to send analytics data related to [!DNL Target] to [!DNL Analytics] for reporting purposes, and you do not want to opt-in to the default settings of having [!DNL Target] and [!DNL Analytics] automatically stitch the analytics data via the SDID, then you can set **analyticsLogging = client_side** via **window.targetGlobalSettings**. 注意：低于 2.1 的任何版本均不支持此方法。

例如：

```
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

此设置具有全局效果，这意味着 at.js 进行的每次调用都将在 请求中发送 **analyticsLogging: &quot;client_side&quot;**，并且将为每个请求返回分析有效负载。[!DNL Target]完成此设置后，返回的有效负载格式如下所示：

```
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

然后，可以通过数据插入API将有效负 [载转发给Analytics](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)。

如果不希望进行全局设置并且想要使用按需方法，则可以使用 at.js 函数 [getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) 通过传入 **analyticsLogging: &quot;client_side&quot;** 来实现此目的。The analytics payload will be returned for only this call and the [!DNL Target] backend will not forward the payload to [!DNL Analytics]. By pursuing this approach, every at.js [!DNL Target] request will not return the payload by default, but instead only when desired and specified.

例如：

```
adobe.target.getOffers({
      request: {
        experienceCloud: {
          analytics: {
            logging: "client_side"
          }
        },
        prefetch: {
          mboxes: [{
            index: 0,
            name: "a1-serverside-xt"
          }]
        }
      }
    })
    .then(console.log)
```

此调用将会调用一个响应，您可以从中提取分析有效负载。

响应如下所示：

```
{
  "prefetch": {
    "mboxes": [{
      "index": 0,
      "name": "a1-serverside-xt",
      "options": [{
        "content": "<img src=\"http://s7d2.scene7.com/is/image/TargetAdobeTargetMobile/L4242-xt-usa?tm=1490025518668&fit=constrain&hei=491&wid=980&fmt=png-alpha\"/>",
        "type": "html",
        "eventToken": "n/K05qdH0MxsiyH4gX05/2qipfsIHvVzTQxHolz2IpSCnQ9Y9OaLL2gsdrWQTvE54PwSz67rmXWmSnkXpSSS2Q==",
        "responseTokens": {
          "profile.memberlevel": "0",
          "geo.city": "bucharest",
          "activity.id": "167169",
          "experience.name": "USA Experience",
          "geo.country": "romania"
        }
      }],
      "analytics": {
        "payload": {
          "pe": "tnt",
          "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
        }
      }
    }]
  }
}
```

然后，可以通过数据插 [!DNL Analytics] 入API将 [有效负荷转发到](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)。

## 步骤 8：验证实施 {#step8}

更新 JavaScript 库后，加载您的页面，以确认 调用中的 `mboxMCSDID`[!DNL Target] 参数值与 页面查看调用中的 `sdid`[!DNL Analytics] 参数值相匹配。

在单页应用程序 (SPA) 中，由于调用顺序并不总是可以预测，因此尤其务必要进行此验证。

**注意：**&#x200B;为使 A4T 能够正常运行，这些值必须匹配。

## 步骤 9：（可选）删除之前的集成代码

我们建议您删除之前的集成，以便简化您的实施，并免除解决系统间差异的麻烦。您可以删除可能已为之前的 SC 与 T&amp;T 集成部署的任何代码，包括 `mboxLoadSCPlugin`。

## 步骤 10：启用可将 Analytics 用作 Target 报表源的选项

In [!DNL Target], click **[!UICONTROL Administation > Visual Experience Composer]** and choose either **[!UICONTROL Select per activity]** or **[!UICONTROL Adobe Analytics]** to enable the options.

* **[!UICONTROL 如果选择为每个活动选择，您在创建每个活动时可以在 和 之间进行选择。]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL 如果选择 Adobe ，则会将 Analytics 设置为您创建的所有活动的报表源。]**[!DNL Analytics]

