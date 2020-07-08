---
keywords: debug mbox;troubleshoot mbox;mbox issues;flicker;mboxDebug;mboxTrace;token;debugger;priority;activity priority;Adobe Experience Cloud Debugger;orderConfirmPage mbox;SiteCatalyst  purchase mbox;top selling;top seller
description: 如果您的页面不显示预期内容，您可以执行一些步骤以在Adobe Target中调试内容投放。
title: 对Adobe Target中的内容投放进行疑难解答
subtopic: Multivariate Test
topic: Standard
uuid: 8837d07a-f793-495e-a6c1-b9c35fbe18b1
translation-type: tm+mt
source-git-commit: c7664f9674234565a3657f453541095811fa5aa6
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 68%

---


# 内容交付故障诊断{#troubleshoot-content-delivery}

如果您的页面没有显示预期内容，可以采取以下步骤来对内容交付进行调试。

* 仔细检查您的活动或营销活动代码。键入错误或其他错误可能会导致无法显示预期内容。
* Use mboxTrace or mboxDebug to troubleshoot the [!DNL Target] request.
* Use the Adobe Experience Cloud Debugger, an easy-to-use tool that provides much of the same information as mboxDebug, to troubleshoot the [!DNL Target] request.

mboxDebug is especially useful when you are setting up [!DNL Target] on your page to make sure the [!DNL Target] request is firing and the cookie is being set. 但是，在调试内容交付时，mboxDebug 并不会提供有用的详细信息。如果活动未显示在页面上或页面上显示了不需要的内容，请使用 mboxTrace 对页面进行细致的检查和调试。

## 检索要与调试工具结合使用的授权令牌 {#section_BED130298E794D1FA229DB7C3358BA54}

由于 mboxTrace 和 mboxDebug 可将营销活动数据和配置文件数据披露给外部各方，因此需要授权令牌。可在 [!DNL Target] UI 中检索授权令牌。令牌的有效时间为 6 个小时。

要检索授权令牌，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL 设置]** > **[!UICONTROL 实施]**。
1. 选择 **[!UICONTROL mbox.js]** 或 **[!UICONTROL at.js]**。
1. 单击&#x200B;**[!UICONTROL 生成授权令牌]**。

   ![生成授权令牌](/help/c-activities/c-troubleshooting-activities/assets/generate-auth-token.png)

1. 将生成的令牌作为一个参数添加到 URL 中，以启用任一高级调试工具。

   ![授权令牌](/help/c-activities/c-troubleshooting-activities/assets/gen-auth-token.png)

## mboxTrace {#section_256FCF7C14BB435BA2C68049EF0BA99E}

mboxTrace enables you to receive trace information attached to [!DNL Target] responses. Trace information reflects the outcome of a [!DNL Target] call (for example, a conversion or an impression) and any additional data that may help in determining why this particular outcome happened, such as a set of available branches among which the selection was made in a campaign. 使用此信息可调试内容发送服务。

可用的参数如下：

| mboxTrace 选项 | 结果 |
|--- |--- |
| `?mboxTrace=console` | 作为对象打印到控制台日志中。<br>对于 at.js，不会像在 mbox.js 中一样弹出新的浏览器窗口或输出到控制台，您而是将需要检查网络请求，并在“预览”(Chrome) 或“响应”(Firefox) 下查看。 |
| `?mboxTrace=json` | 作为 JSON 文字字符串打印到控制台日志中 |
| `?mboxTrace=window` | 作为 JSON 字符串打印到弹出窗口中 |
| `?mboxTrace=disable` | 关闭跟踪会话模式 |

**mboxTrace 调用示例**

`https://www.mysite.com/page.html?mboxTrace=window&authorization=f543abf-0111-4061-9619-d41d665c59a6`

输出会显示与您的内容相关的非常详细的信息。mboxTrace 会显示与您的营销活动或活动以及配置文件相关的详细信息。它还提供执行前配置文件的快照，以及执行后所做更改的快照。同时，也显示为各个位置评估了哪些营销活动或活动。

某些信息包含匹配和不匹配的客户群和定位 ID：

* **SegmentId**：客户群的 ID，来自可重复使用的客户群库或为特定营销活动创建的匿名客户群库。
* **TargetId**：定位的 ID，来自定位表达式库或营销活动中任意客户群的匿名定位。
* **不匹配**：在此调用中，请求不符合这些客户群或定位的要求。
* **匹配**：请求符合指定客户群或定位的要求。

**在“推荐”页面上使用 mboxTrace**：将 mboxTrace 作为查询参数添加到带有推荐的页面上时，会将页面上的“推荐”设计替换成 mboxTrace 详细信息窗口，其中显示了与您的推荐相关的详细信息，包括：

* 返回的推荐与请求的推荐
* 使用的键值，以及该键值是否在生成推荐
* 标准生成的推荐与备用推荐
* 标准配置
* 应用的排除和包含
* 收集规则

您不需要在查询参数中包含 `=console`、`=json` 或 `=window`。完成 mboxTrace 详细信息后，添加 `=disable`，然后按 **[!UICONTROL Enter]** 返回到正常显示模式。

您网站的正常功能和外观不受 mboxTrace 的影响。访客将看到您的常规“推荐”设计。

## mboxDebug {#mboxdebug}

要使用 mboxDebug，请将 mboxDebug 参数附加到您 URL 的末尾。The following table contains information about [!DNL Target] response-related URL parameters.

>[!NOTE]
>
>某些 mboxDebug 参数无论是否进行身份验证均可用。

