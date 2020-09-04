---
keywords: vec;visual experience composer; vec;iframe;extension;browser
description: 此信息介绍如何使用 Adobe Target 可视化体验编辑器 (VEC) 助手浏览器扩展在 VEC 内可靠地加载网站，以快速创作和 QA 体验。
title: Adobe Target 可视化体验编辑器 (VEC) 助手扩展
feature: vec
topic: Standard
translation-type: tm+mt
source-git-commit: 9745315edf83f4210a3650822653b1a3081e1e1c
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 59%

---


# 可视化体验编辑器助手扩展

The [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) Helper browser extension for Google Chrome lets you load websites reliably within the VEC to rapidly author and QA web experiences.

>[!NOTE]
>
>VEC Helper浏览器是Chrome扩展。 使用Mozilla Firefox时不需要此扩展。

## 某些网站在VEC中可能无法可靠打开的原因

* 网站具有严格的安全策略。
* 网站位于 iframe 中。
* 尚未在网站上实施 at.js 库。
* 客户的 QA 和/或测试网站不适用于外部环境（网站为内部网站）。
* 您正在使用Google Chrome 80+和增强的SameSite cookie实施策略。 有关详细信息，请 [参阅最近发布的Google Chrome SameSite cookie实施策略对VEC和EEC有何影响](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)?

适用于 Chrome 的 VEC 助手浏览器扩展可以解决网站加载问题，目前，客户依赖于 [!DNL Target][ 增强型体验编辑器](/help/administrating-target/visual-experience-composer-set-up.md#eec)或第三方扩展（例如 Requestly）来解决该问题.

## 使用VEC Helper扩展的优势

* 将从网站中隐式删除所有 iframe 嵌套标头（例如 X-Frame-Options 和 Content-Security-Policy）。不再需要创建复杂的 Requestly 规则来解决此问题。
* 如果网页尚未包含 [!DNL Target] at.js JavaScript 库，您可以使用该扩展来插入库，这样您便可以为该网站创作体验。然后，您可以创建活动并使用预览链接进行 QA。
* [即使没有](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md) “增强体验书写器”( [!UICONTROL EEC)，也支持] 移动视图端口。
* 对于 [!DNL Target] 的新客户，即便在其 IT 开发人员尚未在其网站上实施 [!DNL Target] 的情况下，也可以使用此扩展来试用 [!DNL Target]。
* 服务于多个客户网站和 [!DNL Target] 帐户的合作伙伴现在有一个简单的机制来支持 VEC 加载，而不用通过第三方工具管理多个规则。

## 获取并安装 VEC 助手浏览器扩展

1. Navigate to the [Adobe Target VEC Helper browser extension in the Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak).
1. 单击&#x200B;**[!UICONTROL 添加到 Chrome > 添加扩展]**。
1. 在中打开VEC [!DNL Target]。
1. 要使用此扩展，请在处于 VEC 或 [QA 模式](/help/c-activities/c-activity-qa/activity-qa.md)时，单击 Chrome 浏览器工具栏中的 VEC 助手浏览器扩展图标 (![VEC 助手图标](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png))。
1. （视情况而定）如果 **[!UICONTROL 网页尚未包含at.js JavaScript库]** ，请将“插入目标库 [!DNL Target] ”滑动至“打开”位置。

   下图显示了已启用[!UICONTROL 插入 Target 库]设置的 VEC 助手：

   ![VEC 助手 1](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   下图显示，VEC 助手询问您是否希望它在页面中插入 [!DNL Target] 库以启用创作功能：

   ![VEC 助手 2](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. (视情况而定 **[!UICONTROL )滑动]** Cookies切换到“开启”位置，自动添加SameSite=None属性浏览器修复，然后指定Cookie名称和域。

   ![Cookie在VEC帮助程序扩展中切换](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   以下链接提供了其他信息：

   * 有关SameSite=None属性浏览器修复的详细信息，请参阅“最近发布的Google Chrome SameSite cookie实施策略如何影响VEC和EEC?” in [Troubleshooting Issues Related to the Visual Experience Composer and Enhanced Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

   * Cookie名称为“mbox”,Cookie域是您为mbox提供服务的域的第二级和顶级。 由于这是来自您的公司域，所以此 Cookie 是第一方 Cookie。示例: `mycompany.com`. 有关详细信息，请参 [阅《Adobe Target](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-target.html) 界面 *用户指南》中的Experience CloudCookie*。

## 注释

* 您的实施必须使用 [!DNL Target] at.js 库。不能将 mbox.js 实施与该扩展一起使用。
* 默认情况下，扩展中的[!UICONTROL 插入 Target 库]标志处于“关”状态。如果要在尚未针对 [!DNL Target] 实施的网站上使用 VEC，则可以启用此标志。

   请注意，此标志是全局设置。可以为在 VEC 中打开的所有网站启用或禁用此标志。因此，例如，如果将此标志设置为“on”并打开已通过at.js实现的网站，您将收到一条消息，通知您at.js已加载。 我们预计，大多数客户的页面上已实施at.js，并将使用默认设置“off”。

* The extension loads the latest version of at.js that is available from the [!DNL Target UI] in [!UICONTROL Administration > Implementation].
* 当在 [QA 模式](/help/c-activities/c-activity-qa/activity-qa.md)下使用扩展插入 at.js 时，必须打开另一个 Chrome 选项卡。此 Chrome 选项卡必须通过您创建该活动的同一 [!DNL Adobe Experience Cloud] 组织的身份验证。
* 以下消息有助于您随时了解以下情况：

   * 如果尝试使用未能加载的 VEC 来加载网站，则会显示一则消息，建议您安装 VEC 助手浏览器扩展。
   * 如果尚未在网站上实施 at.js，则 VEC 中会显示一则消息，建议您安装扩展。
   * 如果扩展已启用并且正在为加载提供支持，则当扩展插入 at.js 库（如果需要），或帮助在 VEC 中可靠地打开网站时，将显示消息。

