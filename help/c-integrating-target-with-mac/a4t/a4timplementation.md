---
keywords: A4T;Adobe Analytics；基于Analytics的活动；Analytics报表包；报表包；Analytics Target集成；配置报表包；at.js;atjs;adobe experience platform Web sdk;aep Web sdk；平台Web sdk
description: 按照为 [!DNL Target] (A4T) in your Adobe [!DNL Target] 和Adobe Analytics解决方案实施Analytics所需的步骤操作。
title: 如何实施适用于 [!DNL Target] (A4T)的Analytics?
feature: Analytics for Target (A4T)
exl-id: b5269b9e-01ef-449a-bb03-3dcc2cd68af7
source-git-commit: ed4e6715c120fe692c7f3f84f6b869b5ad9bd1b7
workflow-type: tm+mt
source-wordcount: '1164'
ht-degree: 24%

---

# 用于[!DNL Target]实施的Analytics

在实施[!DNL Adobe Analytics]作为[!DNL Adobe Target](A4T)的报表源时，需要执行几个步骤。 具体过程会因您是使用[[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html)实施A4T，还是使用at.js实施A4T而异。

## ![Adobe Experience Platform Web SDK徽](/help/assets/platform.png) 章Adobe Experience Platform Web SDK实施的实施步骤 {#platform}

>[!NOTE]
>
>本文中讨论的[!DNL Adobe Experience Platform Web SDK]实施中的A4T支持计划在[!DNL Platform Web SDK]版本2.5.0中提供（2021年5月24日）。

以下部分介绍了在您计划使用Platform Web SDK时，将此集成部署到您的网站所需的步骤：

### 步骤1:请求配置[!DNL Analytics]和[!DNL Target]

在实施A4T之前，必须针对[!DNL Analytics]和[!DNL Target]进行配置。 [使用此表单可请求进行配置](https://adobe.allegiancetech.com/cgi-bin/qwebcorporate.dll?idx=X8SVES)。

### 步骤 2：设置用户权限

必须满足用户帐户要求，然后才能在[!DNL Target]中创建基于[!DNL Analytics]的活动。 请参阅[用户权限要求](/help/c-integrating-target-with-mac/a4t/account-reqs.md)。

### 步骤3:创建边缘配置

使用边缘配置工具使用[!DNL Adobe Experience Platform Launch]创建边缘配置。 配置[[!DNL Analytics] and [!DNL Target] 边缘配置设置](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/datastreams.html)。

### 步骤4:安装和配置平台Web SDK

要开始交付[!DNL Target]体验并应用[!DNL Analytics]以进行跟踪和分析，请在您的网站页面上[安装](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html)和[配置](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html)平台Web SDK。

### 步骤5:启用用于使用A4T的选项

在[!DNL Target] UI中，单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 可视化体验编辑器]**，然后选择&#x200B;**[!UICONTROL 为每个活动]**&#x200B;选择或&#x200B;**[!UICONTROL Adobe Analytics]**。

* **[!UICONTROL 如果选择为每个活动选择，您在创建每个活动时可以在 和 之间进行选择。]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL 如果选择 Adobe ，则会将 Analytics 设置为您创建的所有活动的报表源。]**[!DNL Analytics]

## ![at.js徽](/help/assets/atjs.png) 章at.js实施的实施步骤{#section_73961BAD5BB4430A95E073DE5C026277}

以下部分介绍了如果您计划使用at.js，则将此集成部署到您的网站所需的步骤：

### 步骤 1：请求配置 Analytics 和 Target。

