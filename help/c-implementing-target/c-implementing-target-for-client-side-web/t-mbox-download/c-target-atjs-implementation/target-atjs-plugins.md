---
description: 有关受支持和不受支持的 at.js 插件的信息。
keywords: at.js 插件;受支持的插件;不受支持的插件
seo-description: 有关受支持和不受支持的 at.js 插件的信息。
seo-title: at.js 插件
solution: Target
title: at.js 插件
topic: Standard
uuid: ef36b2b2-bf6d-497e-b3f5-2b572a1b8a8d
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# at.js 插件{#at-js-plug-ins}

有关受支持和不受支持的 at.js 插件的信息。

很多人为 [!DNL mbox.js] 构建了自定义插件和响应插件。这些自定义插件若不更新，便可能不受 [!DNL at.js] 支持。

如果您使用的插件未在此处列出，但是您想知道插件的受支持状态，请联系您的帐户代表。

下面是很多客户用于 [!DNL at.js] 的一些插件的当前受支持状态：

| 插件 | 详细信息 |
|--- |--- |
| mboxTrack | 不受支持。<br>此插件已被 [adobe.target.trackEvent(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md) 函数所取代。请更新您的插件以应用新函数。<br>请参阅[集成](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md)页面。 |
| 永久性配置文件备份插件 | 不受支持。<br>Target 配置文件生命周期从 2 周延长到 90 天后，此插件便已被弃用。请查看 mbox Cookie 的过期日期，以了解您帐户中的配置文件生命周期设置。<br>如果您希望将配置文件生命周期延长到 90 天，请联系客户关怀团队。 |
| ttMeta | 受支持.<br>此插件应该可以继续用于 at.js。 |