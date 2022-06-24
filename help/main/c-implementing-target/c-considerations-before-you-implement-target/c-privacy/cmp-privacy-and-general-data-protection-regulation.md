---
keywords: GDPR;EU;欧盟;隐私;FAQ;常见问题解答;加州消费者隐私法案;CCPA;隐私;数据保护;选择退出;选择退出;政府;法规
description: 了解 [!DNL Target] 和欧盟通用数据保护条例 (GDPR)、加州消费者隐私法案 (CCPA) 和其他隐私要求。
title: ' [!DNL Target] 如何处理隐私和数据保护法规？'
feature: Privacy & Security
role: Developer
exl-id: 5013a9d2-a463-4787-90ee-3248d9cb02b2
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '2235'
ht-degree: 97%

---

# 隐私和数据保护法规

有关欧盟通用数据保护条例 (GDPR)、加州消费者隐私法案 (CCPA) 和其他隐私要求的信息。了解这些法规对您的组织和 [!DNL Adobe Target] 有何影响。

## 隐私和通用数据保护条例 (GDPR) 概述 {#topic_DE567ECB6C944695AEE5073889F1AEA9}

2018 年 5 月 25 日，欧盟的 GDPR 已正式生效。有关此法规对您影响的更多信息，请参阅 [GDPR 和您的业务](https://business.adobe.com/privacy/general-data-protection-regulation.html)。

当 [!DNL Adobe] 向企业提供软件和服务时，作为提供这些服务的一部分，[!DNL Adobe] 将充当其处理并存储的任何个人数据的“数据处理方”。作为“数据处理方”，[!DNL Adobe] 将根据贵公司授予的权限及指示（例如，遵照您与 [!DNL Adobe] 签署的协议中的规定）来处理个人数据。

作为“数据控制方”，您可以决定 [!DNL Adobe] 代表您处理和存储的个人数据。如果您使用 [!DNL Adobe Experience Cloud] 解决方案，[!DNL Adobe] 可能会根据您使用的解决方案和您选择发送到 [!DNL Adobe Experience Cloud] 帐户的信息，来为您托管个人数据。有关详细的示例列表，请参阅 [Adobe Experience Cloud 隐私](https://www.adobe.com/privacy/experience-cloud.html#collect)。

[!DNL Adobe Experience Cloud] 为数据控制方提供支持 GDPR 的 API，允许他们完成以下任务：

* 访问 [!DNL Target] 中存储的数据主体信息
* 删除 [!DNL Target] 中存储的数据主体信息

有关更多信息，请参阅：

* [Adobe Privacy Service 概述](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html){target=-blank}
* [Privacy Service API 指南](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html){target=_blank}
* [Privacy Service UI 概述](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html){target=_blank}

## 《加州消费者隐私法案》(CCPA) 概述

《加州消费者隐私法案》(CCPA) 为加利福尼亚州消费者提供了关于个人信息的新权利，并明确了在加利福尼亚州开展业务的某些实体的数据保护职责。CCPA 在 2020 年 1 月 1 日起生效。

在较高层面上，这项法案为加州人提供了几项主要的权利，具体包括：

* 请求信息（数据访问）
* 选择不出售个人信息（一项广泛定义的权利，选择不与第三方共享信息）
* 删除个人信息
* 获知个人信息正在被披露或出售

如果您去年忙于准备好应对欧洲隐私法律 (GDPR)，那么您可能已经熟悉了这样的一些权利，并且可以重新利用已经完成的许多工作。

>[!NOTE]
>
>适用于 CCPA 的数据访问和删除遵循与 GDPR 相同的过程。

## Adobe [!DNL Target] 和 [!DNL Adobe Experience Platform] 选择启用 {#section_6F7B53F5E40C4425934627B653E831B0}

[!DNL Target] 通过 [!DNL Adobe Experience Platform] 中的标记提供选择启用功能支持，以帮助支持您的同意管理策略。选择加入功能让客户可自行决定如何以及何时触发 [!DNL Target] 标记。还有一个选项，即通过 [!DNL Adobe Experience Platform] 预批准 [!DNL Target] 标记。要启用在 [!DNL Target] at.js 中使用选择加入的功能，您应该使用 `targetGlobalSettings` 并添加 `optinEnabled=true` 设置。在 [!DNL Adobe ExperiencePlatform] 中，从扩展安装视图的 [!UICONTROL GDPR 选择启用]下拉列表中选择“启用”。请参阅 [实施 [!DNL Target] 使用 [!DNL Adobe Experience Platform]](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/){target=_blank}以了解更多详细信息。

以下代码段显示了如何启用 `optinEnabled=true` 设置：

```
window.targetGlobalSettings = {
  optinEnabled: true
};
```

>[!NOTE]
>
>at.js 版本 1.7.0 和 at.js 2.1.0 或更高版本都支持选择加入功能。at.js 版本 2.0.0 和 2.0.1 不支持选择加入功能。
>
>推荐使用 [!DNL Adobe Experience Platform] 管理选择加入功能。[!DNL Adobe Experience Platform] 中存在更细粒度的控制，用于在触发 [!DNL Target] 之前隐藏页面上的选定元素，这对于在同意策略中的使用非常有帮助。

使用选择加入功能时需要考虑三种情景：

1. **已通过 [!DNL Adobe Experience Platform] 预批准 [!DNL Target] 标记（或者数据主体以前已经批准 [!DNL Target]）：**[!DNL Target] 标记不适用于征求同意，且会发挥预期的作用。
1. **[!DNL Target] 标记没有获得预批准且 `bodyHidingEnabled` 设置为 FALSE：**&#x200B;只有在收到客户的同意之后，才会触发 [!DNL Target] 标记。在收到客户同意之前，仅默认内容可用。在收到客户同意之后，将调用 [!DNL Target] 并向数据主体（访客）提供个性化内容。由于在同意之前只有默认内容可用，因此务必要使用正确的策略，例如过场动画页面涵盖了页面的任意部分或者可能个性化的内容。此过程确保对于所有数据主体（访客）保持一致的体验。
1. **[!DNL Target] 标记没有获得预批准且 `bodyHidingEnabled` 设置为 TRUE：**&#x200B;只有在收到客户的同意之后，才会触发 [!DNL Target] 标记。在收到客户同意之前，仅默认内容可用。但是，因为 `bodyHidingEnabled` 设置为 true，`bodyHiddenStyle` 会指示在触发 [!DNL Target] 标记之前页面上需要隐藏的内容（或者数据主体拒绝使用选择加入功能，这种情况下会显示默认内容）。默认情况下，`bodyHiddenStyle` 设置为 `body { opacity:0;}`，这会隐藏 HTML 正文标记。Adobe 的推荐页面配置如下，通过将页面内容放在一个容器中并将同意管理器对话框放在单独的容器中，从而隐藏页面全部正文而不隐藏同意管理器对话框。这种设置会配置 [!DNL Target]，以便仅隐藏页面内容容器。请参阅 [Privacy Service 概述](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=zh-Hans)。

   适用于情景 3 的推荐页面设置是：

   ```
   <html> 
   <head> 
   //visitor, at.js 
   </head> 
   
   <body> 
   <div id = "consentManagerDialog"> 
   
   //consent manager html dialog goes here 
   </div> 
   
   <div id="pageContent"> 
   // page content goes here 
   </div> 
   
   </body> 
   </html> 
   ```

   假设 `bodyHiddenStyle` 为：

   ```
   #pageContent { opacity:0;}
   ```

## 隐私和数据保护法规常见问题解答 {#concept_41F88DE95D2943178BEC382736B5C038}

关于欧盟通用数据保护条例 (GDPR)、加州消费者隐私法案 (CCPA) 和特定于 [!DNL Target] 的其他隐私要求信息的常见问题解答。

### [!DNL Adobe] 针对这些法规有什么政策？ {#section_A6849628D6524C80A6E16946DC5D25A9}

[!DNL Adobe] 已经履行或者正在履行其作为数据处理商的义务。Adobe 在设计上为经认证的安全性和隐私控制奠定了牢固的基础，并在 2018 年 5 月的截止日期之前落实了产品增强功能。企业和客户负责实施这些增强功能，并更新任意必要的策略和过程。

### 作为数据控制方，我的公司是否必须向使用的各个 [!DNL Adobe Experience Cloud] 解决方案提交 GDPR 或 CCPA 请求？ {#section_1DCFA9387D0C4506B14DCE04C49AC22A}

否，[!DNL Adobe] 提供了集中的方法来帮助数据控制方履行其 GDPR 和 CCPA 要求。数据控制方无需直接转向各个解决方案。

所有 [!DNL Experience Cloud] 解决方案的所有 GDPR 和 CCPA 请求，包括 [!DNL Target]，均通过集中 [!DNL Adobe] API 进行，后者目前称为 GDPR API。然后，API 跨数据控制方的 [!DNL Experience Cloud] 解决方案套件完成请求。

### 作为对数据主体/用户请求的回应，[!DNL Adobe] 允许客户删除哪些信息？ {#section_4B51D00924EC4166B2442218B69214F0}

在 [!DNL Target] 中，与单独访客有关的信息包含在 [!DNL Target] 访客配置文件中。[!DNL Target] 允许客户删除与其访客配置文件中某个 ID 关联的所有数据。有关 [!DNL Target] 存储的配置文件数据的示例，请参阅[访客配置文件](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)。

未标识特定个人的聚合或匿名数据（例如，报表数据）或与特定个人无关的数据（例如，内容数据），不在用户删除请求的范围之内。

[!DNL Target]默认情况下，无需执行任何操作，系统即会删除 90 天处于不活跃状态的 访客配置文件。

### 系统支持哪些 ID 来帮助客户完成 [!DNL Target] 的 GDPR 或 CCPA 访问和删除请求？{#section_F7D0EE4E6A28490FB20056A0D26118BC}

[!DNL Target] 支持以下 ID 类型来查找客户配置文件：

| 用户 ID | 命名空间 ID 类型 | 命名空间 ID | 定义 |
|--- |--- |--- |--- |
| Experience Cloud ID (ECID) | Standard | 4 | [!UICONTROL Adobe Experience Cloud ID]，以前称为访客 ID 或 Experience Cloud ID。您可以使用 JavaScript API 来查找此 ID（请参阅下面的详细信息）。 |
| TnT ID / Cookie ID(TNTID) | 标准 | 9 | 在访客的浏览器中设置为 Cookie 的 [!DNL Target] 标识符。您可以使用 JavaScript API 来查找此 ID（请参阅下面的详细信息）。 |
| 第三方 ID / CRM ID (THIRDPARTYID) | [!DNL Target] 特定 | 不适用 | 在为您的客户向 [!DNL Target] 提供 CRM 或其他唯一标识符信息时。 |

>[!NOTE]
>
>尽管 [!DNL Target] 支持第一方和第三方跨域 Cookie，但是仅推荐使用第一方 [!DNL Target] Cookie 以满足 GDPR 和 CCPA 要求。

### [!DNL Target] 如何处理同意管理？ {#section_C86BF5EE4FAA47039659850E7594A6BA}

对于您必须获取同意的情况，GDPR 和 CCPA 没有进行更改，而是更改了您获取同意的方式。每个客户的同意策略取决于其数据收集和使用实践及其隐私政策。同意管理不受 GDPR 和 CCPA 的支持，也不应通过 [!DNL Target] 为 GDPR 和 CCPA 获取同意管理。

[!DNL Adobe] 目前不提供同意管理解决方案，不过，市面上有各种各样的开发工具，可用来解决一些新的需求。有关常规隐私工具的更多信息，包括同意管理器，请参阅&#x200B;*隐私权专家国际协会 (iaap)* 网站上的 [2017 隐私技术供应商报告](https://iapp.org/media/pdf/resource_center/Tech-Vendor-Directory-1.4.1-electronic.pdf)。

[!DNL Target] 不通过 [!DNL Adobe Experience Platform] 支持选择启用功能以支持您的同意管理策略。选择加入功能让客户可自行决定如何以及何时触发 [!DNL Target] 标记。还有一个选项，即通过 [!DNL Adobe Experience Platform] 预批准 [!DNL Target] 标记。推荐使用 [!DNL Adobe Experience Platform] 管理选择加入功能。[!DNL Adobe Experience Platform] 中存在更细粒度的控制，用于在触发 [!DNL Target] 之前隐藏页面上的选定元素，这对于在同意策略中的使用会非常有帮助。

有关 GDPR、CCPA 和 [!DNL Adobe Experience Platform] 的更多信息，请参阅 [Adobe 隐私 JavaScript 库和 GDPR](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en)。此外，请参阅上文的 *Adobe Target 和 Adobe Experience Platform 选择启用*&#x200B;部分。

### `AdobePrivacy.js` 是否向 GDPR API 提交信息？ {#section_1EB8A2BAAD31474C97C1D455F41DA739}

[!DNL AdobePrivacy.js]“不”**&#x200B;向 API 提交此信息。客户必须自行处理。该库仅提供存储在特定访客浏览器中的 ID。

### `removeIdentities` 删除什么？ {#section_D3A1591EA1B84C499CE1563DEAF32448}

[!DNL `removeIdentities`]**“只”删除浏览器中的那些标识，而且仅取决于 [!DNL Adobe] 解决方案是否已经执行了这项操作。

例如，[!DNL Target] 将删除存储其 ID 的 Cookie，但 [!DNL Adobe Audience Manager] (AAM) 不删除存储在第三方 Cookie 中的 demdex ID。

### 在 [!DNL Target] GDPR 或 CCPA 请求中必须包括什么信息？ {#section_D29A4744AE6344E68AD7710B185FD6D0}

除了核心隐私服务的要求之外，[!DNL Target] 的有效 GDPR 或 CCPA 消息还包含：

```
{ 
    "jobId":"12345AD43E", 
    ... 
    "products":["Target",...], 
    "companyContexts":[ 
        { 
            "namespace":"imsOrgID", 
            "value":"123456789@AdobeOrg" 
        }, 
        ... 
    ], 
    "userContexts":[ 
        { 
            "namespace":"ECID", 
            "namespaceId":4, 
            "type":"standard", 
            "value":"53792210477379708453829363835595041181" 
        } 
        And/OR: 
        { 
            "namespace":"TNTID", 
            "namespaceId":9, 
            "type":"standard", 
            "value":"1234567890" 
        } 
        And/OR: 
        { 
            "namespace":"THIRDPARTYID", 
            "type":"target", 
            "value":"thirdPartyIdName" 
        }, 
        ... 
    ] 
}
```

### 通过 GDPR API，我可以期待 [!DNL Target] 给出什么响应？ {#section_F67263D2A72B4641A47CE36729CCAE8F}

| 请求状态 | [!DNL Target] 响应消息 | 情景 |
|--- |--- |--- |
| 正在处理 | 正在处理 | [!DNL Target] 收到了 GDPR 或 CCPA 请求并正在进行处理。 |
| 完成 | 不适用 - 公司上下文不适用 | GDPR 或 CCPA 请求中的 IMS ID 不映射到任何 [!DNL Target] 客户端。<br>一些公司有多个 IMS ID。在配置了 [!DNL Target] 的地方提交 IMS ID。 |
| 完成 | 不适用 - 未找到用户上下文 | 在 GDPR 或 CCPA 请求中为特定访客或数据主体提供的 ID，在 [!DNL Target] 配置文件存储中不存在。<br>如果您尝试提交 [!DNL Target] 不支持的命名空间 ID，也会返回此结果（请参阅上文中支持的 ID）。 |
| 错误 | 错误消息（详细信息取决于错误类型） | 获取或删除请求的数据主体配置文件时出错。<br>上传到 Azure 以请求访问时出错。 |

### [!DNL Target] 针对访问请求将什么响应发送到 GDPR API？ {#section_D96D8FBEAF9C4BDAA638215FAFE00763}

在响应访问数据的请求时，将提供一份有关所讨论访客的 [!DNL Target] 配置文件摘要。此返回结果发送到 [!DNL Experience Cloud] GDPR API，这随之会向数据控制方发送一个响应。

[!DNL Target] 访问 API 响应示例如下所示：

```
{ 
    "jobId":"12345AD43E", 
    ... 
    "products":["Target",...], 
    "companyContexts":[ 
        { 
            "namespace":"imsOrgID", 
            "value":"123456789@AdobeOrg" 
        }, 
        ... 
    ], 
    "userContexts":[ 
        { 
            ~"namespace":"ECID", 
            "namespaceId":4, 
            "type":"standard", 
            "value":"53792210477379708453829363835595041181" 
        } 
        And/OR: 
        { 
            ~"namespace":"tntId", 
            "namespaceId":9, 
            "type":"standard", 
            "value":"1234567890" 
        } 
        And/OR: 
        { 
            "namespace":"thirdPartyId", 
            "type":"target", 
            "value":"thirdPartyIdName" 
        }, 
        ... 
    ] 
} 
```

| 字段 | 描述 |
|--- |--- |
| jobId | 指示来自核心 GDPR API 的 GDPR 或 CCPA 作业 ID。 |
| imsOrgID | 为贵公司提供的唯一标识符。 |
| namespace | 也称为数据源。请参阅“对于 [!DNL Target]，支持哪些 ID 以帮助客户完成 GDPR 或 CCPA 访问和删除请求？”。 |
| type | 您请求访问 GDPR 或 CCPA 数据的 ID 类型。[!DNL Target] 接受多种 ID 类型，其中一些是标准类型，另一些特定于 [!DNL Target]。请参阅“对于 [!DNL Target]，支持哪些 ID 以帮助客户完成 GDPR 或 CCPA 访问和删除请求？”。 |
| value | 命名空间/数据源 ID。请参阅“对于 [!DNL Target]，支持哪些 ID 以帮助客户完成 GDPR 或 CCPA 访问和删除请求？”以获取接受的值。 |
| 集成代码 | 集成代码是您数据源的友好名称，可以让您更轻松地跟踪数据源（与使用数据源 ID 相比）。 |

当提供多个值来识别配置文件时，每个有效的标识符将有一个配置文件。一个或多个配置文件通过 GDPR Central API 发送到了集中 GDPR Azure Blob，采用 [!DNL Target] 配置文件 JSON 响应格式。

[!DNL Target] 配置文件 JSON 示例可能如下所示：

```
{"profileAttributes": 
 
"Sample_Parameter":{"value":"Gold Loyalty Status","modifiedAt":"2018-04-11T21:44:14.000-04:00"}, 
 
"user.ReturnTimeOfDay":{"value":"44.0","modifiedAt":"2018-04-11T21:44:14.000-04:00"}, 
 
"firstSessionStart":{"value":"1523497450602","modifiedAt":"2018-04-11T21:44:10.000-04:00"}, 
 
"user.sessionCountScript":{"value":"1","modifiedAt":"2018-04-11T21:44:14.000-04:00"} 
   } 
} 
```

下表包含说明性配置文件 JSON 字段的描述：

| 字段 | 描述 |
|--- |--- |
| Sample_Parameter | [!DNL Target] 配置文件中的许多信息都由“数据控制方”上传或直接提供。在此示例中，可使用配置文件更新 API 将参数上传到 [!DNL Target] 配置文件中。有关更多信息，请参阅 [将数据导入的方法 [!DNL Target]](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/methods-to-get-data-into-target/){target=_blank}。 |
| user.ReturnTimeOfDay | 此标准字段包括用户最近一次回访的时间。 |
| firstSessionStart | 该标准字段包括用户第一次开始会话的时间。 |
| user.sessionCountScript | [!DNL Target] 配置文件中的许多信息都由“数据控制方”上传或直接提供。在此示例中，配置文件脚本将会增加此访客在“数据控制方”站点上的会话数。有关更多信息，请参阅[配置文件脚本属性](/help/main/c-target/c-visitor-profile/profile-parameters.md)中的“查看配置文件脚本信息卡片”部分。 |

>[!NOTE]
>
>为方便说明，此代码示例是 [!DNL Target] 配置文件 JSON 的简化版本。[!DNL Target] 配置文件的许多字段都不是标准字段。返回的内容取决于特定访客配置文件中的信息。

### [!DNL Target] 是否支持 IP 模糊处理？ {#section_428907B0CD9842D9B245B38C66A53C6A}

如果您选择将 IP 模糊处理用作 GDPR 或 CCPA 实施策略的一部分，则 [!DNL Target] 支持 IP 模糊处理。有关更多信息，请参阅 [隐私](https://developer.adobe.com/target/before-implement/privacy/privacy/){target=_blank}。

### 我是否需要做些什么来防止第三方共享或出售我的数据？

[!DNL Target] 不允许客户直接从 [!DNL Target] 向第三方分享或出售数据，因此无需为 [!DNL Target] 选择禁用出售。
