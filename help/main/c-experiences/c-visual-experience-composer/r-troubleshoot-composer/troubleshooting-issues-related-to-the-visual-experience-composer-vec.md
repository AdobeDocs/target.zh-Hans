---
keywords: 定位；可视化体验编辑器；VEC；可视化体验编辑器故障诊断；故障诊断；TLS;TLS 1.2
description: 了解如何对Adobe中有时出现的问题进行故障诊断 [!DNL Target] 可视化体验编辑器(VEC)。
title: 如何对与可视化体验编辑器有关的问题进行故障诊断？
feature: Visual Experience Composer (VEC)
exl-id: ca251025-25e8-4e56-9b59-81310fc763c1
source-git-commit: 3d2dec3d897e98be84e8a46c5d5bd274615f46bc
workflow-type: tm+mt
source-wordcount: '971'
ht-degree: 68%

---

# 排除与可视化体验编辑器相关的问题

有时， [!DNL Adobe Target] [!UICONTROL 可视化体验编辑器] (VEC)。

## 当我在可视化体验编辑器中打开我的网站时， [!DNL Target] 库不会加载。 （仅 VEC） {#section_8A7D3F4AD2CC4C3B823EE9432B97E06F}

在可视化体验编辑器中打开网站时，Target 会添加两个参数（`mboxEdit=1` 和 `mboxDisable=1`）。

如果您的网站（特别是单页应用程序）裁切掉我们的参数，或者在从一个页面导航到另一个页面（不重新加载页面）时将它们实际删除，则 Target 功能会损坏并且 Target 库不会加载。为避免出现此问题，请确保不要裁切掉或删除这两个参数。

## 我的页面无法在 EEC 中打开，或者加载速度缓慢。活动或体验在 VEC 中的加载速度缓慢。（仅 VEC） {#section_71E7601BE9894E3DA3A7FBBB72B6B0C1}

有几个问题会影响 Target 体验编辑器中的页面性能。一些常见的问题包括：

* 您的页面上没有 mbox。
* 您的网站使用了代理阻止，该功能不允许在任一体验编辑器中打开页面。
* 您的网站不允许在 iFrame 中自行打开。

如果增强型体验编辑器中出现这些问题，请尝试关闭增强型体验编辑器并改用可视化体验编辑器。

要禁用增强型体验编辑器，请转到 **[!UICONTROL 管理]** > **[!UICONTROL 可视化体验编辑器]** 关掉 **[!UICONTROL 启用增强型体验编辑器]** 选项。

某些用户会在控制台中看到以下错误消息：

![控制台错误消息](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/console_error_message.jpg)

如果可视化体验编辑器和增强型体验编辑器均无法使用，请使用浏览器扩展程序，如 Requestly（Chrome 或 Firefox）或 Modify Response Headers (Firefox)，这些扩展程序可以覆盖您网站的 X-Frames 标头选项并允许它们在 iFrames 中加载，从而启用 VEC。如果您无法使用浏览器扩展程序，请使用表单编辑器。

>[!NOTE]
>
>除了以下信息外，您还可以使用适用于 Google Chrome 的 [Adobe Target VEC 助手浏览器扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)。


>[!NOTE]
>
>以下插件仅应在 VEC 编辑上下文中使用。
>
>对于 Requestly 扩展，每当需要删除标头时，您都应该执行以下任一操作：
>
>* 为要在 VEC 中打开的 URL 添加 URL 规则，以便仅删除这些 URL 的标头。
>
>* 在 VEC 中进行编辑时启用该规则，而在不使用 VEC 时禁用该规则。
>
>对于 Modify Response Header (Firefox) 扩展，因为您无法添加 URL 规则，您必须执行以下操作：
>
>* 在 VEC 中进行编辑时启用该规则，而在不使用 VEC 时禁用该规则。


**在 Chrome 或 Firefox 上使用 Requestly 扩展程序：**

