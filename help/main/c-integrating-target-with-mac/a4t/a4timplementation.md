---
keywords: A4T；Adobe Analytics；基于Analytics的活动；Analytics报表包；报表包；Analytics Target集成；配置报表包；at.js；atjs；adobe experience platform web sdk；aep web sdk；平台web sdk
description: 按照在Adobe [!DNL Target] 和Adobe Analytics解决方案中实施Analytics for [!DNL Target] (A4T)所需的步骤操作。
title: 如何为 [!DNL Target] (A4T)实施Analytics？
feature: Analytics for Target (A4T)
exl-id: b5269b9e-01ef-449a-bb03-3dcc2cd68af7
source-git-commit: ddfb06a17a24200b2aa4f01d370cc0e92ff5f180
workflow-type: tm+mt
source-wordcount: '1055'
ht-degree: 19%

---

# Analytics for [!DNL Target]实施

在实施[!DNL Adobe Analytics]作为[!DNL Adobe Target] (A4T)的报表源时，需要执行几个步骤。 此过程因您使用[[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html)还是使用at.js实施A4T而异。

## 适用于Adobe Experience Platform Web SDK实施的![Adobe Experience Platform Web SDK徽章](/help/main/assets/platform.png)实施步骤 {#platform}

如果您计划使用Platform Web SDK，以下部分将介绍将此集成部署到站点所需的步骤：

### 步骤1：请求配置[!DNL Analytics]和[!DNL Target]

在实施A4T之前，必须为[!DNL Analytics]和[!DNL Target]配置您。 [使用此表单请求进行配置](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y)。

### 步骤 2：设置用户权限

必须符合用户帐户要求，然后才能在[!DNL Target]中创建基于[!DNL Analytics]的活动。 请参阅[用户权限要求](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md)。

### 步骤3：创建Edge配置

使用边缘配置工具使用[!DNL Adobe Experience Platform]创建Edge配置。 配置[创建和配置数据流](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=zh-Hans)。

### 步骤4：安装和配置平台Web SDK

要开始提供[!DNL Target]体验并应用[!DNL Analytics]进行跟踪和分析，请在您的网站页面上[安装](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html)和[配置](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) Platform Web SDK。

### 步骤5：启用用于使用A4T的选项

在[!DNL Target]用户界面中，单击&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]**，然后选择&#x200B;**[!UICONTROL Select per activity]**&#x200B;或&#x200B;**[!UICONTROL Adobe Analytics]**。

* 创建每个活动时，**[!UICONTROL Select per activity]**&#x200B;允许您在[!DNL Target]和[!DNL Analytics]之间进行选择。
* **[!UICONTROL Adobe Analytics]**&#x200B;将[!DNL Analytics]设置为您创建的所有活动的报表源。

## 适用于at.js实施的![at.js徽章](/help/main/assets/atjs.png)实施步骤{#section_73961BAD5BB4430A95E073DE5C026277}

如果您计划使用at.js，以下部分将介绍将此集成部署到您的网站所需的步骤：

### 步骤 1：请求配置 Analytics 和 Target。

在您将[!DNL Analytics]实施为[!DNL Target]的报表源后，必须为您配置[!DNL Analytics]和[!DNL Target]。 [使用此表单请求进行配置](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}。

### 步骤 2：设置用户权限

必须先满足用户帐户要求，然后才能在[!DNL Target]中创建基于[!DNL Analytics]的活动。 请参阅[用户权限要求](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md)。

### 步骤 3：实施 Experience Cloud 访客 ID 服务。

