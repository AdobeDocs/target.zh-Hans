---
keywords: 概述和参考
description: 了解如何将Adobe [!DNL Target] 与Adobe Campaign结合使用以优化电子邮件内容。
title: 如何将 [!DNL Target] 与Adobe Campaign集成？
feature: Integrations
exl-id: 605b8fe4-e32f-43bc-9131-245008b655e1
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 32%

---

# 将[!DNL Target]与Adobe Campaign集成

使用带有[!DNL Target]的[!DNL Adobe Campaign]优化电子邮件内容。

要优化电子邮件内容，您可以在[!DNL Target]中创建重定向选件，然后使用[!DNL Adobe Campaign]管理电子邮件选件。 例如，您可以为男性收件人和女性收件人显示不同的选件。

打开电子邮件时，即会开始进行集成。当客户打开电子邮件时，会向[!DNL Target]发出呼叫，并显示内容的动态版本。 该内容包含一个所有浏览器均支持的静态图像。[!DNL Target]跟踪受众或会话级别对选件的反应，该数据在[!DNL Target]报表中可用。

[!DNL Target]可以跟踪以下数据：

* 用户代理
* IP 地址
* 地理位置
* 与[!DNL Target]中的访客ID关联的区段（须经法律批准）
* 来自[!DNL Campaign]数据集市的数据

存在以下几项限制：

* 由于只能使用一个图像，因此无法对内容进行个性化设置。
* 未在[!DNL Adobe Campaign]中合并跟踪。
* 没有统一的用户体验。

同时使用[!DNL Target]和[!DNL Campaign]设置集成的不同部分：

* [!DNL Target]中的原始框和体验

>[!NOTE]
>
>在使用 rawbox 和 [!DNL Target] 时，请参阅[创建允许列表，其中指定有权将 mbox 调用发送到 Target 的主机](/help/main/administrating-target/hosts.md#allowlist)下的重要安全声明。

* [!DNL Campaign]中的投放

## 开始之前 {#section_FF19BF1BCA064260930BF6C141313B0E}

在使用[!DNL Adobe Campaign]设置定向电子邮件优惠之前，请在[!DNL Target]中设置以下内容：

* 两个或更多[!DNL Target]重定向选件

  请参阅[创建重定向选件](/help/main/c-experiences/c-manage-content/offer-redirect.md)。

* [!DNL Target]活动，具有适用于每个选件和所需[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md)的体验。

  请参阅[重定向到 URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md)。

在设置集成的[!DNL Target]部分之前，在[!DNL Campaign]中启动活动。

## 在[!DNL Target]电子邮件中包含[!DNL Adobe Campaign]选件 {#section_B201BBE27A704E18AF0D553F35695837}

1. 在[!DNL Adobe Campaign]中创建电子邮件。
1. 在电子邮件属性中，单击&#x200B;**[!UICONTROL Include]** > **[!UICONTROL Dynamic image served by Adobe Target]**。
1. 从共享的资产中选择默认图像。
1. 指定位置 (rawbox)。
1. 添加任何其他决策参数，例如收件人的性别。
1. 预览电子邮件，并为每个选件至少选择一个收件人（在此示例中，选择的是一位男性和一位女性）。
1. 在[!DNL Campaign]中，定义您用来控制活动和租户名称的[!DNL Target] Edge服务器。
1. 指定用于[!DNL Adobe Experience Cloud]的外部帐户，以便您可以访问[!DNL Experience Cloud]中的资源。

有关详细信息，请参阅[!DNL Adobe Campaign]文档。

## 视频：将[!DNL Target]与[!DNL Campaign]集成

>[!VIDEO](https://video.tv.adobe.com/v/35149)
