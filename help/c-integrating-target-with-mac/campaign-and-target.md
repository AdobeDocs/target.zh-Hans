---
keywords: Overview and Reference
description: 可将 Target 与 Adobe Campaign 结合使用来优化电子邮件内容。
title: 将 Target 与 Adobe Campaign 集成
feature: null
topic: Standard
uuid: 1a5b70e6-d501-4b52-bec8-4ae2c419d331
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 51%

---


# 将 Target 与 Adobe Campaign 集成{#integrate-target-with-adobe-campaign}

Use [!DNL Target] with [!DNL Adobe Campaign] to optimize email content.

To optimize your email content--for example, to display different offers for male and female recipients--you can create a redirect offer in [!DNL Target], then use [!DNL Adobe Campaign] to manage the email offers.

打开电子邮件时，即会开始进行集成。When the customer opens the email, a call is made to [!DNL Target] and a dynamic version of the content appears. 该内容包含一个所有浏览器均支持的静态图像。[!DNL Target] 会在受众级别或会话级别跟踪对选件做出的响应，该跟踪数据将提供在 报表中。[!DNL Target]

Target 可以跟踪以下数据：

* 用户代理
* IP 地址
* 地理位置
* 与 Target 中的访客 ID 关联的区段（需获得法律批准）
* Data from [!DNL Campaign] Datamart

存在以下几项限制：

* 由于只能使用一个图像，因此无法对内容进行个性化设置。
* Tracking is not consolidated in [!DNL Adobe Campaign].
* 没有统一的用户体验。

   You must use both [!DNL Target] and [!DNL Campaign] to set up different parts of the integration:

   *  中的 rawbox 和体验[!DNL Target]
   >[!NOTE]
   >
   >使用rawbox和时，请 [!DNL Target]参阅“创建”下的重 [要安允许列表全声明，该目标指定已获得授权向发送mbox调用的主机](/help/administrating-target/hosts.md#allowlist)。

   * The delivery in [!DNL Campaign]



## 开始之前 {#section_FF19BF1BCA064260930BF6C141313B0E}

Before you use [!DNL Adobe Campaign] to set up your targeted email offers, set up the following in [!DNL Target]:

* Two or more [!DNL Target] redirect offers

   See [Create redirect offer](/help/c-experiences/c-manage-content/offer-redirect.md).
* 包含每个选件所对应体验的 Target 活动，以及所需的[成功量度](/help/c-activities/r-success-metrics/success-metrics.md)。

   请参阅[重定向到 URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md)。

Start the activity in [!DNL Target] before setting up the [!DNL Campaign] portion of the integration.

## 将 Target 选件包含在 Adobe Campaign 电子邮件中 {#section_B201BBE27A704E18AF0D553F35695837}

1. Create an email in [!DNL Adobe Campaign].
1. 在电子邮件属性中，单击&#x200B;**[!UICONTROL 包含]** > **[!UICONTROL 由 Adobe Target 提供的动态图像]**。
1. 从共享的资产中选择默认图像。
1. 指定位置 (rawbox)。
1. 添加任何其他决策参数，例如收件人的性别。
1. 预览电子邮件，并为每个选件至少选择一个收件人（在此示例中，选择的是一位男性和一位女性）。
1. In [!DNL Campaign], define the [!DNL Target] Edge server you are using to control the activity and the name of the tenant.
1. Specify the external account used for the [!DNL Adobe Experience Cloud] so you can access the resources in the [!DNL Experience Cloud].

For more information, refer to the [!DNL Adobe Campaign] documentation.
