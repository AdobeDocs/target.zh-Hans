---
keywords: targeting;cookie;first-party cookie;1st-party cookie
description: Adobe Target 通过 at.js 或 mbox.js JavaScript 库与您的网页集成。
title: 定位工作原理
uuid: 8b5a36c0-555d-42c5-8b24-c08d07440a53
translation-type: tm+mt
source-git-commit: ba4c776d93f911c122f36113a99ce4349b3c5524

---


# 定位工作原理{#how-targeting-works}

Adobe Target 通过 at.js 或 mbox.js JavaScript 库与您的网页集成。每个页面上引用的一个JavaScript库就是运行优化活动所需的全部。

每次在访客请求访问启用了 的页面时，[!DNL Target]Target 都会使用以下流程来提供选件：

1. 客户向您的服务器请求一个页面，然后该页面显示在浏览器中。
1. 在客户的浏览器中设置第一方 Cookie，进而设置唯一的访客 ID。

   如果您使用的是主营销配置文件，则也会设置 [!DNL Experience Cloud visitor ID]。

1. 页面通过 [!DNL Target] 文件或您页面上的 mbox 对 [!DNL target.js] 发起调用。
1. [!DNL Target] 引用与访客关联的配置文件。
1. [!DNL Target] 执行与该配置文件关联的任何配置文件脚本。
1. [!DNL Target] 计算自身的响应。
1. 根据活动或营销活动的规则显示内容。

基本 A/B 测试中显示的选件是随机选取的。由于对流量的这种随机划分，可能会耗用许多初始流量，才能使百分比达到均衡。例如，如果您的一个活动具有两个体验，则会随机选取起始体验。如果流量很少，访客的百分比可能会偏向其中一个体验。随着流量增加，百分比应该会更为均等。
