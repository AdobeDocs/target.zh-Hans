---
keywords: 概述和参考
description: 可将 Target 与 Adobe Campaign 结合使用来优化电子邮件内容。
title: 将 Target 与 Adobe Campaign 集成
topic: Standard
uuid: 1a5b70e6-d501-4b52-bec8-4ae2c419d331
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 将 Target 与 Adobe Campaign 集成{#integrate-target-with-adobe-campaign}

可将 Target 与 Adobe Campaign 结合使用来优化电子邮件内容。

要优化您的电子邮件内容（例如向男性和女性收件人显示不同的选件），您可以先在 Target 中创建一个重定向选件，然后再使用 Adobe Campaign 来管理电子邮件选件。

打开电子邮件时，即会开始进行集成。客户打开电子邮件时，将会对 Target 进行调用，随即会显示内容的动态版本。该内容包含一个所有浏览器均支持的静态图像。Target 会在受众级别或会话级别跟踪对选件做出的响应，该跟踪数据将提供在 Target 报表中。

Target 可以跟踪以下数据：

* 用户代理
* IP 地址
* 地理位置
* 与 Target 中的访客 ID 关联的区段（需获得法律批准）
* 来自 Campaign 数据集市的数据

存在以下几项限制：

* 由于只能使用一个图像，因此无法对内容进行个性化设置。
* 跟踪功能未整合到 Adobe Campaign 中。
* 没有统一的用户体验。

   您必须使用 Target 和 Campaign 来设置集成的不同部分：

   * Target 中的 rawbox 和体验
   * Campaign 中的交付

## 开始之前 {#section_FF19BF1BCA064260930BF6C141313B0E}

在使用 Adobe Campaign 设置目标电子邮件选件之前，需在 Target 中设置以下几项：

* 两个或更多 Target 重定向选件。

   See [Create redirect offer](/help/c-experiences/c-manage-content/offer-redirect.md).
* 包含每个选件所对应体验的 Target 活动，以及所需的[成功量度](/help/c-activities/r-success-metrics/success-metrics.md)。

   请参阅[重定向到 URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md)。

在设置集成的 Campaign 部分之前，请先在 Target 中启动活动。

## 将 Target 选件包含在 Adobe Campaign 电子邮件中 {#section_B201BBE27A704E18AF0D553F35695837}

1. 在 Adobe Campaign 中创建一个电子邮件。
1. 在电子邮件属性中，单击&#x200B;**[!UICONTROL 包含]** &gt; **[!UICONTROL 由 Adobe Target 提供的动态图像]**。
1. 从共享的资产中选择默认图像。
1. 指定位置 (rawbox)。
1. 添加任何其他决策参数，例如收件人的性别。
1. 预览电子邮件，并为每个选件至少选择一个收件人（在此示例中，选择的是一位男性和一位女性）。
1. 在 Campaign 中，定义要用来控制活动的 Target 边缘服务器和租户名称。
1. 指定用于 Experience Cloud 的外部帐户，以便您能够访问 Experience Cloud 中的资源。

有关更多信息，请参阅 Adobe Campaign 文档。
