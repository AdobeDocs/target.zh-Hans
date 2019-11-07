---
keywords: at.js;2.0;1.x;Cookie
description: 有关 Adobe Target at.js 2.x 和 at.js 1.x 如何处理 Cookie 的详细信息
title: Adobe Target at.js Cookie
subtopic: 入门指南
topic: Standard
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# at.js Cookie{#at-js-cookies}

有关 at.js 2.x 和 at.js 1.*x* Cookie 行为的信息。

## at.js 2.x Cookie 行为

对于 at.js 版本 2.0.0，*仅支持第一方 Cookie*。如同在 at.js 1.*x* 中一样，第一方 Cookie“mbox”存储在 `clientdomain.com` 中，其中 `clientdomain` 是您的域。

at.js 会生成一个会话 ID 并将其存储在 Cookie 中。第一个响应包含任何活动信息，以及 [!DNL Target] 服务器生成的 `TNT` 或 `PC ID`。然后，at.js 将 `TNT/PC ID` 写入 Cookie。

尽管 `ECID` 在 [!DNL Target] 请求中传递，但 `AMCV_###@AdobeOrg` 第一方 Cookie 始终由 [!DNL Experience Cloud ID Service] 进行设置。

### 不支持第三方 Cookie 和跨域跟踪

通过跨域跟踪，可以将在不同域中两个相关的站点上的会话作为单个会话查看。您可以创建一个跨越 `siteA.com` 和 `siteB.com` 的 [!DNL Target] 活动，这样访客在跨域访问时将会保持相同的体验。此功能将与 at.js 1.*x* 第三方和第一方 Cookie 行为联系在一起。

在 at.js 1.*x* 中，第三方 Cookie 存储在 `[CLIENTCODE].tt.omtrdc.net` 域中，第一方 Cookie 存储在 `clientdomain.com` 中。第一个请求返回尝试设置名为 `mboxSession` 和 `mboxPC` 的第三方 Cookie 的 HTTP 响应标头，而会使用额外的参数 (`mboxXDomainCheck=true`) 发送回重定向请求。如果浏览器接受第三方 Cookie，则该重定向请求将包含这些 Cookie，同时会返回选件。此工作流程是可行的，因为 at.js 1.*x* 使用 HTTP GET 方法。

但是，在 at.js 2.x 中，不再使用 HTTP GET，而是使用 HTTP POST。HTTP POST 现在由 at.js 用来将 JSON 有效负荷（而不是键值参数）发送到 [!DNL Target] 边缘服务器。这意味着检查浏览器是否支持第三方 Cookie 的重定向请求现在会中断。这是因为 HTTP GET 请求是幂等事务，而 HTTP POST 是非幂等事务，不能任意重复。

因此，at.js 2.0.0 中不支持第三方 Cookie 和跨域跟踪。

## at.js 1.*x* Cookie 行为 {#at-js-1x-cookie-behavior}

对于 at.js 版本 1.*x*，Cookie 行为取决于它是第一方 Cookie、第三方和第一方 Cookie，还是仅仅为第三方 Cookie。

### 何时使用第一方或第三方 Cookie

