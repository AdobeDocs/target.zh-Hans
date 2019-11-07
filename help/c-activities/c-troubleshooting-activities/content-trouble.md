---
keywords: 调试 mbox;mbox 故障诊断;mbox 问题;闪烁;mboxDebug;mboxTrace;令牌;调试器;优先级;活动优先级;Adobe Experience Cloud 调试器;orderConfirmPage mbox;SiteCatalyst 购买 mbox;最畅销;最畅销商品
description: 如果您的页面不显示预期内容，您可以通过以下几个步骤在Adobe target中调试内容交付。
title: 对Adobe Target中的内容交付进行疑难解答
subtopic: 多变量测试
topic: Standard
uuid: 8837d07a-f793-495e-a6c1-b9c35fbe18b1
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 内容交付故障诊断{#troubleshoot-content-delivery}

如果您的页面没有显示预期内容，可以采取以下步骤来对内容交付进行调试。

* 仔细检查您的活动或营销活动代码。键入错误或其他错误可能会导致无法显示预期内容。
* 使用 mboxTrace 或 mboxDebug 对 mbox 进行故障诊断。
* 使用 Adobe Experience Cloud 调试器对 mbox 进行故障诊断，该调试器是一种简单易用的工具，它提供的信息与 mboxDebug 提供的信息大致相同。

当您在页面上设置 Target 以确保正在触发 mbox 且正在设置 Cookie 时，mboxDebug 特别有用。但是，在调试内容交付时，mboxDebug 并不会提供有用的详细信息。如果活动未显示在页面上或页面上显示了不需要的内容，请使用 mboxTrace 对页面进行细致的检查和调试。

## 检索要与调试工具结合使用的授权令牌 {#section_BED130298E794D1FA229DB7C3358BA54}

由于 mboxTrace 和 mboxDebug 可将营销活动数据和配置文件数据披露给外部各方，因此需要授权令牌。可在 [!DNL Target] UI 中检索授权令牌。令牌的有效时间为 6 个小时。

要检索授权令牌，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL 设置]** &gt; **[!UICONTROL 实施]**。
1. 选择 **[!UICONTROL mbox.js]** 或 **[!UICONTROL at.js]**。
1. 单击&#x200B;**[!UICONTROL 生成授权令牌]**。

   ![生成授权令牌](/help/c-activities/c-troubleshooting-activities/assets/generate-auth-token.png)

1. 将生成的令牌作为一个参数添加到 URL 中，以启用任一高级调试工具。

   ![授权令牌](/help/c-activities/c-troubleshooting-activities/assets/gen-auth-token.png)

## mboxTrace {#section_256FCF7C14BB435BA2C68049EF0BA99E}

mboxTrace 让您能够接收 mbox 回复所附带的跟踪信息。跟踪信息可反映 mbox 调用的结果（例如，转化或展示）以及其他任何可能有助于确定为何出现此特定结果的数据，例如可供在营销活动中选择的一组可用分支。使用此信息可调试内容发送服务。

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

要使用 mboxDebug，请将 mboxDebug 参数附加到您 URL 的末尾。下表包含的信息与 mbox 关联的 URL 参数有关。

>[!NOTE]
>
>某些 mboxDebug 参数无论是否进行身份验证均可用。

| URL 参数 | 用途 |
|--- |--- |
| `mboxDebug=1` | 调试器<br>将此参数添加到任何定义了 mbox 的 URL，均会打开一个显示重要调试详情的弹出窗口。Cookie 信息、PCid 和会话 ID 值都会写出，并且用户可看到所有 mbox URL。点击某个 mbox URL 可显示该 mbox 的响应。有关更多信息，请参阅 [mbox_debug.pdf](/help/assets/mbox_debug.pdf)。 |
| `mboxDebug=x-cookie` | 修改 Cookie |
| `mboxDisable=1` | 停用页面上的 mbox |
| `mboxDebug=x-profile` | 查看配置文件集。 |
| `mboxDebug=x-time` | 显示每个 mbox 请求的响应时间 |
| `mboxOverride.browserIp=<Insert IP address>` | 测试地理定位<br>使用此 URL 参数测试地理定位。输入 IP 地址作为此属性的值，Test&amp;Target 的地理定位功能会评估该 IP 地址，查找营销活动中设置的与其匹配的任何地理定位或客户群。 |

>[!NOTE]
>
>确保URL片段位于查询字符串参数之后。 第一个之后的任 `#` 何内容都是片段标识符，导致调试参数无法正确工作。

