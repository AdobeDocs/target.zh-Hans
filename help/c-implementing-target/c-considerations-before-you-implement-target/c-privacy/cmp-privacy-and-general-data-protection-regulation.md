---
description: 有关欧盟一般数据保护规定(GDPR)、California Consumer Privacy Act(CPA)、其他国际隐私要求以及这些法规如何影响组织和Adobe Target的信息。
keywords: gdpr；欧盟；欧盟；隐私；常见问题解答；常见问题解答；加利福尼亚消费者隐私权法案；ccpa；隐私；数据保护；选择退出；退出；政府；法规
seo-description: 有关欧盟一般数据保护规定(GDPR)、California Consumer Privacy Act(CPA)、其他国际隐私要求以及这些法规如何影响组织和Adobe Target的信息。
seo-title: 有关欧盟一般数据保护规定(GDPR)、California Consumer Privacy Act(CPA)、其他国际隐私要求以及这些法规如何影响组织和Adobe Target的信息。
solution: Target
title: 隐私和数据保护规定
topic: Standard
uuid: 5e67adcf-464c-495f-9ba5-15152d9a6a41
translation-type: tm+mt
source-git-commit: ec69199fe85c9d8f2abb4826195ff894bd80af4a

---


# 隐私和数据保护规定 {#privacy-and-general-data-protection-regulation-gdpr}

有关欧盟一般数据保护规定(GDPR)、California Consumer Privacy Act(CPA)、其他国际隐私要求以及这些法规如何影响组织和Adobe Target的信息。

## Privacy and General Data Protection Regulation (GDPR) overview {#topic_DE567ECB6C944695AEE5073889F1AEA9}

