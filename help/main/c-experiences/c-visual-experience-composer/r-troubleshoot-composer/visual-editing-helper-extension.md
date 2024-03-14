---
keywords: vec；可视化体验编辑器；vec；iframe；扩展；浏览器；faq
description: 了解为什么某些网站可能无法在中可靠打开 [!UICONTROL Visual Experience Composer] (VEC)。 此 [!UICONTROL Visual Editing Helper] 通过浏览器扩展，您可以在VEC中以可靠的方式加载网站。
title: 如何使用 [!UICONTROL Visual Editing Helper] 扩展？
feature: Visual Experience Composer (VEC)
exl-id: e5aeb8b9-fab5-4ad4-882e-2106d2c9daab
source-git-commit: 5df9ba6eb249dfc690279177ecb5936aaefa7bdd
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 67%

---

# [!UICONTROL Visual Editing Helper] 扩展

此 [!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] 的浏览器扩展 [!DNL Google Chrome] 允许您在中可靠地加载网站 [!UICONTROL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC)来快速创作和QA Web体验。

>[!IMPORTANT]
>
>新的扩展取代了以前的 [Target VEC 帮助程序浏览器扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)。请参阅该文章顶部的重要说明。

## 为什么某些网站可能无法在可视化体验编辑器 (VEC) 中以可靠的方式打开

* 网站具有严格的安全策略。
* 网站位于 iframe 中。
* 外部无法访问客户的 QA 或阶段站点（该站点为内部站点）。

此 [!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] 的浏览器扩展解决了客户现在依赖的网站加载问题。 [!DNL Target] [增强型体验编辑器](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) 或第三方扩展，例如Requestly。

## 使用 [!UICONTROL Visual Editing Helper] 扩展

* 隐含地从网站中删除所有令 iframe 失效的标头，如 `X-Frame-Options` 和 `Content-Security-Policy`。没有必要创建复杂的 Requestly 规则。
* 如果网页尚未包含 [!DNL Target] at.js 库，您可以使用该扩展来插入库，这样您便可以为该网站创作体验。然后，您可以创建活动并使用预览链接进行 QA。

  使用[增强型体验编写器](/help/main/administrating-target/visual-experience-composer-set-up.md#eec)时，扩展未注入 at.js，但仍存在 SameSite Cookie 功能。要在网页上插入 at.js，请关闭 EEC。

* [移动设备视区](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) 支持，即使没有 [!UICONTROL Enhanced Experience Composer] (EEC)。
* 对于 [!DNL Target] 的新客户，即便在其 IT 开发人员尚未在其网站上实施 [!DNL Target] 的情况下，也可以使用此扩展来试用 [!DNL Target]。
* 服务于多个客户网站和 [!DNL Target] 帐户的合作伙伴现在有一个简单的机制来支持 VEC 加载，而不用通过第三方工具管理多个规则。

## 获取并安装 [!UICONTROL Visual Editing Helper] 浏览器扩展

1. 导航至 [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] Chrome网络商店中的浏览器扩展](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}.
1. 单击 **[!UICONTROL Add to Chrome]** > **[!UICONTROL Add Extension]**.
1. 打开 [!DNL Target] 中的 VEC。
1. 要使用扩展，请单击 [!UICONTROL Visual Editing Helper] 浏览器扩展图标( ![“可视化编辑扩展”图标](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/visual-editing-helper.png) )时，在浏览器工具栏中单击（例如，在VEC或QA模式下）。

   此 [!UICONTROL Visual Editing Helper] 在中打开网站时自动启用 [!UICONTROL Target] VEC支持创作。 该扩展不具有任何有条件的设置。该扩展会自动处理所有设置，包括 SameSite cookie 设置。

   若要了解有关`SameSite=None`属性浏览器修复的更多信息，请参阅“最近公布的 Google Chrome SameSite Cookie 强制执行政策对 VEC 和 EEC 有什么影响？”（在[排除与可视体验编辑器和增强体验编辑器相关的问题](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md)中）。

## 注释

* 对象 [!DNL Target]，该扩展将加载最新版本的at.js，该版本可从 [!DNL Target] 中的UI [!UICONTROL Administration] > [!UICONTROL Implementation] 和at.js会下载创作库。
* 当在 [QA 模式](/help/main/c-activities/c-activity-qa/activity-qa.md)下使用扩展插入 at.js 时，必须打开另一个 Chrome 选项卡。此 Chrome 选项卡必须经过创建活动所在[!DNL Adobe Experience Cloud]组织的身份验证。
* 以下消息有助于您随时了解以下情况：

   * 如果尝试使用无法加载的VEC加载网站，系统会显示一条消息，建议您安装 [!UICONTROL Visual Editing Helper] 浏览器扩展。
   * 如果网站上尚未实施 at.js 或 alloy.js，则 VEC 中将显示一条消息，建议您安装扩展。
* 如果尝试使用新扩展，然后改回[旧扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)，而 [!DNL Target] 未能加载您的网站，请清除所有浏览器数据并禁用新扩展。

## 常见问题解答

### 当扩展在外部使用时，处于活动状态时会执行任何操作 [!DNL Adobe Target] 或 [!UICONTROL Adobe Journey Optimizer] (AJO)？

只有当相关网站加载到 [!DNL Adobe] 产品（[!DNL Target]、[!DNL AJO]）的 iFrame 中时，该扩展程序才会激活。在此流程之外，扩展程序不会尝试添加、删除或修改任何标头，并且扩展程序不会尝试在网站内注入任何代码。

### 当扩展在 [!DNL Adobe Target] VEC 中处于活动状态时会做什么？

当网站加载到 [!DNL Adobe] 产品（[!DNL Target]、[!DNL AJO]）的 iFrame 中时，扩展程序会在网站上注入代码（与扩展程序捆绑在一起）并下载来自 [!DNL Adobe] CDN 的帮助文件，以启用可视化创作。
