---
keywords: 实施；javascript库；js;atjs；设备上决策；设备上决策；at.js；设备上；设备上
description: 了解如何使用at.js库执行设备上决策
title: 设备上决策如何与at.js JavaScript库一起使用？
feature: at.js
role: Developer
exl-id: 5ad6032b-9865-4c80-8800-705673657286
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '3552'
ht-degree: 7%

---

# at.js的设备内决策

从版本2.5.0开始，at.js提供了设备决策功能。 设备内决策允许您缓存 [A/B测试](/help/main/c-activities/t-test-ab/test-ab.md) 和 [体验定位](/help/main/c-activities/t-experience-target/experience-target.md) (XT)在浏览器上执行内存决策的活动，而无需对 [!DNL Adobe Target] 边缘网络。

[!DNL Target] 此外，还可以通过实时服务器调用，灵活地从实验和机器学习驱动（ML驱动）个性化活动中提供最相关、最新的体验。 换句话说，当性能最为重要时，您可以选择使用设备上决策。 但是，当需要最相关、最新且由ML驱动的体验时，可以改为进行服务器调用。

## 设备上决策的好处是什么？

设备上决策的好处包括：

* **提供速度惊人的决策和体验。** 分段和决策在内存和浏览器上执行，以避免阻止网络请求。
* **提高应用程序性能。** 在不影响最终用户体验的情况下，运行实验并为客户提供个性化。
* **提高Google网站质量分数。** 在内存中执行决策后，提高您在线业务的Google网站质量分数，使消费者更容易发现该数据。
* **从实时分析中学习。** 通过 [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)报表。 A4T允许您在关键时刻引导策略。

## 受支持的功能

通过Adobe Target JS SDK，客户可以灵活地在性能和数据新鲜度之间进行选择，以便做出决策。 换句话说，如果通过机器学习来提供最相关且最吸引人的个性化内容对您来说最为重要的，则应该进行实时服务器调用。 但是，当性能更为关键时，应该做出设备内和内存内的决策。 要使设备决策正常工作，请参阅支持的功能列表：

* 活动类型
* 受众定位
* 分配方法

有关更多信息，请参阅 [支持的设备决策功能](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/supported-features/).

## 设备内决策的工作原理是什么？

在启用设备决策的情况下部署和初始化at.js时， [规则对象](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/rule-artifact/){target=_blank}（包括您针对A/B和XT活动、受众和资产的设备决策）将从距离您访客最近的Akamai CDN下载并缓存到访客浏览器本地。 当从at.js发出请求以检索体验时，系统会根据缓存的规则对象中编码的元数据，在内存中决定要返回哪个体验。

## 决策方法

通过设备内决策， [!DNL Target] 引入了名为 [!UICONTROL 决策方法]. 的 [!UICONTROL 决策方法] 设置会指示at.js如何提供您的体验。 [!UICONTROL 决策方法] 具有三个值：

* [!UICONTROL 仅服务器端]
* [!UICONTROL 仅限设备内]
* [!UICONTROL 混合]

### 仅服务器端

[!UICONTROL 仅服务器端] 是开箱即用的默认决策方法，当在您的Web资产上实施和部署at.js 2.5.0+时。

使用 [!UICONTROL 仅限服务器端] 作为默认配置，表示所有决策都是在 [!DNL Target] 边缘网络，涉及阻止服务器调用。 这种方法可以引入增量延迟，但也会带来显着好处，例如让您能够应用Target的机器学习功能，这些功能包括 [Recommendations](/help/main/c-recommendations/recommendations.md), [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) （美联社）和 [自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md) 活动。

此外，使用Target的用户配置文件（跨会话和渠道保留）增强您的个性化体验，可以为您的业务提供强大的结果。

最后， [!UICONTROL 仅限服务器端] 允许您使用Adobe Experience Cloud并微调可通过Audience Manager和Adobe Analytics区段针对的受众。

