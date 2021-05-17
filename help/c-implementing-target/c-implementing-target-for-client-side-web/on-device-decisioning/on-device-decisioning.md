---
keywords: 实现；javascript库；js;atjs；设备上决策；设备上决策；at.js；设备上
description: 了解如何使用at.js库执行设备上决策
title: 设备上决策如何与at.js JavaScript库一起使用？
feature: at.js
role: Developer
exl-id: 5ad6032b-9865-4c80-8800-705673657286
source-git-commit: 7f1db24e902c4b06c2035a94924abfe2d254bf25
workflow-type: tm+mt
source-wordcount: '3491'
ht-degree: 7%

---

# at.js的设备上决策

从版本2.5.0开始，at.js优惠设备上决策。 设备上决策允许您在浏览器上缓存[A/B测试](/help/c-activities/t-test-ab/test-ab.md)和[体验定位](/help/c-activities/t-experience-target/experience-target.md)(XT)活动，以执行内存中决策，而无需对[!DNL Adobe Target]边缘网络发出阻塞网络请求。

[!DNL Target] 还优惠了通过实时服务器调用从实验和机器学习驱动（ML驱动）个性化活动提供最相关、最新体验的灵活性。换句话说，当性能最为重要时，您可以选择使用设备决策。 但是，当需要最相关、最新和ML驱动的体验时，可以进行服务器调用。

## 设备上决策有哪些好处？

设备上决策的优势包括：

* **提供超快的决策和体验。** 在内存中和浏览器上执行分段和决策以避免阻止网络请求。
* **增强应用程序性能。** 在不影响最终用户体验的前提下，运行实验并为客户和用户提供个性化。
* **提高Google网站质量分数。** 随着决策在内存中发生，提高您在线业务的Google网站质量分数，让消费者更容易发现它。
* **从实时分析中学习。** 通过Analytics for 活动(A4T)目标实 [时获得报告](/help/c-integrating-target-with-mac/a4t/a4t.md) 表现的洞察。A4T使您能够在关键时刻将战略枢纽化。

## 受支持的功能

Adobe Target JS SDK可让客户灵活地在数据的性能与新鲜度之间做出选择，以便作出决策。 换句话说，如果通过机器学习交付最相关、最引人入胜的个性化内容对您来说最为重要，则应进行实时服务器调用。 但是，当性能更为关键时，应该做出设备内和内存内决策。 要确保在设备上决策正常工作，请参阅支持的功能列表:

* 活动类型
* 受众定位
* 分配方法

有关详细信息，请参阅[设备决策支持的功能](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/supported-features.md)。

## 设备上的决策如何工作？

在启用设备决策的情况下部署和初始化at.js时，将从最靠近访客的Akamai CDN下载一个[规则伪像](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/rule-artifact.md)，其中包括您对A/B和XT活动、受众和资源的设备上决策，并在访客的浏览器上本地缓存。 当从at.js发出请求以检索体验时，将根据缓存规则对象中编码的元数据在内存中决定要返回的体验。

## 决策方法

对于设备上决策，[!DNL Target]引入了一个名为[!UICONTROL 决策方法]的新设置。 [!UICONTROL 决策方法]设置指示at.js如何提供您的体验。 [!UICONTROL 决策] 方法有三个值：

* [!UICONTROL 仅服务器端]
* [!UICONTROL 仅限设备]
* [!UICONTROL 混合]

### 仅服务器端

[!UICONTROL 仅在服] 务器端是默认的决策方法，当在您的Web属性上实施和部署at.js 2.5.0+时即可使用。

使用[!UICONTROL 仅服务器端]作为默认配置意味着所有决策都在[!DNL Target]边缘网络上做出，这涉及阻塞服务器调用。 此方法可以引入增量延迟，但也提供了显着的优势，例如使您能够应用目标的机器学习功能，这些功能包括[Recommendations](/help/c-recommendations/recommendations.md)、[Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md)(AP)和[自动目标](/help/c-activities/auto-target/auto-target-to-optimize.md)活动。