| URL 参数 | 用途 |
|--- |--- |
| `mboxDebug=1` | Debugger<br>Adding this parameter to any URL with Target requests defined opens a pop-up window with valuable debugging details. Cookie 信息、PCid 和会话 ID 值都会写出，并且用户可看到所有 URL。Click on a Target request URL to show the response for that [!DNL Target] request. 有关更多信息，请参阅 [mbox_debug.pdf](/help/assets/mbox_debug.pdf)。 |
| `mboxDebug=x-cookie` | 修改 Cookie |
| `mboxDisable=1` | 停用页面上的 mbox |
| `mboxDebug=x-profile` | 查看配置文件集。 |
| `mboxDebug=x-time` | Show response time for each [!DNL Target] request |
| `mboxOverride.browserIp=<Insert IP address>` | 测试地理定位<br>使用此 URL 参数测试地理定位。输入 IP 地址作为此属性的值，Test&amp;Target 的地理定位功能会评估该 IP 地址，查找营销活动中设置的与其匹配的任何地理定位或客户群。 |

>[!NOTE]
>
>确保URL片段位于查询字符串参数之后。 第一个代码之 `#` 后的任何内容都是片段标识符，导致调试参数无法正确工作。

## Adobe Experience Cloud 调试器 {#section_A2798ED3A431409690A4BE08A1BFCF17}

借助 Adobe Experience Cloud 调试器，您可以快速、轻松地了解 Target 实施。您可以快速查看库配置、检查请求以确保正确传递自定义参数、打开控制台日志记录以及禁用所有 Target 请求。在Experience Cloud中进行身份验证，您可以使用功能强大的MboxTrace工具检查活动和受众资格以及访客用户档案。

有关更多信息，请参阅下面的培训视频：

有关详细信息，请参 [阅使用Adobe Experience Cloud调试器调试at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md)。

## 如果 target.js 在交付过程中加载失败 {#section_ABBA5EFDFFB749D8BEE172DB1F973058}

如果 target.js 在交付过程中加载失败，mbox.js 会向访客发送一个名为“em-disabled”的 Cookie。此 Cookie 可防止使用 Visual Experience Composer 创建的选件呈现在网站上。具有此 Cookie 的访客既不会看到测试内容，也不会被计入活动报表。所有其他选件内容（例如 Target Classic 中营销活动的选件内容）将继续加载。此 Cookie 的生命周期为自加载失败之时起 30 分钟。

## 推荐中未显示最畅销商品 {#section_3920C857270A406C80BE6CBAC8221ECD}

The *`SiteCatalyst: purchase`* call can&#39;t be used for Purchase algorithm traffic data. 请改用 *`orderConfirmPage`* 呼叫。

## 检查活动优先级 {#section_3D0DD07240F0465BAF655D0804100AED}

Form-based activities created with [!DNL Target Standard/Premium] might collide with activities created in the [!DNL Target Classic] UI that have the same priority and use the same [!DNL Target] request.

## 自定义代码在 Internet Explorer 8 中没有产生预期的结果。{#section_FAC3651F19144D12A37A3E4F14C06945}

Target 不再支持 IE 8。

## JavaScript content delivered by the global [!DNL Target] request doesn&#39;t load when using mbox.js. {#section_03EC9B9C410B4F52A7FCD81840311709}

请升级到 [!DNL mbox.js] 版本 58 或更高版本。

mbox.js version 58 and later executes non-JavaScript content for the global [!DNL Target] request immediately after the HTML `BODY` tag is present. JavaScript content inside `<script>` tags for the global [!DNL Target] request executes after the `DOMContentLoaded` event is fired. This order of content delivery ensures that JavaScript content for the global [!DNL Target] request is delivered and rendered properly.

## 无法设置 Target Cookie {#section_77AFEB541C0B495EB67E29A4475DF960}

如果您的网站具有一个子域（例如 [!DNL us.domain.com]），但您需要在 [!DNL domain.com]（而不是 [!DNL us.domain.com]）上设置 Target Cookie，则必须覆盖 `cookieDomain` 设置。有关更多信息，请参阅 [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)。

## 如果某个元素同时也是 AEM 个性化的一部分，则 Target 内容会闪烁或无法显示。{#section_9E1DABEB75AB431FB9F09887E6DD07D3}

如果某个 DOM 元素是 Adobe Experience Manager (AEM) 个性化定位和 Target 活动的一部分，则 Target 内容可能会闪烁或无法显示。

要修复此问题，您可以在运行 Target 的页面上禁用 AEM 个性化。

## 由于 URL 无效，无法交付重定向选件和远程选件。 {#section_7D09043B687F43B39DAEDF17D00375AC}

如果重定向选件或远程选件使用无效的 URL，则可能无法交付该选件。

For redirect offers, the [!DNL Target] response can contain `/* invalid redirect offer URL */`

或

For remote offers, the [!DNL Target] response can contain `/* invalid remote offer URL */`

You can check the [!DNL Target] response in the browser or using mboxTrace. 有关有效 URL 的更多信息，请参阅 [https://tools.ietf.org/html/std66](https://tools.ietf.org/html/std66)。

## 目标请求未在我的站点上触发。

如果您使用的doctype无效，at.js不会触发目标请求。 at.js 需要 HTML 5 doctype。

## 培训视频

以下视频包含有关本文中所讨论概念的详细信息。

### 添加扩展 ![教程徽章](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23114t2/)

### 基本目标调试 ![教程徽章](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23115t2/)

### Mbox描摹教 ![程徽章](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23113t2/)