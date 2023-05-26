---
keywords: 定位;EEC;可视化体验编辑器;增强型体验编辑器故障诊断;故障诊断
description: 了解如何对Adobe中有时出现的问题进行故障排除 [!DNL Target] 在某些情况下使用增强型体验编辑器(EEC)。
title: 如何解决与增强型体验编辑器相关的问题？
feature: Visual Experience Composer (VEC)
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 38%

---

# 与[!UICONTROL 增强体验编辑器]相关的问题疑难解答

有时会出现显示问题 [!DNL Adobe Target] [!UICONTROL 增强型体验编辑器] (EEC)在一定条件下。

## EEC 无法加载在公共 IP 上不可访问的内部 QA URL。 {#section_D29E96911D5C401889B5EACE267F13CF}

这可以通过列入允许列表以下IP地址来解决。 这些IP地址用于EEC代理所使用的Adobe服务器。 仅在编辑活动时才需要这些地址。列入允许列表您网站的访客不需要这些IP地址。

要求您的IT团队允许列表以下IP地址：

* 34.253.100.20
* 34.248.100.23
* 52.49.228.246
* 54.205.42.123
* 107.22.177.39
* 52.201.5.105
* 52.193.211.177
* 18.180.24.249
* 52.194.154.154

您可能会在中看到以下错误消息 [!DNL Target]：

`Error: Your website domain (ISP) is blocking the [!UICONTROL Enhanced Experience Composer]. You can allowlist the [!UICONTROL Enhanced Experience Composer]'s IP addresses or turn off [!UICONTROL Enhanced Experience Composer] in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![EEC_error图像](assets/EEC_error.png)

以下是您可能会看到此错误消息的原因以及相应的补救措施：

* **问题：** 您的网站域(ISP)正在阻止 [!UICONTROL 增强型体验编辑器].

   **补救措施：** 允许列表上面列出的IP地址。

* **问题：** 列入允许列表 IP地址，但您的网站不支持TLS版本1.2。 [!DNL Target] 当前使用1.2的默认配置。在之前 [!DNL Target] 18.4.1（2018年4月25日），默认配置支持TLS 1.0。有关更多信息，请参阅 [TLS（传输层安全性）加密更改](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank}.

   **解决方案：**[!UICONTROL 请参阅下一个问题（增强型可视化体验编辑器无法加载使用 TLS 1.2 的网站上的安全页面）。]

## EEC 无法加载使用 TLS 1.0 的网站上的安全页面。（仅 EEC） {#section_C5B31E3D32A844F68E5A8153BD17551F}

您可能会看到上面“The [!UICONTROL 增强型可视化体验编辑器] 不会在我的网站上的安全页面上加载。” 列入允许列表如果上述IP地址，但您的网站不支持TLS版本1.2。 [!DNL Target] 当前使用1.2的默认配置。在之前 [!DNL Target] 18.4.1（2018年4月25日），默认配置支持TLS 1.0。有关更多信息，请参阅 [TLS（传输层安全性）加密更改](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank}.

要使用 Firefox 检查您网站上的 TLS 版本（使用其他浏览器的步骤相似），请执行以下操作：

1. 在 Firefox 中打开受影响的网站。
1. 单击浏览器地址栏上的&#x200B;**[!UICONTROL 显示网站信息]**&#x200B;图标。

   ![firefox_more_info图像](assets/firefox_more_info.png)

1. 单击&#x200B;**[!UICONTROL 显示连接详细信息]** > **[!UICONTROL 更多信息]**。

   ![firefox_more_info_2图像](assets/firefox_more_info_2.png)

1. 检查“技术详细信息”下的 TLS 版本信息：

   ![firefox_more_info_3图像](assets/firefox_more_info_3.png)

1. 如果您发现您的网站显示的是TLS 1.0，请参阅 [TLS（传输层安全性）加密更改](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank} for information about Target's TLS support policy. To remedy the situation for now (valid until September 12, 2018){target=_blank}，联系 [客户关怀](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) 用于配置TLS版本和域。

## 加载启用了代理的网站时，我遇到超时或“拒绝访问”错误。（仅 EEC） {#section_60CBB9022DC449F593606C0E6252302D}

请确保代理 IP 在您的环境中未被阻止。
