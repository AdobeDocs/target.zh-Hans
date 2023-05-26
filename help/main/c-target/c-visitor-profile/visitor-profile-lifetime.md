---
keywords: 概述和参考
description: 了解有关访客配置文件何时过期的更多信息 [!DNL Adobe Target].
title: 访客个人资料生命周期是什么？我可以延长它吗？
feature: Audiences
exl-id: 70cb5e3b-ed6d-450d-8c6e-f1bfe8d26e54
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 62%

---

# 访客个人资料生命周期

默认情况下，中的访客资料 [!DNL Adobe Target] 在该访客处于非活动状态14天后过期。 配置文件生命周期可延长。

[请联系客户关怀团队或您的 Adobe 顾问](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)，以免费延长配置文件生命周期。生命周期可设置为长达 90 天。

您无需下载新的 [!DNL Platform Web SDK] 文件或at.js文件（如果您的配置文件扩展超过默认值）。

没有为现有的配置文件重置到期日期。如果旧访客 15 天没有回访，则配置文件会过期。如果旧访客在原始两周配置文件过期之前回访，则将配置文件重置到延长的生命周期。所有新访客配置文件均被设置为延长的配置文件生命周期。