此外，使用目标的用户用户档案增强您的个性化体验，这种体验会跨会话和渠道保留下来，为您的业务提供强大的成果。

最后，[!UICONTROL 仅服务器端]允许您使用Adobe Experience Cloud并微调可通过Audience Manager和Adobe Analytics区段针对的受众。

下图说明了您的访客、浏览器、at.js 2.5.0+和Adobe Target Edge网络之间的交互。 此流程图捕获新访客和返回访客。

![仅服务器端流图](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/server-side-only.png)

以下列表与图中的数字相对应：

| 步骤 | 描述 |
| --- | --- |
| 1 | 从[Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en)检索[!DNL Experience Cloud Visitor ID]。 |
| 2 | at.js 库会同步加载，并隐藏文档正文。<br>   也可以异步加载at.js库，并在页面上实现一个可选的预隐藏片段。 |
| 3 | at.js库隐藏正文以防止闪烁。 |
| 4 | 会发出一个页面加载请求，其中包含所有已配置的参数，如(ECID、客户ID、自定义参数、用户用户档案等)。 |
| 5 | 配置文件脚本在执行后进入配置文件存储区。<br>用户档案 Store从受众库请求限定的受众(例如，从、 [!DNL Adobe Analytics]等共 [!DNL Adobe Audience Manager]享的受众)。<br>客户属性会以批量过程发送到配置文件存储区。 |
| 6 | 用户档案商店用于受众资格和分段以过滤活动。 |
| 7 | 从实时[!DNL Target]活动确定体验后，将选择生成的内容。 |
| 8 | at.js库会隐藏页面上与必须渲染的体验关联的相应元素。 |
| 9 | at.js库显示正文，以便能够加载页面的其余部分，以便访客到视图。 |
| 10 | at.js库操作DOM以从目标 Edge Network中呈现体验。 |
| 11 | 体验为访客呈现。 |
| 12 | 加载整个网页。 |
| 13 | [!DNL Analytics] 数据会发送到数据收集服务器。 |
| 14 | 目标数据通过SDID与[!DNL Analytics]数据匹配，并被处理到[!DNL Analytics]报告存储。 之后，便可以在 [!DNL Analytics] 和 [!DNL Analytics] 中通过 [!DNL Target] for Target[!UICONTROL  (A4T) 报表查看 ]Analytics 数据。 |

### 仅限设备

[!UICONTROL 仅限设] 备的决策方法是必须在at.js 2.5.0+中设置的决策方法，当设备决策只能用于整个网页。

设备上决策可以以超快的速度提供您的体验和个性化活动，因为决策来自缓存的规则伪像，其中包含符合设备上决策资格的所有活动。

要进一步了解哪些活动有资格进行设备上决策，请参阅[设备上决策中支持的功能](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/supported-features.md)。

仅当需要从[!DNL Target]进行决策的所有页面中的性能都非常关键时，才应使用此决策方法。 此外，请记住，当选择此决策方法时，不符合设备上决策条件的[!DNL Target]活动将不会交付或执行。 at.js库2.5.0+配置为仅查找缓存的规则对象以作出决策。

下图说明了访客、浏览器、at.js 2.5.0+和Akamai CDN之间的交互。 Akamai CDN缓存访客首次访问的规则对象。 对于新访客的第一次页面访问，必须从Akamai CDN下载JSON规则伪像，以便在访客的浏览器上本地缓存。 下载JSON规则伪像后，将立即做出决策，而不会进行阻止网络调用。 以下流程图捕获了新访客。

![仅限设备的流图](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-only.png)

以下列表与图中的数字相对应：

>[!NOTE]
>
>[!DNL Adobe Target] 管理服务器可确定您所有有资格进行设备上决策的活动，生成JSON规则对象，并将其传播到Akamai CDN。系统会持续监视活动是否有更新，以输出要传播到Akamai CDN的新JSON规则对象。