下图说明了您的访客、浏览器、at.js 2.5.0及更高版本以及Adobe Target边缘网络之间的交互。 此流程图可捕获新访客和回访访客。

![仅服务器端流程图](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/server-side-only.png)

以下列表对应于图表中的数字：

| 步骤 | 描述 |
| --- | --- |
| 1 | 的 [!DNL Experience Cloud Visitor ID] 从 [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en). |
| 2 | at.js 库会同步加载，并隐藏文档正文。<br>   也可以选择预先隐藏页面上实施的代码片段，以异步方式加载at.js库。 |
| 3 | at.js库会隐藏主体以防止闪烁。 |
| 4 | 会发出一个页面加载请求，该请求包含所有已配置的参数，例如（ECID、客户ID、自定义参数、用户配置文件等）。 |
| 5 | 配置文件脚本在执行后进入配置文件存储区。<br>配置文件存储区从受众库请求符合条件的受众(例如从 [!DNL Adobe Analytics], [!DNL Adobe Audience Manager]，等等。)<br>客户属性会以批量过程发送到配置文件存储区。 |
| 6 | 用户档案存储用于受众资格鉴定和分段以筛选活动。 |
| 7 | 在从实时确定体验后，将选择生成的内容 [!DNL Target] 活动。 |
| 8 | at.js库会隐藏页面上与必须渲染的体验关联的相应元素。 |
| 9 | at.js库会显示正文，以便可以加载页面的其余部分以供访客查看。 |
| 10 | at.js库会处理DOM以从Target边缘网络渲染体验。 |
| 11 | 体验为访客呈现。 |
| 12 | 加载整个网页。 |
| 13 | [!DNL Analytics] 数据会发送到数据收集服务器。 |
| 14 | 目标数据与 [!DNL Analytics] 数据，并会在 [!DNL Analytics] 报表存储。 之后，便可以在 [!DNL Analytics] 和 [!DNL Analytics] 中通过 [!DNL Target] for Target[!UICONTROL  (A4T) 报表查看 ]Analytics 数据。 |

### 仅限设备内

[!UICONTROL 仅限设备内] 是at.js 2.5.0+中必须设置的决策方法，因为设备上决策只能在您的整个网页中使用。

设备上决策可以以惊人的速度提供您的体验和个性化活动，因为决策是根据缓存的规则对象做出的，该对象包含符合设备上决策资格条件的所有活动。

要了解有关哪些活动符合设备上决策的资格的更多信息，请参阅 [设备内决策支持的功能](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/supported-features/).

仅当性能在所有需要做出决策的页面中都非常关键时，才应使用此决策方法 [!DNL Target]. 此外，请记住，当选择此决策方法时，您的 [!DNL Target] 不符合设备上决策条件的活动将不会交付或执行。 at.js库2.5.0及更高版本配置为仅查找缓存的规则对象以做出决策。

下图说明了访客、浏览器、at.js 2.5.0及更高版本与Akamai CDN之间的交互。 Akamai CDN会缓存访客首次访问的规则对象。 对于新访客的首次页面访问，必须从Akamai CDN下载JSON规则对象，以在访客的浏览器中缓存到本地。 下载JSON规则对象后，将立即做出决策，而无需阻止网络调用。 以下流程图会捕获新访客。

![仅限设备内的流程图](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-only.png)

以下列表对应于图表中的数字：

>[!NOTE]
>
>[!DNL Adobe Target] 管理服务器会确定您所有符合设备上决策条件的活动的资格，生成JSON规则对象，并将其传播到Akamai CDN。 系统会持续监控您的活动以获取更新，以输出要传播到Akamai CDN的新JSON规则对象。

