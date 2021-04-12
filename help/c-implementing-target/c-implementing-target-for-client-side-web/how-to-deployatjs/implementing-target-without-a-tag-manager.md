---
keywords: 实现目标；实现；实现at.js；标签管理器；设备上决策；设备上决策
description: 了解如何指定设置（帐户详细信息、实现方法等） 来实施Adobe Target at.js库，而无需使用标签管理器。
title: 我是否可以在没有标签管理器的情况下实施目标?
feature: 实施服务器端
role: Developer
exl-id: cb57f6b8-43cb-485d-a7ea-12db8170013f
translation-type: tm+mt
source-git-commit: 20337e6e54108502b6397c73580b898cc91ebd9b
workflow-type: tm+mt
source-wordcount: '1697'
ht-degree: 51%

---

# 不通过标签管理器实施 Target

有关在不使用标签管理器（[!DNL Adobe Experience Platform Launch]或[!DNL Dynamic Tag Manager]）的情况下实现[!DNL Adobe Target]的信息。

>[!NOTE]
>
>[Adobe Experience Platform ](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) Launch是实现目标和at.js库的首选方法。使用AdobePlatform launch实施目标时，不适用以下信息。

要访问[!UICONTROL 实施]页，请单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 实施]**。

您可以在此页面上指定以下设置：

* 帐户详细信息
* 实现方法
* 用户档案 API
* 调试器工具
* 隐私

>[!NOTE]
>
>您可以覆盖 at.js 库中的设置，而不是在 Target Standard/Premium UI 中或通过使用 REST API 来配置设置。有关更多信息，请参阅 [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)。

## 帐户详细信息

您可以视图以下帐户详细信息。 无法更改这些设置。

| 设置 | 描述 |
| --- | --- |
| [!UICONTROL 客户代码] | 客户端代码是指特定于客户端的字符序列，使用 Target API 时通常需要使用此设置。 |
| [!UICONTROL IMS 组织 ID] | 此 ID 可将您的实施绑定到您的 [!DNL Adobe Experience Cloud] 帐户。 |
| [!UICONTROL 设备上决策] | 要启用设备决策，请将切换滑至“开启”位置。<br>设备上决策允许您在服务器上缓存A/B和体验定位(XT)活动，并在接近零的延迟时执行内存中决策。有关详细信息，请参阅&#x200B;*Adobe Target SDK*&#x200B;指南中的[设备决策](https://adobetarget-sdks.gitbook.io/docs/on-device-decisioning/introduction-to-on-device-decisioning)简介。 |
| [!UICONTROL 在对象中包含所有现有的设备上决策限定活动。] | （视情况而定）如果启用设备决策，则显示此选项。<br>如果希望符合设备决策条件的所有实时目标活动自动包含在对象中，请将切换滑至“开启”位置。<br>关闭此切换意味着您必须重新创建并激活任何设备上决策活动，以便将它们包含在生成的规则对象中。 |

## 实现方法

可以在“实施方法”面板中配置以下设置：

### 全局设置

>[!NOTE]
>
>这些设置将应用于所有[!DNL Target] .js库。 在“实施方法”部分中执行更改后，必须下载库并在实施中更新它。

