---
keywords: A4T;Adobe Analytics;Analytics-based activity;Analytics report suite;report suite;Analytics Target integration;configure report suite
description: 在实施 Adobe Analytics 作为 Target 报表源 (A4T) 时，需要执行几个步骤。
title: Analytics for Target 实施
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: cf47b7f3625bb1c3430b9fba00c573f489efc448
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 50%

---


# Analytics for Target 实施{#analytics-for-target-implementation}

将[!DNL Adobe Analytics]作为[!DNL Target](A4T)的报告源实施时，需要几个步骤。

## 实施步骤{#section_73961BAD5BB4430A95E073DE5C026277}

以下各节介绍了将此集成部署到站点所需的步骤。

## 步骤 1：请求配置 Analytics 和 Target。

将[!DNL Analytics]作为[!DNL Target]的报告源实施后，必须为[!DNL Analytics]和[!DNL Target]设置。 [使用此表单请求设置](http://www.adobe.com/go/audiences)。

## 步骤 2：设置用户权限

必须满足用户帐户要求，才能在[!DNL Target]中创建基于[!DNL Analytics]的活动。 请参阅[用户权限要求](/help/c-integrating-target-with-mac/a4t/account-reqs.md)。

## 步骤 3：实施 Experience Cloud 访客 ID 服务。

通过访客 ID 服务，您可以在各个 [!DNL Adobe Experience Cloud] 解决方案中识别用户。您必须实施或迁移到所需版本的 Experience Cloud 访客 ID 服务。有关更多信息，请参阅[实施之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

请参阅&#x200B;*Experience CloudID服务*&#x200B;文档中的[为目标](https://experienceleague.adobe.com/docs/id-service/using/implementation-guides/setup-target.html)实施Experience CloudID服务。

## 步骤 4：更新 AppMeasurement for JavaScript 或 s_code

您必须实施或迁移到所需版本的 appMeasurement.js。有关更多信息，请参阅[实施之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

有关新的实现，请参阅&#x200B;*Analytics Implementation Guide*&#x200B;中的[JavaScript实现概述](https://experienceleague.adobe.com/docs/analytics/implementation/javascript-implementation/javascript-implementation-overview.html)。

有关迁移，请参阅&#x200B;*分析实施指南*&#x200B;中的[迁移到AppMeasurement for JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs-migrate.html)。

## 第5步：下载和更新at.js

必须使用生产帐户实施或迁移到所需版本的at.js。 无需对代码进行修改。

有关更多信息，请参阅[实施之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

## 第6步：主持人at.js

如果您以前部署了at.js，则可以用更新的版本替换现有文件。 有关更多信息，请参阅[实施之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

如果不替换，则可以将此文件与访客 ID 服务文件和 AppMeasurement for JavaScript 文件一起托管。这些文件必须托管在可从您网站上的所有页面进行访问的 Web 服务器上。下一步需要使用这些文件的路径。

## 第7步：所有站点页面{#step7}上的引用at.js

通过在每页的标记中添加以下代码行，将at.js包含在VisitorAPI.js下：

对于 at.js：

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

在at.js之前加载VisitorAPI.js至关重要。如果要更新现有的at.js或mbox.js文件，请确保验证加载顺序。

从实现角度为[!DNL Target]和[!DNL Analytics]集成配置现成设置的方法是使用从页面传递的SDID在后端自动将[!DNL Target]和[!DNL Analytics]请求串接在一起。

但是，如果您希望更多地控制将与[!DNL Target]相关的分析数据发送到[!DNL Analytics]以用于报告目的的方式和时间，并且您不希望选择通过SDID使[!DNL Target]和[!DNL Analytics]自动缝合分析数据的默认设置，则可以通过&#x200B;**analyticsLogging = client_side**&#x200B;通过&#x200B;**设置window.targetGlobalSettings**。 注意：低于 2.1 的任何版本均不支持此方法。

例如：

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

此设置具有全局效果，这意味着 at.js 进行的每次调用都将在 请求中发送 **analyticsLogging: &quot;client_side&quot;**，并且将为每个请求返回分析有效负载。[!DNL Target]完成此设置后，返回的有效负载格式如下所示：

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

然后，可以通过[数据插入API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)将有效负荷转发到Analytics。 请注意，对于[!UICONTROL 自动分配]和[!UICONTROL 自动目标]活动，您还需要转发sessionId。 有关详细信息，请参阅&#x200B;*Adobe TargetSDK*&#x200B;指南中的[目标分析(A4T)报告](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting)。

如果不希望进行全局设置并且想要使用按需方法，则可以使用 at.js 函数 [getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) 通过传入 **analyticsLogging: &quot;client_side&quot;** 来实现此目的。将仅返回此调用的分析有效负荷，且[!DNL Target]后端不会将有效负荷转发到[!DNL Analytics]。 通过采用此方法，默认情况下，每个at.js [!DNL Target]请求都不会返回有效负荷，而是仅在需要并指定时才返回。

例如：

```javascript
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

```javascript
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

然后，可通过[数据插入API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)将有效负荷转发到[!DNL Analytics]。

## 步骤 8：验证实施 {#step8}

更新 JavaScript 库后，加载您的页面，以确认 调用中的 `mboxMCSDID`[!DNL Target] 参数值与 页面查看调用中的 `sdid`[!DNL Analytics] 参数值相匹配。

在单页应用程序 (SPA) 中，由于调用顺序并不总是可以预测，因此尤其务必要进行此验证。

**注意：**&#x200B;为使 A4T 能够正常运行，这些值必须匹配。

## 步骤 9：（可选）删除之前的集成代码

我们建议您删除之前的集成，以便简化您的实施，并免除解决系统间差异的麻烦。您可以删除可能已为之前的 SC 与 T&amp;T 集成部署的任何代码，包括 `mboxLoadSCPlugin`。

## 步骤 10：启用可将 Analytics 用作 Target 报表源的选项

在[!DNL Target]中，单击&#x200B;**[!UICONTROL 管理>可视体验书写器]**，然后选择&#x200B;**[!UICONTROL 按活动]**&#x200B;或&#x200B;**[!UICONTROL Adobe Analytics]**&#x200B;选择以启用这些选项。

* **[!UICONTROL 如果选择为每个活动选择，您在创建每个活动时可以在 和 之间进行选择。]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL 如果选择 Adobe ，则会将 Analytics 设置为您创建的所有活动的报表源。]**[!DNL Analytics]

