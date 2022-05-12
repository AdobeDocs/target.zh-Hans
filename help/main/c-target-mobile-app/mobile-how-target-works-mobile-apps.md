---
description: 了解如何使用AdobeMobile SDK向移动设备应用程序访客显示最佳体验。
title: 操作方法 [!DNL Target] 在移动设备应用程序中工作？
feature: Implement Mobile
role: Developer
exl-id: 1a5f34dc-932d-47c7-b730-6d1658343fb4
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 84%

---

# 如何 [!DNL Target] 在移动设备应用程序中工作

Adobe Mobile SDK 连接到 Target 服务器以获取内容和其他数据点，从而向用户显示正确的体验。

## Target 位置和成功量度 {#section_A08AAB0ABA9C4568A5AFD4D27EF1CE74}

*Target 位置*&#x200B;也称为 mbox。将会启用应用程序中的标识位置，以用于测试或个性化（例如，主页屏幕上的欢迎消息）。这些位置是在测试创建过程中标识的。

*[](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)*&#x200B;成功量度是指用户执行的用于标识特定活动是否成功的操作（例如注册、购买、订票等等）。

![](assets/mobile-target-location.png)

* **Target 位置：**&#x200B;注册按钮下方显示的内容。

   在下午 6 点之前此特定用户可享受免运费优惠。此位置可以在多个 Target 活动中重复使用，以运行 A/B 测试和个性化。

* **成功量度：**&#x200B;用户执行的点按注册按钮的操作。

**了解 Target 在 SDK 中的工作原理**

![](assets/how-target-mobile-works.png)