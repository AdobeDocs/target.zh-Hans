---
keywords: 混合内容；安全；不安全；chrome；故障诊断；VEC；可视化体验编辑器；不安全；HTTP;HTTPS;Firefox;Internet Explorer
description: 如果安全内容与不安全内容混合在一起，某些浏览器可能会阻止页面显示。了解如何在Chrome、Firefox和Edge中启用混合内容。
title: 如何在浏览器中启用混合内容？
feature: Visual Experience Composer (VEC)
exl-id: a2209af6-65e5-427e-b2cb-53b803728ef3
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 26%

---

# 在浏览器中启用混合内容

如果初始请求通过HTTPS安全，但HTTPS安全，则会出现混合内容 *和* 加载HTTP内容以显示网页。 HTTPS内容是安全的。 HTTP内容不安全。

如果安全内容与不安全内容混合在一起，现代浏览器可能会阻止页面显示或显示警告消息。

如果 [!UICONTROL 可视化体验编辑器] (VEC) [!DNL Target] 尝试打开包含混合内容的页面。 此消息会通知您如何禁用浏览器中的阻止功能。 禁用阻止功能可打开HTTP站点或具有混合调用（HTTPS和HTTP）的站点。

![混合内容警告](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/mixed_content_warning.png)

以前，虽然不允许使用混合内容，但是您在创建活动时仍然能够执行三步引导式工作流的步骤 1 中的某些操作。[!DNL Target]现在， 会阻止执行步骤 1 中的操作。显示此消息时，您必须先启用混合内容，然后才能继续创建活动。

浏览器的安全设置可能会阻止将混合内容或不安全 (HTTP) 内容加载到安全 (HTTPS) 页面或框架（例如 VEC）。如果您不想禁用浏览器的安全设置，则必须拥有HTTPS网站。

如果您的网站在不安全(HTTP)域上运行，则需要允许VEC加载活动的混合内容。

>[!NOTE]
>
>允许混合内容仅会对 VEC 造成影响，而不会影响您已上线的网站。

有关更多信息，请参阅“Mozilla 开发人员网络”**(MDN) 网站上的[混合内容](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content)。

## 在Google Chrome中启用混合内容 {#task_FF297A08F66E47A588C14FD67C037B3A}

如果您通过安全连接访问网站，Chrome会验证网页上的内容是否已安全传输。

请参阅“[此页面包含不安全的内容](https://support.google.com/chrome/answer/1342714?hl=en)”中的“URL”。

如果您将VEC与最新版本的Chrome（版本79.0.3945.117或更高版本）一起使用，则必须更新网站设置。 您网站的访客无需完成这些步骤。

1. 单击锁（警告）图标，然后单击 **[!UICONTROL 网站设置]**.

   ![网站设置](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. 滚动到 **[!UICONTROL 不安全的内容]**，然后使用下拉列表将“块（默认）”更改为“允许”。

   ![不安全的内容](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)

1. 重新加载VEC页面。

## 在Mozilla Firefox中启用混合内容 {#task_5448763B8DC941FD80F84041AEF0A14D}

默认情况下，Firefox 会阻止包含混合（安全和不安全）内容的页面。建议您永久更改此设置以便使用 [!DNL Target]。您网站的访客无需完成这些步骤。

1. 在 Firefox 的地址栏中输入 `about:config`。
1. 确认 Firefox 显示的警告消息。

   ![Firefox警告](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox.png)

1. 在搜索栏中，键入 `block_active`。

   ![Firefoxblock_active设置](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox3.png)

1. 双击 ` **[!UICONTROL security.mixed_content.block_active_content]**`。

   其值随即会从“True”更改为“False”。当值显示为“False”时，即表示操作已完成。

   ![Firefox安全](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox2.png)

更改此设置后重新启动计算机。

## 在Microsoft Edge中启用混合内容

如果您通过安全连接访问网站，Edge会验证网页上的内容是否已安全传输。

如果您将VEC与最新版本的Edge一起使用，则必须更新网站设置。 您网站的访客无需完成这些步骤。

1. 单击锁（警告）图标，然后单击 **[!UICONTROL 网站权限]**.

   ![Microsoft Edge中的网站权限](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge.png)

1. 滚动到 **[!UICONTROL 不安全的内容]**，然后使用下拉列表将“块（默认）”更改为“允许”。

   ![不安全的内容](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge-2.png)

1. 重新加载VEC页面。
