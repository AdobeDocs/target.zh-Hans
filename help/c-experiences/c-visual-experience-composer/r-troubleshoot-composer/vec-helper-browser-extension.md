---
keywords: vec;visual experience composer; vec;iframe;extension;browser
description: 此信息介绍如何使用 Adobe Target 可视化体验编辑器 (VEC) 助手浏览器扩展在 VEC 内可靠地加载网站，以快速创作和 QA 体验。
title: Adobe Target 可视化体验编辑器 (VEC) 助手扩展
topic: Standard
translation-type: tm+mt
source-git-commit: 3edb13b196240bb1918fc66edcc653936e32d3ef
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 94%

---


# 可视化体验编辑器助手扩展

借助适用于 Google Chrome 的 [!DNL Adobe Target] 可视化体验编辑器 (VEC) 助手浏览器扩展，您可以在 VEC 内可靠地加载网站，以快速创作和 QA Web 体验。

某些网站可能无法在 VEC 中可靠打开的原因：

* 网站具有严格的安全策略。
* 网站位于 iframe 中。
* 尚未在网站上实施 at.js 库。
* 客户的 QA 和/或测试网站不适用于外部环境（网站为内部网站）。

适用于 Chrome 的 VEC 助手浏览器扩展可以解决网站加载问题，目前，客户依赖于 [!DNL Target][!UICONTROL  增强型体验编辑器]或第三方扩展（例如 Requestly）来解决该问题

使用 VEC 助手扩展的好处：

* 将从网站中隐式删除所有 iframe 嵌套标头（例如 X-Frame-Options 和 Content-Security-Policy）。不再需要创建复杂的 Requestly 规则来解决此问题。
* 如果网页尚未包含 [!DNL Target] at.js JavaScript 库，您可以使用该扩展来插入库，这样您便可以为该网站创作体验。然后，您可以创建活动并使用预览链接进行 QA。
* 即使没有[!UICONTROL 增强型体验编辑器] (EEC)，也支持移动设备视区。
* 对于 [!DNL Target] 的新客户，即便在其 IT 开发人员尚未在其网站上实施 [!DNL Target] 的情况下，也可以使用此扩展来试用 [!DNL Target]。
* 服务于多个客户网站和 [!DNL Target] 帐户的合作伙伴现在有一个简单的机制来支持 VEC 加载，而不用通过第三方工具管理多个规则。

## 获取并安装 VEC 助手浏览器扩展

1. Navigate to the [Adobe Target VEC Helper browser extension in the Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak).
1. 单击[!UICONTROL 添加到 Chrome > 添加扩展]。
1. 要使用此扩展，请在处于 VEC 或 [QA 模式](/help/c-activities/c-activity-qa/activity-qa.md)时，单击 Chrome 浏览器工具栏中的 VEC 助手浏览器扩展图标 (![VEC 助手图标](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png))。

下图显示了已启用[!UICONTROL 插入 Target 库]设置的 VEC 助手：

![VEC 助手 1](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

下图显示，VEC 助手询问您是否希望它在页面中插入 [!DNL Target] 库以启用创作功能：

![VEC 助手 2](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

## 注释

* 您的实施必须使用 [!DNL Target] at.js 库。不能将 mbox.js 实施与该扩展一起使用。
* 默认情况下，扩展中的[!UICONTROL 插入 Target 库]标志处于“关”状态。如果要在尚未针对 [!DNL Target] 实施的网站上使用 VEC，则可以启用此标志。

   请注意，此标志是全局设置。可以为在 VEC 中打开的所有网站启用或禁用此标志。例如，如果您将此标志设置为“开”并且打开一个已使用 at.js 进行实施的网站，则将会收到一则消息，告知您 at.js 已加载。我们预计大多数客户已经在其页面上实施了 at.js，并且将会使用默认的“关”设置。

* The extension loads the latest version of at.js that is available from the [!DNL Target UI] in [!UICONTROL Administration > Implementation].
* 当在 [QA 模式](/help/c-activities/c-activity-qa/activity-qa.md)下使用扩展插入 at.js 时，必须打开另一个 Chrome 选项卡。此 Chrome 选项卡必须通过您创建该活动的同一 [!DNL Adobe Experience Cloud] 组织的身份验证。
* 以下消息有助于您随时了解以下情况：

   * 如果尝试使用未能加载的 VEC 来加载网站，则会显示一则消息，建议您安装 VEC 助手浏览器扩展。
   * 如果尚未在网站上实施 at.js，则 VEC 中会显示一则消息，建议您安装扩展。
   * 如果扩展已启用并且正在为加载提供支持，则当扩展插入 at.js 库（如果需要），或帮助在 VEC 中可靠地打开网站时，将显示消息。