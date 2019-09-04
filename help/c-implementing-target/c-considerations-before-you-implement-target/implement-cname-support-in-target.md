---
description: 有关与 Adobe 客户关怀一起在 Adobe Target 中实施 CNAME（规范名称）支持的信息。
keywords: 客户关怀;CNAME;证书程序;规范名称;Cookie;证书；amc；Adobe托管证书
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

Information about working with Adobe Client Care to implement CNAME (Canonical Name) support in [!DNL Target]. 为了最好地处理广告拦截问题或与ITP相关的cookie策略，使用CNAME，以便对由客户拥有的域而非Adobe拥有的域调用CNAME。

Perform the following steps to request CNAME support in [!DNL Target]:

1. Open a [Customer Care ticket requesting CNAME support](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) for your [!DNL Target] calls.

1. 创建CNAME记录(请参阅下面的说明)。

   收到票证后，CMS SSL专家应为您提供一对CNAME记录。必须在公司DNS服务器上配置这些记录，然后Adobe才能代表您购买证书。

   CNAME类似于以下示例：

   `DNS record: metrics.example.com IN CNAME metricsexample-fpssl.tt.omtrdc.net`

1. 这些CNAME就位后，Adobe将与DigicerT一起购买并安装Adobe生产服务器上的证书。

1. 完成之前的任务后，您必须在. js中更新 `serverDomain` 新的CNAME。
