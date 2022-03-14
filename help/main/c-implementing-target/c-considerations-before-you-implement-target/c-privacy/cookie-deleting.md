---
keywords: Cookie;Cookie；删除Cookie；删除Target Cookie;Google Chrome;Chrome;Mozilla Firefox;Firefox;Microsoft Edge;Safari
description: 了解如何删除 [!DNL Target] 浏览器cookie，以便您验证体验。
title: 如何删除 [!DNL Target] Cookie?
feature: Privacy & Security
role: Developer
exl-id: f2bc079e-593a-4689-a7cd-dfc6f86f6bb4
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 4%

---

# 删除 [!DNL Target] cookie

您可以删除 [!DNL Adobe Target] 浏览器cookie(mbox)，以便您能够在测试期间验证所有体验。

如果没有 [!DNL Target] cookie(mbox)，则您会被视为新访客并显示新体验。 有多种方法可在不删除所有 的情况下删除您的 mbox Cookie。

>[!NOTE]
>
>所列的浏览器和版本的以下说明正确无误。 在Internet中搜索特定浏览器或版本的说明。

## 删除 [!DNL Target] 来自Google Chrome的Cookie

版本 84.0.4147.105

1. 单击 **铬黄** 菜单> **首选项**.
1. 单击 **隐私和安全** 选项卡。
1. 单击 **Cookie和其他网站数据**.
1. 单击 **查看所有Cookie和网站数据**.
1. 展开 `adobe.com` 选择 **mbox** cookie，然后单击删除图标(X)。

## 删除 [!DNL Target] Mozilla Firefox提供的Cookie

版本 79.0

### 删除与 `adobe.com`

1. 单击 **Firefox** 菜单> **首选项**.
1. 单击 **隐私和安全** 选项卡。
1. 在 **Cookie和网站数据**，单击 **管理数据**.
1. 选择 `adobe.com` 网站，然后单击 **删除选定项**.

   >[!NOTE]
   >
   >这将删除与 `adobe.com` 网站。 如果要删除网站的单个Cookie，请按照以下说明操作。

### 删除单个Cookie(mbox)

1. 在Firefox中，单击 **工具** > **Web开发人员** > **存储检查器**.
1. 单击 **高级** 选项卡。
1. 导航到包含要删除的Cookie的网页。
1. 展开 **Cookie** ，然后单击 `https://experience.adobe.com`.
1. 右键单击 **mbox** Cookie，然后单击 **删除**.

## 删除 [!DNL Target] 来自Microsoft Edge的Cookie

版本 84.0.522.52

1. 单击 **Microsoft Edge** 菜单> **首选项**.
1. 单击 **网站权限** 选项卡。
1. 单击 **Cookie和网站数据**.
1. 单击 **查看所有Cookie和网站数据**.
1. 展开 `adobe.com` 选择 **mbox** cookie，然后单击删除图标(X)。

## 删除 [!DNL Target] 来自Apple Safari的Cookie

版本 13.1.2

### 删除与 `adobe.com`

1. 单击 **Safari** 菜单> **首选项**.
1. 单击 **隐私** 选项卡。
1. 单击 **管理网站数据**.
1. 选择要删除的Cookie的网站，然后单击 **删除**.

   >[!NOTE]
   >
   >这将删除与 `adobe.com` 网站。 如果要删除网站的单个Cookie，请按照以下说明操作。

### 删除单个Cookie(mbox)

1. 单击 **Safari** 菜单> **首选项**.
1. 单击 **高级** 选项卡。
1. 选择 **在菜单栏中显示“开发”菜单** 选项。
1. 导航到包含要删除的Cookie的网页。
1. 单击 **开发** 菜单> **显示Web检查器**.
1. 单击 **存储** 选项卡。
1. 展开 **Cookie** ，然后单击 `www.adobe.com`.
1. 右键单击 **mbox** Cookie，然后单击 **删除**.
