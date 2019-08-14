---
description: 有关与 Adobe 客户关怀一起在 Adobe Target 中实施 CNAME（规范名称）支持的信息。
keywords: 客户关怀;CNAME;证书程序;规范名称;Cookie;证书
seo-description: 有关与 Adobe 客户关怀一起在 Adobe Target 中实施 CNAME（规范名称）支持的信息。
seo-title: CNAME 和 Adobe Target
solution: Target
title: CNAME 和 Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: 72260f1bf82dfeab2582add69111439498ad5eb8

---


# CNAME 和 Adobe Target{#cname-and-adobe-target}

有关与 Adobe 客户关怀一起在 Adobe Target 中实施 CNAME（规范名称）支持的信息。为最好地处理广告拦截问题，使用CNAME，以便对由客户拥有的域而非Adobe拥有的域作出调用。

执行以下步骤可在 Target 中请求 CNAME 支持：

1. 打开[客户关怀票证](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)，为您的 Adobe Target 调用请求 CNAME 支持。
1. 在 [Adobe 管理证书 (AMC) 程序](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html)中进行注册，然后按照“第一方 Cookie”[!DNL Adobe Analytics]**&#x200B;指南中提供的实施步骤操作。

   AMC 程序有助于减少客户在实施第一方 Cookie 时所做的工作和产生的困惑。注册此程序后，Adobe 将购买并颁发证书以将其安装在安全的服务器上。

   >[!NOTE]
   >
   >必须在注册 AMC 程序之前配置 CNAME。

1. 完成之前的任务后，您必须在. js中更新 `serverDomain` 新的CNAME。

## 培训视频：第一方Cookie和使用Adobe Managed Certificates

This video is a recording of [Office Hours](/help/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7), an initiative led by the Adobe Customer Care team. Adobe Managed Certificate Program讨论从10：21开始。

[Adobe Analytics：第一方Cookie和使用Adobe Managed Certificates](https://helpx.adobe.com/customer-care-office-hours/analytics/first-party-cookies-adobe-managed-certificates.html)
