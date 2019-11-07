---
keywords: GDPR;EU;欧盟;隐私;FAQ;常见问题解答;《加州消费者隐私法案》;CCPA;隐私;数据保护;选择退出;选择退出;政府;法规
description: 有关欧盟《通用数据保护条例》(GDPR)、《加州消费者隐私法案》(CCPA) 和其他国际隐私要求，以及这些法规您所在组织和 Adobe Target 有何影响的信息。
title: 有关欧盟《通用数据保护条例》(GDPR)、《加州消费者隐私法案》(CCPA) 和其他国际隐私要求，以及这些法规您所在组织和 Adobe Target 有何影响的信息。
topic: Standard
uuid: 5e67adcf-464c-495f-9ba5-15152d9a6a41
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 隐私和数据保护法规{#privacy-and-general-data-protection-regulation-gdpr}

有关欧盟《通用数据保护条例》(GDPR)、《加州消费者隐私法案》(CCPA) 和其他国际隐私要求，以及这些法规您所在组织和 Adobe Target 有何影响的信息。

## 隐私和《通用数据保护条例》(GDPR) 概述{#topic_DE567ECB6C944695AEE5073889F1AEA9}

2018 年 5 月 25 日，欧盟的 GDPR 已正式生效。有关这项规定对您有何深远影响，请参阅 [GDPR 与您的业务](https://www.adobe.com/privacy/general-data-protection-regulation.html)。

当 [!DNL Adobe] 向企业提供软件和服务时，作为提供这些服务的一部分，[!DNL Adobe] 将充当其处理并存储的任何个人数据的“数据处理方”。作为“数据处理方”，[!DNL Adobe] 将根据贵公司授予的权限及指示（例如，遵照您与 [!DNL Adobe] 签署的协议中的规定）来处理个人数据。

作为“数据控制方”，您可以决定 [!DNL Adobe] 代表您处理和存储的个人数据。如果您使用 [!DNL Adobe Experience Cloud] 解决方案，[!DNL Adobe] 可能会根据您使用的解决方案和您选择发送到 [!DNL Adobe Experience Cloud] 帐户的信息，来为您托管个人数据。有关详细的示例列表，请参阅 [Adobe Experience Cloud 隐私](https://www.adobe.com/privacy/marketing-cloud.html#collect)。

[!DNL Adobe Experience Cloud] 为“数据控制方”提供 GDPR 就绪 API，让“数据控制方”能够完成以下任务：

* 访问 [!DNL Target] 中存储的数据主体信息
* 删除 [!DNL Target] 中存储的数据主体信息

有关详细信息，请参阅：

* [Adobe《通用数据保护条例》API 网站](https://www.adobe.io/apis/cloudplatform/gdpr.html)
* [GDPR 文档](https://www.adobe.io/apis/cloudplatform/gdpr/docs.html)

## 《加州消费者隐私法案》(CCPA) 概述

《加州消费者隐私法案》(CCPA) 为加利福尼亚州消费者提供了关于个人信息的新权利，并明确了在加利福尼亚州开展业务的某些实体的数据保护职责。CCPA 将于 2020 年 1 月 1 日正式生效。

在较高层面上，这项法案为加州人提供了几项主要的权利，具体包括：

* 请求信息（数据访问）
* 选择退出销售个人信息（一项非常宽泛的权利，可选择退出与第三方共享信息）
* 删除个人信息
* 获知个人信息正在被披露或出售

如果您去年忙于为欧盟隐私法 (GDPR) 做准备，那么您可能会非常熟悉其中的某些权利，而且您已完成的许多工作可能能够重新进行调整。

## Adobe Target 和 [!DNL Experience Platform Launch] 选择加入 {#section_6F7B53F5E40C4425934627B653E831B0}

[!DNL Target] 通过 [!DNL Launch] 提供选择加入功能支持，以协助支持您的同意管理策略。选择加入功能让客户可自行决定如何以及何时触发 [!DNL Target] 标记。还有一个选项，即通过 [!DNL Launch] 预批准 [!DNL Target] 标记。要启用在 [!DNL Target] at.js 中使用选择加入的功能，您应该使用 `targetGlobalSettings` 并添加 `optinEnabled=true` 设置。在 [!DNL Launch] 中，您将需要从 [!DNL Launch] 扩展安装视图的 [!UICONTROL GDPR 选择加入]下拉列表中选择“启用”。有关更多详细信息，请参阅 [Launch 文档](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)。

以下代码片段显示了如何启用 `optinEnabled=true` 设置：

```
window.targetGlobalSettings = {
  optinEnabled: true
};
```

>[!NOTE]
>
>at.js 版本 1.7.0 和 at.js 2.1.0 或更高版本都支持选择加入功能。at.js 版本 2.0.0 和 2.0.1 不支持选择加入功能。
>
>推荐使用 [!DNL Experience Platform Launch] 管理选择加入功能。[!DNL Launch] 中提供了更加精细化的控制，可在触发 [!DNL Target] 标记之前隐藏页面的选定元素，这有助于在您的同意策略中利用此功能。

使用选择加入功能时需要考虑三种情景：

1. **已通过[!DNL Launch]预批准[!DNL Target]标记（或者数据主体以前已经批准[!DNL Target]）：**[!DNL Target] 标记不适用于征求同意，且会发挥预期的作用。
1. **[!DNL Target]标记没有获得预批准且`bodyHidingEnabled`设置为 FALSE：**&#x200B;只有在收到客户的同意之后，才会触发 [!DNL Target] 标记。在收到客户同意之前，仅默认内容可用。在收到客户同意之后，将调用 [!DNL Target] 并向数据主体（访客）提供个性化内容。因为在收到同意之前仅默认内容可用，所以利用适当的策略显得尤为重要，例如对可覆盖网页任何区域或内容的醒目页面进行自定义。这可确保数据主体（访客）获得一致的体验。
1. **[!DNL Target]标记没有获得预批准且`bodyHidingEnabled`设置为 TRUE：**&#x200B;只有在收到客户的同意之后，才会触发 [!DNL Target] 标记。在收到客户同意之前，仅默认内容可用。但是，因为 `bodyHidingEnabled` 设置为 true，`bodyHiddenStyle` 会指示在触发 [!DNL Target] 标记之前页面上需要隐藏的内容（或者数据主体拒绝使用选择加入功能，这种情况下会显示默认内容）。默认情况下，`bodyHiddenStyle` 设置为 `body { opacity:0;`}，这将隐藏 HTML 主体标记。我们推荐采用下面的页面配置，以便隐藏除同意管理器对话框之外的整个页面正文，方法是将页面内容放在一个容器，而将同意管理器对话框放在另一容器中。这种设置会配置 [!DNL Target]，以便仅隐藏页面内容容器。关于如何配置这些设置的信息，请参阅 [ Launch 文档](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html)。

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

## 隐私和数据保护法规 FAQ {#concept_41F88DE95D2943178BEC382736B5C038}

有关欧盟《通用数据保护条例》(GDPR)、《加州消费者隐私法案》(CCPA) 和其他专门特定于 Target 的国际隐私要求的常见问题解答。

### Adobe 会采取什么政策来应对这些法规？{#section_A6849628D6524C80A6E16946DC5D25A9}

[!DNL Adobe] 已经履行了或正在履行作为“数据处理方”的责任和义务。从产品设计角度来看，我们拥有强大的认证安全和隐私控制基础，而且在 2018 年 5 月的截止日期来临之前，我们还增强了产品功能。企业客户将有责任执行这些增强功能，并且有责任更新任何必要的政策和规程。

### 我的公司（数据控制方）是否需要对每个使用的 [!DNL Adobe Experience Cloud] 解决方案提交 GDPR 或 CCPA 请求？{#section_1DCFA9387D0C4506B14DCE04C49AC22A}

不需要，[!DNL Adobe] 正准备提供一种核心方法，帮助“数据控制方”满足其 GDPR 和 CCPA 要求。“数据控制方”不需要直接对每个解决方案提交 GDPR 请求。

包括 [!DNL Target] 在内的 [!DNL Experience Cloud] 解决方案的所有 GDPR 和 CCPA 请求，都将通过一个核心 Adobe API（目前称为 GDPR API）来处理。然后，API 将通过“数据控制方”的 [!DNL Experience Cloud] 解决方案包完成请求。

### 应数据主体/用户的请求，[!DNL Adobe] 允许我们的客户删除哪些信息？{#section_4B51D00924EC4166B2442218B69214F0}

在 [!DNL Target] 中，与单独访客有关的信息是包含在 [!DNL Target] 访客配置文件中。[!DNL Target] 允许我们的客户删除其访客配置文件中所有与 ID 关联的数据。有关 [!DNL Target] 存储的配置文件数据的示例，请参阅[访客配置文件](../../../c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)。

未标识特定个人的聚合或匿名数据（例如，报表数据）或与特定个人无关的数据（例如，内容数据），不在用户删除请求的范围之内。

[!DNL Target]默认情况下，无需执行任何操作，系统即会删除 90 天处于不活跃状态的 访客配置文件。

### 系统支持哪些 ID 来帮助客户完成 [!DNL Target] 的 GDPR 或 CCPA 访问和删除请求？{#section_F7D0EE4E6A28490FB20056A0D26118BC}

[!DNL Target] 支持以下 ID 类型来查找客户配置文件：

| 用户 ID | 命名空间 ID 类型 | 命名空间 ID | 定义 |
|--- |--- |--- |--- |
| Experience Cloud ID (ECID) | Standard | 4 | Adobe Experience Cloud ID，以前称为访客 ID 或 Marketing Cloud ID。您可以使用 JavaScript API 来查找此 ID（请参阅下面的详细信息）。 |
| TnT ID / Cookie ID(TNTID) | Standard | 9 | 在访客的浏览器中设置为 Cookie 的 Target 标识符。您可以使用 JavaScript API 来查找此 ID（请参阅下面的详细信息）。 |
| 第三方 ID / CRM ID (THIRDPARTYID) | 特定于 Target | 不适用 | 如果您向 Target 提供您的 CRM 或您的客户的其他唯一标识符信息。 |

>[!NOTE]
>
>尽管 [!DNL Target] 支持第一方和第三方跨域 Cookie，但是仅推荐使用第一方 [!DNL Target] Cookie 以满足 GDPR 和 CCPA 要求。

### [!DNL Target] 如何处理同意管理？{#section_C86BF5EE4FAA47039659850E7594A6BA}

GDPR 和 CCPA 不会对您获得客户同意的时间造成任何影响，但会影响获得客户同意的方式。每位客户的同意策略取决于其数据收集和使用惯例，以及其隐私政策。同意管理不受 GDPR 和 CCPA 的支持，也不应通过 [!DNL Target] 为 GDPR 和 CCPA 获取同意管理。

[!DNL Adobe] 目前不提供同意管理解决方案，不过，市面上有各种各样的开发工具，可用来解决一些新的需求。For more information on privacy tools in general, including consent managers, see the [2017 Privacy Tech Vendor Report](https://iapp.org/media/pdf/resource_center/Tech-Vendor-Directory-1.4.1-electronic.pdf) on the *International Association of Privacy Professionals (iaap)* website.

[!DNL Target] 通过 [!DNL Launch] 提供选择加入功能支持，以支持您的同意管理策略。选择加入功能让客户可自行决定如何以及何时触发 [!DNL Target] 标记。还有一个选项，即通过 [!DNL Launch] 预批准 [!DNL Target] 标记。推荐使用 [!DNL Launch] 管理选择加入功能。[!DNL Launch] 中提供了更加精细化的控制，可在触发 [!DNL Target] 标记之前隐藏页面的选定元素，这可能会有助于在您的同意策略中利用此功能。

For more information on GDPR, CCPA, and [!DNL Launch], see [The Adobe Privacy JavaScript Library and GDPR](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html). 另请参阅上文中 *Adobe Target 和 Experience Platform Launch 选择加入功能*&#x200B;部分。

### AdobePrivacy.js 是否向 GDPR API 提交信息？{#section_1EB8A2BAAD31474C97C1D455F41DA739}

[!DNL AdobePrivacy.js]“不”**&#x200B;向 API 提交此信息。客户必须自行处理。该库仅提供存储在特定访客浏览器中的 ID。

### removeIdentities 会删除什么内容？{#section_D3A1591EA1B84C499CE1563DEAF32448}

[!DNL removeIdentities]**“只”删除浏览器中的那些标识，而且仅取决于 [!DNL Adobe] 解决方案是否已经执行了这项操作。

例如，[!DNL Target] 将删除存储其 ID 的 Cookie，但 [!DNL Adobe Audience Manager] (AAM) 不删除存储在第三方 Cookie 中的 demdex ID。

### Target GDPR 或 CCPA 请求中需要包含哪些信息？{#section_D29A4744AE6344E68AD7710B185FD6D0}

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

### 我可以通过 GDPR API 从 Target 获得哪些类型的响应？{#section_F67263D2A72B4641A47CE36729CCAE8F}

| 请求状态 | Target 响应消息 | 情景 |
|--- |--- |--- |
| 正在处理 | 正在处理 | Target 收到了 GDPR 或 CCPA 请求并正在进行处理。 |
| 完成 | 不适用 - 公司上下文不适用 | GDPR 或 CCPA 请求中的 IMS ID 未映射到任何 Target 客户端。<br>请注意，一些公司拥有多个 IMS ID。您必须提交配置了 Target 的 IMS ID。 |
| 完成 | 不适用 - 未找到用户上下文 | Target 配置文件存储中不存在 GDPR 或 CCPA 请求中为特定访客或数据主体提供的 ID。<br>请注意，如果您尝试提交 Target 不支持的命名空间 ID 类型，则也会返回此结果（请参阅上面的受支持 ID）。 |
| 错误 | 错误消息（详细信息取决于错误类型） | 获取或删除请求的数据主体配置文件时出错。<br>上传到 Azure 以请求访问时出错。 |

### 对于访问请求，Target 会向 GDPR API 发送什么响应？{#section_D96D8FBEAF9C4BDAA638215FAFE00763}

在响应访问数据的请求时，将提供一份有关所讨论访客的 [!DNL Target] 配置文件摘要。请注意，这些响应信息将发送至 [!DNL Experience Cloud] GDPR API，而 Experience Cloud GDPR API 又会向“数据控制方”发送一个响应。

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
| namespace | 也称为数据源。请参阅本主题中的“系统支持哪些 ID 来帮助客户完成 Target 的 GDPR 或 CCPA 访问和删除请求？”。 |
| type | 您请求访问 GDPR 或 CCPA 数据的 ID 类型。Target 接受多种 ID 类型，其中一些是标准类型，有一些是特定于 Target 的类型。请参阅本主题中的“系统支持哪些 ID 来帮助客户完成 Target 的 GDPR 或 CCPA 访问和删除请求？”。 |
| value | 命名空间/数据源 ID。请参阅本主题中的“系统支持哪些 ID 来帮助客户完成 Target 的 GDPR 或 CCPA 访问和删除请求？”以获取接受的值。 |
| 集成代码 | 集成代码是您数据源的友好名称，可以让您更轻松地跟踪数据源（与使用数据源 ID 相比）。 |

当提供多个值来识别配置文件时，每个有效的标识符将有一个配置文件。该配置文件将通过 GDPR 核心 API 发送到核心 GDPR Azure Blob，以 [!DNL Target] 配置文件 JSON 格式进行响应。

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
| Sample_Parameter | [!DNL Target] 配置文件中的许多信息都由“数据控制方”上传或直接提供。在此示例中，可使用配置文件更新 API 将参数上传到 [!DNL Target] 配置文件中。有关更多信息，请参阅[将数据导入 Target 的方法](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md)。 |
| user.ReturnTimeOfDay | 此标准字段包括用户最近一次回访的时间。 |
| firstSessionStart | 该标准字段包括用户第一次开始会话的时间。 |
| user.sessionCountScript | [!DNL Target] 配置文件中的许多信息都由“数据控制方”上传或直接提供。在此示例中，配置文件脚本将会增加此访客在“数据控制方”站点上的会话数。有关更多信息，请参阅[配置文件脚本属性](/help/c-target/c-visitor-profile/profile-parameters.md)中的“查看配置文件脚本信息卡片”部分。 |

>[!NOTE]
>
>这是 [!DNL Target] 配置文件 JSON 的简化版本，用于提供说明。[!DNL Target] 配置文件的许多字段都不是标准字段。返回的内容取决于特定访客配置文件中的信息。

### Target 是否支持 IP 模糊处理？ {#section_428907B0CD9842D9B245B38C66A53C6A}

如果您选择将 IP 模糊处理用作 GDPR 或 CCPA 实施策略的一部分，则 [!DNL Target] 支持 IP 模糊处理。有关更多信息，请参阅[隐私](../../../c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#concept_639482A343DB4963A6144378E1D8D7F0)。
