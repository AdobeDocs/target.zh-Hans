---
keywords: at.js 插件;受支持的插件;不受支持的插件;ttMeta;ttmeta;mboxTrack
description: 了解旧版mbox.js对Adobe Target的实施。 迁移至Adobe Experience PlatformWeb SDK(AEP Web SDK)或最新版at.js。
title: 目标at.js不支持哪些旧版插件？
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 82%

---


# at.js 插件

有关 Adobe Target 支持和不支持的 at.js 插件的信息。

很多人为 [!DNL mbox.js] 构建了自定义插件和响应插件。这些自定义插件若不更新，便可能不受 [!DNL at.js] 支持。

如果您使用的插件未在此处列出，但是您想知道插件的受支持状态，请联系您的帐户代表。

下面是很多客户用于 [!DNL at.js] 的一些插件的当前受支持状态：

| 插件 | 详细信息 |
|--- |--- |
| mboxTrack | 不受支持。<br>此插件已被 [adobe.target.trackEvent(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md) 函数所取代。请更新您的插件以应用新函数。<br>请参阅[集成](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md)页面。 |
| 永久性配置文件备份插件 | 不受支持。<br>Target 配置文件生命周期从 2 周延长到 90 天后，此插件便已被弃用。请查看 mbox Cookie 的过期日期，以了解您帐户中的配置文件生命周期设置。<br>如果您希望将配置文件生命周期延长到 90 天，请联系客户关怀团队。 |
| ttMeta | 应停用旧的 SiteCatalyst 插件，并改为[将 Adobe Analytics 作为 Adobe Target 的报表源](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T)。ttMeta 插件应停用并替换为 [Adobe Experience Cloud 调试器](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj)。 |