---
keywords: 定位;EEC;可视化体验编辑器;增强型体验编辑器故障诊断;故障诊断
description: 了解如何解决在某些情况下，Adobe [!DNL Target] 增强型体验编辑器(EEC)中有时出现的问题。
title: 如何解决与增强型体验编辑器相关的问题？
feature: Visual Experience Composer (VEC)
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
source-git-commit: 04f8e22361b1e961a88d3e9d28ccfd600fae0218
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 23%

---

# 与[!UICONTROL Enhanced Experience Composer]相关的问题疑难解答

在某些情况下，[!DNL Adobe Target] [!UICONTROL Enhanced Experience Composer] (EEC)中有时会出现显示问题。

## EEC无法加载在公共IP上不可访问的内部QA URL。 {#section_D29E96911D5C401889B5EACE267F13CF}

这可以通过列入允许列表以下IP地址来解决。 这些IP地址用于Adobe服务器，用于EEC代理。 仅在编辑活动时才需要这些地址。您网站的访客不需要列入允许列表这些IP地址。

要求您的IT团队允许列表以下IP地址：

### 美国(va7)

40.70.154.136/29
52.254.106.240/28
52.254.106.160/28
52.254.107.16/28
20.186.185.181
20.22.83.112
20.186.185.227
52.254.106.192/28
52.254.106.0/28
52.254.107.128/28
52.254.107.80/28
52.254.106.176/28
52.254.107.32/28
52.254.105.192/28
52.254.107.64/28
52.254.106.208/28
52.254.107.0/28
52.254.106.224/28
20.14.241.153
20.186.185.239
4.152.211.251
52.254.107.144/28
52.254.106.144/28

### EMEA (nld2)

51.138.17.16/28
51.138.17.48/28
51.138.16.128/28
51.138.17.32/28
51.138.16.240/28
51.138.17.112/28
51.138.16.160/28
51.138.16.208/28
51.138.17.80/28
51.138.17.0/28
51.138.17.96/28
51.138.16.144/28
20.31.145.248
20.126.189.248
51.138.16.224/28
51.138.16.192/28
51.138.12.94
51.138.12.11
51.138.16.176/28
51.138.12.100
51.138.17.64/28
51.138.12.160/28

### APAC (aus)

20.43.104.160/28
20.227.35.177
20.40.188.227
20.43.104.112/28
20.43.104.128/28
20.43.104.144/28
20.40.188.166
20.53.206.128
20.43.104.80/28
20.43.104.16/28
20.43.105.48/28
20.43.104.96/28
20.43.104.48/28
20.40.188.194
20.43.104.32/28
20.40.191.224/28
20.43.105.16/28
20.40.191.96/28
20.43.104.176/28
20.40.191.240/28
20.43.104.64/28
20.43.105.32/28
20.43.104.192/28
20.43.105.0/28
20.43.104.0/28

### 旧版IP地址

在进一步通知之前，应继续列入允许列表以下旧版IP地址。

34.254.77.200
54.73.207.147
54.229.152.123
3.224.194.242
54.90.51.39
34.228.136.112
54.150.116.11
18.178.142.8
54.199.107.77
99.80.139.221
54.78.56.224
54.247.179.246
54.80.219.243
34.201.235.54
54.196.224.236
35.75.212.45
52.199.184.130
18.180.161.176

您可能会在[!DNL Target]中看到以下错误消息：

`Error: Your website domain (ISP) is blocking the [!UICONTROL Enhanced Experience Composer]. You can allowlist the [!UICONTROL Enhanced Experience Composer]'s IP addresses or turn off [!UICONTROL Enhanced Experience Composer] in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![EEC_error图像](assets/EEC_error.png)

以下是您可能会看到此错误消息的原因以及相应的补救措施：

* **问题：**&#x200B;您的网站域(ISP)正在阻止[!UICONTROL Enhanced Experience Composer]。

  **补救措施：**&#x200B;允许列表上面列出的IP地址。

* 列入允许列表 **问题：** IP地址已，但您的网站不支持TLS版本1.2。[!DNL Target]当前使用默认配置1.2。在[!DNL Target] 18.4.1（2018年4月25日）之前，默认配置支持TLS 1.0。有关详细信息，请参阅[TLS（传输层安全性）加密更改](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html?lang=zh-Hans){target=_blank}。

  **解决方案：**&#x200B;请参阅以下问题（[!UICONTROL Enhanced Visual Experience Composer]将不会在我的网站上使用TLS 1.2的安全页面上加载）。

## EEC 无法加载使用 TLS 1.0 的网站上的安全页面。（仅 EEC） {#section_C5B31E3D32A844F68E5A8153BD17551F}

您可能会看到上文“我的网站的安全页面上不会加载[!UICONTROL Enhanced Visual Experience Composer]”中所述的错误消息。 如果上述IP地址已列入允许列表，但您的网站不支持TLS版本1.2。[!DNL Target]当前使用默认配置1.2。在[!DNL Target] 18.4.1（2018年4月25日）之前，默认配置支持TLS 1.0。有关详细信息，请参阅[TLS （传输层安全性）加密更改](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html?lang=zh-Hans){target=_blank}。

要使用 Firefox 检查您网站上的 TLS 版本（使用其他浏览器的步骤相似），请执行以下操作：

1. 在 Firefox 中打开受影响的网站。
1. 单击浏览器地址栏上的&#x200B;**[!UICONTROL Show Site Information]**&#x200B;图标。

   ![firefox_more_info图像](assets/firefox_more_info.png)

1. 单击&#x200B;**[!UICONTROL Show Connection Details]** > **[!UICONTROL More Information]**。

   ![firefox_more_info_2图像](assets/firefox_more_info_2.png)

1. 检查“技术详细信息”下的 TLS 版本信息：

   ![firefox_more_info_3图像](assets/firefox_more_info_3.png)

1. 如果您发现网站显示的是TLS 1.0，请参阅[TLS（传输层安全性）加密更改](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html?lang=zh-Hans){target=_blank}以了解有关Target的TLS支持策略的信息。 若要补救当前情况（有效期至2018年9月12日）{target=_blank}，请联系[客户关怀](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)以获取TLS版本和域的配置。

## 加载启用了代理的网站时，我遇到超时或“拒绝访问”错误。（仅 EEC） {#section_60CBB9022DC449F593606C0E6252302D}

请确保代理 IP 在您的环境中未被阻止。