| 设置 | 描述 |
| --- | --- |
| 已启用页面加载(自动创建全局mbox | 选择是否要将全局 mbox 调用嵌入到 at.js 文件中，以使其在每次加载页面时自动触发。 |
| 全局 mbox | 为全局 mbox 选择一个名称。默认情况下，此名称为 target-global-mbox。<br>使用 at.js 的 mbox 名称中可以使用特殊字符，包括与号 (&amp;)。 |
| 超时（秒） | 如果 [!DNL Target] 未在定义的时间段内做出响应并显示相应内容，则服务器调用会超时，此时会显示默认内容。在访客会话期间会继续尝试发起其他调用。默认时间为 5 秒。<br>at.js 库使用的是 `XMLHttpRequest` 中的超时设置。超时从请求被触发时开始，直到 [!DNL Target] 收到来自服务器的响应时结束。有关更多信息，请参阅 Mozilla 开发人员网络上的 [XMLHttpRequest.timeout](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/timeout)。<br>如果在指定的超时内未收到响应，则会显示默认内容，且访客可能会被计为活动的参加者，因为所有数据收集都是在 [!DNL Target] 边缘网络中进行的。如果 [!DNL Target] 边缘网络收到了请求，则访客会被计为参加者。<br>配置超时设置时，请考虑以下事项：<ul><li>如果超时值过低，则用户大部分时间可能都会看到默认内容，即使访客可被计为活动参加者也是如此。</li><li>如果超时值过高，则在延长的时间段内，访客可能会在您的网页上看到空白区域，如果您使用了主体隐藏技术，则可能还会看到空白页面。</li></ul>要更好地了解 mbox 响应时间，请查看浏览器“开发人员工具”中的“网络”选项卡。您还可以使用第三方 Web 性能监测工具，例如 Catchpoint。<br>**注意**：[visitorApiTimeout](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) 设置可确保 [!DNL Target] 等待访客 API 响应的时间不会太长。此设置和此处介绍的 at.js 中的“超时”设置不会相互影响。 |
| 配置文件生命周期 | 此设置可决定访客配置文件的存储时长。默认情况下，配置文件会存储两周时间。此设置最多可增加90天。<br>要更改“配置文件生命周期”设置，请联系[客户关怀团队](https://helpx.adobe.com/cn/contact/enterprise-support.ec.html)。 |

### 一种主要实现方法

>[!IMPORTANT]
>
>目标团队同时支持at.js 1。*x* 与 at.js 2.*x* 之间的映射。升级到at.js的任一主要版本的最新更新，以确保您运行的是受支持的版本。

要下载所需的at.js版本，请单击相应的&#x200B;**[!UICONTROL 下载]**&#x200B;按钮。

要编辑at.js设置，请单击所需at.js版本旁边的&#x200B;**[!UICONTROL 编辑]**。

>[!IMPORTANT]
>
>在更改这些默认设置之前，请咨询[Client Care](/help/cmp-resources-and-contact-information.md)，以便不影响当前实施。

除上述设置外，还提供以下特定at.js设置：

| 设置 | 描述 |
|--- |--- |
| 自定义库标题 | 将任何自定义 JavaScript 添加到库顶部。 |
| 自定义库页脚 | 将任何自定义 JavaScript 添加到库底部。 |

### 用户档案 API

可为通过 API 进行的批量更新启用或禁用身份验证，并生成配置文件身份验证令牌。

有关详细信息，请参阅[用户档案API设置](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/profile-api-settings.md)。

### 调试器工具

生成授权令牌以使用高级[!DNL Target]调试工具。 单击&#x200B;**[!UICONTROL 生成新身份验证令牌]**。

![生成新身份验证令牌](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/debugger-auth-token.png)

### 隐私

这些设置允许您按照适用的数据隐私法使用[!DNL Target]。

从“模糊处理访客IP地址”下拉式列表中选择所需的设置：

* 上一个八位字节模糊处理
* 整个IP模糊处理
* None

有关更多信息，请参阅[隐私](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md)。

>[!NOTE]
>
>“旧版浏览器支持”选项在at.js版本0.9.3及更早版本中可用。 at.js 版本 0.9.4 中已删除此选项。要获取 at.js 支持的浏览器列表，请参阅[受支持的浏览器](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md)。<br>旧版浏览器是指早期推出的不完全支持 CORS（跨域资源共享）的浏览器。这些浏览器包括：Internet Explorer 版本 11 之前的浏览器，以及 Safari 版本 6 及更低版本。如果禁用了“旧版浏览器支持”，则目标不会在这些浏览器上的报表中传送内容或计数访客。 如果启用了此选项，则建议跨旧版浏览器进行质量保证，以确保良好的客户体验。

## 下载 at.js {#concept_1E1F958F9CCC4E35AD97581EFAF659E2}

使用[!DNL Target]接口或Download API下载库的说明。

>[!NOTE]
>
>* [Adobe Experience Platform ](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) Launch是实现目标和at.js库的首选方法。使用AdobePlatform launch实施目标时，不适用以下信息。
   >
   >
* 目标团队同时支持at.js 1。*x* 与 at.js 2.*x* 之间的映射。请升级到at.js的任一主要版本的最新更新，以确保您运行的是受支持的版本。 有关每个版本中功能的更多信息，请参阅 [at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)。


### 使用目标接口{#section_1F5EE401C2314338910FC57F9592894E}下载at.js

要从 [!DNL Target] 界面下载 [!DNL at.js]，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 实施]**。
1. 从[!UICONTROL 实现方法]部分，单击所需at.js版本旁边的&#x200B;**[!UICONTROL 下载]**&#x200B;按钮。

### 使用目标 Download API {#section_C0D9D2A9068144708D08526BA5CA10D0}下载at.js

要使用 API 下载 [!DNL at.js]，请执行以下操作：

1. 获取您的客户端代码。

   您的客户端代码位于[!DNL Target]接口的&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Implementation]**&#x200B;页面顶部。

