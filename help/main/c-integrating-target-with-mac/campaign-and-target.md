---
keywords: 概述和参考
description: 了解如何使用Adobe [!DNL Target] 与Adobe Campaign一起优化电子邮件内容。
title: 如何集成 [!DNL Target] 和Adobe Campaign?
feature: Integrations
exl-id: 605b8fe4-e32f-43bc-9131-245008b655e1
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 41%

---

# 集成 [!DNL Target] 与Adobe Campaign

使用 [!DNL Target] with [!DNL Adobe Campaign] 以优化电子邮件内容。

要优化电子邮件内容，您可以在 [!DNL Target]，然后使用 [!DNL Adobe Campaign] 以管理电子邮件选件。 例如，您可以为男性和女性收件人显示不同的选件。

打开电子邮件时，即会开始进行集成。当客户打开电子邮件时，将 [!DNL Target] 此时会显示内容的动态版本。 该内容包含一个所有浏览器均支持的静态图像。[!DNL Target] 会在受众级别或会话级别跟踪对选件做出的响应，该跟踪数据将提供在 报表中。[!DNL Target]

[!DNL Target] 可以跟踪以下数据：

* 用户代理
* IP 地址
* 地理位置
* 与 [!DNL Target] （须经法律批准）
* 数据来源 [!DNL Campaign] Datamart

存在以下几项限制：

* 由于只能使用一个图像，因此无法对内容进行个性化设置。
* 未在 [!DNL Adobe Campaign].
* 没有统一的用户体验。

同时使用 [!DNL Target] 和 [!DNL Campaign] 要设置集成的不同部分，请执行以下操作：

* 原始框和 [!DNL Target]

>[!NOTE]
>
>在使用 rawbox 和 [!DNL Target] 时，请参阅[创建允许列表，其中指定有权将 mbox 调用发送到 Target 的主机](/help/main/administrating-target/hosts.md#allowlist)下的重要安全声明。

* 中的投放 [!DNL Campaign]

## 开始之前 {#section_FF19BF1BCA064260930BF6C141313B0E}

使用之前 [!DNL Adobe Campaign] 要设置定向的电子邮件选件，请在 [!DNL Target]:

* 两个或多个 [!DNL Target] 重定向选件

   请参阅 [创建重定向选件](/help/main/c-experiences/c-manage-content/offer-redirect.md).

* A [!DNL Target] 活动，每个选件和所需的 [成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md).

   请参阅[重定向到 URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md)。

在中启动活动 [!DNL Target] 设置之前 [!DNL Campaign] 部分集成。

## 包括 [!DNL Target] 选件 [!DNL Adobe Campaign] 电子邮件 {#section_B201BBE27A704E18AF0D553F35695837}

1. 在中创建电子邮件 [!DNL Adobe Campaign].
1. 在电子邮件属性中，单击&#x200B;**[!UICONTROL 包含]** > **[!UICONTROL 由 Adobe Target 提供的动态图像]**。
1. 从共享的资产中选择默认图像。
1. 指定位置 (rawbox)。
1. 添加任何其他决策参数，例如收件人的性别。
1. 预览电子邮件，并为每个选件至少选择一个收件人（在此示例中，选择的是一位男性和一位女性）。
1. 在 [!DNL Campaign]，定义 [!DNL Target] 用于控制活动和租户名称的边缘服务器。
1. 指定用于 [!DNL Adobe Experience Cloud] 以便您能够在 [!DNL Experience Cloud].

有关更多信息，请参阅 [!DNL Adobe Campaign] 文档。

## 视频：集成 [!DNL Target] with [!DNL Campaign]

>[!VIDEO](https://video.tv.adobe.com/v/35149)
