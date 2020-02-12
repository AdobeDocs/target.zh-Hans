---
keywords: mixed content;secure;insecure;chrome;troubleshooting;vec;visual experience composer;unsecure
description: 如果安全内容与不安全内容混合在一起，某些浏览器可能会阻止页面显示。
title: 在浏览器中启用混合内容
topic: Advanced,Standard,Classic
uuid: 6944ce97-ff73-4b61-b006-35862ff83ef1
translation-type: tm+mt
source-git-commit: 65a4fd0d05ad065c9291a83dc0b3066451f7373e

---


# Enabling mixed content in your browser{#enabling-mixed-content-in-your-browser}

如果安全内容与不安全内容混合在一起，某些浏览器可能会阻止页面显示。

如果可视化体验编辑器 (VEC) 尝试打开包含混合（安全和不安全）内容的页面，系统会显示一条消息，告知您如何禁用浏览器中的阻止功能，以便打开 HTTP 网站或包含混合调用（HTTPS 和 HTTP）的网站。

![](assets/mixed_content_warning.gif)

以前，虽然不允许使用混合内容，但是您在创建活动时仍然能够执行三步引导式工作流的步骤 1 中的某些操作。现在，Target 会阻止执行步骤 1 中的操作。显示此消息时，您必须先启用混合内容，然后才能继续操作。

浏览器的安全设置可能会阻止将混合内容或不安全 (HTTP) 内容加载到安全 (HTTPS) 页面或框架（例如 VEC）。如果您不希望禁用浏览器的安全设置，则需要使用 HTTPS 网站。

如果您的网站在不安全的域（即 HTTP 域）上运行，您需要允许 VEC 加载活跃的混合内容。

>[!NOTE]
>
>允许混合内容仅会对 VEC 造成影响，而不会影响您已上线的网站。

有关更多信息，请参阅“Mozilla 开发人员网络”**(MDN) 网站上的[混合内容](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content)。

## Enabling mixed content in Google Chrome {#task_FF297A08F66E47A588C14FD67C037B3A}

如果您通过安全连接访问网站，Google Chrome 会验证网页上的内容是否已安全传输。

请参阅 Google Chrome 帮助中的[此页面包含不安全的内容](https://support.google.com/chrome/answer/1342714?hl=en)。

### 培训视频：在Chrome版本79.0.3945.117或更高版本（2020年1月）中启用VEC ![概述徽章](/help/assets/overview.png)

如果您将VEC与最新版Chrome（版本79.0.3945.117或更高版本）结合使用，则需要更新站点设置。 您网站的访客无需完成这些步骤。

>[!VIDEO](https://www.youtube.com/watch?v=6zGCi5Y8eVo)

以上视频概述了所需的步骤：

1. 单击锁定或警告图标，然后单击站点设置。

   ![站点设置](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. 滚动到Insecure内容，然后使用下拉列表将块（默认）更改为允许。

   ![不安全的内容](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)

1. 重新加载VEC页面。

## Enabling mixed content in Mozilla Firefox {#task_5448763B8DC941FD80F84041AEF0A14D}

默认情况下，Firefox 会阻止包含混合（安全和不安全）内容的页面。建议您永久更改此设置以便使用 [!DNL Target]。

1. 在 Firefox 的地址栏中输入 `about:config`。
1. 确认 Firefox 显示的警告消息。
1. 在搜索栏中，键入 `block_active`。
1. 双击 ` **[!UICONTROL security.mixed_content.block_active_content]**`。

   其值随即会从“True”更改为“False”。当值显示为“False”时，即表示操作已完成。建议您在更改此设置后重新启动计算机。

## Enabling mixed content in Microsoft Internet Explorer {#task_59E7D13C04DF486C92CD78D0C63DDDE8}

默认情况下，Internet Explorer 会阻止包含混合（安全和不安全）内容的页面。建议您永久更改此设置以便使用 Target。

1. 在 Internet Explorer 中，单击“设置”图标，然后单击 **[!UICONTROL Internet 选项]**。
1. 打开“[!UICONTROL 安全]”选项卡。
1. 选择 **[!UICONTROL Internet]**，然后单击&#x200B;**[!UICONTROL 自定义级别]**。
1. 选择&#x200B;**[!UICONTROL 其他]**。
1. 在[!UICONTROL 其他]下方，启用&#x200B;**[!UICONTROL 显示混合内容]**。
1. 单击&#x200B;**[!UICONTROL 确定]** > **[!UICONTROL 是]** > **[!UICONTROL 应用]**。

我们建议您在更改此设置后重新启动计算机。

