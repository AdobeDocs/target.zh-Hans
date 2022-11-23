---
keywords: A4T;Adobe Analytics；基于Analytics的活动；Analytics报表包；报表包；Analytics Target集成；配置报表包；at.js;atjs;adobe experience platform Web sdk;aep Web sdk；平台Web sdk
description: 按照实施Analytics(适用于 [!DNL Target] (A4T)Adobe [!DNL Target] 和Adobe Analytics解决方案。
title: 如何为实施Analytics [!DNL Target] (A4T)?
feature: Analytics for Target (A4T)
exl-id: b5269b9e-01ef-449a-bb03-3dcc2cd68af7
source-git-commit: f19d7de5b248ab1a55e7aad47d2e445eadf69717
workflow-type: tm+mt
source-wordcount: '1162'
ht-degree: 24%

---

# Analytics for[!DNL Target]实施

实施时需要执行几个步骤 [!DNL Adobe Analytics] 作为报表源 [!DNL Adobe Target] (A4T)。 具体过程会因您是否使用 [[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) 或使用at.js。

## ![Adobe Experience Platform Web SDK徽章](/help/main/assets/platform.png) Adobe Experience Platform Web SDK实施的实施步骤 {#platform}

以下部分介绍了在您计划使用Platform Web SDK时，将此集成部署到您的网站所需的步骤：

### 步骤1:请求配置 [!DNL Analytics] 和 [!DNL Target]

在实施A4T之前，您必须配置 [!DNL Analytics] 和 [!DNL Target]. [使用此表单请求进行配置](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y).

### 步骤 2：设置用户权限

必须满足用户帐户要求，才能根据 [!DNL Analytics] in [!DNL Target]. 请参阅[用户权限要求](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md)。

### 步骤3:创建边缘配置

使用创建边缘配置 [!DNL Adobe Experience Platform] 使用边缘配置工具。 配置 [[!DNL Analytics] and [!DNL Target] 边缘配置设置](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/datastreams.html).

### 步骤4:安装和配置平台Web SDK

开始投放 [!DNL Target] 要应用的体验 [!DNL Analytics] 用于跟踪和分析， [安装](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html) 和 [配置](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) 平台Web SDK。

### 步骤5:启用用于使用A4T的选项

在 [!DNL Target] UI，单击 **[!UICONTROL 管理]** > **[!UICONTROL 可视化体验编辑器]**，然后选择 **[!UICONTROL 为每个活动选择]** 或 **[!UICONTROL Adobe Analytics]**.

* **[!UICONTROL 如果选择为每个活动选择，您在创建每个活动时可以在 和 之间进行选择。]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL 如果选择 Adobe ，则会将 Analytics 设置为您创建的所有活动的报表源。]**[!DNL Analytics]

## ![at.js徽章](/help/main/assets/atjs.png) at.js实施的实施步骤{#section_73961BAD5BB4430A95E073DE5C026277}

以下部分介绍了如果您计划使用at.js，则将此集成部署到您的网站所需的步骤：

### 步骤 1：请求配置 Analytics 和 Target。

实施后 [!DNL Analytics] 作为报表源 [!DNL Target]，则必须为 [!DNL Analytics] 和 [!DNL Target]. [使用此表单请求进行配置](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}。

### 步骤 2：设置用户权限

必须先满足用户帐户要求，然后才能创建 [!DNL Analytics]在中基于活动 [!DNL Target]. 请参阅[用户权限要求](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md)。

### 步骤 3：实施 Experience Cloud 访客 ID 服务。

通过访客 ID 服务，您可以在各个 [!DNL Adobe Experience Cloud] 解决方案中识别用户。实施或迁移到所需版本的Experience Cloud访客ID。 有关更多信息，请参阅[实施之前](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

请参阅 [实施适用于Target的Experience CloudID服务](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-target.html) 在 *Experience Cloud访客ID服务* 文档。

### 步骤 4：更新 AppMeasurement for JavaScript 或 s_code

实施或迁移到所需版本的appMeasurement.js。 有关更多信息，请参阅[实施之前](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

有关新实施，请参阅 [JavaScript实施概述](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html) 在 *Analytics实施指南*.

有关迁移，请参阅 [迁移到AppMeasurement for JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/migrate-from-hcode.html) 在 *Analytics实施指南*.

### 步骤5:下载和更新at.js

使用您的生产帐户实施或迁移到所需版本的at.js。 无需对代码进行修改。

有关更多信息，请参阅[实施之前](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

### 步骤6:托管at.js

如果您之前已部署at.js，则可以将现有文件替换为更新版本。 有关更多信息，请参阅[实施之前](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

如果不替换，则可以将此文件与访客 ID 服务文件和 AppMeasurement for JavaScript 文件一起托管。这些文件必须托管在可从您网站上的所有页面进行访问的 Web 服务器上。下一步需要使用这些文件的路径。

### 步骤7:在所有网站页面上引用at.js {#step7}

通过将下面一行代码添加到每个页面的标记中，将at.js包含到VisitorAPI.js下：

对于 at.js：

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

必须先加载VisitorAPI.js，然后再加载at.js。 如果您要更新现有的at.js文件，请确保验证加载顺序。

的默认设置 [!DNL Target] 和 [!DNL Analytics] 从实施角度来看，集成是使用从页面传递的SDID拼合 [!DNL Target] 和 [!DNL Analytics] 自动在后端一起请求。

您可以控制如何以及何时发送与 [!DNL Target] to [!DNL Analytics] 报表。 如果您不想选择使用 [!DNL Target] 和 [!DNL Analytics] 通过SDID自动拼合分析数据， **analyticsLogging = client_side** 通过 **window.targetGlobalSettings**. 注意：低于 2.1 的任何版本均不支持此方法。

例如：

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

此设置具有全局效果，这意味着at.js发出的每个调用都具有 **analytics日志记录：&quot;client_side&quot;** 在 [!DNL Target] 会为每个请求返回请求和analytics有效负载。 设置此选项时，返回的有效负载格式如下所示：

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

然后，可以通过 [数据插入API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html). 对于自动分配和自动定位活动，还必须转发sessionId。 有关更多信息，请参阅 [Analytics for Target(A4T)报表](https://developer.adobe.com/target/implement/server-side/sdk-guides/integration-with-experience-cloud/a4t-reporting/){target=_blank} *Adobe Target SDK* 的双曲余切值。

如果不希望进行全局设置并且希望使用按需方法，请使用at.js函数 [getOffers()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffers-atjs-2/)通过传入{target=_blank} **analytics日志记录：&quot;client_side&quot;**. 仅会为此调用返回分析有效负载，并且 [!DNL Target] 后端不会将有效负载转发到 [!DNL Analytics]. 通过采用这种方法，每个at.js [!DNL Target] 默认情况下，请求会返回有效负载，但只有在需要和指定时才会返回。

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

然后，可将该有效负载转发到 [!DNL Analytics] 通过 [数据插入API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

### 步骤 8：验证实施 {#step8}

更新 JavaScript 库后，加载您的页面，以确认 调用中的 `mboxMCSDID`[!DNL Target] 参数值与 页面查看调用中的 `sdid`[!DNL Analytics] 参数值相匹配。

在单页应用程序(SPA)中，调用顺序并非总是可预测的情况下，请务必确认这些值是否匹配。

>[!NOTE]
>
>A4T要正常运行，需要匹配这些值。

### 步骤 9：（可选）删除之前的集成代码

Adobe建议您删除之前的集成，以简化实施，并消除解决系统间差异的需要。 您可以删除之前为SC与T&amp;T集成部署的任何代码，包括 `mboxLoadSCPlugin`.

### 步骤 10：启用可将 Analytics 用作 Target 报表源的选项

在 [!DNL Target]，单击 **[!UICONTROL 管理>报表]** 选择 **[!UICONTROL 为每个活动选择]** 或 **[!UICONTROL Adobe Analytics]** 以启用选项。

* **[!UICONTROL 如果选择为每个活动选择，您在创建每个活动时可以在 和 之间进行选择。]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL 如果选择 Adobe ，则会将 Analytics 设置为您创建的所有活动的报表源。]**[!DNL Analytics]


