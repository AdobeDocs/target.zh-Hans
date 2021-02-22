---
keywords: 混合内容；安全；不安全；chrome；疑难解答；vec；可视体验编辑器；不安全；http;https;firefox;internet explorer
description: 如果安全内容与不安全内容混合在一起，某些浏览器可能会阻止页面显示。了解如何在Chrome、Firefox和Edge中启用混合内容。
title: 如何在浏览器中启用混合内容？
feature: 可视化体验编辑器 (VEC)
translation-type: tm+mt
source-git-commit: 453106f7534f83c205722421bbf00044fde7da67
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 26%

---


# 在浏览器中启用混合内容

如果初始请求通过HTTPS是安全的，但加载了HTTPS *和* HTTP内容以显示网页，则混合内容会发生。 HTTPS内容是安全的。 HTTP内容不安全。

如果安全内容与不安全内容混合在一起，现代浏览器可能会阻止页面显示或显示警告消息。

如果[!DNL Target]中的[!UICONTROL 可视体验书写器](VEC)尝试打开包含混合内容的页面，则会显示一条警告消息。 此消息会通知您如何在浏览器中禁用阻止。 禁用阻止功能可让您打开HTTP站点或具有混合调用（HTTPS和HTTP）的站点。

![混合内容警告](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/mixed_content_warning.png)

以前，虽然不允许使用混合内容，但是您在创建活动时仍然能够执行三步引导式工作流的步骤 1 中的某些操作。[!DNL Target]现在， 会阻止执行步骤 1 中的操作。显示此消息时，必须先启用混合内容，然后才能继续创建活动。

浏览器的安全设置可能会阻止将混合内容或不安全 (HTTP) 内容加载到安全 (HTTPS) 页面或框架（例如 VEC）。如果您不想禁用浏览器的安全设置，则必须有HTTPS网站。

如果您的网站在不安全(HTTP)域上运行，则需要允许VEC加载活动混合内容。

>[!NOTE]
>
>允许混合内容仅会对 VEC 造成影响，而不会影响您已上线的网站。

有关更多信息，请参阅“Mozilla 开发人员网络”**(MDN) 网站上的[混合内容](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content)。

## 在Google Chrome中启用混合内容{#task_FF297A08F66E47A588C14FD67C037B3A}

如果您通过安全连接访问站点，Chrome将验证网页上的内容是否已安全传输。

请参阅Google Chrome帮助中的“[此页面具有不安全的内容](https://support.google.com/chrome/answer/1342714?hl=en)”。

如果要将VEC与最新版Chrome（版本79.0.3945.117或更高版本）一起使用，则必须更新站点设置。 访客访问您的站点无需完成这些步骤。

1. 单击锁（警告）图标，然后单击&#x200B;**[!UICONTROL 站点设置]**。

   ![站点设置](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. 滚动到&#x200B;**[!UICONTROL Insecure content]**，然后使用下拉列表将“Block(default)”更改为“Allow”。

   ![不安全的内容](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)

1. 重新加载VEC页。

## 在Mozilla Firefox {#task_5448763B8DC941FD80F84041AEF0A14D}中启用混合内容

默认情况下，Firefox 会阻止包含混合（安全和不安全）内容的页面。建议您永久更改此设置以便使用 [!DNL Target]。访客访问您的站点无需完成这些步骤。

1. 在 Firefox 的地址栏中输入 `about:config`。
1. 确认 Firefox 显示的警告消息。

   ![Firefox警告](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox.png)

1. 在搜索栏中，键入 `block_active`。

   ![Firefox block_active设置](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox3.png)

1. 双击 ` **[!UICONTROL security.mixed_content.block_active_content]**`。

   其值随即会从“True”更改为“False”。当值显示为“False”时，即表示操作已完成。

   ![Firefox安全性](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox2.png)

更改此设置后，重新启动计算机。

## 在Microsoft Edge中启用混合内容

如果您通过安全连接访问站点，Edge会验证网页上的内容是否已安全传输。

如果您正在将VEC与最新版Edge一起使用，则必须更新站点设置。 访客访问您的站点无需完成这些步骤。

1. 单击锁（警告）图标，然后单击&#x200B;**[!UICONTROL 站点权限]**。

   ![Microsoft Edge中的站点权限](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge.png)

1. 滚动到&#x200B;**[!UICONTROL Insecure content]**，然后使用下拉列表将“Block(default)”更改为“Allow”。

   ![不安全的内容](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge-2.png)

1. 重新加载VEC页。