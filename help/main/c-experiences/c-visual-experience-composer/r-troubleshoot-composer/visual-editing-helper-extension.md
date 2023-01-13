---
keywords: VEC;可视化体验编辑器;VEC;iframe;扩展;浏览器;faq
description: 了解为什么某些网站可能无法在[!UICONTROL 可视化体验编辑器 (VEC) ]中以可靠的方式打开。[!UICONTROL 可视化体验编辑器]浏览器扩展允许您在 VEC 中以可靠的方式加载网站。
title: 如何使用[!UICONTROL 可视化编辑帮助程序]扩展？
feature: Visual Experience Composer (VEC)
exl-id: e5aeb8b9-fab5-4ad4-882e-2106d2c9daab
source-git-commit: 30ad6712d9722854384721ca20d38a605930c4d7
workflow-type: tm+mt
source-wordcount: '712'
ht-degree: 83%

---

# [!UICONTROL 可视化编辑帮助程序]扩展

Google Chrome 的[!DNL Adobe Experience Cloud][!UICONTROL 可视化编辑帮助程序]浏览器扩展允许您在 [!UICONTROL Adobe Target][!UICONTROL  可视化体验编辑器 (VEC)] 中以可靠的方式加载网站，以便快速创作和管控 web 体验。

>[!IMPORTANT]
>
>新的扩展取代了以前的 [Target VEC 帮助程序浏览器扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)。请参阅该文章顶部的重要说明。

## 为什么某些网站可能无法在可视化体验编辑器 (VEC) 中以可靠的方式打开

* 网站具有严格的安全策略。
* 网站位于 iframe 中。
* 外部无法访问客户的 QA 或阶段站点（该站点为内部站点）。

针对 Chrome 的[!DNL Adobe Experience Cloud][!UICONTROL 可视化编辑帮助程序]浏览器扩展解决了客户现在依赖于[!DNL Target][增强型体验编辑器](/help/main/administrating-target/visual-experience-composer-set-up.md#eec)或第三方扩展（如 Requestly）的站点加载问题。

## 使用[!UICONTROL 可视化编辑帮助程序]扩展的益处

* 隐含地从网站中删除所有令 iframe 失效的标头，如 `X-Frame-Options` 和 `Content-Security-Policy`。没有必要创建复杂的 Requestly 规则。
* 如果网页尚未包含 [!DNL Target] at.js 库，您可以使用该扩展来插入库，这样您便可以为该网站创作体验。然后，您可以创建活动并使用预览链接进行 QA。

   使用[增强型体验编写器](/help/main/administrating-target/visual-experience-composer-set-up.md#eec)时，扩展未注入 at.js，但仍存在 SameSite Cookie 功能。要在网页上插入 at.js，请关闭 EEC。

* 即使没有[!UICONTROL 增强型体验编写器 (EEC)]，也支持[移动视口](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md)。
* 对于 [!DNL Target] 的新客户，即便在其 IT 开发人员尚未在其网站上实施 [!DNL Target] 的情况下，也可以使用此扩展来试用 [!DNL Target]。
* 服务于多个客户网站和 [!DNL Target] 帐户的合作伙伴现在有一个简单的机制来支持 VEC 加载，而不用通过第三方工具管理多个规则。

## 获得并安装[!UICONTROL 可视化编辑帮助程序]浏览器扩展

1. 导航至[[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper]  Chrome 网络商店中的浏览器扩展](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}.
1. 点击&#x200B;**[!UICONTROL 添加至 Chrome]** > **[!UICONTROL 添加扩展。]**
1. 打开 [!DNL Target] 中的 VEC。
1. 要使用扩展，请在 VEC 或 QA 模式下，单击 Chrome 浏览器工具栏中的[!UICONTROL 可视化编辑帮助程序]浏览器扩展图标（![可视化编辑扩展图标](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/visual-editing-helper.png)）。

   当在目标 [!UICONTROL Target] 中打开网站以进行创作时，会自动启用[!UICONTROL 可视化编辑帮助程序]。该扩展不具有任何有条件的设置。该扩展会自动处理所有设置，包括 SameSite cookie 设置。

   若要了解有关`SameSite=None`属性浏览器修复的更多信息，请参阅“最近公布的 Google Chrome SameSite Cookie 强制执行政策对 VEC 和 EEC 有什么影响？”（在[排除与可视体验编辑器和增强体验编辑器相关的问题](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md)中）。

## 注释

* 对于 [!DNL Target]，扩展插件会加载[!UICONTROL “管理”]>[!UICONTROL “实现”]中 [!DNL Target]UI 内可用的最新版本的 at.js，而 at.js 则会下载创作库。
* 当在 [QA 模式](/help/main/c-activities/c-activity-qa/activity-qa.md)下使用扩展插入 at.js 时，必须打开另一个 Chrome 选项卡。此 Chrome 选项卡必须经过创建活动所在[!DNL Adobe Experience Cloud]组织的身份验证。
* 以下消息有助于您随时了解以下情况：

   * 如果尝试使用无法加载的 VEC 加载网站，系统会显示一条消息，建议您安装[!UICONTROL 可视化编辑帮助程序]浏览器扩展。
   * 如果网站上尚未实施 at.js 或 alloy.js，则 VEC 中将显示一条消息，建议您安装扩展。
* 如果尝试使用新扩展，然后改回[旧扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)，而 [!DNL Target] 未能加载您的网站，请清除所有浏览器数据并禁用新扩展。

## 常见问题解答

### 该扩展在处于活动状态时，在以外使用时，会执行任何操作 [!DNL Adobe Target] 或 [!UICONTROL Adobe Journey Optimizer] (AJO)?

仅当相关网站在iFrame中加载时，该扩展才会激活 [!DNL Adobe] 产品([!DNL Target], [!DNL AJO])。 在此流程之外，扩展不会尝试添加、删除或修改任何标头，并且扩展也不会尝试在网站中插入任何代码。

### 扩展在中处于活动状态时会执行哪些操作 [!DNL Adobe Target] VEC?

当网站加载到 [!DNL Adobe] 产品([!DNL Target], [!DNL AJO])，扩展在网站上插入代码（与扩展捆绑在一起），并从下载帮助程序文件 [!DNL Adobe] CDN以启用可视化创作。