1. 关闭增强型体验编辑器。
1. 在 Chrome 或 Firefox 上安装 Requestly 浏览器扩展程序。
1. 打开该扩展程序，并执行以下操作以对其进行配置：
1. 选择&#x200B;**[!UICONTROL 修改标头]**。
1. 输入以下内容：

   * 规则名称
   * 修改规则

      * 将&#x200B;**[!UICONTROL 添加]**&#x200B;切换为&#x200B;**[!UICONTROL 删除]**。
      * 将&#x200B;**[!UICONTROL 请求]**&#x200B;切换为&#x200B;**[!UICONTROL 响应]**。
      * 输入“X-Frame-Options”作为标头名称。
      * 重复执行上述步骤，输入“x-frame-options”作为标头名称。

         >[!NOTE]
         >
         >通过 Requestly 处理的标头区分大小写。

      * 将&#x200B;**[!UICONTROL 等于]**&#x200B;更改为&#x200B;**[!UICONTROL 包含]**&#x200B;以作为源 URL 的条件，并输入您尝试在 VEC 中加载的活动的 URL。

      ![chrome_extension图像](assets/chrome_extension.png)


1. 单击&#x200B;**[!UICONTROL 保存]**。

   ![请求图像](assets/requestly.png)

   现在，您应当能够使用可视化体验编辑器快速加载页面。

**在 Firefox 上使用 Modify Response Headers 扩展程序：**

1. 在 Firefox 上安装 Modify Response Headers，然后重新启动浏览器。
1. 从 Firefox 扩展程序中，选择 Modify Response Headers 扩展程序。
1. 单击&#x200B;**[!UICONTROL 首选项]**。
1. 从“操作”下拉菜单中选择&#x200B;**[!UICONTROL 筛选器]**。
1. 在“标头名称”字段中，输入：**[!UICONTROL X-Frame-Options]**。
1. 重复执行步骤 4 和 5，添加一个使用 **[!UICONTROL x-frame-options]** 的筛选器。
1. 单击&#x200B;**[!UICONTROL 添加]**。
1. 单击&#x200B;**[!UICONTROL 开始]**。

![firefox_extension图像](assets/firefox_extension.png)

设置扩展程序后，打开 Target。即使禁用了增强型体验编辑器，您的页面现在也应当能够在可视化体验编辑器中加载。

## VEC 中不显示我的页面（仅 VEC） {#does-not-load}

* 浏览器不受支持。
* 浏览器阻止安全网站上的不安全页面。

   请单击浏览器地址栏中 URL 左侧的图标，然后再单击&#x200B;**[!UICONTROL 在此页面上禁用保护]**
* 您输入了无效的 URL。
* 您尚未在帐户设置页面中输入默认 URL。

   确保已启用此设置，然后在您的网站上下载并更新at.js。

* 如果您尝试使用 [新建 [!UICONTROL 可视化编辑助手] 扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) 然后回到 [旧扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) 和 [!DNL Target] 无法加载您的网站、清除所有浏览器数据并禁用新扩展。

* 如果您的网站无法在VEC中加载，或者行为异常，则可能的修复是：在尝试在中加载网站之前，先在浏览器中接受您网站上的Cookie [!DNL Target].

## 使用浏览模式时，VEC 显示已损坏。（仅 VEC） {#section_FA2A18E8FD6A4274B2E395DBAA2FB407}

在使用浏览模式时，如果您访问的URL没有 [!DNL Target] 已实施的库([at.js](https://developer.adobe.com/target/implement/client-side/){target=_blank} or [Adobe Experience Platform Web SDK](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/){target=_blank})或包含frame-buster标头时，VEC显示为已损坏。 出于对浏览器安全性的考虑， [!DNL Target] 无法正确访问您导航到的URL，或者如果页面加载，VEC URL不会持续更新。

出现此问题的原因是VEC在 `<iframe>`. 浏览器的当前安全机制会阻止 [!DNL Target] UI访问给定帧的元素，因为存在相同原点策略。 浏览器会阻止尝试访问具有不同原点且包含以下信息的框架的脚本 `location.href`.

您必须使用新 [Visual Editing Helper扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) （推荐）或 [旧扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) 注入 [!DNL Target] 库添加到页面中，以便以最佳方式浏览页面。
