---
keywords: VEC;可视化体验编辑器;VEC;iframe;扩展;浏览器
description: 了解为什么某些网站可能无法在 [!UICONTROL 可视化体验编辑器] (VEC)。 的 [!UICONTROL 可视化编辑助手] 通过浏览器扩展，您可以在VEC内可靠地加载网站。
title: 如何使用 [!UICONTROL 可视化编辑助手] 扩展？
feature: Visual Experience Composer (VEC)
source-git-commit: 70ab1ec7f5313d8c1f8ecaa9b436d95919cf479a
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 28%

---

# [!UICONTROL 可视化编辑助手] 扩展

的 [!DNL Adobe Experience Cloud] [!UICONTROL 可视化编辑助手] 适用于Google Chrome的浏览器扩展允许您在 [!UICONTROL Adobe Target] [!UICONTROL 可视化体验编辑器] (VEC)快速创作和QA Web体验。

>[!IMPORTANT]
>
>此新扩展取代了 [Target VEC助手浏览器扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md).

## 某些网站可能无法在VEC中可靠打开的原因

* 网站具有严格的安全策略。
* 网站位于 iframe 中。
* 客户的QA或阶段网站不适用于外部环境（网站是内部网站）。

的 [!DNL Adobe Experience Cloud] [!UICONTROL 可视化编辑助手] 适用于Chrome的浏览器扩展可解决网站加载问题，而客户现在依赖这些问题 [!DNL Target] [增强型体验编辑器](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) 或第三方扩展，如Requestly。

## 使用 [!UICONTROL 可视化编辑助手] 扩展

* 所有防iframe嵌套标头，例如 `X-Frame-Options` 和 `Content-Security-Policy`，则会从网站中隐式删除。 无需创建复杂的Requestly规则。
* 如果网页尚未包含 [!DNL Target] at.js 库，您可以使用该扩展来插入库，这样您便可以为该网站创作体验。然后，您可以创建活动并使用预览链接进行 QA。

请注意，使用 [增强型体验编辑器](/help/main/administrating-target/visual-experience-composer-set-up.md#eec)，则扩展不会插入at.js，但仍然存在SameSite Cookie功能。 要在网页上注入at.js，请关闭EEC。

* [移动设备视区](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) 即使没有 [!UICONTROL 增强型体验编辑器] (EEC)。
* 对于 [!DNL Target] 的新客户，即便在其 IT 开发人员尚未在其网站上实施 [!DNL Target] 的情况下，也可以使用此扩展来试用 [!DNL Target]。
* 服务于多个客户网站和 [!DNL Target] 帐户的合作伙伴现在有一个简单的机制来支持 VEC 加载，而不用通过第三方工具管理多个规则。

## 获取并安装 [!UICONTROL 可视化编辑助手] 浏览器扩展

1. 导航到 [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] Chrome网上应用店中的浏览器扩展](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}。
1. 单击 **[!UICONTROL 添加到Chrome]** > **[!UICONTROL 添加扩展]**.
1. 在中打开VEC [!DNL Target].
1. 要使用该扩展，请单击 [!UICONTROL 可视化编辑助手] 浏览器扩展图标( ![“可视化编辑扩展”图标](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/visual-editing-helper.png) )来访问Advertising Cloud的帮助。

   的 [!UICONTROL 可视化编辑助手] 在 [!UICONTROL Target] 通过VEC进行创作。 扩展没有任何条件设置。 该扩展会自动处理所有设置，包括SameSite Cookie设置。

   有关 `SameSite=None` 属性浏览器修复，请参阅“最近宣布的Google Chrome SameSite Cookie实施策略对VEC和EEC有何影响？” （在[排除与可视体验编辑器和增强体验编辑器相关的问题](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md)中）。

## 注释

* 对于 [!DNL Target]，则扩展会加载最新版本的at.js(可从 [!DNL Target] 中的UI [!UICONTROL 管理] > [!UICONTROL 实施] 和at.js会下载创作库。
* 当在 [QA 模式](/help/main/c-activities/c-activity-qa/activity-qa.md)下使用扩展插入 at.js 时，必须打开另一个 Chrome 选项卡。此Chrome选项卡必须通过同一Chrome选项卡的身份验证 [!DNL Adobe Experience Cloud] 创建活动的组织。
* 以下消息有助于您随时了解以下情况：

   * 如果您尝试使用加载失败的VEC来加载网站，则会显示一条消息，建议您安装 [!UICONTROL 可视化编辑助手] 浏览器扩展。
   * 如果尚未在网站上实施at.js或alloy.js，则VEC中会显示一条消息，建议您安装扩展。

## 有关此功能的更多帮助

* [对与可视化体验编辑器和增强型体验编辑器有关的问题进行故障诊断](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md)
* [对与可视化体验编辑器有关的问题进行故障诊断](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-visual-experience-composer-vec.md)
* [对与增强型体验编辑器有关的问题进行故障诊断](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md)



