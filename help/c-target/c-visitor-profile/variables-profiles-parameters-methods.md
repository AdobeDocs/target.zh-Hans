---
keywords: variables;profiles;parameters;built in profiles;methods;url variables;geo profiles;third party profiles;mbox variables;campaign variables;customer attributes
description: 此页面列出了配置文件脚本中有用的配置文件、变量和参数。
title: 配置文件和变量一览表
feature: null
topic: Standard
uuid: 9286467c-cbb5-42be-99c0-6687ffab0969
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 93%

---


# 配置文件和变量一览表{#profile-and-variable-glossary}

此页面列出了配置文件脚本中有用的配置文件、变量和参数。

## 内置配置文件 {#section_2B694370003C4F8E8E29E0B2F6E52045}

| 配置文件 | 注释 |
|--- |--- |
| user.activeActivities<br>user.activeCampaigns | 返回用户参与的所有营销活动/活动的 ID，即使用户未在当前会话中与营销活动/活动进行交互。 |
| user.pcId |  |
| user.sessionId |  |
| user.categoryAffinity |  |
| user.categoryAffinities | 返回访客填充的一组喜好。 |
| user.isFirstSession |  |
| user.isNewSession |  |
| user.daysSinceLastVisit |  |
| user.browser | 用户代理 |
| user.header | 所有 `user.header` 配置文件均从 mbox 请求标头数据内置 |
| user.header(&#39;x-cluster-client-ip&#39;)<br><br>oruser.header(&#39;x-forwarded-for&#39;) | 访客所在网络连接的公共 IP 地址。<br>您可以通过多种方法获取此地址，例如通过 [whatismyip.com](https://www.whatismyip.com/) / 获取。此 IP 地址不是以 10.、192.168. 或 172. 开头的 NAT 地址（内部地址）。 |
| user.header(&#39;host&#39;) | 网站主机名 |
| user.header(&#39;cookie&#39;) | 访客 Cookie 数据 |
| user.header(&#39;user-agent&#39;) | 访客浏览器用户代理 |
| user.header(&#39;accept-language&#39;) | 访客语言 |
| user.header(&#39;accept-encoding&#39;) | 访客字符编码 |
| user.header(&#39;accept&#39;) | 访客语言和字符编码 |
| user.header(&#39;connection&#39;) | 服务器连接。例如：keep-live |
| user.header(&#39;referrer&#39;) | 访客当前页面的网站 URL。不适用于 Internet Explorer。 |
| user.getLocal(&#39;param_name&#39;,&#39;value&#39;); |  |
| user.setLocal(&#39;param_name&#39;,&#39;value&#39;); |  |
| user.get(&#39;param_name&#39;) |  |
| user.parameter | 从配置文件脚本创建的永久性配置文件属性。还会引用地理位置、访问计数等“系统”配置文件。 |
| profile.get(&#39;param_name&#39;) | 获取用户档案脚本中使用的用户档案参数的正确方法是用户档案.get(&#39;param_name&#39;)方法。 |
| profile.param(&#39;param_name&#39;); |  |
| profile.parameter(&#39;parameter_name&#39;); | 因带有 profile.   前缀而使其具有持久性的 mbox 参数。 |
| profile.browserTime | 访客的本地浏览器时间。对于系统时间，在配置文件脚本中创建新的日期对象 |
| profile.averageDaysBetweenVisits |  |
| profile.sessionCount |  |
| parameter= | 通过 mbox 传递的其他值的统称，通常为名称/值对。不具有持久性，除非使用 `profile.parameter` 或 `user.parameter` 设定了持久性。 |

## URL 变量 {#section_8F25958273164EBAA6DC659302993FD3}

| `landing` | `referrer` | `page` |
|---|---|---|
| `landing.url` | `referrer.url` | `page.url` |
| `landing.domain` | `referrer.domain` | `page.domain` |
| `landing.protocol` | `referrer.protocol` | `page.protocol` |
| `landing.param` | `referrer.param` | `page.param` |
| `landing.query` | `referrer.query` | `page.query` |

## 地域和移动设备运营商配置文件 {#section_08441DA42E7346918FBB345818854997}

* `profile.geolocation.country`
* `profile.geolocation.state`
* `profile.geolocation.city`
* `profile.geolocation.zip`
* `profile.geolocation.dma`
* `profile.geolocation.domainName`
* `profile.geolocation.ispName`
* `profile.geolocation.connectionSpeed`
* `profile.geolocation.mobileCarrier`
* `profile.geolocation.latitude`
* `profile.geolocation.longitude`

## Mbox 变量 {#section_C42F0D33BD8044BE812FA0B7905CC0ED}

| 变量 | 注释 |
|--- |--- |
| `mbox.name` |  |
| mbox.param(&#39;param_name&#39;) |  |
| 与每个请求一起自动传递的参数：<ul><li>mbox.param(&#39;browserHeight&#39;)</li><li>mbox.param(&#39;browserTimeOffset&#39;)</li><li>mbox.param(&#39;browserWidth&#39;)</li><li>mbox.param(&#39;colorDepth&#39;)</li><li>mbox.param(&#39;mboxXDomain&#39;)</li><li>mbox.param(&#39;mboxTime&#39;)</li><li>mbox.param(&#39;screenHeight&#39;)</li><li>mbox.param(&#39;screenWidth&#39;)</li></ul> |
| 与订单 mbox 一起传递的参数：<ul><li>mbox.param(&#39;orderId&#39;)</li><li>mbox.param(&#39;orderTotal&#39;)</li><li>mbox.param(&#39;productPurchasedId&#39;)</li></ul> |
| mbox3rdPartyId | 用于将客户 ID 同步到 Target mboxPCID 的 mbox 参数。客户 ID 是指贵公司用于跟踪访客的 ID，例如 CRM ID、会员 ID 或诸如此类的 ID。此 ID 随后可用于通过配置文件 API 和[客户属性](/help/c-target/c-visitor-profile/working-with-customer-attributes.md)。 |
| mboxPageValue | 在每个 mbox 调用中，都会为页面分配值。 |
| mboxDebug | 仅用于调试信息。已添加到 mbox.js 所查找的页面 URL 中。 |
| mboxOverride.browserIp | 设置与实际位置不同的地理位置，以便测试在其他位置时的情况。<br>**注意：**mboxOverride 参数仅应在测试活动时使用，而不应在生产中使用。使用[Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md)(A4T) 时，使用任何 mboxOverride 参数都可能导致报表不一致。您应使用[活动 QA 模式](/help/c-activities/c-activity-qa/activity-qa.md)，以确保活动在推送到实时环境之前可以按预期方式运行。 |

## 客户属性 {#section_62B4821EB6564FF4A14159A837AD4EDB}

可以在配置文件脚本中引用客户属性，格式如下：`crs.get('<Datasource Name>.<Attribute name>')`。

这些属性还可用作配置文件脚本中的令牌，以及直接用作选件中的令牌，而无需首先设置配置文件脚本。令牌应使用以下格式：`${crs.datasourceName.attributeName}`。请注意，应从任 `datasourceName` 何API调用中去除中的空格。
