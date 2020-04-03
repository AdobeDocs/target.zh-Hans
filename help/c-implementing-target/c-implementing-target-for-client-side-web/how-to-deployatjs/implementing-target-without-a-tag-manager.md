---
keywords: order confirmation;orderConfirmPage
description: 此信息介绍了如何在不使用标签管理器（Adobe Launch 或动态标签管理）的情况下实施 Adobe Target。
title: 不通过标签管理器实施 Target
subtopic: Getting Started
topic: Standard
uuid: 3ecc041a-42d8-40f8-90be-7856e1d3d080
translation-type: tm+mt
source-git-commit: ff3e0d7baacc149e53641f0340dded3a310c60f9

---


# 不通过标签管理器实施 Target{#implement-target-without-a-tag-manager}

此信息介绍了如何在不使用标签管理器（Adobe Launch 或动态标签管理）的情况下实施 [!DNL Adobe Target]。

## 不通过标签管理器实施 Target {#topic_397FFA3D6918456BBE02A9FBE9537894}

此信息介绍了如何在不使用标签管理器（Adobe Launch 或动态标签管理）的情况下实施 Adobe Target。

>[!NOTE]
>
>[Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) 是实施 Target 和 at.js 库的首选方法。以下信息不适用于使用 Adobe Launch 实施 Target 的情况。

## at.js configurations {#concept_2FA0456607D04F82B0539C5BF5309812}

此信息可帮助您在 at.js“设置”页面上设定多个设置。

>[!NOTE]
>
>[Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) 是实施 Target 和 at.js 库的首选方法。以下信息不适用于使用 Adobe Launch 实施 Target 的情况。

>[!NOTE]
>
>您可以覆盖 at.js 库中的设置，而不是在 Target Standard/Premium UI 中或通过使用 REST API 来配置设置。有关更多信息，请参阅 [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)。

要打开“[!UICONTROL 设置]”页面，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL 设置]** > **[!UICONTROL 实施]**。
1. 选择 **[!UICONTROL at.js]** > **[!UICONTROL 编辑 at.js 设置]**。

## 内容交付设置 {#section_118D290DFC444509AD8E4AE86C9D92C0}

更改这些设置之前，请先咨询客户关怀团队。大部分实施都需要使用这些设置。

| 设置 | 描述 |
|--- |--- |
| 自动创建全局 mbox | 选择是否要将全局 mbox 调用嵌入到 at.js 文件中，以使其在每次加载页面时自动触发。<br>更改此设置对 at.js 和 mbox.js 都会造成影响。 |
| 全局 mbox 名称 | 为全局 mbox 选择一个名称。默认情况下，此名称为 target-global-mbox。<br>使用 at.js 的 mbox 名称中可以使用特殊字符，包括与号 (&amp;)。<br>更改此设置对 at.js 和 mbox.js 都会造成影响。 |

## 高级设置 {#section_33B697B77BA64A01B5939D7EC75231F2}

