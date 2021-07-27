---
keywords: Adobe Experience Platform Web SDK;aep Web SDK;Web SDK;Adobe Experience Cloud；平台边缘网络；Adobe Experience Platform边缘网络；边缘网络；aep边缘网络
description: 了解如何使用Adobe Experience Platform Web SDK通过AEP Edge Network与Adobe Experience Cloud中的各种服务进行交互。
title: 如何使用Experience PlatformWeb SDK实施？
feature: AEP Web SDK
role: Developer
exl-id: afcd741f-bb7e-4bc2-b96c-ec10d5d6f4c5
source-git-commit: a2b3bf75e8b14c3068b8dba59f31d2577d9cec29
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 5%

---

# Adobe Experience Platform Web SDK

[!DNL Adobe Experience Platform Web SDK] (AEP Web SDK)是一个客户端JavaScript库，它允 [!DNL Adobe Experience Cloud] 许客户通过Adobe Experience Platform边缘网络( [!DNL Target]包括 [!UICONTROL  Edge Network])与Experience Cloud中的各种服务进行交互。除了JavaScript库之外，还有一个[!DNL Experience Platform Launch]扩展，可帮助您配置Web SDK。

有关更多信息，请参阅&#x200B;*Adobe Experience Platform Web SDK*&#x200B;帮助中的以下链接：

* 欲知全面信息：[什么是Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html)
* 有关[!DNL Target]的特定信息：[Target概述](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html)

## 本指南中的推荐文档

除了上述[!DNL Platform Web SKD]文档之外，本指南中的主题还包含与[!DNL Target]特性和功能相关的特定信息。[!DNL Platform Web SDK]

| 功能 | 描述/链接 |
| --- | --- |
| [[!DNL Adobe Analytics] as the reporting source for [!DNL Adobe Target] (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md) | [!DNL Adobe Analytics for Target] (A4T)是一种跨解决方案的集成，允许您根据转化量度和 [!DNL Analytics] 受众区段创建活动。A4T集成允许您使用[!DNL Analytics]报表来检查结果。<br>请参 [阅Adobe Experience Platform ](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) Web SDK实 [施支持的活动类型和实施步骤](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#platform)。 |
| [活动 QA](/help/c-activities/c-activity-qa/activity-qa.md) | 使用[!DNL Adobe Target]中的QA URL来执行简单的端到端活动QA，它提供了永不更改的预览链接、可选的受众定位以及从实时活动数据中分段的QA报表。 [!UICONTROL 活动] QA允许您在启动活动 [!DNL Target] 之前对其进行全面测试。<br>有关更 [多信息，请参阅Target JavaScript库QA](/help/c-activities/c-activity-qa/activity-qa.md#compatibility) 模式兼容 [性和](/help/c-activities/c-activity-qa/activity-qa.md#preview) 预览URL 。 |
| [受众](/help/c-target/target.md) | [!DNL Adobe Target]中的受众可确定在目标活动中看到内容和体验的受众。<br>请参 [阅使用受众](/help/c-target/c-audiences/audiences.md#use-list) 列 [表合并多个受众](/help/c-target/combining-multiple-audiences.md)。 |
| [重定向选件 - A4T 常见问题解答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) | 重定向选件会导致访客的浏览器重定向到新页面。<br>请参 [阅是 [!DNL Adobe Experience Platform Web SDK] 否支持A4T的重定向选件？](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#platform) |
| [响应令牌](/help/administrating-target/response-tokens.md) | 响应令牌允许您将Target数据发送到Google Analytics和其他第三方集成。<br>请参 [阅通过Platform Web SDK向Google Analytics发](/help/administrating-target/response-tokens.md#platform-web-sdk) 送数据，以查看如何完成此任务的代码示例。 |
| [TLS（传输层安全性）加密更改](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md) | TLS（传输层安全性）可帮助您保持最高的安全标准并提升客户数据的安全性。 |