将[!DNL Analytics]作为[!DNL Target]的报表源实施后，必须为[!DNL Analytics]和[!DNL Target]配置。 [使用此表单可请求进行配置](http://www.adobe.com/go/audiences)。

### 步骤 2：设置用户权限

在[!DNL Target]中创建基于[!DNL Analytics]的活动之前，必须满足用户帐户要求。 请参阅[用户权限要求](/help/c-integrating-target-with-mac/a4t/account-reqs.md)。

### 步骤 3：实施 Experience Cloud 访客 ID 服务。

通过访客 ID 服务，您可以在各个 [!DNL Adobe Experience Cloud] 解决方案中识别用户。实施或迁移到所需版本的Experience Cloud访客ID。 有关更多信息，请参阅[实施之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

请参阅&#x200B;*Experience Cloud访客ID服务*&#x200B;文档中的[为Target](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-target.html)实施Experience CloudID服务。

### 步骤 4：更新 AppMeasurement for JavaScript 或 s_code

实施或迁移到所需版本的appMeasurement.js。 有关更多信息，请参阅[实施之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

有关新实施的信息，请参阅&#x200B;*Analytics实施指南*&#x200B;中的[JavaScript实施概述](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html)。

有关迁移，请参阅&#x200B;*Analytics实施指南*&#x200B;中的[迁移到AppMeasurement for JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/migrate-from-hcode.html)。

### 步骤5:下载和更新at.js

使用您的生产帐户实施或迁移到所需版本的at.js。 无需对代码进行修改。

有关更多信息，请参阅[实施之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

### 步骤6:托管at.js

如果您之前已部署at.js，则可以将现有文件替换为更新版本。 有关更多信息，请参阅[实施之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

如果不替换，则可以将此文件与访客 ID 服务文件和 AppMeasurement for JavaScript 文件一起托管。这些文件必须托管在可从您网站上的所有页面进行访问的 Web 服务器上。下一步需要使用这些文件的路径。

### 步骤7:在所有网站页面上引用at.js {#step7}

通过将下面一行代码添加到每个页面的标记中，将at.js包含到VisitorAPI.js下：

对于 at.js：

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

必须先加载VisitorAPI.js，然后再加载at.js。 如果您要更新现有的at.js或mbox.js文件，请确保验证加载顺序。

从实施角度来看，[!DNL Target]和[!DNL Analytics]集成的默认设置是使用从页面传递的SDID在后端自动将[!DNL Target]和[!DNL Analytics]请求拼合在一起。

您可以控制如何以及何时将与[!DNL Target]相关的分析数据发送到[!DNL Analytics]以进行报告。 如果您不想选择使用默认设置，即让[!DNL Target]和[!DNL Analytics]通过SDID自动拼合分析数据，请通过&#x200B;**window.targetGlobalSettings**&#x200B;设置&#x200B;**analyticsLogging = client_side**。 注意：低于 2.1 的任何版本均不支持此方法。

例如：

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

此设置具有全局效果，这意味着at.js进行的每次调用都具有&#x200B;**analyticsLogging:在[!DNL Target]请求中发送的&quot;client_side&quot;**，并且会为每个请求返回分析有效负载。 设置此选项时，返回的有效负载格式如下所示：

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

然后，可以通过[数据插入API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)将负载转发到Analytics。 对于自动分配和自动定位活动，还必须转发sessionId。 有关更多信息，请参阅&#x200B;*Adobe Target SDK*&#x200B;指南中的[Analytics for Target(A4T)报表](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting)。

如果不希望进行全局设置并且希望使用按需方法，请通过传入&#x200B;**analyticsLogging，使用at.js函数[getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md):&quot;client_side&quot;**。 仅为此调用返回分析有效负载，且[!DNL Target]后端不会将有效负载转发到[!DNL Analytics]。 通过采用这种方法，每个at.js [!DNL Target]请求都会默认返回有效负载，但只有在需要和指定时才会返回。

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

然后，可以通过[数据插入API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)将负载转发到[!DNL Analytics]。

### 步骤 8：验证实施 {#step8}

更新 JavaScript 库后，加载您的页面，以确认 调用中的 `mboxMCSDID`[!DNL Target] 参数值与 页面查看调用中的 `sdid`[!DNL Analytics] 参数值相匹配。

在单页应用程序(SPA)中，调用顺序并非总是可预测的情况下，确认这些值是否匹配尤为重要。

>[!NOTE]
>
>A4T要正常运行，需要匹配这些值。

### 步骤 9：（可选）删除之前的集成代码

Adobe建议您删除之前的集成，以简化实施，并消除解决系统间差异的需要。 您可以删除为之前的SC与T&amp;T集成部署的任何代码，包括`mboxLoadSCPlugin`。

### 步骤 10：启用可将 Analytics 用作 Target 报表源的选项

在[!DNL Target]中，单击&#x200B;**[!UICONTROL 管理>可视化体验编辑器]**，然后选择&#x200B;**[!UICONTROL 为每个活动]**&#x200B;选择或&#x200B;**[!UICONTROL Adobe Analytics]**&#x200B;以启用选项。

* **[!UICONTROL 如果选择为每个活动选择，您在创建每个活动时可以在 和 之间进行选择。]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL 如果选择 Adobe ，则会将 Analytics 设置为您创建的所有活动的报表源。]**[!DNL Analytics]


