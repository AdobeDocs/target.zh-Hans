---
title: 报告
description: 了解如何使用Customer Journey Analytics在Flags中查看功能标记报告。
hide: true
exl-id: edddca99-f263-461b-a16f-b46ee7c15f6c
source-git-commit: 35fa45d2a5374dcc47a02bb737f28f24847d7fc6
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 1%

---

# 报表 {#reporting}

标记通过&#x200B;**Customer Journey Analytics (CJA)**&#x200B;提供报表。 控制台内没有“结果”或“报告”选项卡 — 相反，每个功能标志或功能组上的&#x200B;**报告**&#x200B;按钮会为该项目打开一个限定范围的CJA仪表板。

## 先决条件 {#prerequisites}

在查看报表之前，请确保：

1. 已为您的应用程序设置报表 — 请参阅[使用Customer Journey Analytics设置报表](#setup)。
1. 您的功能标志或功能组处于活动状态并具有累积数据。

## 查看报表 {#view-report}

要打开功能标志或功能组的报表，请执行以下操作：

1. 导航到控制台中的功能标志或功能组。
1. 选择&#x200B;**报告**。

此时将打开一个限定范围的Customer Journey Analytics功能板，其中显示该标记或功能组的数据。 仪表板包括：

* **参与者** — 符合该功能资格的用户总数（变体+控制组组合）
* **控制组** — 分配给控制组的用户数（收到默认体验的用户）
* **变体细分** — 已注册每个变体和对照组的用户的累计计数
* **每日注册** — 显示一段时间内每个变体和对照组的注册情况的日级别图表

## 使用Customer Journey Analytics设置报表 {#setup}

报表要求将Customer Journey Analytics数据集连接到您的Flags应用程序。 请联系Flags支持或您的Adobe代表以启用应用程序的报表。

>[!NOTE]
>
>在功能请求中传递的标识无需链接到配置文件。 评估在运行时进行，并且事件会发送到Customer Journey Analytics。

## 另请参阅 {#see-also}

* [创建您的第一个功能标记](create-your-first-feature-flag.md)
* [使用功能标记进行A/B测试](a-b-testing.md)
* [创建功能组](create-a-feature-group.md)

<!-- -->
