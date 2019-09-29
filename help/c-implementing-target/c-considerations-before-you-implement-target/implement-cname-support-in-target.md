---
description: 有关与 Adobe 客户关怀一起在 Adobe Target 中实施 CNAME（规范名称）支持的信息。
keywords: 客户关怀;CNAME;证书程序;规范名称;Cookie;证书;amc;adobe managed certificate
seo-description: 有关与 Adobe 客户关怀一起在 Adobe Target 中实施 CNAME（规范名称）支持的信息。
seo-title: CNAME 和 Adobe Target
solution: Target
title: CNAME 和 Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: b7a80326b0b89f6fe3bac70ccc6941be09d14ac1

---


# CNAME 和 Adobe Target {#cname-and-adobe-target}

Information about working with Adobe Client Care to implement CNAME (Canonical Name) support in [!DNL Target]. 为了最好地处理广告阻止问题或与ITP相关的Cookie策略，会使用CNAME，以便对客户所拥有的域而不是Adobe所拥有的域进行调用。

Perform the following steps to request CNAME support in [!DNL Target]:

1. Open a [Customer Care ticket requesting CNAME support](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) for your [!DNL Target] calls.

1. Create CNAME records (see instructions below).

   Upon receiving the ticket, a FPSSL specialist should provide you with a pair of CNAME records. These records must be configured on your company's DNS server before Adobe can purchase the certificate on your behalf.

   The CNAMES will be similar to the following example:

   `DNS record: metrics.example.com IN CNAME metricsexample-fpssl.tt.omtrdc.net`

1. When these CNAMES are in place, Adobe will work with DigiCert to purchase and install a certificate on Adobe's production servers.

1. After completing the preceding tasks, you must update the  to the new CNAME in at.js.`serverDomain`
