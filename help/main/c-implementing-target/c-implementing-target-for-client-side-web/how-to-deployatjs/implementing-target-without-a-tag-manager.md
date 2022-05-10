---
keywords: 实施target；实施；实施at.js；标签管理器；设备上决策；设备上决策
description: 了解如何指定设置（帐户详细信息、实施方法等） 实施Adobe [!DNL Target] at.js库，而不使用标签管理器。
title: 我能否实施 [!DNL Target] 没有标签管理器？
feature: Implement Server-side
role: Developer
exl-id: cb57f6b8-43cb-485d-a7ea-12db8170013f
source-git-commit: cba754e4cdd1ba7cfe3bb84039224f311b06c41d
workflow-type: tm+mt
source-wordcount: '1794'
ht-degree: 49%

---

# 实施 [!DNL Target] 没有标签管理器

有关实施的信息 [!DNL Adobe Target] ，而无需在 [!DNL Adobe Experience Platform].

>[!NOTE]
>
>中的标记 [Adobe Experience Platform](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) 是实现 [!DNL Target] 和at.js库。 在中使用标记时，以下信息不适用 [!DNL Adobe Experience Platform] 实施 [!DNL Target].

访问 [!UICONTROL 实施] 页面，单击 **[!UICONTROL 管理]** > **[!UICONTROL 实施]**.

您可以在此页面上指定以下设置：

* 帐户详细信息
* 实施方法
* 配置文件API
* 调试器工具
* 隐私

>[!NOTE]
>
>您可以覆盖 at.js 库中的设置，而不是在 [!DNL Target Standard/Premium] UI 中或通过使用 REST API 来配置设置。有关更多信息，请参阅 [targetGlobalSettings()](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)。

## 帐户详细信息

您可以查看以下帐户详细信息。 这些设置无法更改。