1. 获取您的管理员编号。

   加载以下 URL：

   ```
   https://admin.testandtarget.omniture.com/rest/v1/endpoint/<varname>client code</varname>
   ```

   使用步骤1中的客户端代码替换`client code`。

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

   * 将`admin number`替换为您的管理员号。
   * 使用步骤1中的客户端代码替换`client code`。
   * 将`version number`替换为所需的at.js版本号（例如，2.2）。

   >[!IMPORTANT]
   >
   >Target 团队仅维护两个版本的 [!DNL at.js]：当前版本和当前版本的上一个版本。请根据需要升级 [!DNL at.js]，以确保您运行的是受支持的版本。有关每个版本中功能的更多信息，请参阅 [at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)。

   加载此 URL 后，便会开始下载您的自定义 [!DNL at.js] 文件。

## at.js实现{#concept_03CFA86973A147839BEB48A06FEE5E5A}

at.js 应该在您网站每个页面的 `<head>` 元素中实施。

未使用[AdobePlatform launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25)或[动态标签管理](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-using-dynamic-tag-management.md#concept_3A40AF6FFC0E4FD2AA81B303A79D0B96)等标签管理器的目标的典型实现如下所示：

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

* 应使用HTML5 Doctype（例如`<!doctype html>`）。 不受支持或较旧的 doctypes 可能会导致 Target 无法提出请求。
* “预连接”和“预提取”选项可帮助提升网页加载速度。如果您使用这些配置，请确保将`<client code>`替换为您自己的客户端代码，您可以从&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 实施]页获取该客户端代码。
* 如果您拥有数据层，那么在 at.js 加载之前，最好在页面的 `<head>` 中定义尽可能多的数据层。此版面提供了在目标中使用此信息进行个性化的最大能力。
* 特殊 Target 函数（例如 `targetPageParams()`、`targetPageParamsAll()`、数据提供程序和 `targetGlobalSettings()`）应在 at.js 加载之前，数据层加载之后进行定义。或者，这些函数可以保存在[!UICONTROL 编辑at.js设置]页面的[!UICONTROL 库标题]部分，并保存为at.js库本身的一部分。 有关这些函数的详细信息，请参阅[at.js函数](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md)。
* 如果您使用JavaScript帮助程序库（如jQuery），请在目标之前将其包含在内，这样您就可以在构建目标体验时使用其语法和方法。
* 将 at.js 包含在您页面的 `<head>` 中。

## 跟踪转换{#task_E85D2F64FEB84201A594F2288FABF053}

订单确认 mbox 将记录您网站上订单的详细信息，并能够基于收入和订单生成报表。订单确认 mbox 还可驱动推荐算法，例如“购买了产品 x，也购买了产品 y 的人”。

>[!NOTE]
>
>如果用户在您的网站上购买产品，即使您将Analytics for 目标(A4T)用于报告,Adobe也建议实施订单确认mbox。

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
