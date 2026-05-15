---
keywords: 变量;轮廓;参数;内置轮廓;方法;URL 变量;地域轮廓;第三方轮廓;mbox 变量;营销活动变量;客户属性
description: 查看在Adobe Target中的配置文件脚本中有用的各种配置文件、变量和参数的列表。
title: ' [!DNL Target]中使用了哪些配置文件、变量和参数？'
feature: Audiences
exl-id: 96ef9a56-fe76-428e-a164-c01829fdf45d
TQID: https://experienceleague.adobe.com/YMF4eXnu758kloK--c2mBzP-rwLBNRO2jLoV6s-P5JM
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eebid: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2: id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 699
ht-degree: 59%

---

# 轮廓和变量一览表

此页面列出了轮廓脚本中有用的轮廓、变量和参数。

## 内置配置文件 {#section_2B694370003C4F8E8E29E0B2F6E52045}

| 轮廓 | 注释 |
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
| user.browserType | 返回浏览器类型，例如safari、chrome等。 |
| user.header | 所有 `user.header` 轮廓均从 mbox 请求标头数据内置 |
| user.header(&#39;x-forwarded-for&#39;) | 访客所在网络连接的公共 IP 地址。<br>您可以通过多种方式获取此地址，例如[whatismyip.com](https://www.whatismyip.com/)。 IP地址不是NAT地址（内部地址），从10.、192.168.或172.<br>注意：已弃用user.header(&#39;x-cluster-client-ip&#39;)。 |
| user.header(&#39;host&#39;) | 网站主机名 |
| user.header(&#39;cookie&#39;) | 访客 Cookie 数据 |
| user.header(&#39;user-agent&#39;) | 访客浏览器用户代理 |
| user.header(&#39;accept-language&#39;) | 访客语言 |
| user.header(&#39;accept-encoding&#39;) | 访客字符编码 |
| user.header(&#39;accept&#39;) | 访客语言和字符编码 |
| user.header(&#39;connection&#39;) | 服务器连接。 例如：keep-live |
| user.header(&#39;referrer&#39;) | 访客当前页面的网站 URL。 不适用于 Internet Explorer。 |
| user.getLocal(&#39;param_name&#39;)； | 检索您使用`user.setLocal`设置的值。 |
| user.setLocal(&#39;param_name&#39;，&#39;value&#39;) | 在配置文件脚本中创建保留的配置文件值。 这些值就像配置文件脚本一样持续存在，但您只能在设置它的脚本中访问它。 |
| user.get(&#39;param_name&#39;) |  |
| user.parameter | 从配置文件脚本创建的永久性配置文件属性。 还引用“系统”配置文件，如地理位置、访问计数等。 |
| profile.get(&#39;param_name&#39;) | 获取要在配置文件脚本中使用的配置文件参数的正确方法是profile.get(&#39;param_name&#39;)方法。 |
| profile.param(&#39;param_name&#39;); |  |
| profile.parameter(&#39;parameter_name&#39;); | 因带有 profile.  前缀而使其具有持久性的 mbox 参数。 |
| profile.browserTime | 访客的本地浏览器时间。 对于系统时间，在配置文件脚本中创建新的日期对象 |
| profile.averageDaysBetweenVisits |  |
| profile.sessionCount |  |
| profile.mobile.isTablet | 访客设备是平板电脑。<P>**注意**：此配置文件取代了已弃用的旧版浏览器iPad受众类别。 有关详细信息，请参阅[浏览器](/help/main/c-target/c-audiences/c-target-rules/browser.md#profile-scripts)。 |
| profile.mobile.isMobilePhone | 访客设备是移动电话。<P>**注意**：此配置文件取代了已弃用的旧版浏览器iPhone受众类别。 有关详细信息，请参阅[浏览器](/help/main/c-target/c-audiences/c-target-rules/browser.md#profile-scripts)。 |
| parameter= | 通过 mbox 传递的其他值的统称，通常为名称/值对。 不具有持久性，除非使用 `profile.parameter` 或 `user.parameter` 设定了持久性。 |

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
| 与每个请求一起自动传递的参数：<ul><li>mbox.param(&#39;browserHeight&#39;)</li><li>mbox.param(&#39;browserTimeOffset&#39;)</li><li>mbox.param(&#39;browserWidth&#39;)</li><li>mbox.param(&#39;colorDepth&#39;)</li><li>mbox.param(&#39;mboxXDomain&#39;)</li><li>mbox.param(&#39;mboxTime&#39;)</li><li>mbox.param(&#39;screenHeight&#39;)</li><li>mbox.param(&#39;screenWidth&#39;)</li></ul> |  |
| 与订单 mbox 一起传递的参数：<ul><li>mbox.param(&#39;orderId&#39;)</li><li>mbox.param(&#39;orderTotal&#39;)</li><li>mbox.param(&#39;productPurchasedId&#39;)</li></ul> |  |
| mbox3rdPartyId | 用于将客户 ID 同步到 Target mboxPCID 的 mbox 参数。 客户 ID 是指贵公司用于跟踪访客的 ID，例如 CRM ID、会员 ID 或诸如此类的 ID。 然后，可以使用此ID通过配置文件API和[客户属性](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/customer-attributes.html){target=_blank}添加信息。 |
| mboxPageValue | 在每个 mbox 调用中，都会为页面分配值。 |
| mboxDebug | 仅用于调试信息。 已添加到at.js所查找的页面URL中。 |
| mboxOverride.browserIp | 设置与实际位置不同的地理位置，以便测试其他位置中某些内容的显示方式。<br>**注意：**&#x200B;只有在测试活动而不是在生产环境中时，才应使用mboxOverride参数。 使用 [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) 时，使用任何 mboxOverride 参数都可能导致报表不一致。 您应使用[活动 QA 模式](/help/main/c-activities/c-activity-qa/activity-qa.md)，以确保活动在推送到实时环境之前可以按预期方式运行。 |

## 客户属性 {#section_62B4821EB6564FF4A14159A837AD4EDB}

可以在轮廓脚本中引用客户属性，格式如下：`crs.get('<Datasource Name>.<Attribute name>')`。

这些属性还可用作轮廓脚本中的令牌，以及直接用作产品建议中的令牌，而无需首先设置轮廓脚本。 令牌应使用以下格式： `${crs.datasourceName.attributeName}`。 请注意，应从任何API调用中移除`datasourceName`中的空格。