| 步骤 | 描述 |
| --- | --- |
| 1 | 从[Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html)检索[!DNL Experience Cloud Visitor ID]。 |
| 2 | at.js 库会同步加载，并隐藏文档正文。<br>也可以异步加载at.js库，并在页面上实现一个可选的预隐藏片段。 |
| 1 | at.js库隐藏正文以防止闪烁。 |
| 4 | at.js库请求从最近的Akamai CDN检索JSON规则对象到访客。 |
| 5 | Akamai CDN使用JSON规则对象做出响应。 |
| 6 | JSON规则对象将在访客的浏览器上本地缓存。 |
| 7 | at.js库解释JSON规则对象，并执行检索体验和隐藏测试元素的决定。 |
| 8 | at.js库显示正文，以便能够加载页面的其余部分，以便访客到视图。 |
| 9 | at.js库处理DOM以从缓存的JSON规则对象中呈现体验。 |
| 10 | 体验为访客呈现。 |
| 11 | 加载整个网页。 |
| 12 | [!DNL Analytics] 数据会发送到数据收集服务器。目标数据通过SDID与[!DNL Analytics]数据匹配，并被处理到[!DNL Analytics]报告存储。 之后，便可以在 和 中通过 for Target (A4T) 报表查看 [!DNL Analytics][!DNL Analytics]Analytics 数据。[!DNL Target] |

下图说明了访客、浏览器at.js 2.5.0+与访客后续页面点击或返回访问缓存的JSON规则对象之间的交互。 由于JSON规则对象已缓存并可在浏览器上使用，因此无需进行阻止网络调用即可立即做出决策。 此流程图可捕获后续页面导航或返回访客。

![用于后续页面导航和重复访问的仅限设备的流图](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-only-subsequent.png)

以下列表与图中的数字相对应：

>[!NOTE]
>
>[!DNL Adobe Target] 管理服务器可确定您所有有资格进行设备上决策的活动，生成JSON规则对象，并将其传播到Akamai CDN。系统会持续监视活动是否有更新，以输出要传播到Akamai CDN的新JSON规则对象。

| 步骤 | 描述 |
| --- | --- |
| 1 | 从[Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html)检索[!DNL Experience Cloud Visitor ID]。 |
| 2 | at.js 库会同步加载，并隐藏文档正文。<br>也可以异步加载at.js库，并在页面上实现一个可选的预隐藏片段。 |
| 1 | at.js库隐藏正文以防止闪烁。 |
| 4 | at.js库解释JSON规则对象，并在内存中执行检索体验的决定。 |
| 5 | 已测试的元素处于隐藏状态。 |
| 6 | at.js库显示正文，以便能够加载页面的其余部分，以便访客到视图。 |
| 7 | at.js库处理DOM以从缓存的JSON规则对象中呈现体验。 |
| 8 | 体验为访客呈现。 |
| 9 | 加载整个网页。 |
| 10 | [!DNL Analytics] 数据会发送到数据收集服务器。目标数据通过SDID与[!DNL Analytics]数据匹配，并被处理到[!DNL Analytics]报告存储。 之后，便可以在 [!DNL Analytics] 和 [!DNL Analytics] 中通过 [!DNL Target] for Target[!UICONTROL  (A4T) 报表查看 ]Analytics 数据。 |

### 混合

[!UICONTROL 在必] 须同时执行设备上决策和需要对Adobe Target Edge网络进行网络调用的活动时，混合在at.js 2.5.0+中必须设置的决策方法。

当您同时管理设备上决策活动和服务器端活动时，在考虑如何在页面上部署和配置[!DNL Target]时，可能会有些复杂和乏味。 [!DNL Target]将混合作为决策方法，它知道何时必须对需要服务器端执行的活动进行服务器调用到Adobe Target Edge网络，以及何时仅执行设备上决策。

