---
keywords: 混合内容;安全;不安全;chrome;故障排除;vec;可视体验编辑器;不安全;http;https;firefox;internet explorer
description: 了解如何在中启用混合内容 [!DNL Chrome]， [!DNL Firefox]、和 [!DNL Edge].
title: 如何在我的浏览器中启用混合内容
feature: Visual Experience Composer (VEC)
exl-id: a2209af6-65e5-427e-b2cb-53b803728ef3
source-git-commit: c5b43faa2fc55c2c8737e586cfdfaa1444a05880
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 64%

---

# 在浏览器中启用混合内容

如果初始请求通过 HTTPS 安全地发出，但加载了 HTTPS *和* HTTP 内容以显示网页，则会出现混合内容。HTTPS 内容是安全的。HTTP 内容是不安全的。

如果安全内容与不安全内容混合在一起，现代浏览器可能会阻止页面显示或者显示警告消息。

如果 [!DNL Adobe Target] 中的[!UICONTROL 可视体验编辑器] (VEC) 尝试打开包含混合内容的页面，则会显示警告消息。此消息告知您如何在浏览器中禁用阻止。禁用阻止可让您打开HTTP网站或包含混合内容（HTTPS和HTTP）的网站。

![混合内容警告](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/mixed_content_warning.png)

以前，虽然不允许使用混合内容，但是您在创建活动时仍然能够执行三步引导式工作流的步骤 1 中的某些操作。现在，[!DNL Target] 会阻止执行步骤 1 中的操作。显示此消息时，您必须先启用混合内容，然后才能继续创建活动。

浏览器的安全设置可能会阻止将混合内容或不安全 (HTTP) 内容加载到安全 (HTTPS) 页面或框架（例如 VEC）。如果您不希望禁用浏览器的安全设置，则必须使用 HTTPS 网站。

如果您的网站运行在不安全 (HTTP) 的域上，您需要允许 VEC 加载活动的混合内容。

>[!IMPORTANT]
>
>允许混合内容仅会对 VEC 造成影响，而不会影响您已上线的网站。

有关更多信息，请参阅“Mozilla 开发人员网络”**(MDN) 网站上的[混合内容](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content)。

## 在中启用混合内容 [!DNL Google Chrome] {#task_FF297A08F66E47A588C14FD67C037B3A}

如果您通过安全连接访问站点， [!DNL Chrome] 验证网页上的内容是否已安全地传输。

请参阅&quot;[管理有关不安全站点的警告](https://support.google.com/chrome/answer/99020?hl=en)”在Google Chrome帮助中。

如果您正在将VEC与最新版本的 [!DNL Chrome] （版本79.0.3945.117或更高版本），您必须更新网站设置。 您网站的访客无需完成这些步骤。

1. 单击锁（请小心）图标，然后单击&#x200B;**[!UICONTROL 网站设置]**。

   ![网站设置](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. 滚动到&#x200B;**[!UICONTROL 不安全的内容]**，然后使用下拉列表将“阻止（默认值）”更改为“允许”。

   ![不安全的内容](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)

1. 重新加载 VEC 页面。

## 在中启用混合内容 [!DNL Mozilla Firefox] {#task_5448763B8DC941FD80F84041AEF0A14D}

默认情况下， [!DNL Firebox] 阻止将安全内容和不安全内容混合在一起的页面。 您应该永久更改此设置以便使用 [!DNL Target]. 您网站的访客无需完成这些步骤。

1. 在 Firefox 的地址栏中输入 `about:config`。
1. 确认显示的警告消息 [!DNL Firefox].

   ![Firefox 警告](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox.png)

1. 在搜索栏中，键入 `block_active`。

   ![Firefox block_active 设置](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox3.png)

1. 双击 ` **[!UICONTROL security.mixed_content.block_active_content]**`。

   其值随即会从“True”更改为“False”。当值显示为“False”时，即表示操作已完成。

   ![Firefox 安全性](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox2.png)

1. 在更改此设置后重新启动计算机。

## 在中启用混合内容 [!DNL Microsoft Edge]

如果您通过安全连接访问站点， [!DNL Edge] 验证网页上的内容是否已安全地传输。

如果您正在将VEC与最新版本的 [!DNL Edge]中，您必须更新网站设置。 您网站的访客无需完成这些步骤。

1. 在 [!DNL Edge]，单击 **[!DNL Microsoft Edge]** 在菜单栏中， **[!UICONTROL 设置]**，然后单击 **Cookie和网站权限**.

1. 滚动到 **[!UICONTROL 不安全的内容]**.

1. 单击 **[!UICONTROL 不安全的内容]**，然后单击 **[!UICONTROL 添加]** 旁边 **[!UICONTROL 允许]**，添加允许不安全内容的站点，然后单击 **[!UICONTROL 添加]**.

1. 重新加载 VEC 页面。
