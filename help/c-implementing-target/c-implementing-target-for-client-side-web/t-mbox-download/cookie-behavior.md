---
keywords: 概述和参考；Webkit;Cookie；第一方；第三方；第一方；第三方
description: 了解 [!DNL Target] Cookie行为（第一方Cookie、第三方与第一方Cookie，或仅第三方Cookie）。
title: 在哪里可以找到有关 [!DNL Target] Cookie的信息？
feature: at.js
role: Developer
exl-id: 1c4e5b0b-8ae4-4526-aea0-318a33f4d247
source-git-commit: e773db20ac593108aa3e54aae1bcb2c0f713e387
workflow-type: tm+mt
source-wordcount: '1542'
ht-degree: 58%

---

# Target Cookie

Cookie 行为取决于它是第一方 Cookie、第三方和第一方 Cookie，还是仅仅为第三方 Cookie。

>[!NOTE]
>
>本主题包含有关 `mboxSession` 和 `mboxPC` 的信息。实施最佳实践建议您不要使用Cookie数据链接或存储敏感信息：`mboxSession`或`mboxPC`。

另请参阅[删除Target Cookie](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cookie-deleting.md)。

## 何时使用第一方或第三方 Cookie {#section_F71B29420C004A7FA3B1921E619B326E}

您的网站设置决定了您要使用的 Cookie。了解[!DNL Target]在尝试了解第一方和第三方Cookie时的工作方式会很有帮助。 有关更多信息，请参阅[How [!DNL Adobe Target] Works](/help/c-intro/how-target-works.md#concept_459AB4DEE7364A9290C2FD405DC29584) 。

下面提供了 Cookie 的三个主要用例：

1. 一个域。

   所有测试都在一个顶级域（`www.domain.com`、`store.domain.com`、`anysub.domain.com`等）中进行。

   方法：仅使用第一方Cookie（默认）。

1. 用户跨域，而您想要跟踪和测试用户在这些域里的行为。

   示例：一个用户来到您的网站上购物，但通过 Yahoo 商店结账。此时有三种方法（请与您的客服专员合作以确定最佳方法）：

   * 启用第一方和第三方 Cookie。
   * 仅启用第三方Cookie（很少使用，但有利于将mbox Cookie保留在域外）。
   * 跨域时只启用第一方 Cookie 并传递 `mboxSession` 参数。

      必须将`mboxSession`参数传递到登陆页面，并从JavaScript库(Adobe Experience Platform Web SDK或at.js)中引用该参数。 不能是中间重定向页面。

1. 您在第三方网站上只使用 adbox 或 Flashbox。

   两种方法（请与您的客户代表合作以确定最佳方法）：

   * 启用第一方和第三方 Cookie。

      Flashbox 和动态创意需要使用第一方和第三方 Cookie。

   * 仅启用第三方 Cookie。

      这种方法只适用于极少数情况，即使用 AdBox 实施但不进行现场定位的情况。

## 第一方 Cookie 行为 {#section_CE6313D979EA4D0897D2F661E7A8AFA7}

第一方 Cookie 存储在 [!DNL clientdomain.com] 中，其中 `clientdomain` 是您的域。

JavaScript库会生成一个`mboxSession ID`并将其存储在[!DNL Target] Cookie中。 第一个mbox响应包含选件，而JavaScript则将应用程序生成的`mboxPC ID`存储在mbox Cookie中。

>[!NOTE]
>
>[!DNL AMCV_###@AdobeOrg] 第一方 Cookie 始终使用 [!DNL Experience Cloud Visitor ID] 进行设置。

## 第三方 Cookie 行为 {#section_4C3A83990BF8415BB1806602D84AED48}

第三方 Cookie 存储在 [!DNL clientcode.tt.omtrdc.net] 中，第一方 Cookie 存储在 [!DNL clientdomain.com] 中，其中 `clientdomain` 是您的域。

JavaScript库会生成一个`mboxSession ID`。 第一个位置请求会返回尝试设置名为 `mboxSession` 和 `mboxPC` 的第三方 Cookie 的 HTTP 响应标头，并且会使用额外的参数 (`mboxXDomainCheck=true`) 发送回重定向请求。

如果浏览器接受第三方 Cookie，则该重定向请求将包含这些 Cookie，同时会返回选件。

如果浏览器拒绝第三方 Cookie，则该重定向请求将不包含这些 Cookie，并且会在页面上的所有位置显示默认内容。由于没有设置 Cookie，因此每次请求访问页面时都会再次发生上述相同的过程。

>[!NOTE]
>
>如果未阻止第三方 Cookie，则会设置 [!DNL demdex.net] Cookie。

## 第三方和第一方 Cookie 行为 {#section_F0C9AD8BFDF8457A999C4A07A0F7A981}

第三方 Cookie 存储在 [!DNL clientcode.tt.omtrdc.net] 中，第一方 Cookie 存储在 [!DNL clientdomain.com] 中，其中 `clientdomain` 是您的域。

JavaScript库会生成一个`mboxSession ID`。 第一个位置请求会返回尝试设置名为 `mboxSession` 和 `mboxPC` 的第三方 Cookie 的 HTTP 响应标头，并且会使用额外的参数 (`mboxXDomainCheck=true`) 发送回重定向请求。

如果浏览器接受第三方 Cookie，则该重定向请求将包含这些 Cookie，同时会返回选件。

某些浏览器会拒绝第三方 Cookie。如果第三方 Cookie 被阻止，则第一方 Cookie 仍将可用。[!DNL Target] 会尝试设置第三方 Cookie，如果失败，则 [!DNL Target] 只能跟踪客户端的特定域。如果第三方Cookie被阻止，则无法进行跨域跟踪，除非将`mboxSession`附加到跨域的链接中。 在这种情况下，系统会设置另一个第一方 Cookie，并将其与先前域的第一方 Cookie 进行同步。

## Cookie 设置 {#section_B498B8D1A34A444BBF84CC720EE9D87F}

Cookie 有多个默认设置。您可以根据需要更改这些设置，但Cookie持续时间除外。 更改 Cookie 设置时可咨询您的客服专员。

| 设置 | 信息 |
|--- |--- |
| Cookie 名称 | mbox。 |
| Cookie 域 | 您从中提供内容的的第二级域和顶级域。由于这是来自您公司的域，因此Cookie是第一方Cookie。<br>示例: `mycompany.com`. |
| 服务器域 | `clientcode.tt.omtrdc.net`，使用您帐户的客户代码。 |
| Cookie 持续时间 | 自上次登录后两周，该Cookie将在访客的浏览器上保留。 您不能更改 Cookie 持续时间。 |
| P3P 政策 | 根据大多数浏览器默认设置的要求，使用 P3P 政策发布 Cookie。P3P策略向提供Cookie的浏览器指示信息的使用方式。 |

Cookie会保留各种值以管理访客体验营销活动的方式：

| 值 | 定义 |
|--- |--- |
| session ID | 用户会话的唯一 ID。默认情况下，此ID持续30分钟。 |
| pc ID | 访客浏览器的半永久性 ID。持续 14 天。 |
| check | 用来确定访客是否支持 Cookie 的简单测试值。每次用户请求页面时设置。 |
| disable | 如果访客的加载时间超过了JavaScript库文件中配置的超时值，则进行设置。 默认情况下，此值持续1小时。 |

## 由于Apple WebKit跟踪更改而对Safari访客的[!DNL Target]产生的影响 {#section_2A2E5730ED7D4A0985C904AFEA310AAE}

**跟踪如 [!DNL Adobe Target] 何工作？**

| Cookie | 详细信息 |
|--- |--- |
| 第一方域 | [!DNL Target]客户的标准实施。 “mbox”Cookie 在客户的域中进行设置。 |
| 第三方跟踪 | 第三方跟踪对于[!DNL Target]和[!DNL Adobe Audience Manager](AAM)中的广告和定位用例非常重要。 第三方跟踪需要跨站点脚本技术。[!DNL Target] 使用在 `clientcode.tt.omtrd.net` 域中设置的两个 Cookie：“mboxSession”和“mboxPC”。 |
**Apple 的方法是什么？**

来自 Apple：

“智能防跟踪是一项新的 WebKit 功能，用于通过进一步限制 Cookie 和其他网站数据来减少跨站点跟踪。”

“这就是所谓的跨站点跟踪，`example-tracker.com` 使用的 Cookie 称为第三方 Cookie。在我们的测试中，我们发现一些热门网站具有超过 70 个此类跟踪器，它们都在默默地收集用户相关数据。”

| 方法 | 详细信息 |
|--- |--- |
| 智能防跟踪 | 有关更多信息，请参阅 WebKit 开源 Web 浏览器引擎网站上的[智能防跟踪](https://webkit.org/blog/7675/intelligent-tracking-prevention/)。 |
| Cookie | Safari 如何处理 Cookie：<ul><li>用户直接访问的域中未包含的第三方 Cookie 从不会进行保存。这不是一种新的行为。Safari 中还不支持第三方 Cookie。</li><li>24 小时后会清除在用户直接访问的域中设置的第三方 Cookie。</li><li>如果第一方域被分类为跨站点跟踪用户，则第一方 Cookie 会在 30 天后清除。此问题可能适用于将用户在线发送到不同域的大型公司。Apple尚未明确说明这些域的具体分类方式，或域如何确定它们是否已被分类为跨站点跟踪用户。</li></ul> |
| 机器学习以识别跨站点的域 | 来自 Apple：<br>机器学习分类器：机器学习模型用于根据收集的统计数据对哪些顶级私人控制域可以跨站点跟踪用户进行分类。在收集的各种统计数据中，根据当前的跟踪实践，以下三个矢量证明具有强烈的分类信号：唯一域数量下的子资源、唯一域数量下的子框架以及重定向到的唯一域数量。所有数据收集和分类均在设备上进行。<br>但是，如果用户与作为 `example.com` 顶级域（通常称为第一方域）进行交互，则智能防跟踪会将其视为用户对网站感兴趣的信号，并暂时调整其行为，如此时间轴所示：<br>如果用户在过去24小时内 `example.com` 进行了交互，则当是第三方时，其 `example.com` Cookie将可用。此做法允许“使用我的X帐户在Y上登录”登录方案。<ul><li>作为顶级域访问的域不会受到影响。 例如，OKTA 等网站</li><li>在多个唯一域中识别属于当前页面的子域或子框架的域。</li></ul> |

**Adobe受到什么影响？**

| 受影响的功能 | 详细信息 |
|--- |--- |
| 选择退出支持 | Apple 的 WebKit 跟踪更改会中断选择退出支持。<br>[!DNL Target] 选择退出使用 `clientcode.tt.omtrdc.net` 域中的一个 Cookie。有关更多详细信息，请参阅[隐私](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md)。<br>[!DNL Target] 支持两种选择退出方式：<ul><li>一种是按客户端退出（客户端管理选择退出链接）。</li><li>一个通过[!DNL Adobe]，用于使用户退出所有客户的所有[!DNL Target]功能。</li></ul>这两种方法都使用第三方 Cookie。 |
| [!DNL Target] 活动 | 客户可以为其[!DNL Target]帐户（最长90天）选择其[配置文件生命周期长度](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md)。 问题在于如果帐户的配置文件生命周期超过30天，并且因客户的域已被标记为跨站点跟踪用户而清除了第一方Cookie，则Safari访客的行为会在[!DNL Target]的以下区域中受到影响：<br>**[!DNL Target]报表&#x200B;**:如果Safari用户进入活动，30天后返回，然后进行转化，则该用户将计为两个访客和一次转化。<br>[!DNL Analytics]对于使用 作为报表源 (A4T) 的活动，此行为是相同的。<br>**&#x200B;配置文件和活动成员资格&#x200B;**:<ul><li>第一方 Cookie 过期后会擦除配置文件数据。</li><li>第一方 Cookie 过期后会擦除活动成员资格。</li><li> [!DNL Target]对于使用第三方 Cookie 实施或第一方和第三方 Cookie 实施的帐户， 无法在 Safari 中使用。这不是一种新的行为。Safari有一段时间不允许使用第三方Cookie。</li></ul><br>**建议**:如果担心客户域可能会被标记为跨会话跟踪访客的一个域，则最安全的做法是将中的配置文件生命周期设置为等于或少于30天 [!DNL Target]。此限制可确保在Safari和所有其他浏览器中以类似的方式跟踪用户。 |