您的网站设置决定了您要使用的 Cookie。在尝试了解第一方和第三方 Cookie 时，了解 Target 的工作原理将会很有用。请参阅 ](/help/c-intro/how-target-works.md)Adobe Target 的工作原理[，以了解更多信息。

下面提供了 Cookie 的三个主要用例：

1. 一个域。

   所有测试都将在一个顶级域（`www.domain.com`、`store.domain.com`、`anysub.domain.com` 等）中进行。

   仅使用第一方 Cookie。这是默认方法。

1. 用户跨域，而您想要跟踪和测试用户在这些域里的行为。

   示例：一个用户来到您的网站上购物，但通过 Yahoo 商店结账。此时有三种方法（请与您的客服专员合作以确定最佳方法）：

   * 启用第一方和第三方 Cookie。
   * 仅启用第三方 Cookie（非常少见，但有利于在您的域以外保留 at.js Cookie）。
   * 跨域时只启用第一方 Cookie 并传递 `mboxSession` 参数。

      必须将 `mboxSession` 参数传递到引用 at.js 的登陆页。不能是中间重定向页面。

1. 您在第三方网站上只使用 adbox 或 Flashbox。

   此时有两种方法（请与您的客户服务经理合作以确定最佳方法）：

   * 启用第一方和第三方 Cookie。

      Flashbox 和动态创意需要使用第一方和第三方 Cookie。

   * 仅启用第三方 Cookie。

      这种方法只适用于极少数情况，即使用 AdBox 实施但不进行现场定位的情况。

### 第一方 Cookie 行为

第一方 Cookie 存储在 `clientdomain.com` 中，其中 `clientdomain` 是您的域。

at.js 会生成一个 `mboxSession ID` 并将其存储在 Cookie 中。第一个 响应包含选件和 JavaScript，后者将应用程序生成的 `mboxPC ID` 存储在 Cookie 中。

>[!NOTE]
>
>`AMCV_###@AdobeOrg` 第一方 Cookie 始终使用 [!DNL Experience Cloud Visitor ID] 进行设置。

### 第三方 Cookie 行为

第三方 Cookie 存储在 `clientcode.tt.omtrdc.net` 中，第一方 Cookie 存储在 `clientdomain.com` 中，其中 `clientdomain` 是您的域。

at.js 生成一个 `mboxSession ID`。第一个位置请求会返回尝试设置名为 `mboxSession` 和 `mboxPC` 的第三方 Cookie 的 HTTP 响应标头，并且会使用额外的参数 (`mboxXDomainCheck=true`) 发送回重定向请求。

如果浏览器接受第三方 Cookie，则该重定向请求将包含这些 Cookie，同时会返回选件。

如果浏览器拒绝第三方 Cookie，则该重定向请求将不包含这些 Cookie，并且会在页面上的所有位置显示默认内容。由于没有设置 Cookie，因此每次请求访问页面时都会再次发生上述相同的过程。

### 第三方和第一方 Cookie 行为

第三方 Cookie 存储在 `clientcode.tt.omtrdc.net` 中，第一方 Cookie 存储在 `clientdomain.com` 中，其中 `clientdomain` 是您的域。

at.js 生成一个 `mboxSession ID`。第一个位置请求会返回尝试设置名为 `mboxSession` 和 `mboxPC` 的第三方 Cookie 的 HTTP 响应标头，并且会使用额外的参数 (`mboxXDomainCheck=true`) 发送回重定向请求。

如果浏览器接受第三方 Cookie，则该重定向请求将包含这些 Cookie，同时会返回选件。

某些浏览器会拒绝第三方 Cookie。如果第三方 Cookie 被阻止，则第一方 Cookie 仍将可用。[!DNL Target] 会尝试设置第三方 Cookie，如果失败，则 [!DNL Target] 只能跟踪客户端的特定域。如果第三方 Cookie 被阻止，则无法执行跨域跟踪，除非将 `mboxSession` 附加到跨域的链接中。在这种情况下，系统会设置另一个第一方 Cookie，并将其与先前域的第一方 Cookie 进行同步。

## Cookie 设置

Cookie 有多个默认设置。您可以根据需要更改这些设置，但 Cookie 持续时间除外。更改 Cookie 设置时可咨询您的客服专员。

| 设置 | 信息 |
|--- |--- |
| Cookie 名称 | mbox。 |
| Cookie 域 | 您从中提供内容的的第二级域和顶级域。由于这是来自您的公司域，所以此 Cookie 是第一方 Cookie。示例: `mycompany.com`。 |
| 服务器域 | `clientcode.tt.omtrdc.net`，使用您帐户的客户代码。 |
| Cookie 持续时间 | 访客上次登录两年后的浏览器中仍保留该Cookie。 您不能更改 Cookie 持续时间。 |
| P3P 政策 | 根据大多数浏览器默认设置的要求，使用 P3P 政策发布 Cookie。P3P 政策指示提供 Cookie 的浏览器以及使用该信息的方式。 |

此 Cookie 保存一系列值，以控制您的访客体验营销活动的方式：

| 值 | 定义 |
|--- |--- |
| session ID | 用户会话的唯一 ID。默认情况下，该 ID 持续 30 分钟。 |
| pc ID | 访客浏览器的半永久性 ID。持续 14 天。 |
| check | 用来确定访客是否支持 Cookie 的简单测试值。每次用户请求页面时设置。 |
| disable | 如果访客的加载时间超过了 mbox.js 文件中设置的超时值，则进行设置。默认情况下，该设置持续 1 小时。 |

## 由于 Apple WebKit 跟踪更改而对 Safari 访客的 Target 产生的影响

请牢记以下内容：

### Adobe Target 跟踪如何工作？

| Cookie | 详细信息 |
|--- |--- |
| 第一方域 | 这是 Target 客户的标准实施。“mbox”Cookie 在客户的域中进行设置。 |
| 第三方跟踪 | 第三方跟踪对于 Target 和 Adobe Audience Manager (AAM) 中的广告和定位用例非常重要。第三方跟踪需要跨站点脚本技术。Target 使用在 `clientcode.tt.omtrd.net` 域中设置的两个 Cookie：“mboxSession”和“mboxPC”。 |

### Apple 的方法是什么？

来自 Apple：

“智能防跟踪是一项新的 WebKit 功能，用于通过进一步限制 Cookie 和其他网站数据来减少跨站点跟踪。”

“这就是所谓的跨站点跟踪，`example-tracker.com` 使用的 Cookie 称为第三方 Cookie。在我们的测试中，我们发现一些热门网站具有超过 70 个此类跟踪器，它们都在默默地收集用户相关数据。”

| 方法 | 详细信息 |
|--- |--- |
| 智能防跟踪 | 有关更多信息，请参阅 WebKit 开源 Web 浏览器引擎网站上的[智能防跟踪](https://webkit.org/blog/7675/intelligent-tracking-prevention/)。 |
| Cookie | Safari 如何处理 Cookie：<ul><li>用户直接访问的域中未包含的第三方 Cookie 从不会进行保存。这不是一种新的行为。Safari 中还不支持第三方 Cookie。</li><li>24 小时后会清除在用户直接访问的域中设置的第三方 Cookie。</li><li>如果第一方域被分类为跨站点跟踪用户，则第一方 Cookie 会在 30 天后清除。此问题可能适用于将用户在线发送到不同域的大型公司。Apple 并未明确说明将如何对这些域进行正确分类，或者如何确定域是否已被分类为跨站点跟踪用户。</li></ul> |
| 机器学习以识别跨站点的域 | 来自 Apple：<br>机器学习分类器：机器学习模型用于根据收集的统计数据，对能够跨站点跟踪用户的顶级私人控制域进行分类。在收集的各种统计数据中，根据当前的跟踪实践，以下三个矢量证明具有强烈的分类信号：唯一域数量下的子资源、唯一域数量下的子框架以及重定向到的唯一域数量。所有数据收集和分类均在设备上进行。<br>但是，如果用户与作为顶级域的（通常称为第一方域）example.com 进行互动，则智能防跟踪会将此视为用户对该网站感兴趣的信号，并且会暂时调整其行为，如此时间轴所示：<br>如果用户在过去 24 小时内与 example.com 进行了交互，则当 `example.com` 是第三方时，其 Cookie 将可用。这允许“使用我的 X 帐户登录到 Y”登录方案。<ul><li>作为顶级域访问的域不会受到影响。例如，OKTA 等网站</li><li>在多个唯一域中识别属于当前页面的子域或子框架的域.</li></ul> |

### Adobe 将受到何种影响？

| 受影响的功能 | 详细信息 |
|--- |--- |
| 选择退出支持 | Apple 的 WebKit 跟踪更改会中断选择退出支持。<br>Target 选择退出使用 `clientcode.tt.omtrdc.net` 域中的一个 Cookie。有关更多详细信息，请参阅[隐私](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md)。<br>Target 支持两种选择退出方式：<ul><li>一种是按客户端退出（客户端管理选择退出链接）。</li><li>另一种是通过 Adobe 使用户从所有客户的所有 Target 功能中退出。</li></ul>这两种方法都使用第三方 Cookie。 |
| Target 活动 | 客户可以为他们的 Target 帐户选择[配置文件生命周期](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md)，最长为 90 天。问题在于如果帐户的配置文件生命周期超过 30 天，并且因客户的域已被标记为跨站点跟踪用户而清除了第一方 Cookie，则 Safari 访客的行为将在 Target 的以下区域中受到影响：<br>**Target 报表**：如果 Safari 用户进入活动，30 天后返回活动，然后进行转化，则该用户将会被计为两个访客和一次转化。<br>对于使用 Analytics 作为报表源 (A4T) 的活动，此行为是相同的。<br>**配置文件和活动成员资格**:<ul><li>第一方 Cookie 过期后会擦除配置文件数据。</li><li>第一方 Cookie 过期后会擦除活动成员资格。</li><li> 对于使用第三方 Cookie 实施或第一方和第三方 Cookie 实施的帐户，Target 无法在 Safari 中使用。请注意，这不是一种新的行为。Safari 暂时还不允许使用第三方 Cookie。</li></ul><br>**建议**：如果您担心客户域可能会被标记为跨会话跟踪访客，则最安全的做法是将 Target 中的配置文件生命周期设置为等于或少于 30 天。这可确保在 Safari 和所有其他浏览器中以类似的方式对用户进行跟踪。 |
