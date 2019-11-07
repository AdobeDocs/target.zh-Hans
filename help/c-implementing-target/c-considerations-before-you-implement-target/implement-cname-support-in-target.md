---
keywords: 客户关怀；cname；证书程序；规范名；cookie；证书；amc;adobe受管证书
description: 有关与 Adobe 客户关怀一起在 Adobe Target 中实施 CNAME（规范名称）支持的信息。
title: CNAME 和 Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# CNAME 和 Adobe Target {#cname-and-adobe-target}

Information about working with Adobe Client Care to implement CNAME (Canonical Name) support in [!DNL Target]. 为了最好地处理广告阻止问题或与ITP相关的Cookie策略，会使用CNAME，以便对客户所拥有的域而不是Adobe所拥有的域进行调用。

Perform the following steps to request CNAME support in [!DNL Target]:

1. Open a [Customer Care ticket requesting CNAME support](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) for your [!DNL Target] calls.

1. 创建CNAME记录（请参阅下面的说明）。

   收到票证后，FPSSL专家应为您提供一对CNAME记录。 必须先在您公司的DNS服务器上配置这些记录，然后Adobe才能代表您购买证书。

   CNAMES将类似于以下示例：

   `DNS record: metrics.example.com IN CNAME metricsexample-fpssl.tt.omtrdc.net`

1. 当这些CNAMES到位后，Adobe将与DigiCert合作，在Adobe的生产服务器上购买并安装证书。

1. 完成上述任务后，您必须在 at.js 中将 `serverDomain` 更新为新 CNAME。
