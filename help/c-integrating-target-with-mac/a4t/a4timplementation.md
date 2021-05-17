---
keywords: A4T;Adobe Analytics；基于分析的活动；分析报表包；报表包；分析目标集成；配置报表包；at.js;atjs;adobe experience platform web sdk;aep web sdk；平台web sdk
description: 按照为 [!DNL Target] (A4T) in your Adobe [!DNL Target] 和Adobe Analytics解决方案实施Analytics所需的步骤操作。
title: 如何为 [!DNL Target] (A4T)实施Analytics?
feature: Analytics for Target (A4T)
exl-id: b5269b9e-01ef-449a-bb03-3dcc2cd68af7
source-git-commit: efa796edf3cd4da718fdcb0dbfd3d6f635ebf401
workflow-type: tm+mt
source-wordcount: '1156'
ht-degree: 24%

---

# [!DNL Target]实施的分析

当将[!DNL Adobe Analytics]作为[!DNL Adobe Target](A4T)的报告源实施时，需要执行多个步骤。 该过程会因您是使用[[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html)实现A4T还是使用at.js而不同。

## Adobe Experience Platform Web SDK实施的实施步骤 {#platform}

>[!NOTE]
>
>本文讨论的[!DNL Adobe Experience Platform Web SDK]实现中的A4T支持计划随[!DNL Platform Web SDK]版本2.5.0版本（2021年5月24日）提供。

以下各节描述了在您计划使用平台Web SDK时将此集成部署到您的站点所需的步骤：

### 第1步：请求[!DNL Analytics]和[!DNL Target]的设置

在实施A4T之前，必须为[!DNL Analytics]和[!DNL Target]设置。 [使用此表单请求置备](https://adobe.allegiancetech.com/cgi-bin/qwebcorporate.dll?idx=X8SVES)。

### 步骤 2：设置用户权限

必须先满足用户帐户要求，然后才能在[!DNL Target]中创建基于[!DNL Analytics]的活动。 请参阅[用户权限要求](/help/c-integrating-target-with-mac/a4t/account-reqs.md)。

### 第3步：创建边缘配置

使用边缘配置工具使用[!DNL Adobe Experience Platform Launch]创建边缘配置。 配置[[!DNL Analytics] and [!DNL Target] 边缘配置设置](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/datastreams.html)。

### 第4步：安装和配置平台Web SDK

要开始交付[!DNL Target]体验并应用[!DNL Analytics]以用于跟踪和分析目的，请在您的网页上[安装](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html)和[配置](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html)平台Web SDK。

### 第5步：启用使用A4T的选项

在[!DNL Target] UI中，单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 可视体验书写器]**，然后选择&#x200B;**[!UICONTROL 按活动]**&#x200B;或&#x200B;**[!UICONTROL Adobe Analytics]**&#x200B;选择。

* **[!UICONTROL 如果选择为每个活动选择，您在创建每个活动时可以在 和 之间进行选择。]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL 如果选择 Adobe ，则会将 Analytics 设置为您创建的所有活动的报表源。]**[!DNL Analytics]

## at.js实施的实施步骤{#section_73961BAD5BB4430A95E073DE5C026277}

以下各节介绍了在您计划使用at.js时将此集成部署到站点所需的步骤：

### 步骤 1：请求配置 Analytics 和 Target。

