---
keywords: A4T；Adobe Analytics；基于Analytics的活动；Analytics报表包；报表包；Analytics Target集成；配置报表包；at.js；atjs；adobe experience platform web sdk；aep web sdk；平台web sdk
description: 请按照为实施Analytics所需的步骤操作 [!DNL Target] (A4T)在您的Adobe中 [!DNL Target] 和Adobe Analytics解决方案。
title: 如何实施Analytics for [!DNL Target] (A4T)？
feature: Analytics for Target (A4T)
exl-id: b5269b9e-01ef-449a-bb03-3dcc2cd68af7
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '1158'
ht-degree: 26%

---

# Analytics for[!DNL Target]实施

实施时需要执行几个步骤 [!DNL Adobe Analytics] 作为的报表源 [!DNL Adobe Target] (A4T)。 根据您是否使用实施A4T，此过程会有所不同 [[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) 或使用at.js。

## ![Adobe Experience Platform Web SDK徽章](/help/main/assets/platform.png) Adobe Experience Platform Web SDK实施步骤 {#platform}

以下部分介绍了在计划使用Platform Web SDK时将此集成部署到站点时所需的步骤：

### 步骤1：请求配置 [!DNL Analytics] 和 [!DNL Target]

在实施A4T之前，必须预配 [!DNL Analytics] 和 [!DNL Target]. [使用此表单可请求进行配置](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y).

### 步骤 2：设置用户权限

必须先满足用户帐户要求，然后才能根据以下条件创建活动 [!DNL Analytics] 在 [!DNL Target]. 请参阅[用户权限要求](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md)。

### 步骤3：创建Edge配置

创建Edge配置，使用 [!DNL Adobe Experience Platform] 使用edge配置工具。 配置 [[!DNL Analytics] and [!DNL Target] 边缘配置设置](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/datastreams.html).

### 步骤4：安装和配置Platform Web SDK

开始投放 [!DNL Target] 体验和应用 [!DNL Analytics] 出于跟踪和分析目的， [安装](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html) 和 [配置](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) 网站页面上的Platform Web SDK。

### 步骤5：启用用于使用A4T的选项

在 [!DNL Target] UI，单击 **[!UICONTROL 管理]** > **[!UICONTROL 可视化体验编辑器]**，然后选择以下任一选项 **[!UICONTROL 为每个活动选择]** 或 **[!UICONTROL Adobe Analytics]**.

* **[!UICONTROL 如果选择为每个活动选择，您在创建每个活动时可以在 和 之间进行选择。]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL 如果选择 Adobe ，则会将 Analytics 设置为您创建的所有活动的报表源。]**[!DNL Analytics]

## ![at.js徽章](/help/main/assets/atjs.png) at.js实施的实施步骤{#section_73961BAD5BB4430A95E073DE5C026277}

以下部分介绍了在计划使用at.js时，将此集成部署到站点所需的步骤：

### 步骤 1：请求配置 Analytics 和 Target。

实施之后 [!DNL Analytics] 作为的报表源 [!DNL Target]，您必须已配置 [!DNL Analytics] 和 [!DNL Target]. [使用此表单可请求进行配置](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}.

### 步骤 2：设置用户权限

必须先满足用户帐户要求，然后才能创建 [!DNL Analytics]中基于的活动 [!DNL Target]. 请参阅[用户权限要求](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md)。

### 步骤 3：实施 Experience Cloud 访客 ID 服务。

