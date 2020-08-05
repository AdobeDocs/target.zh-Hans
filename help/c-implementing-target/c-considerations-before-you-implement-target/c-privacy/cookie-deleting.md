---
description: 可删除 Target 浏览器 Cookie，以便您能够对所有体验进行验证。
title: 删除Adobe Targetcookie
topic: Standard
uuid: 6e95ee4d-dbf2-4432-8abe-cfd9bc928f0c
translation-type: tm+mt
source-git-commit: 79bcd452a9faa0883272d2e686efd7c4ddfa34a2
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 5%

---


# 删除 Target Cookie{#delete-the-target-cookie}

您可以删除 [!DNL Target] 浏览器cookie(mbox)，以便在测试过程中验证所有体验。

If there is no [!DNL Target] cookie (mbox), you are considered a new visitor and shown a new experience. There are several ways to delete your [!DNL Target] cookies without deleting all of your browser cookies.

>[!NOTE]
>
>下面的说明对于列出的浏览器和版本是正确的。 在Internet上搜索特定浏览器或版本的说明。

## 从Google Chrome中删除目标cookie

版本 84.0.4147.105

1. 单击“铬 **黄** ”菜单> **“首选项**”。
1. 单击“隐 **私和安全”选项** 卡。
1. 单击 **Cookie和其他站点数据**。
1. 单击 **查看所有Cookie和站点数据**。
1. 展开 `adobe.com` 该部分，选 **择mbox** cookie，然后单击删除图标(X)。

## 从Mozilla Firefox中删除目标cookie

版本 79.0

1. 单击“Firefox **”菜单** >“ **首选项**”。
1. 单击“隐 **私和安全”选项** 卡。
1. 在“ **Cookie和站点数据**”下，单 **击“管理数据**”。
1. 选择站 `adobe.com` 点，然后单击“ **删除选定项**”。

   >[!NOTE]
   >
   >这将删除与该站点关联的所有 `adobe.com` Cookie。 如果要删除或编辑站点的单个Cookie，可在开发人员工具的 [存储检查器中执行此操作](https://developer.mozilla.org/en-US/docs/Tools/Storage_Inspector)。 您应删除的特定Cookie名为“mbox”。

## 从Microsoft Edge中删除目标cookie

版本 84.0.522.52

1. 单击“Microsoft **Edge** ”菜单>“ **首选项**”。
1. Click the **Site Permissions** tab.
1. 单击 **Cookie和网站数据**。
1. 单击 **查看所有Cookie和站点数据**。
1. 展开 `adobe.com` 该部分，选 **择mbox** cookie，然后单击删除图标(X)。

## 从Apple Safari中删除目标Cookie

版本 13.1.2

1. 单击“Safari **”菜** 单>“ **首选项**”。
1. Click the **Privacy** tab.
1. 单击“ **管理网站数据**”。
1. 选择要删除的Cookie的站点，然后单击“删 **除”**。

>[!NOTE]
>
>这将删除与该站点关联的所有 `adobe.com` Cookie。 如果要删除站点的单个Cookie，请按照以下说明操作：

1. 单击“Safari **”菜** 单>“ **首选项**”。
1. Click the **Advanced** tab.
1. 在菜单栏 **中选择“显示修改照片”菜单** 。
1. 导航到包含要删除的Cookie的网页。
1. 单击“开 **发** ”菜单> **“显示Web检查器**”。
1. Click the **Storage** tab.
1. 展开“ **Cookie** ”部分，然后单击 `www.adobe.com`。
1. 右键单击mbox **cookie** ，然后单击 **删除**。