将[!DNL Analytics]作为[!DNL Target]的报告源实施后，必须为[!DNL Analytics]和[!DNL Target]设置。 [使用此表单请求置备](http://www.adobe.com/go/audiences)。

### 步骤 2：设置用户权限

必须先满足用户帐户要求，然后才能在[!DNL Target]中创建基于[!DNL Analytics]的活动。 请参阅[用户权限要求](/help/c-integrating-target-with-mac/a4t/account-reqs.md)。

### 步骤 3：实施 Experience Cloud 访客 ID 服务。

通过访客 ID 服务，您可以在各个 [!DNL Adobe Experience Cloud] 解决方案中识别用户。实施或迁移到所需版本的Experience Cloud访客ID。 有关更多信息，请参阅[实施之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

请参阅&#x200B;*Experience Cloud访客ID服务*&#x200B;文档中的[为目标](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-target.html)实施Experience CloudID服务。

### 步骤 4：更新 AppMeasurement for JavaScript 或 s_code

实施或迁移到所需版本的appMeasurement.js。 有关更多信息，请参阅[实施之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

有关新的实现，请参阅&#x200B;*Analytics实施指南*&#x200B;中的[JavaScript实现概述](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html)。

有关迁移，请参阅&#x200B;*分析实施指南*&#x200B;中的[迁移到AppMeasurement for JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/migrate-from-hcode.html)。

### 第5步：下载和更新at.js

使用生产帐户实施或迁移到所需版本的at.js。 无需对代码进行修改。

有关更多信息，请参阅[实施之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

### 第6步：主持人at.js

如果您之前部署了at.js，则可以用更新后的版本替换现有文件。 有关更多信息，请参阅[实施之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

如果不替换，则可以将此文件与访客 ID 服务文件和 AppMeasurement for JavaScript 文件一起托管。这些文件必须托管在可从您网站上的所有页面进行访问的 Web 服务器上。下一步需要使用这些文件的路径。

### 第7步：在所有网站页面上引用at.js {#step7}

在VisitorAPI.js下添加at.js，方法是在每个页面的标记中添加以下代码行：

对于 at.js：

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

必须先加载VisitorAPI.js，然后再加载at.js。 如果要更新现有的at.js或mbox.js文件，请确保验证加载顺序。

从实现角度来看，[!DNL Target]和[!DNL Analytics]集成的默认设置是使用从页面传递的SDID自动在后端将[!DNL Target]和[!DNL Analytics]请求串接在一起。

您可以控制将与[!DNL Target]相关的分析数据发送到[!DNL Analytics]的方式和时间，以便进行报告。 如果您不希望选择加入使用默认设置，让[!DNL Target]和[!DNL Analytics]通过SDID自动缝合分析数据，请通过&#x200B;**window.targetGlobalSettings**&#x200B;设置&#x200B;**analyticsLogging = client_side**。 注意：低于 2.1 的任何版本均不支持此方法。

例如：

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

此设置具有全局效果，这意味着at.js发出的每个调用都具有&#x200B;**analyticsLogging:在[!DNL Target]请求中发送的&quot;client_side&quot;**，并为每个请求返回一个分析有效负荷。 设置此选项时，返回的有效负荷的格式如下所示：

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

然后，可以通过[数据插入API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)将负载转发到Analytics。 对于“自动分配”和“自动目标”活动，您还必须转发sessionId。 有关详细信息，请参阅&#x200B;*Adobe Target SDK*&#x200B;指南中的[目标分析(A4T)报告](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting)。

如果不需要全局设置，而更可取的是按需方法，请通过传入&#x200B;**analyticsLogging，使用at.js函数[getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md):&quot;client_side&quot;**。 仅为此调用返回分析负载，且[!DNL Target]后端不会将负载转发到[!DNL Analytics]。 通过采用此方法，默认情况下，每个at.js [!DNL Target]请求都返回有效负荷，但仅在需要并指定时才返回。

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

然后，可以通过[数据插入API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)将有效负荷转发到[!DNL Analytics]。

### 步骤 8：验证实施 {#step8}

更新 JavaScript 库后，加载您的页面，以确认 调用中的 `mboxMCSDID`[!DNL Target] 参数值与 页面查看调用中的 `sdid`[!DNL Analytics] 参数值相匹配。

确认这些值是否在单页应用程序(SPA)中匹配尤为重要，因为在单页应用程序中，调用的顺序并不总是可预测的。

>[!NOTE]
>
>要使A4T正常工作，必须匹配这些值。

### 步骤 9：（可选）删除之前的集成代码

Adobe建议您删除之前的集成，以简化实施并消除解决系统间差异的需要。 您可以删除之前SC到T&amp;T集成所部署的任何代码，包括`mboxLoadSCPlugin`。

### 步骤 10：启用可将 Analytics 用作 Target 报表源的选项

在[!DNL Target]中，单击&#x200B;**[!UICONTROL “管理”>“可视体验书写器”]**，然后选择&#x200B;**[!UICONTROL “按活动]**&#x200B;或&#x200B;**[!UICONTROL Adobe Analytics]**&#x200B;选择”以启用这些选项。

* **[!UICONTROL 如果选择为每个活动选择，您在创建每个活动时可以在 和 之间进行选择。]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL 如果选择 Adobe ，则会将 Analytics 设置为您创建的所有活动的报表源。]**[!DNL Analytics]