| 设置 | 描述 |
|--- |--- |
| 客户代码 | 客户端代码是指特定于客户端的字符序列，使用 Target API 时通常需要使用此设置。<br>此设置无法更改。 |
| IMS 组织 ID | 此 ID 可将您的实施绑定到您的 [!DNL Adobe Experience Cloud] 帐户。<br>此设置无法更改。 |
| 配置文件生命周期 | 此设置可决定访客配置文件的存储时长。默认情况下，配置文件会存储两周时间。最多可将此时间延长到 90 天。<br>要更改“配置文件生命周期”设置，请联系[客户关怀团队](https://helpx.adobe.com/contact/enterprise-support.ec.html)。 |
| X-Domain | 确定浏览器是在您自己的域中设置 Cookie（第一方 Cookie），还是在 Target 域中设置 Cookie，亦或在两者中都设置 Cookie。<br>更改此设置对 at.js 和 mbox.js 都会造成影响。 |
| 超时 | 如果 [!DNL Target] 未在定义的时间段内做出响应并显示相应内容，则服务器调用会超时，此时会显示默认内容。在访客会话期间会继续尝试发起其他调用。默认时间为 5 秒。<br>更改此设置对 at.js 和 mbox.js 都会造成影响。<br>at.js 库使用的是 `XMLHttpRequest` 中的超时设置。超时从请求被触发时开始，直到 Target 收到来自服务器的响应时结束。有关更多信息，请参阅 Mozilla 开发人员网络上的 [XMLHttpRequest.timeout](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/timeout)。<br>如果在指定的超时内未收到响应，则会显示默认内容，且访客可能会被计为活动的参加者，因为所有数据收集都是在 [!DNL Target] 边缘网络中进行的。如果 [!DNL Target] 边缘网络收到了请求，则访客会被计为参加者。<br>配置超时设置时，请考虑以下事项：<ul><li>如果超时值过低，则用户大部分时间可能都会看到默认内容，即使访客可被计为活动参加者也是如此。</li><li>如果超时值过高，则在延长的时间段内，访客可能会在您的网页上看到空白区域，如果您使用了主体隐藏技术，则可能还会看到空白页面。</li></ul>要更好地了解 mbox 响应时间，请查看浏览器“开发人员工具”中的“网络”选项卡。您还可以使用第三方 Web 性能监测工具，例如 Catchpoint。<br>**注意&#x200B;**：[visitorApiTimeout](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)设置可确保[!DNL Target]等待访客 API 响应的时间不会太长。此设置和此处介绍的 at.js 中的“超时”设置不会相互影响。 |
| 旧版浏览器支持 | **注意**：at.js 版本 0.9.3 及更低版本中提供了“旧版浏览器支持”选项。at.js 版本 0.9.4 中已删除此选项。要获取 at.js 支持的浏览器列表，请参阅[受支持的浏览器](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md)。<br>旧版浏览器是指早期推出的不完全支持 CORS（跨域资源共享）的浏览器。这些浏览器包括：Internet Explorer 版本 11 之前的浏览器，以及 Safari 版本 6 及更低版本。如果禁用“旧版浏览器支持”，则在旧版浏览器上，Target 不会交付内容或将访客计入报表。如果启用此选项，则建议在各个旧版浏览器中执行质量保证，以确保提供良好的客户体验。 |

## 代码设置 {#section_D41C905D0F8149949F525C85F2CCFF7F}

| 设置 | 描述 |
|--- |--- |
| 库标头 | 将任何自定义 JavaScript 添加到库顶部。 |
| 库页脚 | 将任何自定义 JavaScript 添加到库底部。 |

## 下载 at.js {#concept_1E1F958F9CCC4E35AD97581EFAF659E2}

有关使用 Target 界面或下载 API 来下载 库的说明。

<!-- 

ov2/c_target-configure-atjs.xml

 -->

>[!NOTE]
>
>[Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) 是实施 Target 和 at.js 库的首选方法。以下信息不适用于使用 Adobe Launch 实施 Target 的情况。

>[!IMPORTANT]
>
>Target 团队仅维护两个版本的 [!DNL at.js]：当前版本和当前版本的上一个版本。请根据需要升级 [!DNL at.js]，以确保您运行的是受支持的版本。有关每个版本中功能的更多信息，请参阅 [at.js 版本详细信息](../../../c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)。

## Download at.js using the Target interface {#section_1F5EE401C2314338910FC57F9592894E}

要从 [!DNL Target] 界面下载 [!DNL at.js]，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL 设置]** > **[!UICONTROL 实施]**。
1. 选择 **[!UICONTROL at.js]**。
1. 单击&#x200B;**[!UICONTROL 下载 at.js]**。

## Download at.js using the Target Download API {#section_C0D9D2A9068144708D08526BA5CA10D0}

要使用 API 下载 [!DNL at.js]，请执行以下操作：

1. 获取您的客户端代码。

   您的客户端代码位于 **[!UICONTROL 界面中的]**&#x200B;设置&#x200B;**[!UICONTROL >]**&#x200B;实施&#x200B;**[!UICONTROL >]**&#x200B;编辑 at.js 设置[!DNL Target]页面顶部。

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
* “预连接”和“预提取”选项可帮助提升网页加载速度。If you use these configurations, ensure that you replace `<client code>` with your own client code, which you can obtain from the **[!UICONTROL Setup]** > **[!UICONTROL Implementation]** > **[!UICONTROL Edit at.js Settings]** page.
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