| 步骤 | 描述 |
| --- | --- |
| 1 | 的 [!DNL Experience Cloud Visitor ID] 从 [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | at.js 库会同步加载，并隐藏文档正文。<br>也可以选择预先隐藏页面上实施的代码片段，以异步方式加载at.js库。 |
| 3 | at.js库会隐藏主体以防止闪烁。 |
| 4 | at.js库会请求从访客最近的Akamai CDN中检索JSON规则对象。 |
| 5 | Akamai CDN将使用JSON规则对象进行响应。 |
| 6 | JSON规则对象会在访客的浏览器上缓存到本地。 |
| 7 | at.js库会解释JSON规则对象并执行检索体验和隐藏测试元素的决策。 |
| 8 | at.js库会显示正文，以便可以加载页面的其余部分以供访客查看。 |
| 9 | at.js库会处理DOM以从缓存的JSON规则对象中呈现体验。 |
| 10 | 体验为访客呈现。 |
| 11 | 加载整个网页。 |
| 12 | [!DNL Analytics] 数据会发送到数据收集服务器。目标数据与 [!DNL Analytics] 数据，并会在 [!DNL Analytics] 报表存储。 之后，便可以在 和 中通过 for Target (A4T) 报表查看 [!DNL Analytics][!DNL Analytics]Analytics 数据。[!DNL Target] |

下图说明了访客、浏览器、at.js 2.5.0及更高版本以及访客后续页面点击或返回访问的缓存JSON规则对象之间的交互。 由于JSON规则对象已在浏览器上缓存并可用，因此无需阻止网络调用即可立即做出决策。 此流程图可捕获后续页面导航或旧访客。

![用于后续页面导航和重复访问的仅限设备内流程图](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-only-subsequent.png)

以下列表对应于图表中的数字：

>[!NOTE]
>
>[!DNL Adobe Target] 管理服务器会确定您所有符合设备上决策条件的活动的资格，生成JSON规则对象，并将其传播到Akamai CDN。 系统会持续监控您的活动以获取更新，以输出要传播到Akamai CDN的新JSON规则对象。

| 步骤 | 描述 |
| --- | --- |
| 1 | 的 [!DNL Experience Cloud Visitor ID] 从 [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | at.js 库会同步加载，并隐藏文档正文。<br>也可以选择预先隐藏页面上实施的代码片段，以异步方式加载at.js库。 |
| 3 | at.js库会隐藏主体以防止闪烁。 |
| 4 | at.js库会解释JSON规则对象，并在内存中执行检索体验的决策。 |
| 5 | 已测试的元素处于隐藏状态。 |
| 6 | at.js库会显示正文，以便可以加载页面的其余部分以供访客查看。 |
| 7 | at.js库会处理DOM以从缓存的JSON规则对象中呈现体验。 |
| 8 | 体验为访客呈现。 |
| 9 | 加载整个网页。 |
| 10 | [!DNL Analytics] 数据会发送到数据收集服务器。目标数据与 [!DNL Analytics] 数据，并会在 [!DNL Analytics] 报表存储。 之后，便可以在 [!DNL Analytics] 和 [!DNL Analytics] 中通过 [!DNL Target] for Target[!UICONTROL  (A4T) 报表查看 ]Analytics 数据。 |

### 混合

[!UICONTROL 混合] 是at.js 2.5.0+中必须设置的决策方法，当设备上决策和需要网络调用访问Adobe Target边缘网络的活动都必须执行时。

如果您同时管理设备上的决策活动和服务器端活动，那么在思考如何部署和配置时，这可能会有些复杂且繁琐 [!DNL Target] 在您的页面上。 以混合决策方法， [!DNL Target] 知道何时必须对Adobe Target边缘网络进行服务器调用，以执行需要服务器端执行的活动，以及何时只执行设备上的决策。

JSON规则对象包含元数据，用于通知at.jsmbox是运行服务器端活动还是设备决策活动。 此决策方法可确保您打算快速交付的活动通过设备决策完成；对于需要更强大的ML驱动个性化的活动，这些活动会通过Adobe Target边缘网络完成。

下图说明了首次访问您页面的新访客在您的访客、浏览器、at.js 2.5.0及更高版本、Akamai CDN和Adobe Target边缘网络之间的交互。 此图表的优势在于，在通过Adobe Target边缘网络做出决策时，会异步下载JSON规则对象。

此方法可确保对象（可包含许多活动）的大小不会对决策的延迟产生负面影响。 同步下载JSON规则对象并随后做出决策也可能对延迟产生不利影响，并且可能不一致。 因此，混合决策方法是最佳实践建议，始终为新访客的决策进行服务器端调用，并且由于JSON规则对象是并行缓存的。 对于任何后续页面访问和回访，都会通过JSON规则对象从缓存和内存中做出决策。

![首次访客的混合流程图](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/hybrid-first-time-visitor.png)

以下列表对应于图表中的数字：

>[!NOTE]
>
>[!DNL Adobe Target] 管理服务器会确定您所有符合设备上决策条件的活动的资格，生成JSON规则对象，并将其传播到Akamai CDN。 系统会持续监控您的活动以获取更新，以输出要传播到Akamai CDN的新JSON规则对象。

| 步骤 | 描述 |
| --- | --- |
| 1 | 的 [!DNL Experience Cloud Visitor ID] 从 [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | at.js 库会同步加载，并隐藏文档正文。<br>也可以选择预先隐藏页面上实施的代码片段，以异步方式加载at.js库。 |
| 3 | at.js库会隐藏主体以防止闪烁。 |
| 4 | 系统会向Adobe Target边缘网络发出页面加载请求，其中包括所有已配置的参数，例如（ECID、客户ID、自定义参数、用户配置文件等）。 |
| 5 | 同时，at.js会请求从访客最近的Akamai CDN中检索JSON规则对象。 |
| 6 | (Adobe Target边缘网络)配置文件脚本执行并馈送到配置文件存储区。 配置文件存储区从受众库请求符合条件的受众(例如从 [!DNL Adobe Analytics], [!DNL Adobe Audience Manager]，等等。) |
| 7 | Akamai CDN将使用JSON规则对象进行响应。 |
| 8 | 用户档案存储用于受众资格鉴定和分段以筛选活动。 |
| 9 | 在从实时确定体验后，将选择生成的内容 [!DNL Target] 活动。 |
| 10 | at.js库会隐藏页面上与必须渲染的体验关联的相应元素。 |
| 11 | at.js库会显示正文，以便可以加载页面的其余部分以供访客查看。 |
| 12 | at.js库会处理DOM以从Target边缘网络渲染体验。 |
| 13 | 体验为访客呈现。 |
| 14 | 加载整个网页。 |
| 15 | [!DNL Analytics] 数据会发送到数据收集服务器。目标数据与 [!DNL Analytics] 数据，并会在 [!DNL Analytics] 报表存储。 之后，便可以在 [!DNL Analytics] 和 [!DNL Analytics] 中通过 [!DNL Target] for Target[!UICONTROL  (A4T) 报表查看 ]Analytics 数据。 |

下图说明了访客、浏览器、at.js 2.5.0及更高版本以及为后续页面导航或回访缓存的JSON规则对象之间的交互。 在此图表中，仅重点关注在设备上针对后续页面导航或回访做出决策的用例。 请记住，根据特定页面的活动处于何种状态，可以进行服务器端调用以执行服务器端决策。

![用于后续页面导航和重复访问的混合流程图](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/hybrid-subsequent.png)

以下列表对应于图表中的数字：

>[!NOTE]
>
>[!DNL Adobe Target] 管理服务器会确定您所有符合设备上决策条件的活动的资格，生成JSON规则对象，并将其传播到Akamai CDN。 系统会持续监控您的活动以获取更新，以输出要传播到Akamai CDN的新JSON规则对象。

| 步骤 | 描述 |
| --- | --- |
| 1 | 的 [!DNL Experience Cloud Visitor ID] 从 [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | at.js 库会同步加载，并隐藏文档正文。<br>也可以选择预先隐藏页面上实施的代码片段，以异步方式加载at.js库。 |
| 3 | at.js库会隐藏主体以防止闪烁。 |
| 4 | 将发出请求以检索体验。 |
| 5 | at.js库会确认JSON规则对象已缓存，并执行内存中用于检索体验的决策。 |
| 6 | 已测试的元素处于隐藏状态。 |
| 7 | at.js库会显示正文，以便可以加载页面的其余部分以供访客查看。 |
| 8 | at.js库会处理DOM以从缓存的JSON规则对象中呈现体验。 |
| 9 | 体验为访客呈现。 |
| 10 | 加载整个网页。 |
| 11 | [!DNL Analytics] 数据会发送到数据收集服务器。目标数据与 [!DNL Analytics] 数据，并会在 [!DNL Analytics] 报表存储。 之后，便可以在 [!DNL Analytics] 和 [!DNL Analytics] 中通过 [!DNL Target] for Target[!UICONTROL  (A4T) 报表查看 ]Analytics 数据。 |

## 如何启用设备上决策？

设备内决策适用于所有人 [!DNL Target] 使用At.js 2.5.0及更高版本的客户。

要启用设备上决策，请执行以下操作：

>[!NOTE]
>
>您必须拥有 [!UICONTROL 管理员] 或 [!UICONTROL 审批者] [用户角色](/help/main/administrating-target/c-user-management/user-management.md) 启用或禁用设备决策切换开关。

1. 单击 **[!UICONTROL 管理]** > **[!UICONTROL 实施]** > **[!UICONTROL 帐户详细信息]**.
1. 在 **[!UICONTROL 帐户详细信息]**，滑动 **[!UICONTROL 设备内决策]** 切换到“开”位置。

   ![设备内决策切换开关](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-toggle.png)

   “[!UICONTROL 在项目中包含所有现有的设备上决策合格活动]“ ”选项会在您启用设备决策时显示。
1. （视情况而定）如果您希望符合设备决策条件的所有实时Target活动都自动包含在项目中，请将切换开关滑动到“开”位置。

   关闭此切换开关意味着您必须重新创建并激活任何设备上决策活动，以便将这些活动包含在生成的规则对象中。 换言之，在打开 [!UICONTROL 设备内决策] 切换未包含在规则对象中。

启用 [!UICONTROL 设备内决策] 切换， [!DNL Target] 开始生成和传播 [规则工件](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/rule-artifact/){target=_blank}。

>[!IMPORTANT]
>
>在初始化Adobe Target SDK以使用设备决策之前，请确保启用切换开关。 规则工件首先需要生成并传播到Akamai CDN，才能在设备上做出决策。 传播过程可能需要5到10分钟，才能生成第一个规则对象并将其传播到Akamai CDN。

## 如何配置at.js 2.5.0及更高版本以使用设备决策？

1. 单击 **[!UICONTROL 管理]** > **[!UICONTROL 实施]** > **[!UICONTROL 帐户详细信息]**.
1. 在 **[!UICONTROL 实施方法]** > **[!UICONTROL 主要实现方法]**，单击 **[!UICONTROL 编辑]** at.js版本旁边（必须是at.js 2.5.0或更高版本）。

   ![编辑主要实施方法设置](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/main-implementation-method.png)

   >[!IMPORTANT]
   >
   >在更改这些默认设置之前，请咨询客户关怀团队，以便您不会影响当前的实施。

1. 选择所需的决策方法：

   * [!UICONTROL 仅服务器端]
   * [!UICONTROL 仅限设备内]
   * [!UICONTROL 混合]

   ![编辑at.js设置面板](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/global-settings.png)

### 全局设置

您可以配置默认 [!UICONTROL 决策方法] 全部 [!DNL Target] 决策。 各种决策方法包括 [!UICONTROL 仅服务器端], [!UICONTROL 仅限设备内]和 [!UICONTROL 混合]. 在Target UI中选择的决策方法在 `window.targetGlobalSettings` 下 `decisioningMethod` 字段。 进一步了解 `decisioningMethod` in [targetGlobalSettings()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/).

```javascript
<head> 
    <script type="text/javascript">

        window.targetGlobalSettings = { 
            clientCode: "yourClientCodeHere", 
            imsOrgId: "imsOrgId@AdobeOrg", 
            decisioningMethod: "on-device"

        }; 
    </script>

    <script type="text/javascript" src="at.js"></script> 
</head>
```

### 自定义设置

如果您将 `decisioningMethod` in `window.targetGlobalSettings`，但是希望覆盖 `decisioningMethod` 对于根据您的用例做出的每个Adobe Target决策，您可以通过指定 `decisioningMethod` 在At.js2.5.0+的 [getOffers()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffers-atjs-2/){target=_blank}调用。

```javascript
adobe.target.getOffers({ 

  decisioningMethod:"on-device", 
  request: { 
    execute: { 
      mboxes: [ 
        { 
          index: 0, 
          name: "homepage" 
        } 
      ] 
    } 
 } 
});
```

>[!NOTE]
>
>要在getOffers()调用中将“在设备上”或“混合”用作决策方法，请确保全局设置已 `decisioningMethod` “设备内”或“混合”。 at.js库2.5.0及更高版本必须知道是否在页面上加载后立即下载和缓存JSON规则对象。 如果用于全局设置的决策方法设置为“服务器端”，并且“设备上”或“混合”决策方法被传递到getOffers()调用中，则at.js 2.5.0及更高版本将不会缓存JSON规则对象以执行设备上的决策。

### 伪像缓存TTL

[!DNL Target] 将符合设备上决策资格的活动表示为包含元数据、规则和条件的项目。 此项目已缓存在Akamai CDN中。 在用户首次访问期间，用户的浏览器会下载并缓存代表您的设备决策活动的项目。

随后访问您的网站时，浏览器会自动检查是否必须下载较新版本的项目。 此检查会增加延迟。 项目缓存TTL定义自上次成功下载以来您不希望浏览器检查更新项目的分钟数。 时间范围越长，性能越好。 时间范围越短，数据刷新就越好，但需要增加延迟。

## 我如何知道设备上决策活动符合条件？

在您创建符合设备决策条件的活动后，会显示一个标签，其中显示 [!UICONTROL 设备内决策符合条件]，在活动中可见 [!UICONTROL 概述] 页面。

![活动“概述”页面上的“设备上决策”符合条件标签。](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-eligible-label.png)

此标签并不表示活动将始终通过设备决策来交付。 只有当at.js 2.5.0及更高版本配置为使用设备上决策时，才会在设备上执行此活动。 如果at.js 2.5.0及更高版本未配置为使用设备上的，则此活动仍将通过使用at.js发起的服务器调用来交付。

您可以筛选符合 [!UICONTROL 活动] 页面 [!UICONTROL 设备内决策符合条件] 过滤器。

![“活动”页面上的设备内决策符合条件的过滤器。](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-filter.png)

>[!NOTE]
>
>创建并激活符合设备决策条件的活动后，该活动可能需要五到十分钟才能包含在生成并传播到Akamai CDN呈现点的规则对象中。

## 确保通过At.js 2.5.0+?交付设备上决策活动的步骤摘要

1. 访问Adobe Target UI并导航到 **[!UICONTROL 管理]** > **[!UICONTROL 实施]** > **[!DNL Account Details]** 启用 **[!UICONTROL 设备内决策]** 切换。
1. 启用 **&quot;[!UICONTROL 在项目中包含所有现有的设备上决策合格活动]&quot;** 切换。

   第一个JSON规则对象生成最多可能需要10分钟。

1. 创建和激活 [设备决策支持的活动类型](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/supported-features/)，并确认其符合设备上决策的条件。
1. 设置 **[!UICONTROL 决策方法]** 选择 **[!UICONTROL &quot;混合&quot;]** 或 **[!UICONTROL &quot;仅限设备&quot;]** 通过at.js设置UI。
1. 将At.js 2.5.0及更高版本下载并部署到您的页面。
