---
keywords: Targeting;eec;visual experience composer;troubleshoot enhanced experience composer;troubleshooting
description: 有时，在某些情况下，增强型体验编辑器 (EEC) 会发生显示问题。
title: 对与增强型体验编辑器有关的问题进行故障诊断
uuid: 2ea9a91f-08ca-4a06-ad5d-35ced140db14
translation-type: tm+mt
source-git-commit: cf69c1d8472088d5f6a6b7250bedd1048cac5c10
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 71%

---


# 对与增强型体验编辑器有关的问题进行故障诊断{#troubleshooting-issues-related-to-the-enhanced-experience-composer}

有时，在某些情况下，增强型体验编辑器 (EEC) 会发生显示问题。

## EEC 无法加载在公共 IP 上不可访问的内部 QA URL。（仅 EEC）{#section_D29E96911D5C401889B5EACE267F13CF}

这可以通过允许列出以下IP地址来解决。 用作增强型体验编辑器代理的 Adobe 服务器使用这些 IP 地址。仅在编辑活动时才需要这些地址。访客到您的站点不需要这些允许的IP地址

请让您的IT团队允许列出以下IP地址：

| 区域 | IP 地址 | 主机名 |
|--- |--- |--- |
| 美国 | 52.55.99.45 | `us1-proxy.adobemc.com` |
| 欧洲、中东和非洲 (EMEA) | 52.51.238.221 | `emea1-proxy.adobemc.com` |
| 亚太 (APAC) | 52.193.67.35 | `apac1-proxy.adobemc.com` |

您可能会在 Target 中看到以下错误消息：

`Error: Your website domain (ISP) is blocking the Enhanced Experience Composer. You can allowlist the Enhanced Experience Composer's IP addresses or turn off Enhanced Experience Composer in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![](assets/EEC_error.png)

以下是您可能会看到此错误消息的原因以及相应的补救措施：

* **问题：**&#x200B;您的网站域 (ISP) 正在阻止增强型体验编辑器。

   **补偿：** 允许列出上面列出的IP地址。

* **问题：** 允许列出IP地址，但您的网站不支持TLS版本1.2。目标当前使用默认配置1.2。在目标18.4.1（2018年4月25日）之前，默认配置支持TLS 1.0。有关详细信息，请参 [阅TLS（传输层安全）加密更改](../../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451).

   **解决方案：**&#x200B;请参阅下一个问题（增强型可视化体验编辑器无法加载使用 TLS 1.2 的网站上的安全页面）。

## EEC 无法加载使用 TLS 1.0 的网站上的安全页面。（仅 EEC）{#section_C5B31E3D32A844F68E5A8153BD17551F}

如果以上 IP 地址已列入白名单，但您的网站不支持 TLS 版本 1.2，则您可能会看到在上面“增强型可视化体验编辑器无法加载我网站上的安全页面”中所述的错误消息。if the above IP addresses are allowlisted but your website does not support TLS version 1.2. Target currently uses the default configuration of 1.2. Prior to the Target 18.4.1 (April 25, 2018), the default configuration supported TLS 1.0. For more information, see [TLS (Transport Layer Security) Encryption Changes](../../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451).

要使用 Firefox 检查您网站上的 TLS 版本（使用其他浏览器的步骤相似），请执行以下操作：

1. 在 Firefox 中打开受影响的网站。
1. 单击浏览器地址栏上的&#x200B;**[!UICONTROL 显示网站信息]**&#x200B;图标。

   ![](assets/firefox_more_info.png)

1. 单击&#x200B;**[!UICONTROL 显示连接详细信息]** > **[!UICONTROL 更多信息]**。

   ![](assets/firefox_more_info_2.png)

1. 检查“技术详细信息”下的 TLS 版本信息：

   ![](assets/firefox_more_info_3.png)

1. 如果发现您的网站显示的是 TLS 1.0，请参阅 [TLS（传输层安全性）加密更改](../../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)，以获取有关 Target 的 TLS 支持政策的信息。目前要解决这种情况（有效期至 2018 年 9 月 12 日），请与[客户关怀](../../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)联系，以获取 TLS 版本和域的配置。

## 加载启用了代理的网站时，我遇到超时或“拒绝访问”错误。（仅 EEC）{#section_60CBB9022DC449F593606C0E6252302D}

请确保代理 IP 在您的环境中未被阻止。
