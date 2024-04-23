---
keywords: VEC;可视化体验编辑器;VEC;iframe;扩展;浏览器
description: 了解为什么某些网站可能无法在中可靠打开 [!UICONTROL Visual Experience Composer] (VEC)。 通过VEC助手浏览器扩展，您可以在VEC中以可靠的方式加载网站。
title: 如何使用 [!UICONTROL Visual Experience Composer] (VEC)助手扩展？
feature: Visual Experience Composer (VEC)
exl-id: 3f38db69-046d-42c9-8c09-eca11d404b12
source-git-commit: 97b1d78de2d6ba33c1dd72494edcfc97fc3ba7e6
workflow-type: tm+mt
source-wordcount: '1043'
ht-degree: 50%

---

# [!UICONTROL Visual Experience Composer] 帮助程序扩展

此 [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC)的帮助程序浏览器扩展 [!DNL Google Chrome] 允许您在VEC中以可靠的方式加载网站，以便快速创作和QA Web体验。

VEC助手浏览器是 [!DNL Chrome] 扩展。 使用时，不需要使用此扩展 [!DNL Mozilla Firefox].

>[!IMPORTANT]
>
>旧版 [!DNL Target] 本文中记录的VEC助手扩展是使用清单V2创建的。 [!DNL Google] 宣布从2024年6月起，将不再允许使用清单V2创建的扩展。 欲了解更多信息，请参见 [清单V2支持时间表公告](https://developer.chrome.com/docs/extensions/develop/migrate/mv2-deprecation-timeline){target=_blank} 从 [!DNL Google] 在 *适用于开发人员的Chrome* 站点。
>
>从2024年6月开始 [!DNL Google] 将开始禁用使用清单V2创建的扩展，包括本主题中介绍的扩展。 [!DNL Adobe] 建议客户迁移到较新版本 [可视化编辑帮助程序扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) 尽可能早。

## 为什么某些网站可能无法在可视化体验编辑器 (VEC) 中以可靠的方式打开

* 网站具有严格的安全策略。
* 网站位于 iframe 中。
* 尚未在网站上实施 at.js 库。
* 外部无法访问客户的 QA 或阶段站点（该站点为内部站点）。
* 在尝试使用VEC打开正在使用的网站时，当前存在一些限制 [服务工作程序](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API){target=_blank} (SW)。

SW 是一种 Web 技术，可用于拦截对网页所安装的域的请求。SW 在页面访问中留存，并在后续访问中自我激活。SW 可以决定哪些请求将通过，哪些请求被拦截并从缓存中提供服务。

SW 可以控制缓存；可以缓存网页本身、静态资源（例如 JS、CSS、IMG、AJAX 请求）、它们的内容和响应头，包括我们的 [Target VEC Helper 扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)尝试删除的项，例如 X-Frame-Options：SAMEORIGIN、CSP (Content-Security-Policy) 或 Set-Cookie。

不幸的是，拦截Web请求的Chrome扩展API不会收到已由SW拦截和处理的请求。 因此，如果网页请求是由SW从缓存中提供的，则扩展无法修复标头和Cookie，因为网页将不会在VEC中加载（原因是，X-Frame-Options或CSP标头也已被缓存）。

作为潜在的解决方法，您可以从Chrome的“开发人员工具”>“应用程序”选项卡中禁用Service Worker，然后启用Service Worker部分下的“绕过网络”复选框。

* 您正在将Google Chrome 80及更高版本与增强的SameSite Cookie实施策略配合使用。 有关更多信息，请参阅 [最近公布的Google Chrome SameSite Cookie强制执行政策对VEC和EEC有什么影响？](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)？

适用于Chrome的VEC助手浏览器扩展解决了客户现在依赖的网站加载问题 [!DNL Target] [增强型体验编辑器](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) 或第三方扩展，例如Requestly。

## 使用VEC助手扩展的好处

* 将从网站中隐式删除所有 iframe 嵌套标头（例如 X-Frame-Options 和 Content-Security-Policy）。不再需要创建复杂的Requestly规则。
* 如果网页尚未包含 [!DNL Target] at.js JavaScript 库，您可以使用该扩展来插入库，这样您便可以为该网站创作体验。然后，您可以创建活动并使用预览链接进行 QA。

  请注意，使用增强型体验编辑器(EEC)时，扩展不会插入.js，但是SameSite Cookie功能仍然会存在。 要在网页上插入 at.js，请关闭 EEC。

* [移动设备视区](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) 支持，即使没有 [!UICONTROL Enhanced Experience Composer] (EEC)。
* 对于 [!DNL Target] 的新客户，即便在其 IT 开发人员尚未在其网站上实施 [!DNL Target] 的情况下，也可以使用此扩展来试用 [!DNL Target]。
* 服务于多个客户网站和 [!DNL Target] 帐户的合作伙伴现在有一个简单的机制来支持 VEC 加载，而不用通过第三方工具管理多个规则。

## 获取并安装 VEC 助手浏览器扩展

1. 导航至 [Chrome网络商店中的Adobe Target VEC助手浏览器扩展](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak).
1. 单击 **[!UICONTROL Add to Chrome > Add Extension]**。
1. 打开 [!DNL Target] 中的 VEC。
1. 要使用此扩展，请在处于 VEC 或 [QA 模式](/help/main/c-activities/c-activity-qa/activity-qa.md)时，单击 Chrome 浏览器工具栏中的 VEC 助手浏览器扩展图标 (![VEC 助手图标](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png))。
1. （视情况而定）滑动 **[!UICONTROL Inject Target Libraries]** 如果网页尚未包含 [!DNL Target] at.js JavaScript库。

   下图显示了使用的VEC助手 [!UICONTROL Inject Target Libraries] 设置已启用：

   ![VEC 助手 1](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   下图显示，VEC 助手询问您是否希望它在页面中插入 [!DNL Target] 库以启用创作功能：

   ![VEC 助手 2](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. （视情况而定）滑动 **[!UICONTROL Cookies]** 切换到“开”位置以自动添加 `SameSite=None` 属性浏览器修复。

   ![VEC助手扩展中的Cookie切换](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   若要了解有关`SameSite=None`属性浏览器修复的更多信息，请参阅“最近公布的 Google Chrome SameSite Cookie 强制执行政策对 VEC 和 EEC 有什么影响？”（在[排除与可视体验编辑器和增强体验编辑器相关的问题](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)中）。

## 注释

* 此 [!UICONTROL Inject Target libraries] 默认情况下，扩展中的标志为OFF。 如果要在尚未针对 [!DNL Target] 实施的网站上使用 VEC，则可以启用此标志。

  此标志是全局设置。 可以为在 VEC 中打开的所有网站启用或禁用此标志。因此，例如，如果您将此标志设置为“开”，并打开一个已使用at.js进行实施的网站，则会收到一则消息，告知您at.js已加载。 Adobe预计大多数客户已在其页面上实施了at.js，并且会使用默认设置“关闭”。

* 该扩展加载最新版本的at.js，该版本可从 [!DNL Target UI] 在 [!UICONTROL Administration > Implementation].
* 当在 [QA 模式](/help/main/c-activities/c-activity-qa/activity-qa.md)下使用扩展插入 at.js 时，必须打开另一个 Chrome 选项卡。此 Chrome 选项卡必须通过您创建该活动的同一 [!DNL Adobe Experience Cloud] 组织的身份验证。
* 以下消息有助于您随时了解以下情况：

   * 如果尝试使用未能加载的 VEC 来加载网站，则会显示一则消息，建议您安装 VEC 助手浏览器扩展。
   * 如果尚未在网站上实施 at.js，则 VEC 中会显示一则消息，建议您安装扩展。
   * 如果扩展已启用并且正在为加载提供支持，则当扩展插入 at.js 库（如果需要），或帮助在 VEC 中可靠地打开网站时，将显示消息。
