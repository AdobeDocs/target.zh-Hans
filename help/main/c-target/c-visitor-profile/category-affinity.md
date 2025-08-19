---
keywords: 亲和度;类别亲和度
description: 了解 [!DNL Adobe Target] 中的类别亲和度，该功能可自动捕获用户访问的类别，然后计算用户对该类别的喜爱程度，从而可以对用户进行定位和细分。
title: 什么是类别亲和度？
feature: Audiences
exl-id: 9478a7fb-e4b5-46d9-be73-b72cb99c3e5e
source-git-commit: 80481a149d436f13bd510c4c4287d447799afbb4
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 56%

---

# 类别亲和力

[!DNL Adobe Target]中的类别亲和度功能会自动捕获用户访问您网站上的类别，然后计算用户对每个类别的喜爱程度，从而可以对用户进行定位和细分。 类别亲和度有助于确保内容被定位到最有可能对该信息做出回应的访客。

## 正在将类别亲和度信息传递到[!DNL Target] {#section_B0C8E46EEBAC4549AD90352A47787D04}

不论用户何时访问您的网站，都会将特定于访客的轮廓参数记录到 [!DNL Target] 数据库中。该数据将与用户的 Cookie 绑定。一个有用的参数是`user.categoryId`，它是在产品页面上分配的mbox参数。 访客持续浏览时，或离开后返回进行另一个会话时，都可以记录特定用户查看的产品类别。您还可以将类别信息作为任何mbox（包括嵌套mbox）中的mbox参数`user.categoryId`或作为URL参数`user.categoryId`进行传递，或者通过全局mbox在[!DNL Target]页面参数中进行传递，从而记录类别信息。 有关更多详细信息，请咨询您的帐户代表。

要将一个项目包含在多个类别中，请使用逗号分隔类别。例如：

* `user.categoryId=clothing,shoes,nike,running,nike clothing,nike shoes,nike running shoes`

根据对您的产品类别进行访问的频率和近期情况，会记录用户所具有的类别亲和度（如果有）。类别亲和度可用于为活动定位访客群体。

您可以在配置文件脚本中使用`user.categoryAffinities[]`以返回访客填充的一组喜好。 有关详细信息，请参阅配置文件属性[中的对象和方法下的](/help/main/c-target/c-visitor-profile/profile-parameters.md#objects)user.categoryAffinities。

>[!IMPORTANT]
>
>用于类别亲和度算法的`user.categoryId`属性不同于用于`entity.categoryId`”产品和内容推荐的[!DNL Adobe Target Recommendations]属性。 要跟踪用户喜爱的类别，需要使用 `user.categoryId`。要根据当前页面或当前项目所属的类别进行推荐，需要使用 `entity.categoryId`。如果要同时使用这两项功能，请将这两个值都传递给[!DNL Target]。

## 类别亲和度的商业案例 {#section_D6FF913E88E6486B8FBCE117CA8B253B}

访客在一个会话中的活动（例如他们查看次数最多的类别）可用于在后续访问中进行定位。 系统会捕捉访客在一次会话中查看的各类别页面，并根据新近度和频率模型来计算出访客“最喜爱”的类别。之后，访客每次返回到主页时，便可以对主页图像区域进行定位，使其显示与该访客最喜爱的类别有关的内容。

## 使用类别亲和度的示例 {#section_A4AC0CA550924CB4875F4F4047554C18}

假设您在线销售乐器，并希望将低音吉他促销定位到过去对吉他感兴趣的访客。使用类别亲和度，您可以创建仅向具有此类别亲和度的访客显示的选件。

## 类别亲和度算法 {#section_8B86C7FF50294208866ABF16F07D5EB9}

类别亲和度算法采用如下计算方式：

* 查看的第一个类别获得10分
* 在第一次查看后单击的每个类别将各获得5分
* 点击新类别后，之前点击的所有类别都将减去 1 分
* 如果已点击（已查看）某个类别，则再次单击该类别时，所有其他类别都将不会减去1分
* 如果点击了第六个新类别，则将从计算中删除前五个类别中得分最低的类别
* 会话结束时将所有值除以 2

>[!NOTE]
>
>在一个mbox调用中传递多个类别时，`categoryAffinities`中的类别顺序无法得到保证。 首先记录任意类别，并获得10分。

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

以下部分包含的信息可帮助您使用类别亲和度受众在活动中进行定位。

### 创建要使用类别亲和度的受众 {#section_A27C600BBA664FE7A74F8FE076B78F40}

1. 从&#x200B;**[!UICONTROL Audiences]**&#x200B;列表中，单击&#x200B;**[!UICONTROL Create Audience]**。

   或

   在受众列表中，将鼠标悬停在所需受众上，然后单击复制图标，以复制现有受众。然后，您可以对受众进行编辑以创建一个类似的受众。

1. 键入描述性受众名称。
1. 单击&#x200B;**[!UICONTROL + Add Rule]** > **[!UICONTROL Visitor Profile]**。
1. 从&#x200B;**[!UICONTROL Visitor Profile]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL Category Affinity]**。

   ![“访客轮廓”>“类别亲和度”](assets/affinity.png)

1. 选择所需类别：

   ![“类别亲和度”>“类别”](assets/affinity-category.png)

   类别包括：

   * 最喜爱类别
   * 第一类别
   * 第二类别
   * 第三类别
   * 第四类别
   * 第五类别

   “最喜爱的类别”和“第一个类别”选项是等效的。

1. 选择计算器：

   * 包含（不区分大小写）
   * 不包含（不区分大小写）
   * 等于

1. 在单独的行中指定每个新值（例如，“鞋子”）。
1. 单击 **[!UICONTROL Save]**。

### 在活动中使用类别亲和度受众 {#section_91526B942D1B4AEBB8FCDF4EBFF931CF}

您可以在任何活动中使用类别亲和度受众。 在三步引导式工作流中，在[!UICONTROL Target]步骤中选择所需的受众。