JSON规则对象包含元数据，用于通知at.jsmbox是运行服务器端活动还是设备上决策活动。 此决策方法可确保您打算快速交付的活动通过设备上决策完成，对于需要更强大的ML驱动个性化的活动，这些活动通过Adobe Target Edge网络完成。

下图说明了访客、浏览器、at.js 2.5.0+、Akamai CDN和Adobe Target Edge Network之间的交互，前者是首次访问您页面的新访客。 从此图中可以看出，在通过Adobe Target Edge网络做出决策时，JSON规则对象将异步下载。

此方法确保伪像的大小(可以包含许多活动)不会对决策的延迟产生负面影响。 同步下载JSON规则伪像并随后做出决策也可能会对延迟产生不利影响，并可能不一致。 因此，混合决策方法是一种最佳实践建议，它总是对新访客的决策进行服务器端调用，并且当JSON规则伪像并行缓存时。 对于任何后续页面访问和回访，通过JSON规则伪造从缓存和内存中做出决策。

![用于首次访客的混合流图](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/hybrid-first-time-visitor.png)

以下列表与图中的数字相对应：

>[!NOTE]
>
>[!DNL Adobe Target] 管理服务器可确定您所有有资格进行设备上决策的活动，生成JSON规则对象，并将其传播到Akamai CDN。系统会持续监视活动是否有更新，以输出要传播到Akamai CDN的新JSON规则对象。

| 步骤 | 描述 |
| --- | --- |
| 1 | 从[Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html)检索[!DNL Experience Cloud Visitor ID]。 |
| 2 | at.js 库会同步加载，并隐藏文档正文。<br>也可以异步加载at.js库，并在页面上实现一个可选的预隐藏片段。 |
| 1 | at.js库隐藏正文以防止闪烁。 |
| 4 | 会向Adobe Target Edge Network发出页面加载请求，包括所有已配置的参数，如(ECID、客户ID、自定义参数、用户用户档案等)。 |
| 5 | 同时，at.js请求从最近的Akamai CDN检索JSON规则对象到访客。 |
| 6 | (Adobe Target Edge Network)用户档案脚本执行，然后输入到用户档案存储中。 用户档案存储从受众库请求限定的受众(例如，从[!DNL Adobe Analytics]、[!DNL Adobe Audience Manager]等共享的受众)。 |
| 7 | Akamai CDN使用JSON规则对象做出响应。 |
| 8 | 用户档案商店用于受众资格和分段以过滤活动。 |
| 9 | 从实时[!DNL Target]活动确定体验后，将选择生成的内容。 |
| 10 | at.js库会隐藏页面上与必须渲染的体验关联的相应元素。 |
| 11 | at.js库显示正文，以便能够加载页面的其余部分，以便访客到视图。 |
| 12 | at.js库操作DOM以从目标 Edge Network中呈现体验。 |
| 13 | 体验为访客呈现。 |
| 14 | 加载整个网页。 |
| 15 | [!DNL Analytics] 数据会发送到数据收集服务器。目标数据通过SDID与[!DNL Analytics]数据匹配，并被处理到[!DNL Analytics]报告存储。 之后，便可以在 [!DNL Analytics] 和 [!DNL Analytics] 中通过 [!DNL Target] for Target[!UICONTROL  (A4T) 报表查看 ]Analytics 数据。 |

下图说明了访客、浏览器、at.js 2.5.0+与缓存的JSON规则对象之间的交互，这些对象用于后续页面导航或返回访问。 在此图中，只关注为后续页面导航或返回访问做出设备上决策的用例。 请记住，根据特定页面的实时活动，可以进行服务器端调用以执行服务器端决策。

![用于后续页面导航和重复访问的混合流图](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/hybrid-subsequent.png)

以下列表与图中的数字相对应：

