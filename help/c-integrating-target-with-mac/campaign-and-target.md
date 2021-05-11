---
keywords: 概述和参考
description: 了解如何将Adobe [!DNL Target] 与Adobe Campaign结合使用以优化电子邮件内容。
title: 如何将 [!DNL Target] 与Adobe Campaign集成？
feature: 集成
exl-id: 605b8fe4-e32f-43bc-9131-245008b655e1
translation-type: tm+mt
source-git-commit: 2a78828c0d04add812a73ea04f4b3927d3dbc392
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 41%

---

# 将[!DNL Target]与Adobe Campaign集成

将[!DNL Target]与[!DNL Adobe Campaign]一起使用可优化电子邮件内容。

要优化电子邮件内容，您可以在[!DNL Target]中创建重定向优惠，然后使用[!DNL Adobe Campaign]管理电子邮件优惠。 例如，可以为男优惠和女收件人显示不同的。

打开电子邮件时，即会开始进行集成。当客户打开电子邮件时，将对[!DNL Target]进行调用，并显示内容的动态版本。 该内容包含一个所有浏览器均支持的静态图像。[!DNL Target] 会在受众级别或会话级别跟踪对选件做出的响应，该跟踪数据将提供在 报表中。[!DNL Target]

[!DNL Target] 可以跟踪以下数据：

* 用户代理
* IP 地址
* 地理位置
* 与[!DNL Target]中的访客ID关联的区段（须经法律批准）
* [!DNL Campaign] Datamart中的数据

存在以下几项限制：

* 由于只能使用一个图像，因此无法对内容进行个性化设置。
* 未在[!DNL Adobe Campaign]中合并跟踪。
* 没有统一的用户体验。

使用[!DNL Target]和[!DNL Campaign]设置集成的不同部分：

* [!DNL Target]中的原始框和体验

>[!NOTE]
>
>在使用 rawbox 和 [!DNL Target] 时，请参阅[创建允许列表，其中指定有权将 mbox 调用发送到 Target 的主机](/help/administrating-target/hosts.md#allowlist)下的重要安全声明。

* [!DNL Campaign]中的投放

## 开始{#section_FF19BF1BCA064260930BF6C141313B0E}之前

在使用[!DNL Adobe Campaign]设置目标电子邮件优惠之前，请在[!DNL Target]中设置以下内容：

* 两个或更多[!DNL Target]重定向优惠

   请参阅[创建重定向优惠](/help/c-experiences/c-manage-content/offer-redirect.md)。

* [!DNL Target]活动，具有每个优惠的体验和所需的[成功量度](/help/c-activities/r-success-metrics/success-metrics.md)。

   请参阅[重定向到 URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md)。

开始[!DNL Target]中的活动，然后设置集成的[!DNL Campaign]部分。

## 在[!DNL Adobe Campaign]电子邮件{#section_B201BBE27A704E18AF0D553F35695837}中包含[!DNL Target]优惠

1. 在[!DNL Adobe Campaign]中创建电子邮件。
1. 在电子邮件属性中，单击&#x200B;**[!UICONTROL 包含]** > **[!UICONTROL 由 Adobe Target 提供的动态图像]**。
1. 从共享的资产中选择默认图像。
1. 指定位置 (rawbox)。
1. 添加任何其他决策参数，例如收件人的性别。
1. 预览电子邮件，并为每个选件至少选择一个收件人（在此示例中，选择的是一位男性和一位女性）。
1. 在[!DNL Campaign]中，定义用于控制租户活动和名称的[!DNL Target]边缘服务器。
1. 指定用于[!DNL Adobe Experience Cloud]的外部帐户，以便您能够访问[!DNL Experience Cloud]中的资源。

有关详细信息，请参阅[!DNL Adobe Campaign]文档。

## 视频：将[!DNL Target]与[!DNL Campaign]集成

>[!VIDEO](https://video.tv.adobe.com/v/35149)
