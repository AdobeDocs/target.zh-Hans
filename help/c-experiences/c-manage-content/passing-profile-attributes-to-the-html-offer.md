---
keywords: dynamic data;assets;data;offers;personalized offers;personal offers;token replace
description: 您可以在一个 HTML 或 JSON 选件中直接显示配置文件值和活动信息。
title: 将动态数据传递给选件
feature: offers
uuid: 1910a7f5-e4bd-413a-9875-e0b005407f50
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 100%

---


# 将动态数据传递给选件{#pass-dynamic-data-into-offers}

您可以动态显示存储在 Target 配置文件中的访客信息。同样，还可以使用活动信息（例如活动名称或体验名称）来创建单个选件，以根据访客兴趣、过去的行为和整个配置文件动态地返回个性化内容。

**商业案例**

* 促销折扣选件，以“填充”或“补充”上次购买的产品。除了为目录中的每个项目创建单独的选件之外，您可以创建一个包含动态文本的选件，其会从配置文件中读取“上次购买的产品”并在选件中显示链接。
* 一个访客通过 `keyword=world``cup` 访问您的登陆页。您在选件中显示词语 *World cup*。
* 使用以下信息来个性化推荐标签，例如 (1) 添加到访客购物车的最后一个项目 (Nike Air Max 1000s)、(2) 访客的颜色偏好（黑色），以及 (3) 访客最喜爱的非鞋类产品（连帽衫）。示例：“用这些炫酷的‘黑色’‘连帽衫’来搭配您的‘Nike Air Max 1000s’！”


**技术优势**

由于用户特定的偏好、行为、状态等可以存储在用户的配置文件中，因此您可以在他或她的下次访问时重复显示此消息。动态选件允许您在活动中设置单个选件以向所有访客显示个性化消息，因此支持更大的范围。随着访客意向的改变，您的网站内容也将自动反映这些变化。

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
| 过去的行为 | `${user.endpoint.lastPurchasedEntity}`、`${user.endpoint.lastViewedEntity}`、`${user.endpoint.mostViewedEntity}`、`${user.endpoint.categoryAffinity}` |

在控制台中记录信息以进行调试，例如 `${campaign.name}`、`${campaign.id}`、`${campaign.recipe.name}`、`${campaign.recipe.id}`、`${offer.name}`、`${offer.id}`、`${campaign.name}`

有关“推荐”设计的信息，请参阅[设计概述](/help/c-recommendations/c-design-overview/design-overview.md)中的其他示例。

**实施**

要了解传递到 mbox 的配置文件参数，请使用语法：`${profile.parameter}`。要了解在配置文件脚本中创建的配置文件参数，请使用语法：

`${user.parameter}`

在“推荐”设计中使用动态属性时，必须在美元符号（“$”）之前插入反斜杠（“\”），以便正确呈现动态值：`\${user.endpoint.lastViewedEntity}`

这些变量可以被服务器端的值所替换，因此不需要引用或其他 JavaScript 也能正确显示。

也可以指定默认值，作为您想要在选件上显示的值。语法如下：

`${user.testAttribute default="All Items!"}`

当 `testAttribute` 不存在或为空时，将输出“All Items!”。如果一个空属性值是有效的，并且您想要将它写出而不是显示默认值，则可以使用：

`${user.testAttribute default="All Items!" show_blank="true"}`

您还可以对显示的某些值进行转义或不转义。例如，如果某个值有一个单引号，那么您可以对该值进行转义，使其不会在页面上打断 JavaScript。（选件采用 JavaScript 编写，因此单撇号容易与引号混淆。）例如：

`${user.encodedValue encode="unescape"}`

`${user.unencodedValue encode="escape"}`