>[!NOTE]
>
>[!DNL Adobe Target] 管理服务器可确定您所有有资格进行设备上决策的活动，生成JSON规则对象，并将其传播到Akamai CDN。系统会持续监视活动是否有更新，以输出要传播到Akamai CDN的新JSON规则对象。

| 步骤 | 描述 |
| --- | --- |
| 1 | 从[Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html)检索[!DNL Experience Cloud Visitor ID]。 |
| 2 | at.js 库会同步加载，并隐藏文档正文。<br>也可以异步加载at.js库，并在页面上实现一个可选的预隐藏片段。 |
| 3 | at.js库隐藏正文以防止闪烁。 |
| 4 | 会请求以检索体验。 |
| 5 | at.js库确认已缓存JSON规则对象，并在内存中执行检索体验的决定。 |
| 6 | 已测试的元素处于隐藏状态。 |
| 7 | at.js库显示正文，以便能够加载页面的其余部分，以便访客到视图。 |
| 8 | at.js库处理DOM以从缓存的JSON规则对象中呈现体验。 |
| 9 | 体验为访客呈现。 |
| 10 | 加载整个网页。 |
| 11 | [!DNL Analytics] 数据会发送到数据收集服务器。目标数据通过SDID与[!DNL Analytics]数据匹配，并被处理到[!DNL Analytics]报告存储。 之后，便可以在 [!DNL Analytics] 和 [!DNL Analytics] 中通过 [!DNL Target] for Target[!UICONTROL  (A4T) 报表查看 ]Analytics 数据。 |

## 如何启用设备上决策？

设备上决策适用于所有使用At.js 2.5.0+的[!DNL Target]客户。

要启用设备决策：

>[!NOTE]
>
>您必须具有[!UICONTROL Admin]或[!UICONTROL Approver] [用户角色](/help/administrating-target/c-user-management/user-management.md)才能启用或禁用设备决策切换。

1. 单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 实施]** > **[!UICONTROL 帐户详细信息]**。
1. 在“**[!UICONTROL 帐户详细信息]**”下，将“**[!UICONTROL 设备上决策]**”滑动到“on”位置。

   ![设备上决策切换](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-toggle.png)

   如果启用设备上决策，则会显示“[!UICONTROL 包括对象]中所有现有设备上决策限定活动”选项。
1. （视情况而定）如果您希望符合设备决策条件的所有实时目标活动自动包含在对象中，请将切换滑至“开启”位置。

   关闭此切换意味着您必须重新创建并激活任何设备上决策活动，以便将其包含在生成的规则对象中。 换句话说，在打开[!UICONTROL 设备上决策]切换之前处于实时状态的任何活动不包括在规则伪像中。

启用[!UICONTROL 设备上决策]切换后，[!DNL Target]开始为您的客户端生成并传播[规则对象](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/rule-artifact.md)。

>[!IMPORTANT]
>
>请确保在初始化Adobe Target SDK之前启用切换，以使用设备决策。 规则伪像首先需要生成并传播到Akamai CDN，以便在设备上进行决策。 传播可能需要5到10分钟，第一个规则伪像才能生成并传播到Akamai CDN。

## 如何配置at.js 2.5.0+以使用设备决策？

1. 单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 实施]** > **[!UICONTROL 帐户详细信息]**。
1. 在&#x200B;**[!UICONTROL 实现方法]** > **[!UICONTROL 主要实现方法]**&#x200B;下，单击您的at.js版本（必须为at.js 2.5.0或更高版本）旁边的&#x200B;**[!UICONTROL 编辑]**。

   ![编辑主要实现方法设置](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/main-implementation-method.png)

   >[!IMPORTANT]
   >
   >在更改这些默认设置之前，请咨询Client Care，以便不影响当前实施。

1. 选择所需的决策方法：

   * [!UICONTROL 仅服务器端]
   * [!UICONTROL 仅限设备]
   * [!UICONTROL 混合]

   ![编辑at.js设置面板](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/global-settings.png)

