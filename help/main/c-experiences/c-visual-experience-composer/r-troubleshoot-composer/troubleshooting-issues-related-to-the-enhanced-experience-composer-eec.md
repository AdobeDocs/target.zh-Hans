---
keywords: 定位;EEC;可视化体验编辑器;增强型体验编辑器故障诊断;故障诊断
description: 了解如何对Adobe中有时发生的问题进行故障排除 [!DNL Target] 在某些情况下会使用增强型体验编辑器(EEC)。
title: 如何解决与增强型体验编辑器相关的问题？
feature: Visual Experience Composer (VEC)
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
source-git-commit: 7562a1da201b570ee529db9763ef5f4b463f65a8
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 23%

---

# 对与相关的问题进行故障诊断 [!UICONTROL Enhanced Experience Composer]

有时会出现显示问题 [!DNL Adobe Target] [!UICONTROL Enhanced Experience Composer] (EEC)。

## EEC无法加载在公共IP上不可访问的内部QA URL。 {#section_D29E96911D5C401889B5EACE267F13CF}

这可以通过列入允许列表以下IP地址来解决。 这些IP地址用于Adobe用于EEC代理的服务器。 仅在编辑活动时才需要这些地址。您网站的访客不需要列入允许列表这些IP地址。

要求您的IT团队允许列表以下IP地址：

* 34.254.77.200
* 54.73.207.147
* 54.229.152.123
* 3.224.194.242
* 54.90.51.39
* 34.228.136.112
* 54.150.116.11
* 18.178.142.8
* 54.199.107.77
* 99.80.139.221
* 54.78.56.224
* 54.247.179.246
* 54.80.219.243
* 34.201.235.54
* 54.196.224.236
* 35.75.212.45
* 52.199.184.130
* 18.180.161.176

您可能会在中看到以下错误消息 [!DNL Target]：

`Error: Your website domain (ISP) is blocking the [!UICONTROL Enhanced Experience Composer]. You can allowlist the [!UICONTROL Enhanced Experience Composer]'s IP addresses or turn off [!UICONTROL Enhanced Experience Composer] in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![EEC_error图像](assets/EEC_error.png)

以下是您可能会看到此错误消息的原因以及相应的补救措施：

* **问题：** 您的网站域(ISP)正在阻止 [!UICONTROL Enhanced Experience Composer].

  **补救措施：** 允许列表上面列出的IP地址。

* **问题：** 将列入允许列表IP地址，但您的网站不支持TLS版本1.2。 [!DNL Target] 当前使用1.2的默认配置。在之前 [!DNL Target] 18.4.1（2018年4月25日），默认配置支持TLS 1.0。有关更多信息，请参阅 [TLS（传输层安全性）加密更改](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank}.

  **解决方案：** 请参阅以下问题(关于 [!UICONTROL Enhanced Visual Experience Composer] 不会在我的网站上使用TLS 1.2的安全页面上加载)。

## EEC 无法加载使用 TLS 1.0 的网站上的安全页面。（仅 EEC） {#section_C5B31E3D32A844F68E5A8153BD17551F}

您可能会看到上文“The [!UICONTROL Enhanced Visual Experience Composer] 不会在我的网站的安全页面上加载。” 如果上述IP地址已列入允许列表，但您的网站不支持TLS版本1.2。 [!DNL Target] 当前使用1.2的默认配置。在之前 [!DNL Target] 18.4.1（2018年4月25日），默认配置支持TLS 1.0。有关更多信息，请参阅 [TLS（传输层安全性）加密更改](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank}.

要使用 Firefox 检查您网站上的 TLS 版本（使用其他浏览器的步骤相似），请执行以下操作：

1. 在 Firefox 中打开受影响的网站。
1. 单击 **[!UICONTROL Show Site Information]** 图标（位于浏览器的地址栏上）。

   ![firefox_more_info图像](assets/firefox_more_info.png)

1. 单击 **[!UICONTROL Show Connection Details]** > **[!UICONTROL More Information]**.

   ![firefox_more_info_2图像](assets/firefox_more_info_2.png)

1. 检查“技术详细信息”下的 TLS 版本信息：

   ![firefox_more_info_3图像](assets/firefox_more_info_3.png)

1. 如果您发现您的网站显示的是TLS 1.0，请参阅 [TLS（传输层安全性）加密更改](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank} 有关Target的TLS支持策略的信息。 目前补救情况（有效期至2018年9月12日）{target=_blank}，联系 [客户关怀](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) 用于配置TLS版本和域。

## 加载启用了代理的网站时，我遇到超时或“拒绝访问”错误。（仅 EEC） {#section_60CBB9022DC449F593606C0E6252302D}

请确保代理 IP 在您的环境中未被阻止。
