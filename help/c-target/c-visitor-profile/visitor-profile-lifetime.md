---
keywords: Overview and Reference
description: 默认情况下，访客配置文件会存储 14 天。配置文件生命周期可延长。
title: 访客配置文件生命周期
feature: visitor profiles
subtopic: Getting Started
topic: Standard
uuid: 01ccda60-7e28-4d26-8d5d-1c0a022bbef0
translation-type: tm+mt
source-git-commit: 32853a516910358034bacaa58e594cfb1eb91f29
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 83%

---


# 访客配置文件生命周期{#visitor-profile-lifetime}

默认情况下，访客配置文件会在访客处于不活动状态 14 天后过期。配置文件生命周期可延长。

[请联系客户关怀团队或您的 Adobe 顾问](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)，以免费延长配置文件生命周期。生命周期可设置为长达 90 天。

您使用的 [!DNL Target] JavaScript 库（[!DNL at.js] 或 [!DNL mbox.js]）决定了是否需要下载新文件：

| 定位库 | 详细信息 |
|--- |--- |
| at.js | 如果您的配置文件生命周期超出默认值，您不需要下载新的 at.js 文件。 |
| mbox.js | 如果您的配置文件生命周期超出默认的 14 天，则在您的顾问或客户关怀团队更改您的设置后，您必须下载新的 mbox.js 配置文件。用于支持更改的配置文件生命周期的 Cookie 扩展包括在更新的 mbox.js 文件中。开始使用新库后，访客的配置文件生命周期会相应地进行更新。 |

没有为现有的配置文件重置到期日期。如果旧访客 15 天没有回访，则配置文件会过期。如果旧访客在原始两周配置文件过期之前回访，则将配置文件重置到延长的生命周期。所有新访客配置文件均被设置为延长的配置文件生命周期。

在以下情形中，假定一个或两个站点是使用mbox.js实现的，这要求在更新用户档案后进行代码更新。 如果两个站点都在一个客户端代码下，并且访客访问了两个站点，则用户档案将设置为上次访问的站点上用户档案的生命周期。 例如，如果网站 1 上的配置文件生命周期为 84 天，而网站 2 上的生命周期为 14 天，且访客是先访问网站 1，然后再访问网站 2，则访客的配置文件会在访客处于不活动状态 14 天后过期。但如果访客先访问网站 2，然后再访问网站 1，则访客的配置文件会在访客处于不活动状态 84 天后过期。
