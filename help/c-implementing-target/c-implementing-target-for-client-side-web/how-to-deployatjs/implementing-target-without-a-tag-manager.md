---
keywords: implement target;implementation;implement at.js;tag manager
description: 此信息介绍了如何在不使用标签管理器（Adobe Launch 或动态标签管理）的情况下实施 Adobe Target。
title: 不通过标签管理器实施 Target
subtopic: Getting Started
topic: Standard
uuid: 3ecc041a-42d8-40f8-90be-7856e1d3d080
translation-type: tm+mt
source-git-commit: 3edb13b196240bb1918fc66edcc653936e32d3ef
workflow-type: tm+mt
source-wordcount: '1537'
ht-degree: 66%

---


# 不通过标签管理器实施 Target{#implement-target-without-a-tag-manager}

有关不使用标 [!DNL Adobe Target] 签管理器（或）实[!DNL Adobe Launch] 施的 [!DNL Dynamic Tag Manager]信息。

>[!NOTE]
>
>[Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) 是实施 Target 和 at.js 库的首选方法。以下信息不适用于使用 Adobe Launch 实施 Target 的情况。

要访问“实 [!UICONTROL 施] ”页，请单 **[!UICONTROL 击“管理]** ” **[!UICONTROL >“]**&#x200B;实施”。

您可以在此页面上指定以下设置：

* 帐户详细信息
* 实现方法
* 用户档案API
* 调试器工具
* 隐私

>[!NOTE]
>
>您可以覆盖 at.js 库中的设置，而不是在 Target Standard/Premium UI 中或通过使用 REST API 来配置设置。有关更多信息，请参阅 [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)。

## 帐户详细信息

您可以视图以下帐户详细信息。 无法更改这些设置。

| 设置 | 描述 |
| --- | --- |
| 客户代码 | 客户端代码是指特定于客户端的字符序列，使用 Target API 时通常需要使用此设置。 |
| IMS 组织 ID | 此 ID 可将您的实施绑定到您的 [!DNL Adobe Experience Cloud] 帐户。 |

## 实现方法

可以在“实施方法”面板中配置以下设置：

### 全局设置

>[!NOTE]
>
>这些设置将应用于所 [!DNL Target] 有。js库。 在“实施方法” [!UICONTROL 部分执行更] 改后，您需要下载库并在实施中更新它。

