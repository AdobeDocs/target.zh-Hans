---
keywords: 定位;EEC;可视化体验编辑器;增强型体验编辑器故障诊断;故障诊断
description: 了解如何解决某些情况下Adobe [!DNL Target] 增强体验书写器(EEC)中有时出现的问题。
title: 如何解决与增强体验书写器相关的问题？
feature: 可视化体验编辑器 (VEC)
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
translation-type: tm+mt
source-git-commit: 28e21ea0b0e2306a54c9353ae57de7de5d94f564
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 61%

---

# 与增强体验书写器相关的问题疑难解答

在某些条件下，在[!DNL Adobe Target] [!UICONTROL 增强体验书写器](EEC)中有时会出现显示问题。

## EEC 无法加载在公共 IP 上不可访问的内部 QA URL。（仅 EEC）{#section_D29E96911D5C401889B5EACE267F13CF}

这可以通过列入允许列表以下IP地址来解决。 用作增强型体验编辑器代理的 Adobe 服务器使用这些 IP 地址。仅在编辑活动时才需要这些地址。访客到您的站点不需要这些IP地列入允许列表址

请让您的IT团队允许列表以下IP地址：

* 52.16.72.74
* 52.5.174.79
* 54.246.238.65
* 54.249.183.154
* 54.65.105.214
* 54.82.142.68

您可能会在 Target 中看到以下错误消息：

`Error: Your website domain (ISP) is blocking the Enhanced Experience Composer. You can allowlist the Enhanced Experience Composer's IP addresses or turn off Enhanced Experience Composer in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![](assets/EEC_error.png)

以下是您可能会看到此错误消息的原因以及相应的补救措施：

* **问题：**&#x200B;您的网站域 (ISP) 正在阻止增强型体验编辑器。

   **Remedy:** 允许列表上面列出的IP地址。

* **问题：** IP地址已 [，但您的网站不支持TLS版本1.2。目标当前使用默认配置1.2。在目标18.4.1（2018年4月25日）之前，默认配置支持TLS 1.0。有关详细信息，请参](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)阅TLS（传输层安全）加密更改。

   **解决方案：**&#x200B;请参阅下一个问题（增强型可视化体验编辑器无法加载使用 TLS 1.2 的网站上的安全页面）。

## EEC 无法加载使用 TLS 1.0 的网站上的安全页面。（仅 EEC）{#section_C5B31E3D32A844F68E5A8153BD17551F}

如果以上 IP 地址已列入白名单，但您的网站不支持 TLS 版本 1.2，则您可能会看到在上面“增强型可视化体验编辑器无法加载我网站上的安全页面”中所述的错误消息。如果上述IP地列入允许列表址已，但您的网站不支持TLS 1.2版。目标当前使用默认配置1.2。在目标18.4.1（2018年4月25日）之前，默认配置支持TLS 1.0。有关详细信息，请参阅[TLS（传输层安全）加密更改](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)。

要使用 Firefox 检查您网站上的 TLS 版本（使用其他浏览器的步骤相似），请执行以下操作：

1. 在 Firefox 中打开受影响的网站。
1. 单击浏览器地址栏上的&#x200B;**[!UICONTROL 显示网站信息]**&#x200B;图标。

   ![](assets/firefox_more_info.png)

1. 单击&#x200B;**[!UICONTROL 显示连接详细信息]** > **[!UICONTROL 更多信息]**。

   ![](assets/firefox_more_info_2.png)

1. 检查“技术详细信息”下的 TLS 版本信息：

   ![](assets/firefox_more_info_3.png)

1. 如果发现您的网站显示的是 TLS 1.0，请参阅 [TLS（传输层安全性）加密更改](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)，以获取有关 Target 的 TLS 支持政策的信息。目前要解决这种情况（有效期至 2018 年 9 月 12 日），请与[客户关怀](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)联系，以获取 TLS 版本和域的配置。

## 加载启用了代理的网站时，我遇到超时或“拒绝访问”错误。（仅 EEC）{#section_60CBB9022DC449F593606C0E6252302D}

请确保代理 IP 在您的环境中未被阻止。