2018年月25日，欧盟的GDPR生效。有关这项规定对您有何深远影响，请参阅 [GDPR 与您的业务](https://www.adobe.com/privacy/general-data-protection-regulation.html)。

When [!DNL Adobe] is providing software and services to an enterprise, [!DNL Adobe] is acting as a Data Processor for any personal data it processes and stores as part of providing these services. As a Data Processor, [!DNL Adobe] processes personal data in accordance with your company's permission and instructions (for example, as set out in your agreement with [!DNL Adobe]).

As the Data Controller, you determine the personal data that [!DNL Adobe] processes and stores on your behalf. If you use [!DNL Adobe Experience Cloud] solutions, [!DNL Adobe] might host personal data for you, depending on the solutions you use and the information you choose to send to your [!DNL Adobe Experience Cloud] account. 有关详细的示例列表，请参阅 [Adobe Experience Cloud 隐私](https://www.adobe.com/privacy/marketing-cloud.html#collect)。

[!DNL Adobe Experience Cloud] 为数据管理者提供可用于GDPR的API，使其能够完成以下任务：

* 访问 中存储的数据主体信息[!DNL Target]
* 删除 中存储的数据主体信息[!DNL Target]

有关详细信息，请参阅：

* [Adobe《通用数据保护条例》API 网站](https://www.adobe.io/apis/cloudplatform/gdpr.html)
* [GDPR 文档](https://www.adobe.io/apis/cloudplatform/gdpr/docs.html)

## California Consumer Privacy Act(CPA)概述

加利福尼亚州消费者隐私法案(CPA)为加利福尼亚消费者提供有关其个人信息的新权利，并为在加利福尼亚开展业务的某些实体施加数据保护职责。在较高级别上，法律为加利福尼亚州提供几项主要权利，包括：

* 请求信息(数据访问)
* 选择退出销售个人信息(被广泛定义的权利决定退出与第三方共享信息)
* 删除个人信息
* 获知个人信息正在被披露或出售

如果您去年忙于准备欧洲隐私法(GDPR)，其中某些权利可能会非常熟悉，您完成的许多工作可能会被重新确定用途。

## Adobe Target and [!DNL Experience Platform Launch] opt-in {#section_6F7B53F5E40C4425934627B653E831B0}

[!DNL Target] 提供支持 [!DNL Launch] 功能支持，以帮助支持您的同意管理战略。Opt-in functionality lets customers control how and when the [!DNL Target] tag is fired. There is also an option via [!DNL Launch] to pre-approve the [!DNL Target] tag. To enable the ability to use Opt-In in the [!DNL Target] at.js library, you should use `targetGlobalSettings` and add the `optinEnabled=true` setting. In [!DNL Launch] you'll need to select "enable" from the [!UICONTROL GDPR Opt-In] drop-down list in the [!DNL Launch] extension installation view. 有关更多详细信息，请参阅 [Launch 文档](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)。

以下代码片段显示了如何启用 `optinEnabled=true` 设置：

```
window.targetGlobalSettings = {
  optinEnabled: true
};
```

>[!NOTE]
>
>在. js版本1.7.0和. js2.1.0或更高版本中支持选择加入功能。在. js版本2.0.0和2.0.1中不支持选择加入。
>
>Using [!DNL Experience Platform Launch] to manage opt-in is the recommended approach. [!DNL Launch][!DNL Target] 在触发之前隐藏页面中的选定元素，以此作为您同意战略的一部分，从而更精细地控制您的页面。

使用选择加入功能时需要考虑三种情景：

1. **[!DNL Target]标记经过预先批准[!DNL Launch](或之前批准的数据主体[!DNL Target])：**[!DNL Target] 该标记未接受同意和按预期运行。
1. **[!DNL Target]标记没有获得预批准且`bodyHidingEnabled`设置为 FALSE：**&#x200B;只有在收到客户的同意之后，才会触发 标记。[!DNL Target]在收到客户同意之前，仅默认内容可用。After consent is received, [!DNL Target] is called and personalized content is available to the data subject (visitor). 因为在收到同意之前仅默认内容可用，所以利用适当的策略显得尤为重要，例如对可覆盖网页任何区域或内容的醒目页面进行自定义。这可确保数据主体（访客）获得一致的体验。
1. **[!DNL Target]标记没有获得预批准且`bodyHidingEnabled`设置为 TRUE：**&#x200B;只有在收到客户的同意之后，才会触发 标记。[!DNL Target]在收到客户同意之前，仅默认内容可用。但是，因为 `bodyHidingEnabled` 设置为 true，`bodyHiddenStyle` 会指示在触发 标记之前页面上需要隐藏的内容（或者数据主体拒绝使用选择加入功能，这种情况下会显示默认内容）。[!DNL Target]默认情况下，`bodyHiddenStyle` 设置为 `body { opacity:0;`}，这将隐藏 HTML 主体标记。我们推荐采用下面的页面配置，以便隐藏除同意管理器对话框之外的整个页面正文，方法是将页面内容放在一个容器，而将同意管理器对话框放在另一容器中。This setup configures [!DNL Target] so that it hides the page content container only. 关于如何配置这些设置的信息，请参阅 [ Launch 文档](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html)。

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

关于欧盟一般数据保护规定(GDPR)、California Consumer Privacy Act(CPA)以及针对Target的其他国际隐私要求的常见问题解答。

### Adobe对这些法规有何政策？ {#section_A6849628D6524C80A6E16946DC5D25A9}

[!DNL Adobe] 已经履行了或正在履行作为“数据处理方”的责任和义务。我们在经认证的安全和隐私控制方面拥有坚实的基础，在2018年月截止日期之前进行了产品增强。企业客户将有责任执行这些增强功能，并且有责任更新任何必要的政策和规程。

### Will my company, the Data Controller, need to submit a GDPR or CCPA request to each [!DNL Adobe Experience Cloud] solution that it uses? {#section_1DCFA9387D0C4506B14DCE04C49AC22A}

No, [!DNL Adobe] is providing a central way to help Data Controllers meet their GDPR and CCPA requirements. “数据控制方”不需要直接对每个解决方案提交 GDPR 请求。

All GDPR and CCPA requests across [!DNL Experience Cloud] solutions, including [!DNL Target], will be made through a central Adobe API, currently called the GDPR API. The API will then complete the request across the Data Controller's [!DNL Experience Cloud] solution suite.

### What information will [!DNL Adobe] enable our customers to delete in response to a data subject/user request? {#section_4B51D00924EC4166B2442218B69214F0}

The information related to an individual visitor within [!DNL Target] is contained within the [!DNL Target] Visitor Profile. [!DNL Target] 允许我们的客户删除其访客配置文件中所有与 ID 关联的数据。有关配置文件数据 [!DNL Target] 存储的示例，请参阅 [访客配置文件](../../../c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)。

未标识特定个人的聚合或匿名数据（例如，报表数据）或与特定个人无关的数据（例如，内容数据），不在用户删除请求的范围之内。

[!DNL Target]默认情况下，无需执行任何操作，系统即会删除 90 天处于不活跃状态的 访客配置文件。

### What IDs are supported to help customers complete a GDPR or CCPA access and deletion request for [!DNL Target]? {#section_F7D0EE4E6A28490FB20056A0D26118BC}

[!DNL Target] 支持以下 ID 类型来查找客户配置文件：

| 用户 ID | 命名空间 ID 类型 | 命名空间 ID | 定义 |
|--- |--- |--- |--- |
| Experience Cloud ID (ECID) | Standard | 4 | Adobe Experience Cloud ID，以前称为访客 ID 或 Marketing Cloud ID。您可以使用 JavaScript API 来查找此 ID（请参阅下面的详细信息）。 |
| TnT ID / Cookie ID(TNTID) | Standard | 9 | 在访客的浏览器中设置为 Cookie 的 Target 标识符。您可以使用 JavaScript API 来查找此 ID（请参阅下面的详细信息）。 |
| 第三方 ID / CRM ID (THIRDPARTYID) | 特定于 Target | 不适用 | 如果您向 Target 提供您的 CRM 或您的客户的其他唯一标识符信息。 |

>[!NOTE]
>
>Although [!DNL Target] supports both first-party and third-party cross-domain cookies, first-party [!DNL Target] cookies only are recommended for GDPR and CCPA.

### [!DNL Target] 如何处理同意管理？ {#section_C86BF5EE4FAA47039659850E7594A6BA}

GDPR和CPA不会在您需要获得同意时发生变化，但得到的信息是如何得到的。每位客户的同意策略取决于其数据收集和使用惯例，以及其隐私政策。Consent management isn’t supported by and shouldn’t be achieved via [!DNL Target] for GDPR and CCPA.

[!DNL Adobe] 目前不提供同意管理解决方案，不过，市面上有各种各样的开发工具，可用来解决一些新的需求。For more information on privacy tools in general, including consent managers, see the [2017 Privacy Tech Vendor Report](https://iapp.org/media/pdf/resource_center/Tech-Vendor-Directory-1.4.1-electronic.pdf) on the *International Association of Privacy Professionals (iaap)* website.

[!DNL Target] 提供了参与功能支持， [!DNL Launch] 以提供对同意管理战略的支持。Opt-in functionality lets customers control how and when the [!DNL Target] tag is fired. There is also an option via [!DNL Launch] to pre-approve the [!DNL Target] tag. Using [!DNL Launch] to manage opt-in is the recommended approach. Further granular control exists in [!DNL Launch] to hide select elements of your page prior to the [!DNL Target] firing that might be helpful to leverage as part of your consent strategy.

For more information on GDPR, CCPA, and [!DNL Launch], see [The Adobe Privacy JavaScript Library and GDPR](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html). Also, see the *Adobe Target and Experience Platform Launch opt-in* section above.

### AdobePrivacy.js 是否向 GDPR API 提交信息？{#section_1EB8A2BAAD31474C97C1D455F41DA739}

[!DNL AdobePrivacy.js]“不”**&#x200B;向 API 提交此信息。客户必须自行处理。该库仅提供存储在特定访客浏览器中的 ID。

### removeIdentities 会删除什么内容？{#section_D3A1591EA1B84C499CE1563DEAF32448}

[!DNL removeIdentities]*“只”*[!DNL Adobe]删除浏览器中的那些标识，而且仅取决于 解决方案是否已经执行了这项操作。

For example, [!DNL Target] deletes the cookies storing its IDs, but [!DNL Adobe Audience Manager] (AAM) does not delete the demdex ID that is stored in a third-party cookie.

### What information needs to be included in a Target GDPR or CCPA request? {#section_D29A4744AE6344E68AD7710B185FD6D0}

In addition to the requirements from Central Privacy Service, a valid GDPR or CCPA message for [!DNL Target] contains:

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
| 正在处理 | 正在处理 | Target收到GDPR或CCPA请求，正在处理。 |
| 完成 | 不适用 - 公司上下文不适用 | GDPR或CCPA请求中的IMS ID未映射到任何Target客户端。<br>请注意，一些公司拥有多个 IMS ID。您必须提交配置了 Target 的 IMS ID。 |
| 完成 | 不适用 - 未找到用户上下文 | GDPR或CPA请求中为特定访客或数据主体提供的ID不存在于Target配置文件存储中。<br>请注意，如果您尝试提交 Target 不支持的命名空间 ID 类型，则也会返回此结果（请参阅上面的受支持 ID）。 |
| 错误 | 错误消息（详细信息取决于错误类型） | 获取或删除请求的数据主体配置文件时出错。<br>上传到 Azure 以请求访问时出错。 |

### 对于访问请求，Target 会向 GDPR API 发送什么响应？{#section_D96D8FBEAF9C4BDAA638215FAFE00763}

Responses to access data requests contain a summary of the [!DNL Target] profile for the visitor in question. Note that this return is sent to the [!DNL Experience Cloud] GDPR API, which in turn sends Data Controllers a response.

A sample [!DNL Target] access API response could look like this:

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
| jobId | 指示Central GDPR API中的GDPR或CPA作业ID。 |
| imsOrgID | 为贵公司提供的唯一标识符。 |
| namespace | 也称为数据源。请参阅“哪些ID可帮助客户完成GDPR或CCPA访问和删除请求的目标？”。 |
| type | 您请求GDPR或CCPA数据访问的ID类型。Target 接受多种 ID 类型，其中一些是标准类型，有一些是特定于 Target 的类型。请参阅“哪些ID可帮助客户完成GDPR或CCPA访问和删除请求的目标？”。 |
| value | 命名空间/数据源 ID。请参阅“哪些ID可帮助客户完成GDPR或CCPA访问和删除请求的目标？”以获取接受的值。 |
| 集成代码 | 集成代码是您数据源的友好名称，可以让您更轻松地跟踪数据源（与使用数据源 ID 相比）。 |

当提供多个值来识别配置文件时，每个有效的标识符将有一个配置文件。The profile file(s) are sent to the central GDPR Azure Blob through the GDPR Central API, in the format of [!DNL Target] Profile JSON response.

[!DNL Target] 示例配置文件JSON可能类似于以下示例：

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
| Sample_Parameter | [!DNL Target] 配置文件中的许多信息都由数据管理者上传或直接提供。In this example, a parameter was uploaded into the [!DNL Target] profile using the Profile Update API. 有关详细信息，请参阅 [将数据获取到Target](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md)的方法。 |
| user.ReturnTimeOfDay | 此标准字段包括用户最近一次回访的时间。 |
| firstSessionStart | 该标准字段包括用户第一次开始会话的时间。 |
| user.sessionCountScript | [!DNL Target] 配置文件中的许多信息都由数据管理者上传或直接提供。在此示例中，配置文件脚本将会增加此访客在“数据控制方”站点上的会话数。有关更多信息，请参阅[配置文件脚本属性](/help/c-target/c-visitor-profile/profile-parameters.md)中的“查看配置文件脚本信息卡片”部分。 |

>[!NOTE]
>
>This is a shortened version of a [!DNL Target] profile JSON for the purpose of illustration. [!DNL Target] 配置文件的许多字段不是标准的。返回的内容取决于特定访客配置文件中的信息。

### Target 是否支持 IP 模糊处理？ {#section_428907B0CD9842D9B245B38C66A53C6A}

[!DNL Target] 如果您选择将IP模糊处理用作GDPR或CCPA实施战略的一部分，请支持IP模糊处理。For more information, see [Privacy](../../../c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#concept_639482A343DB4963A6144378E1D8D7F0).