|启用页面加载(自动创建全局mbox|选择是否将全局mbox调用嵌入at.js文件以自动触发每页加载。|
|全局mbox|为全局mbox选择名称。 默认情况下，此名称为 target-global-mbox。<br>使用 at.js 的 mbox 名称中可以使用特殊字符，包括与号 (&amp;)。|
|Timeout (seconds)|If [!DNL Target] does not respond with content within the defined period, the server call times out and default content is displayed. 在访客会话期间会继续尝试发起其他调用。默认时间为 5 秒。<br>at.js 库使用的是 `XMLHttpRequest` 中的超时设置。超时从请求被触发时开始，直到 [!DNL Target] 收到来自服务器的响应时结束。有关更多信息，请参阅 Mozilla 开发人员网络上的 [XMLHttpRequest.timeout](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/timeout)。<br>如果在指定的超时内未收到响应，则会显示默认内容，且访客可能会被计为活动的参加者，因为所有数据收集都是在 [!DNL Target] 边缘网络中进行的。如果 [!DNL Target] 边缘网络收到了请求，则访客会被计为参加者。<br>配置超时设置时，请考虑以下事项：<ul><li>如果超时值过低，则用户大部分时间可能都会看到默认内容，即使访客可被计为活动参加者也是如此。</li><li>如果超时值过高，则在延长的时间段内，访客可能会在您的网页上看到空白区域，如果您使用了主体隐藏技术，则可能还会看到空白页面。</li></ul>要更好地了解 mbox 响应时间，请查看浏览器“开发人员工具”中的“网络”选项卡。您还可以使用第三方 Web 性能监测工具，例如 Catchpoint。<br>**注意&#x200B;**：[visitorApiTimeout](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)设置可确保[!DNL Target]等待访客 API 响应的时间不会太长。此设置和此处介绍的 at.js 中的“超时”设置不会相互影响。|
|用户档案生命周期|此设置确定存储访客用户档案的时间。 默认情况下，配置文件会存储两周时间。最多可将此时间延长到 90 天。<br>要更改用户档案生命周期设置，请与客[户关怀](https://helpx.adobe.com/cn/contact/enterprise-support.ec.html)。|

### 主要实现方法

>[!IMPORTANT]
>
>目标团队支持at.js 1。*x* 与 at.js 2.*x* 之间的映射。请升级到at.js的任一主要版本的最新更新，以确保您运行的是受支持的版本。

要下载所需的at.js版本，请单击相应的“下 **[!UICONTROL 载]** ”按钮。

要编辑at.js设置，请单 **[!UICONTROL 击]** 所需at.js版本旁的“编辑”。

>[!IMPORTANT]
>
>在更改这些默认设置之前，请咨 [询Client Care](/help/cmp-resources-and-contact-information.md) ，以便不影响当前实施。

除上述设置外，还提供以下特定at.js设置：

| 设置 | 描述 |
|--- |--- |
| 自定义库标题 | 将任何自定义 JavaScript 添加到库顶部。 |
| 自定义库页脚 | 将任何自定义 JavaScript 添加到库底部。 |

### 用户档案API

可为通过 API 进行的批量更新启用或禁用身份验证，并生成配置文件身份验证令牌。

For more information, see [Profile API settings](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/profile-api-settings.md).

### 调试器工具

生成授权令牌以使用高级 [!DNL Target] 调试工具。 Click **[!UICONTROL Generate New Authentication Token]**.

![生成新的身份验证令牌](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/debugger-auth-token.png)

### 隐私

这些设置允许您在遵守 [!DNL Target] 适用数据隐私法的情况下使用。

从“模糊访客IP地址”下拉列表中选择所需的设置：

* 最后八位字节模糊化
* 整个IP模糊化
* None

有关更多信息，请参阅[隐私](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md)。

>[!NOTE]
>
>at.js版本0.9.3及更早版本中提供了“旧版浏览器支持”选项。 at.js 版本 0.9.4 中已删除此选项。要获取 at.js 支持的浏览器列表，请参阅[受支持的浏览器](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md)。<br>旧版浏览器是指早期推出的不完全支持 CORS（跨域资源共享）的浏览器。这些浏览器包括：Internet Explorer 版本 11 之前的浏览器，以及 Safari 版本 6 及更低版本。如果禁用了“旧版浏览器支持”,目标不会在这些浏览器上的报告中提供内容或计算访客数。 如果启用了此选项，则建议跨旧版浏览器进行质量保证，以确保良好的客户体验。

## 下载 at.js {#concept_1E1F958F9CCC4E35AD97581EFAF659E2}

Instructions to download the library using the [!DNL Target] interface or the Download API.

>[!NOTE]
>
>* [Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) 是实施 Target 和 at.js 库的首选方法。以下信息不适用于使用 Adobe Launch 实施 Target 的情况。
   >
   >
* 目标团队支持at.js 1。*x* 与 at.js 2.*x* 之间的映射。请升级到at.js的任一主要版本的最新更新，以确保您运行的是受支持的版本。 有关每个版本中功能的更多信息，请参阅 [at.js 版本详细信息](../../../c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)。


### Download at.js using the Target interface {#section_1F5EE401C2314338910FC57F9592894E}

要从 [!DNL Target] 界面下载 [!DNL at.js]，请执行以下操作：

1. 单击“ **[!UICONTROL 管理]** ”>“ **[!UICONTROL 实施]**”。
1. 在“实 [!UICONTROL 施方法] ”部分，单 **[!UICONTROL 击所需]** at.js版本旁的“下载”按钮。

### Download at.js using the Target Download API {#section_C0D9D2A9068144708D08526BA5CA10D0}

要使用 API 下载 [!DNL at.js]，请执行以下操作：

1. 获取您的客户端代码。

   Your client code is available at the top of the **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** page of the [!DNL Target] interface.

1. 获取您的管理员编号。

   加载以下 URL：

   ```
   https://admin.testandtarget.omniture.com/rest/v1/endpoint/<varname>client code</varname>
   ```

   Replace `client code` with the client code from Step 1.

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

   * Replace `admin number` with your admin number.
   * Replace `client code` with the client code from Step 1.
   * Replace `version number` with the desired at.js version number (for example, 2.2).

   >[!IMPORTANT]
   >
   >Target 团队仅维护两个版本的 [!DNL at.js]：当前版本和当前版本的上一个版本。请根据需要升级 [!DNL at.js]，以确保您运行的是受支持的版本。有关每个版本中功能的更多信息，请参阅 [at.js 版本详细信息](../../../c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)。

   加载此 URL 后，便会开始下载您的自定义 [!DNL at.js] 文件。

## at.js implementation {#concept_03CFA86973A147839BEB48A06FEE5E5A}

at.js 应该在您网站每个页面的 `<head>` 元素中实施。

不使用标签管理（例如 [Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) 或[动态标签管理](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-using-dynamic-tag-management.md#concept_3A40AF6FFC0E4FD2AA81B303A79D0B96)）的典型 Target 实施如下所示：

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

* 应使用 HTML5 Doctype（例如 `<!doctype html>`）。不受支持或较旧的 doctypes 可能会导致 Target 无法提出请求。
* “预连接”和“预提取”选项可帮助提升网页加载速度。If you use these configurations, ensure that you replace `<client code>` with your own client code, which you can obtain from the **[!UICONTROL Administration]** > **[!UICONTROL Implementation] page.
* 如果您拥有数据层，那么在 at.js 加载之前，最好在页面的 `<head>` 中定义尽可能多的数据层。此位置允许您在 Target 中利用此信息进行最大程度的个性化。
* 特殊 Target 函数（例如 `targetPageParams()`、`targetPageParamsAll()`、数据提供程序和 `targetGlobalSettings()`）应在 at.js 加载之前，数据层加载之后进行定义。或者，可以将这些函数保存在“[!UICONTROL 编辑 at.js 设置]”页面的“[!UICONTROL 库标头]”部分中，并另存为 at.js 库的一部分。有关这些函数的更多信息，请参阅 [at.js 函数](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md)。
* 如果您使用 JavaScript 帮助程序库（例如 jQuery），则请在使用 Target 之前包含它们，以便在构建 Target 体验时可以利用它们的语法和方法。
* 将 at.js 包含在您页面的 `<head>` 中。

## Track conversions {#task_E85D2F64FEB84201A594F2288FABF053}

订单确认 mbox 将记录您网站上订单的详细信息，并能够基于收入和订单生成报表。订单确认 mbox 还可驱动推荐算法，例如“购买了产品 x，也购买了产品 y 的人”。

>[!NOTE]
>
>如果用户在您的网站上进行购买，那么即使您使用了 Analytics for Target (A4T) 进行报告，我们也仍然建议您实施订单确认 mbox。

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