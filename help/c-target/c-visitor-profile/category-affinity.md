---
keywords: affinity;category affinity
description: Adobe Target 中的类别亲和度功能会自动捕捉用户访问的类别，然后计算用户对该类别的喜爱程度，从而可以对用户进行定位和细分。这有助于确保内容会被定位到最有可能对该信息做出回应的访客。
title: 在 Adobe Target 中使用类别亲和度
feature: visitor profiles
topic: Standard
uuid: b81d9c91-a222-4768-9ac8-359f9ab9ca2d
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '830'
ht-degree: 98%

---


# 类别亲和度{#category-affinity}

类别亲和度功能会自动捕捉用户访问的类别，然后计算用户对该类别的喜爱程度，从而可以对用户进行定位和细分。这有助于确保内容会被定位到最有可能对该信息做出回应的访客。

## 将类别亲和度信息传递到 Target {#section_B0C8E46EEBAC4549AD90352A47787D04}

不论用户何时访问您的网站，都会将特定于访客的配置文件参数记录到 [!DNL Target] 数据库中。该数据将与用户的 Cookie 绑定。一个特别有用的参数是 `user.categoryId`，它是在产品页面上分配的 mbox 参数。访客持续浏览时，或离开后返回进行另一个会话时，都可以记录特定用户查看的产品类别。您还可以将类别信息作为任何 mbox（包括嵌套 mbox）中的 mbox 参数 `user.categoryId` 或作为 URL 参数 `user.categoryId` 进行传递，或者通过全局 mbox 在 Target 页面参数中进行传递，从而记录类别信息。有关更多详细信息，请咨询您的帐户代表。

要将一个项目包含在多个类别中，请使用逗号分隔类别。例如：

* `user.categoryId=clothing,shoes,nike,running,nike clothing,nike shoes,nike running shoes`

根据对您的产品类别进行访问的频率和近期情况，会记录用户所具有的类别亲和度（如果有）。类别亲和度可用于为活动定位访客群体。

您可以在配置文件脚本中使用 `user.categoryAffinities[]` 以返回访客填充的一组喜好。

>[!IMPORTANT]
>
>Adobe Target 类别亲和度算法所使用的 `user.categoryId` 属性不同于 Adobe Target“推荐”产品和内容推荐所使用的 `entity.categoryId` 属性。要跟踪用户喜爱的类别，需要使用 `user.categoryId`。要根据当前页面或当前项目所属的类别进行推荐，需要使用 `entity.categoryId`。如果要同时使用这两项功能，请将这两个值都传递给 Adobe Target。

## 类别亲和度的商业案例 {#section_D6FF913E88E6486B8FBCE117CA8B253B}

访客在某次会话中的活动（例如访客在此次会话中查看次数最多的类别）可在后续访问中用来进行定位。系统会捕捉访客在一次会话中查看的各类别页面，并根据新近度和频率模型来计算出访客“最喜爱”的类别。之后，访客每次返回到主页时，便可以对主页图像区域进行定位，使其显示与该访客最喜爱的类别有关的内容。

## 使用类别亲和度的示例 {#section_A4AC0CA550924CB4875F4F4047554C18}

假设您在线销售乐器，并希望将低音吉他促销定位到过去对吉他感兴趣的访客。使用类别亲和度，您可以创建仅向具有此类别亲和度的访客显示的选件。

## 类别亲和度算法 {#section_8B86C7FF50294208866ABF16F07D5EB9}

类别亲和度算法采用如下计算方式：

* 第一次查看的类别获得 10 分
* 第一次查看后所点击的每个类别将各获得 5 分
* 点击新类别后，之前点击的所有类别都将减去 1 分
* 如果已点击（已显示）某个类别，则再次点击该类别时，所有其他类别都将不会减去 1 分
* 如果点击了第六个新类别，则将从计算中删除前五个类别中得分最低的类别
* 会话结束时将所有值除以 2

### 示例：类别亲和度算法

例如，依次查看会话中 `mens-clothing` 类别、`accessories`、`jewelry`，然后再次查看 `accessories`，这会产生以下亲和度：

* `accessories`：9 (+5 – 1 + 5)

* `mens-clothing`：8 (+10 – 1 – 1)

* `jewelry`：5 (+5)

当会话结束，用户稍后返回到站点时，分数将会减半：

* `accessories`：4.5 (9/2)

* `mens-clothing`：4 (8/2)

* `jewelry`：2.5 (5/2)

假设用户随后按顺序查看 `jewelry`、`accessories`、`beauty`、`shoes` 和 `womens-clothing`：

* `accessories`：6.5 (4.5 + 5 – 1 – 1 - 1)

* `womens-clothing`：5 (+5)

* `jewelry`：4.5 (2.5 + 5 – 1 – 1 - 1)

* `shoes`：4 (+5 – 1)

* `beauty`：3 (+5 – 1 - 1)

* 最后一次点击 `womens-clothing` 后，`mens-clothing` 将作为得分最低的类别而遭到删除，其得分为 1 (4 – 1 – 1 - 1)

当会话结束，用户稍后返回到站点时，分数将会减半：

* `accessories`：3.3 (6.5/2)

* `womens-clothing`：2.5 (5/2)

* `jewelry`：2.3 (4.5/2)

* `shoes`：2 (4/2)

* `beauty`：1.5 (3/2)

## 使用类别亲和度进行定位 {#concept_5750C9E6C97A40F8B062A5C16F2B5FFC}

此信息可帮助您在活动中使用[!UICONTROL 类别亲和度]进行定位。

本节包含以下信息：

* [创建要使用类别亲和度的受众](../../c-target/c-visitor-profile/category-affinity.md#section_A27C600BBA664FE7A74F8FE076B78F40)
* [在活动中使用类别亲和度受众](../../c-target/c-visitor-profile/category-affinity.md#section_91526B942D1B4AEBB8FCDF4EBFF931CF)

## 创建要使用类别亲和度的受众 {#section_A27C600BBA664FE7A74F8FE076B78F40}

1. 从&#x200B;**[!UICONTROL 受众]**&#x200B;列表中，单击 **[!UICONTROL + 创建受众]**。

   或

   在受众列表中，将鼠标悬停在所需受众上，然后单击复制图标，以复制现有受众。然后，您可以对受众进行编辑以创建一个类似的受众。

1. 键入描述性受众名称。
1. 单击 **[!UICONTROL + 添加规则]** > **[!UICONTROL 访客配置文件]**。
1. 从&#x200B;**[!UICONTROL 访客配置文件]**&#x200B;下拉列表中，选择&#x200B;**[!UICONTROL 类别亲和度]**。

   ![“访客配置文件”>“类别亲和度”](assets/affinity.png)

1. 选择所需类别：

   ![“类别亲和度”>“类别”](/help/c-target/c-visitor-profile/assets/affinity-category.png)

   类别包括：

   * 最喜爱类别
   * 第一类别
   * 第二类别
   * 第三类别
   * 第四类别
   * 第五类别

   “Favorite类别”和“First类别”选项是相等的。

1. 选择计算器：

   * 包含（不区分大小写）
   * 不包含（不区分大小写）
   * 等于

1. 在单独的行中指定每个新值（例如，“鞋子”）。
1. 单击&#x200B;**[!UICONTROL 保存]**。

## 在活动中使用类别亲和度受众 {#section_91526B942D1B4AEBB8FCDF4EBFF931CF}

您可以在任何活动中使用类别亲和度受众。在三步引导式工作流的“定位”步骤中，选择所需受众。