访客ID服务允许您跨[!DNL Adobe Experience Cloud]解决方案识别用户。 实施或迁移到所需版本的Experience Cloud访客ID。 有关更多信息，请参阅[实施之前](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

请参阅&#x200B;*Experience Cloud访客ID服务*&#x200B;文档中的[为Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-target.html)实施访客ID服务。

### 步骤 4：更新 AppMeasurement for JavaScript 或 s_code

实施或迁移到所需版本的appMeasurement.js。 有关更多信息，请参阅[实施之前](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

有关新实施的信息，请参阅&#x200B;*JavaScript实施指南*&#x200B;中的[Analytics实施概述](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html)。

有关迁移，请参阅&#x200B;*Analytics Implementation Guide*&#x200B;中的[迁移到JavaScript的AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/js/migrate-from-hcode.html)。

### 步骤5：下载并更新at.js

使用您的生产帐户实施或迁移到所需版本的at.js。 无需对代码进行修改。

有关更多信息，请参阅[实施之前](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

### 步骤6：托管at.js

如果您之前已部署at.js，则可以将现有文件替换为更新版本。 有关更多信息，请参阅[实施之前](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

如果不替换，则可以将此文件与访客 ID 服务文件和 AppMeasurement for JavaScript 文件一起托管。这些文件必须托管在可从您网站上的所有页面进行访问的 Web 服务器上。下一步需要使用这些文件的路径。

### 步骤7：在所有网站页面上引用at.js {#step7}

通过将下面一行代码添加至每个页面的标记中，将at.js包含在VisitorAPI.js下：

对于 at.js：

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

必须先加载VisitorAPI.js，然后再加载at.js。 如果要更新现有的at.js文件，请确保验证加载顺序。

从实施的角度来看，[!DNL Target]和[!DNL Analytics]集成的默认设置为使用从页面传递的SDID在后端自动将[!DNL Target]和[!DNL Analytics]请求拼合在一起。

您可以控制如何以及何时将与[!DNL Target]相关的分析数据发送到[!DNL Analytics]以进行报告。 如果您不想选择使用[!DNL Target]和[!DNL Analytics]通过SDID自动拼合分析数据的默认设置，请通过&#x200B;**window.targetGlobalSettings**&#x200B;设置&#x200B;**analyticsLogging = client_side**。 注意：低于 2.1 的任何版本均不支持此方法。

例如：

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

此设置具有全局效果，这意味着at.js进行的每次调用都将在[!DNL Target]请求中发送&#x200B;**analyticsLogging： &quot;client_side&quot;**，并且将为每个请求返回分析有效负载。 设置此选项后，返回的有效负载格式如下所示：

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

然后，可以通过[数据插入API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)将该有效负载转发到Analytics。 对于自动分配和自动定位活动，还必须转发sessionId。 有关详细信息，请参阅&#x200B;*Adobe Target SDK*&#x200B;指南中的[Analytics for Target (A4T)报表](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html){target=_blank}。

如果不希望进行全局设置并且想要使用按需方法，请通过传入&#x200B;**analyticsLogging： &quot;client_side&quot;**&#x200B;来使用at.js函数[getOffers()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-getoffers-atjs-2.html){target=_blank}。 仅为此调用返回分析有效负载，[!DNL Target]后端未将该有效负载转发到[!DNL Analytics]。 如果采用这种方法，每个at.js [!DNL Target]请求都会默认返回有效负载，但只有在需要和指定时才会返回。

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

然后，可以通过[数据插入API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)将该有效负载转发到[!DNL Analytics]。

### 步骤 8：验证实施 {#step8}

更新JavaScript库后加载页面，以确认[!DNL Target]调用中的`mboxMCSDID`参数值与[!DNL Analytics]页面查看调用中的`sdid`参数值匹配。

尤其重要的是，要确认这些值与单页应用程序(SPA)中的值相匹配，因为后者的调用顺序并不总是可预见的。

>[!NOTE]
>
>A4T需要匹配这些值才能正常工作。

### 步骤 9：（可选）删除之前的集成代码

Adobe建议您删除之前的集成，以简化实施过程，并免除解决系统间差异的麻烦。 您可以删除为之前的SC与T&amp;T集成部署的任何代码，包括`mboxLoadSCPlugin`。

### 步骤 10：启用可将 Analytics 用作 Target 报表源的选项

在[!DNL Target]中，单击&#x200B;**[!UICONTROL Administration > Reporting]**&#x200B;并选择&#x200B;**[!UICONTROL Select per activity]**&#x200B;或&#x200B;**[!UICONTROL Adobe Analytics]**&#x200B;以启用这些选项。

* 创建每个活动时，**[!UICONTROL Select per activity]**&#x200B;允许您在[!DNL Target]和[!DNL Analytics]之间进行选择。
* **[!UICONTROL Adobe Analytics]**&#x200B;将[!DNL Analytics]设置为您创建的所有活动的报表源。