通过访客 ID 服务，您可以在各个 [!DNL Adobe Experience Cloud] 解决方案中识别用户。实施或迁移到所需版本的Experience Cloud访客ID。 有关更多信息，请参阅[实施之前](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

参见 [实施适用于Target的Experience CloudID服务](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-target.html) 在 *Experience Cloud访客ID服务* 文档。

### 步骤 4：更新 AppMeasurement for JavaScript 或 s_code

实施或迁移到所需版本的appMeasurement.js。 有关更多信息，请参阅[实施之前](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

有关新实施的信息，请参阅 [JavaScript实施概述](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html) 在 *Analytics实施指南*.

有关迁移，请参阅 [迁移到AppMeasurement for JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/migrate-from-hcode.html) 在 *Analytics实施指南*.

### 步骤5：下载并更新at.js

使用您的生产帐户实施或迁移到所需版本的at.js。 无需对代码进行修改。

有关更多信息，请参阅[实施之前](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

### 步骤6：托管at.js

如果您之前部署了at.js，则可以使用更新版本替换现有文件。 有关更多信息，请参阅[实施之前](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

如果不替换，则可以将此文件与访客 ID 服务文件和 AppMeasurement for JavaScript 文件一起托管。这些文件必须托管在可从您网站上的所有页面进行访问的 Web 服务器上。下一步需要使用这些文件的路径。

### 步骤7：在所有网站页面上引用at.js {#step7}

通过将下面一行代码添加至每个页面的标记中，将at.js包含在VisitorAPI.js下：

对于 at.js：

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

必须先加载VisitorAPI.js，然后再加载at.js。 如果要更新现有的at.js文件，请确保验证加载顺序。

的默认设置 [!DNL Target] 和 [!DNL Analytics] 从实施角度来看，集成就是使用从页面传递的SDID来拼合 [!DNL Target] 和 [!DNL Analytics] 一起在后端自动请求。

您可以控制如何以及何时发送与相关的分析数据 [!DNL Target] 到 [!DNL Analytics] 作报告用途。 如果您不想选择使用默认设置，则 [!DNL Target] 和 [!DNL Analytics] 通过SDID自动拼合分析数据，设置 **analyticsLogging =客户端** via **window.targetGlobalSettings**. 注意：低于 2.1 的任何版本均不支持此方法。

例如：

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

此设置具有全局效果，这意味着at.js发出的每个调用都具有 **analyticsLogging： &quot;client_side&quot;** 发送于 [!DNL Target] 将为每个请求返回请求和analytics有效负载。 设置此选项后，返回的有效负载格式如下所示：

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

然后，可以通过将有效负载转发到Analytics [数据插入API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html). 对于自动分配和自动定位活动，还必须转发sessionId。 有关更多信息，请参阅 [Analytics for Target (A4T)报表](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html){target=_blank} 在 *ADOBE TARGET SDK* 指南。

如果不希望进行全局设置并且想要使用按需方法，请使用at.js函数 [getOffers()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-getoffers-atjs-2.html){target=_blank} 通过传入 **analyticsLogging： &quot;client_side&quot;**. 仅为此调用返回分析有效负载，并且 [!DNL Target] 后端未将有效负载转发到 [!DNL Analytics]. 通过采用这种方法，每个at.js [!DNL Target] 默认情况下，请求会返回有效负载，但只有在需要和指定时才会返回。

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

然后，可以将有效负载转发到 [!DNL Analytics] 通过 [数据插入API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

### 步骤 8：验证实施 {#step8}

更新 JavaScript 库后，加载您的页面，以确认 调用中的 `mboxMCSDID`[!DNL Target] 参数值与 页面查看调用中的 `sdid`[!DNL Analytics] 参数值相匹配。

尤其重要的是，要确认这些值与单页应用程序(SPA)中的值相匹配，因为此类应用程序的调用顺序并不总是可预测的。

>[!NOTE]
>
>A4T需要匹配这些值才能正常工作。

### 步骤 9：（可选）删除之前的集成代码

Adobe建议您删除之前的集成，以简化实施并消除解决系统之间差异的必要性。 您可以删除为以前的SC与T&amp;T集成部署的任何代码，包括 `mboxLoadSCPlugin`.

### 步骤 10：启用可将 Analytics 用作 Target 报表源的选项

In [!DNL Target]，单击 **[!UICONTROL 管理>报表]** 并选择 **[!UICONTROL 为每个活动选择]** 或 **[!UICONTROL Adobe Analytics]** 以启用选项。

* **[!UICONTROL 如果选择为每个活动选择，您在创建每个活动时可以在 和 之间进行选择。]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL 如果选择 Adobe ，则会将 Analytics 设置为您创建的所有活动的报表源。]**[!DNL Analytics]


