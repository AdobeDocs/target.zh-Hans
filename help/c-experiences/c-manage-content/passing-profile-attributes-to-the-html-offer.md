---
description: 您可以直接在HTML或JSON选件中显示配置文件值和活动信息。
keywords: 动态数据；资源；数据；优惠；个性化优惠；个人优惠；令牌替换
seo-description: 您可以直接在HTML或JSON选件中显示配置文件值和活动信息。
seo-title: 将动态数据传递给选件
solution: Target
title: 将动态数据传递给选件
topic: Premium
uuid: 1910a7f5-e4bd-413a-9875-e0b005407f50
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 将动态数据传递给选件{#pass-dynamic-data-into-offers}

您可以动态显示存储在Target配置文件中的访客信息。同样，活动信息(例如活动的名称或体验的名称)也可用于创建单一选件，根据访客的兴趣、过去的行为和整体档案动态返回个性化内容。

**商业案例**

* 将折扣优惠推广到“升级”或“补充”上次购买的产品。除了为目录中的每个项目创建单独的选件，您还可以使用动态文本创建选件，该文本从配置文件中读取“最后购买的产品”并显示选件中的链接。
* 一个访客通过 `keyword=world``cup` 访问您的登陆页。您在选件中显示词语 *World cup*。
* 使用信息(如(1)将最后一个项目添加到访客的购物车(Nike Air Max1000s))、(2)访客的颜色首选项(黑色)和(3)访客喜爱的非鞋类类别(挂钩)个性化推荐标签。示例：“用这些酷炫的&#39;黑色&#39;挂钩，对您的Nike Air Max1000s进行装饰！”


**技术优势**

因为用户特定的首选项、行为、状态等。可存储在用户个人资料中，您可以在下次访问时重复此消息。动态选件允许您在一个活动中设置一个单独的选件，该选件可显示面向所有访客的个性化消息。当访客意图发生变化时，网站内容会自动反映这些更改。

**示例**

* `mboxCreate("landingpage"`, `"profile.keyword=World Cup");`

* HTML 选件代码：`Get your ${profile.keyword} information here!`
* 用户会看到：Get your World Cup information here!

下面的值可以作为“替换的令牌”：

| 值 | 示例 |
|--- |--- |
| mbox 内配置文件参数 | `${profile.age}` |
| 脚本配置文件参数 | `${user.lifetimeSpend}` |
| Mbox 参数 | `${mbox.favoriteColor}` |
| 营销活动信息 | `${campaign.name}`、`${campaign.recipe.name}`、`${campaign.id}`、`${campaign.recipe.id}` 和 `${campaign.recipe.trafficType}` |
| 唯一的访客 ID | `${user.pcId}` |
| 唯一的会话 ID | `${user.sessionId}` |
| 访客的第一次会话（true 或 false） | `${user.isFirstSession}` |
| 过去的行为 | `{$user.endpoint.lastPurchasedEntity}`, `{$user.endpoint.lastViewedEntity}`, `{$user.endpoint.mostViewedEntity}`, `{$user.endpoint.categoryAffinity}` |

在控制台中记录信息以进行调试，如 `${campaign.name}``${campaign.id}``${campaign.recipe.name}``${campaign.recipe.id}``${offer.name}``${offer.id}`、 `${campaign.name}`

有关Recommendations设计，请参阅设计概述中 [的其他示例](/help/c-recommendations/c-design-overview/design-overview.md)。

**实施**

对于传递到mbox中的配置文件参数，请使用语法： `${profile.parameter}` 对于在配置文件脚本中创建的配置文件参数，请使用语法：

`${user.parameter}`

在Recommendations设计中使用动态属性时，您必须在美元符号(&#39;$&#39;)之前插入一个反斜杠(&#39;\&#39;)，以便动态值正确呈现： `\${user.endpoint.lastViewedEntity}`

这些变量可以被服务器端的值所替换，因此不需要引用或其他 JavaScript 也能正确显示。

也可以指定默认值，作为您想要在选件上显示的值。语法如下：

`${user.testAttribute default="All Items!"}`

当 `testAttribute` 不存在或为空时，将输出“All Items!”。如果一个空属性值是有效的，并且您想要将它写出而不是显示默认值，则可以使用：

`${user.testAttribute default="All Items!" show_blank="true"}`

您还可以对显示的某些值进行转义或不转义。例如，如果某个值有一个单引号，那么您可以对该值进行转义，使其不会在页面上打断 JavaScript。（选件采用 JavaScript 编写，因此单撇号容易与引号混淆。）例如：

`${user.encodedValue encode="unescape"}`

`${user.unencodedValue encode="escape"}`