| 设置 | 描述 |
| --- | --- |
| [!UICONTROL 客户代码] | 客户端代码是指特定于客户端的字符序列，使用 [!DNL Target] API 时通常需要使用此设置。 |
| [!UICONTROL IMS 组织 ID] | 此 ID 可将您的实施绑定到您的 [!DNL Adobe Experience Cloud] 帐户。 |
| [!UICONTROL 设备内决策] | 要启用设备上的决策，请将切换开关滑动到“开”位置。<br>设备内决策允许您缓存A/B和 [!UICONTROL 体验定位] (XT)营销活动，并在接近零的延迟下执行内存决策。 有关更多信息，请参阅 [设备上决策简介](https://adobetarget-sdks.gitbook.io/docs/on-device-decisioning/introduction-to-on-device-decisioning) 在 *[!DNL Adobe Target]SDK* 的双曲余切值。 |
| [!UICONTROL 在对象中包含所有现有的设备上决策合格活动。] | （视情况而定）如果您启用设备决策，则会显示此选项。<br>如果您希望所有符合设备决策条件的实时Target活动自动包含在项目中，请将切换开关滑动到“开”位置。<br>关闭此切换开关意味着您必须重新创建并激活任何设备上决策活动，才能将这些活动包含在生成的规则对象中。 |

## 实施方法

可以在“实施方法”面板中配置以下设置：

### 全局设置

>[!NOTE]
>
>这些设置将应用于所有 [!DNL Target] .js库。 在实施方法部分中执行更改后，您必须下载库并在实施中对其进行更新。

| 设置 | 描述 |
| --- | --- |
| 启用页面加载（自动创建全局mbox） | 选择是否要将全局 mbox 调用嵌入到 at.js 文件中，以使其在每次加载页面时自动触发。 |
| 全局 mbox | 为全局 mbox 选择一个名称。默认情况下，此名称为 target-global-mbox。<br>使用 at.js 的 mbox 名称中可以使用特殊字符，包括与号 (&amp;)。 |
| 超时（秒） | 如果 [!DNL Target] 未在定义的时间段内做出响应并显示相应内容，则服务器调用会超时，此时会显示默认内容。在访客会话期间会继续尝试发起其他调用。默认时间为 5 秒。<br>at.js 库使用的是 `XMLHttpRequest` 中的超时设置。超时从请求被触发时开始，直到 [!DNL Target] 收到来自服务器的响应时结束。有关更多信息，请参阅 Mozilla 开发人员网络上的 [XMLHttpRequest.timeout](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/timeout)。<br>如果在指定的超时内未收到响应，则会显示默认内容，且访客可能会被计为活动的参加者，因为所有数据收集都是在 [!DNL Target] 边缘网络中进行的。如果 [!DNL Target] 边缘网络收到了请求，则访客会被计为参加者。<br>配置超时设置时，请考虑以下事项：<ul><li>如果超时值过低，则用户大部分时间可能都会看到默认内容，即使访客可被计为活动参加者也是如此。</li><li>如果超时值过高，则在延长的时间段内，访客可能会在您的网页上看到空白区域，如果您使用了主体隐藏技术，则可能还会看到空白页面。</li></ul>要更好地了解 mbox 响应时间，请查看浏览器“开发人员工具”中的“网络”选项卡。您还可以使用第三方 Web 性能监测工具，例如 Catchpoint。<br>**注意**：[visitorApiTimeout](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) 设置可确保 [!DNL Target] 等待访客 API 响应的时间不会太长。此设置和此处介绍的 at.js 中的“超时”设置不会相互影响。 |
| 配置文件生命周期 | 此设置可决定访客配置文件的存储时长。默认情况下，配置文件会存储两周时间。此设置最多可增加90天。<br>要更改“配置文件生命周期”设置，请联系[客户关怀团队](https://helpx.adobe.com/cn/contact/enterprise-support.ec.html)。 |

### 主要实现方法

>[!IMPORTANT]
>
>Target团队同时支持at.js 1.*x* 与 at.js 2.*x* 之间的映射。请升级到at.js任一主要版本的最新更新，以确保您运行的是受支持的版本。

要下载所需的at.js版本，请单击相应的 **[!UICONTROL 下载]** 按钮。

要编辑at.js设置，请单击 **[!UICONTROL 编辑]** 的子目录访问Advertising Cloud帮助。

>[!IMPORTANT]
>
>在更改这些默认设置之前，请咨询 [客户关怀](/help/main/cmp-resources-and-contact-information.md) 这样您就不会影响当前的实施。

除了上述设置之外，还提供了以下特定的at.js设置：

| 设置 | 描述 |
|--- |--- |
| 自定义库标题 | 将任何自定义 JavaScript 添加到库顶部。 |
| 自定义库页脚 | 将任何自定义 JavaScript 添加到库底部。 |

### 使用设备上决策的实施方法

从版本2.5.0开始，at.js提供了设备决策功能。 设备内决策允许您缓存 [A/B测试](/help/main/c-activities/t-test-ab/test-ab.md) 和 [体验定位](/help/main/c-activities/t-experience-target/experience-target.md) (XT)在浏览器上执行内存决策的活动，而无需对 [!DNL Adobe Target] 边缘网络。

有关更多信息，请参阅：

* 客户端： [at.js的设备内决策](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md)
* 服务器端： [设备上决策简介](https://adobetarget-sdks.gitbook.io/docs/on-device-decisioning/introduction-to-on-device-decisioning)
* 服务器端： [设备内决策](/help/main/c-implementing-target/c-api-and-sdk-overview/on-device-decisioning.md){target=_blank}
* Node.js: [为贵组织启用设备决策](https://adobetarget-sdks.gitbook.io/docs/getting-started/node.js){target=_blank}
* Java: [为贵组织启用设备决策](https://adobetarget-sdks.gitbook.io/docs/getting-started/java){target=_blank}
* .NET: [为贵组织启用设备决策](https://adobetarget-sdks.gitbook.io/docs/getting-started/dotnet){target=_blank}
* Python: [为贵组织启用设备决策](https://adobetarget-sdks.gitbook.io/docs/getting-started/python){target=_blank}

### 配置文件API

可为通过 API 进行的批量更新启用或禁用身份验证，并生成配置文件身份验证令牌。

有关更多信息，请参阅 [配置文件API设置](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/profile-api-settings.md).

### 调试器工具

生成要使用高级的授权令牌 [!DNL Target] 调试工具。 单击 **[!UICONTROL 生成新的身份验证令牌]**.

![生成新的身份验证令牌](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/debugger-auth-token.png)

### 隐私

这些设置允许您使用 [!DNL Target] 遵守适用的数据隐私法。

从“模糊处理访客IP地址”下拉列表中选择所需的设置：

* 最后八位字节模糊处理
* 整个IP模糊处理
* 无

有关更多信息，请参阅[隐私](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md)。

>[!NOTE]
>
>at.js版本0.9.3及更低版本中提供了“旧版浏览器支持”选项。 at.js 版本 0.9.4 中已删除此选项。要获取 at.js 支持的浏览器列表，请参阅[受支持的浏览器](/help/main/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md)。<br>旧版浏览器是指早期推出的不完全支持 CORS（跨域资源共享）的浏览器。这些浏览器包括：Internet Explorer 版本 11 之前的浏览器，以及 Safari 版本 6 及更低版本。如果禁用了“旧版浏览器支持”，则Target不会在这些浏览器的报表中提供内容或计数访客。 如果启用了此选项，则建议跨旧版浏览器进行质量保证，以确保获得良好的客户体验。

## 下载 at.js {#concept_1E1F958F9CCC4E35AD97581EFAF659E2}

有关使用 [!DNL Target] 界面或下载API。

>[!NOTE]
>
>* [[!DNL Adobe Experience Platform]](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) 是实现 [!DNL Target] 和at.js库。 在中使用标记时，以下信息不适用 [!DNL Adobe Experience Platform] 实施 [!DNL Target].
>
>* 的 [!DNL Target] 团队同时支持at.js 1.*x* 与 at.js 2.*x* 之间的映射。请升级到at.js任一主要版本的最新更新，以确保您运行的是受支持的版本。 有关每个版本中功能的更多信息，请参阅 [at.js 版本详细信息](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)。


### 使用 [!DNL Target] 界面 {#section_1F5EE401C2314338910FC57F9592894E}

要从 [!DNL Target] 界面下载 [!DNL at.js]，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL “管理”]**>**[!UICONTROL “实现”]**。
1. 从 [!UICONTROL 实施方法] ，单击 **[!UICONTROL 下载]** 按钮。

### 使用 [!DNL Target] 下载API {#section_C0D9D2A9068144708D08526BA5CA10D0}

要使用 API 下载 [!DNL at.js]，请执行以下操作：

1. 获取您的客户端代码。

   您的客户端代码位于 **[!UICONTROL 管理]** > **[!UICONTROL 实施]** 页面 [!DNL Target] 界面。

1. 获取您的管理员编号。

   加载以下 URL：

   ```
   https://admin.testandtarget.omniture.com/rest/v1/endpoint/<varname>client code</varname>
   ```

   替换 `client code` 与步骤1中的客户端代码一起使用。

   加载此 URL 后，应该会出现类似于以下示例的结果：

   ```
   { 
     "api": "https://admin6.testandtarget.omniture.com/admin/rest/v1" 
   }
   ```

   在此示例中，“6”表示管理员编号。

1. 下载 [!DNL at.js]。

   加载具有以下结构的 URL：

   ```
   https://admin<varname>admin number</varname>.testandtarget.omniture.com/admin/rest/v1/libraries/atjs/download?client=<varname>client code</varname>&version=<version number>
   ```

   * 替换 `admin number` 使用您的管理员编号。
   * 替换 `client code` 与步骤1中的客户端代码一起使用。
   * 替换 `version number` ，以使用所需的at.js版本号（例如，2.2）。

   >[!IMPORTANT]
   >
   >Target 团队仅维护两个版本的 [!DNL at.js]：当前版本和当前版本的上一个版本。请根据需要升级 [!DNL at.js]，以确保您运行的是受支持的版本。有关每个版本中功能的更多信息，请参阅 [at.js 版本详细信息](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)。

   加载此 URL 后，便会开始下载您的自定义 [!DNL at.js] 文件。

## at.js 实施 {#concept_03CFA86973A147839BEB48A06FEE5E5A}

at.js 应该在您网站每个页面的 `<head>` 元素中实施。

不使用标签管理器的典型Target实施，例如 [[!DNL Adobe Experience Platform]](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) 如下所示：

```
<!doctype html> 
<html> 
<head> 
    <meta charset="utf-8"> 
    <title>Title of the Page</title> 
    <!--Preconnect and DNS-Prefetch to improve page load time--> 
    <link rel="preconnect" href="//<client code>.tt.omtrdc.net"> 
    <link rel="dns-prefetch" href="//<client code>.tt.omtrdc.net"> 
    <!--/Preconnect and DNS-Prefetch--> 
    <!--Data Layer to enable rich data collection and targeting--> 
    <script> 
        var digitalData = { 
            "page": { 
                "pageInfo": { 
                    "pageName": "Home" 
                } 
            } 
        }; 
    </script> 
    <!--/Data Layer--> 
    <!-- targetPageParams(), targetPageParamsAll(), Data Providers or targetGlobalSettings() functions to enrich the visitor profile or modify the library settings--> 
    <script> 
        targetPageParams = function() { 
            return { 
                "a": 1, 
                "b": 2, 
                "pageName": digitalData.page.pageInfo.pageName, 
                "profile": { 
                    "age": 26, 
                    "country": { 
                        "city": "San Francisco" 
                    } 
                } 
            }; 
        }; 
    </script> 
    <!--/targetPageParams()--> 
 
    <!--jQuery or other helper libraries should be implemented before at.js if you would like to use their methods in Target--> 
    <script src="jquery-3.3.1.min.js"></script> 
    <!--/jQuery--> 
    <!--Target's JavaScript SDK, at.js--> 
    <script src="at.js"></script> 
    <!--/at.js--> 
</head>
<body> 
    The default content of the page 
</body> 
</html>
```

请注意以下重要说明：

* HTML5 Doctype(例如， `<!doctype html>`)。 不受支持或较旧的 doctypes 可能会导致 Target 无法提出请求。
* “预连接”和“预提取”选项可帮助提升网页加载速度。如果您使用这些配置，请确保将 `<client code>` 使用您自己的客户端代码，您可以从 **[!UICONTROL 管理]** > **[!UICONTROL 实施] 页面。
* 如果您拥有数据层，那么在 at.js 加载之前，最好在页面的 `<head>` 中定义尽可能多的数据层。此位置允许在Target中最大限度地使用此信息进行个性化。
* 特殊 Target 函数（例如 `targetPageParams()`、`targetPageParamsAll()`、数据提供程序和 `targetGlobalSettings()`）应在 at.js 加载之前，数据层加载之后进行定义。或者，这些函数也可以保存在 [!UICONTROL 库标题] 部分 [!UICONTROL 编辑at.js设置] 页面，并另存为at.js库本身的一部分。 有关这些函数的更多信息，请参阅 [at.js函数](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md).
* 如果您使用JavaScript帮助程序库（如jQuery），请在Target之前包含这些库，以便在构建Target体验时可以使用它们的语法和方法。
* 将 at.js 包含在您页面的 `<head>` 中。

## 跟踪转化 {#task_E85D2F64FEB84201A594F2288FABF053}

订单确认 mbox 将记录您网站上订单的详细信息，并能够基于收入和订单生成报表。订单确认 mbox 还可驱动推荐算法，例如“购买了产品 x，也购买了产品 y 的人”。

>[!NOTE]
>
>如果用户在您的网站上购买产品，则即使您使用Analytics for Target(A4T)进行报表，Adobe仍建议实施订单确认mbox。

1. 在订单详细信息页面，按照以下模式插入 mbox 脚本。
1. 使用您目录中的动态或静态值替换大写的文字。

   >[!NOTE]
   >
   >使用逗号分隔多个产品 ID。

   **提示：**&#x200B;您也可以在任意 mbox（必须命名为 `orderConfirmPage`）中传递订单信息。还可以在同一营销活动之内的多个 mbox 中传递订单信息。

   ```
   <script type="text/javascript"> 
   adobe.target.trackEvent({ 
       "mbox": "orderConfirmPage", 
       "params":{  
           "orderId": "ORDER ID FROM YOUR ORDER PAGE",  
           "orderTotal": "ORDER TOTAL FROM YOUR ORDER PAGE",  
           "productPurchasedId": "PRODUCT ID FROM YOUR ORDER PAGE, PRODUCT ID2, PRODUCT ID3"  
       } 
   }); 
   </script> 
   ```

订单确认 mbox 使用以下参数：

| 参数 | 描述 |
|--- |--- |
| orderId | 针对转化计数标识订单的唯一值。<br>`orderId` 必须唯一。报表中会忽略重复订单。 |
| orderTotal | 所购产品的币值。<br>不要传递货币符号。使用小数点（而非逗号）表示小数值。 |
| productPurchasedId（可选） | 订单中所购产品的产品 ID（逗号分隔）列表。<br>这些产品 ID 显示在审计报表中，以支持其他报表分析。 |