## Adobe Experience Cloud 调试器 {#section_A2798ED3A431409690A4BE08A1BFCF17}

借助 Adobe Experience Cloud 调试器，您可以快速、轻松地了解 Target 实施。您可以快速查看库配置、检查请求以确保正确传递自定义参数、打开控制台日志记录以及禁用所有 Target 请求。在 Experience Cloud 中进行身份验证后，您可以使用功能强大的 Mbox 跟踪工具来检查您的活动和受众资格以及访客配置文件。

有关更多信息，请参阅下面的培训视频：

有关详细信息，请参 [阅使用Adobe Experience cloud调试器调试at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md)。

## 如果 target.js 在交付过程中加载失败 {#section_ABBA5EFDFFB749D8BEE172DB1F973058}

如果 target.js 在交付过程中加载失败，mbox.js 会向访客发送一个名为“em-disabled”的 Cookie。此 Cookie 可防止使用 Visual Experience Composer 创建的选件呈现在网站上。具有此 Cookie 的访客既不会看到测试内容，也不会被计入活动报表。所有其他选件内容（例如 Target Classic 中营销活动的选件内容）将继续加载。此 Cookie 的生命周期为自加载失败之时起 30 分钟。

## 推荐中未显示最畅销商品 {#section_3920C857270A406C80BE6CBAC8221ECD}

*`SIteCatalyst: purchase`* mbox 无法用于“购买”算法流量数据。请改用 *`orderConfirmPage`* mbox。

## 检查活动优先级 {#section_3D0DD07240F0465BAF655D0804100AED}

在 [!DNL Target Standard/Premium] 中创建的基于表单的活动可能会与在 [!DNL Target Classic] UI 中创建的具有相同优先级且使用相同 mbox 的活动发生冲突。

## 自定义代码在 Internet Explorer 8 中没有产生预期的结果。{#section_FAC3651F19144D12A37A3E4F14C06945}

Target 不再支持 IE 8。

## 使用 mbox.js 时，由全局 mbox 交付的 JavaScript 内容无法加载。{#section_03EC9B9C410B4F52A7FCD81840311709}

请升级到 [!DNL mbox.js] 版本 58 或更高版本。

在 HTML `BODY` 标记出现后，mbox.js 版本 58 及更高版本会立即执行全局 mbox 的非 JavaScript 内容。`DOMContentLoaded` 事件触发后，全局 mbox 的 `<script>` 标记内的 JavaScript 内容便会执行。这种内容交付顺序可确保全局 mbox 的 JavaScript 内容被正确交付和渲染。

## 无法设置 Target Cookie {#section_77AFEB541C0B495EB67E29A4475DF960}

如果您的网站具有一个子域（例如 [!DNL us.domain.com]），但您需要在 [!DNL domain.com]（而不是 [!DNL us.domain.com]）上设置 Target Cookie，则必须覆盖 `cookieDomain` 设置。有关更多信息，请参阅 [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)。

## 如果某个元素同时也是 AEM 个性化的一部分，则 Target 内容会闪烁或无法显示。{#section_9E1DABEB75AB431FB9F09887E6DD07D3}

如果某个 DOM 元素是 Adobe Experience Manager (AEM) 个性化定位和 Target 活动的一部分，则 Target 内容可能会闪烁或无法显示。

要修复此问题，您可以在运行 Target 的页面上禁用 AEM 个性化。

## 由于 URL 无效，无法交付重定向选件和远程选件。 {#section_7D09043B687F43B39DAEDF17D00375AC}

如果重定向选件或远程选件使用无效的 URL，则可能无法交付该选件。

对于重定向选件，mbox 响应可以包含 `/* invalid redirect offer URL */`

或

对于远程选件，mbox 响应可以包含 `/* invalid remote offer URL */`

您可以在浏览器中或使用 mboxTrace 检查 mbox 响应。有关有效 URL 的更多信息，请参阅 [https://tools.ietf.org/html/std66](https://tools.ietf.org/html/std66)。

## mbox 未我的网站上触发。

如果您使用的是无效的 doctype，则 at.js 不会触发 Target mbox。at.js 需要 HTML 5 doctype。

## 培训视频

以下视频包含有关本文中所讨论概念的详细信息。

### 添加扩展

>[!VIDEO](https://video.tv.adobe.com/v/23114t2/?captions=chi_hans)

### Target 基本调试

>[!VIDEO](https://video.tv.adobe.com/v/23115t2/?captions=chi_hans)

### Mbox 跟踪

>[!VIDEO](https://video.tv.adobe.com/v/23113t2/?captions=chi_hans)