### 全局设置

您可以为所有[!DNL Target]决策配置默认[!UICONTROL 决策方法]。 各种决策方法为[!UICONTROL 仅服务器端]、[!UICONTROL 仅设备上]和[!UICONTROL 混合]。 在目标UI中选择的决策方法是在`decisioningMethod`字段下的`window.targetGlobalSettings`中配置的。 了解有关[targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)中`decisioningMethod`的更多信息。

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

如果您在`window.targetGlobalSettings`中设置`decisioningMethod`，但希望根据您的用例覆盖每个Adobe Target决定的`decisioningMethod`，则可以通过在At.js2.5.0+的[getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md)调用中指定`decisioningMethod`来完成此过程。

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
>要在getOffers()调用中将“on-device”或“hybrid”用作决策方法，请确保全局设置将`decisioningMethod`作为“on-device”或“hybrid”。 at.js库2.5.0+必须知道在页面上加载后是否立即下载和缓存JSON规则对象。 如果全局设置的决策方法设置为“服务器端”，并且“设备上”或“混合”决策方法传递到getOffers()调用中，at.js 2.5.0+将不会缓存JSON规则伪像以执行您的设备决策。

### 伪像缓存TTL

[!DNL Target] 表示您的活动，它们有资格将设备上决策作为由元数据、规则和条件组成的项目。此项目将缓存在Akamai CDN上。 在用户首次访问期间，用户的浏览器会下载并缓存表示设备上决策活动的伪像。

随后访问您的网站时，浏览器会自动检查是否必须下载较新版本的项目。 此检查会增加延迟。 “项目缓存TTL”定义自上次成功下载以来您不希望浏览器检查更新项目的分钟数。 时间越长，性能越好。 时间帧越短，数据的新鲜度就越好，但代价是增加了延迟。

## 我如何知道活动有资格在设备上进行决策？

在创建符合设备上决策条件的活动后，活动的[!UICONTROL 概述]页面中将显示一个标签，其中显示有[!UICONTROL 符合条件的设备上决策]。

![活动“概述”页面上的“设备上决策”合格标签。](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-eligible-label.png)

此标签并不意味着活动始终通过设备上决策提供。 仅当将at.js 2.5.0+配置为使用设备上决策时，才会在设备上执行此活动。 如果at.js 2.5.0+未配置为使用设备上，则此活动仍将通过由at.js发出的服务器调用交付。

您可以通过[!UICONTROL 设备决策符合条件]过滤器过滤[!UICONTROL 活动]页上符合条件的所有设备上决策活动。

![“活动”页面上的“设备上决策”“合格”筛选器。](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-filter.png)

>[!NOTE]
>
>创建并激活符合设备上决策条件的活动后，可能需要5到10分钟时间，才能将其包含在生成并传播到Akamai CDN演示点的规则伪像中。

## 确保通过At.js 2.5.0+提供设备上决策活动的步骤摘要？

1. 访问Adobe Target UI并导航到&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 实施]** > **[!DNL Account Details]**&#x200B;以启用&#x200B;**[!UICONTROL 设备上决策]**&#x200B;切换。
1. 启用&#x200B;**&quot;[!UICONTROL 在项目]&quot;**&#x200B;切换中包括所有现有的设备上决策限定活动。

   第一次生成JSON规则对象最多可能需要10分钟。

1. 创建并激活设备决策](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/supported-features.md)支持的[活动类型，并验证设备决策符合条件。
1. 通过at.js设置UI将&#x200B;**[!UICONTROL 决策方法]**&#x200B;设置为&#x200B;**[!UICONTROL &quot;Hybrid&quot;]**&#x200B;或&#x200B;**[!UICONTROL &quot;仅限设备&quot;]**。
1. 下载At.js 2.5.0+并将其部署到您的页面。
