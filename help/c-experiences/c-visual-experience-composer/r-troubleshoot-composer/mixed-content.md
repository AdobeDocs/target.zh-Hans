---
keywords: mixed content;secure;insecure;chrome;troubleshooting;vec;visual experience composer;unsecure;http;https;firefox;internet explorer
description: 如果安全内容与不安全内容混合在一起，某些浏览器可能会阻止页面显示。
title: 在浏览器中启用混合内容
feature: null
topic: Advanced,Standard,Classic
uuid: 6944ce97-ff73-4b61-b006-35862ff83ef1
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 35%

---


# Enabling mixed content in your browser{#enabling-mixed-content-in-your-browser}

如果加载HTTPS（安全）和 *HTTP* （不安全）内容以显示同一网页，并且初始请求通过HTTPS是安全的，则混合内容会发生。

如果安全内容与不安全内容混合在一起，新式浏览器可能会阻止显示页面或显示警告消息。

If the [!UICONTROL Visual Experience Composer] (VEC) in [!DNL Target] tries to open a page containing mixed content, a message displays showing how to disable blocking in your browser so you can open an HTTP site or a site that has mixed calls (HTTPS and HTTP).

![混合内容警告](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/mixed_content_warning.png)

以前，虽然不允许使用混合内容，但是您在创建活动时仍然能够执行三步引导式工作流的步骤 1 中的某些操作。[!DNL Target]现在， 会阻止执行步骤 1 中的操作。显示此消息时，必须先启用混合内容，然后才能继续创建活动。

浏览器的安全设置可能会阻止将混合内容或不安全 (HTTP) 内容加载到安全 (HTTPS) 页面或框架（例如 VEC）。如果您不希望禁用浏览器的安全设置，则需要使用 HTTPS 网站。

如果您的网站在不安全的域（即 HTTP 域）上运行，您需要允许 VEC 加载活跃的混合内容。

>[!NOTE]
>
>允许混合内容仅会对 VEC 造成影响，而不会影响您已上线的网站。

有关更多信息，请参阅“Mozilla 开发人员网络”**(MDN) 网站上的[混合内容](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content)。

## Enabling mixed content in Google Chrome {#task_FF297A08F66E47A588C14FD67C037B3A}

如果您通过安全连接访问网站，Chrome将验证网页上的内容是否已安全传输。

请参阅 Google Chrome 帮助中的[此页面包含不安全的内容](https://support.google.com/chrome/answer/1342714?hl=en)。

如果您将VEC与最新版Chrome（版本79.0.3945.117或更高版本）一起使用，则需要更新站点设置。 访客访问您的站点无需完成这些步骤。

1. 单击锁定或警告图标，然后单击“站 **[!UICONTROL 点设置”]**。

   ![站点设置](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. 滚动到 **[!UICONTROL 不安全的内]**&#x200B;容，然后使用下拉列表将“Block(default)”更改为“Allow”。

   ![不安全的内容](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)

1. 重新加载VEC页面。

## Enabling mixed content in Mozilla Firefox {#task_5448763B8DC941FD80F84041AEF0A14D}

默认情况下，Firefox 会阻止包含混合（安全和不安全）内容的页面。建议您永久更改此设置以便使用 [!DNL Target]。访客访问您的站点无需完成这些步骤。

1. 在 Firefox 的地址栏中输入 `about:config`。
1. 确认 Firefox 显示的警告消息。

   ![Firefox警告](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox.png)

1. 在搜索栏中，键入 `block_active`。

   ![Firefox阻止活动设置](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox3.png)

1. 双击 ` **[!UICONTROL security.mixed_content.block_active_content]**`。

   其值随即会从“True”更改为“False”。当值显示为“False”时，即表示操作已完成。

   ![Firefox安全性](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox2.png)

我们建议您在更改此设置后重新启动计算机。

## 在Microsoft Edge中启用混合内容

如果您通过安全连接访问站点，Edge会验证网页上的内容是否已安全传输。

如果您正在将VEC与最新版Edge结合使用，则需要更新站点设置。 访客访问您的站点无需完成这些步骤。

1. 单击锁定或警告图标，然后单击“站 **[!UICONTROL 点权限”]**。

   ![Microsoft Edge中的站点权限](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge.png)

1. 滚动到 **[!UICONTROL 不安全的内]**&#x200B;容，然后使用下拉列表将“Block(default)”更改为“Allow”。

   ![不安全的内容](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge-2.png)

1. 重新加载VEC页面。