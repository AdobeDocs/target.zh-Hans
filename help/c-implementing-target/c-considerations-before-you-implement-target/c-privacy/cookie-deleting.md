---
keywords: cookie;cookies；删除cookie；删除目标cookie;google chrome;chrome;mozilla firefox;firefox;microsoft edge;safari
description: 了解如何删除您的 [!DNL Target] 浏览器cookies，以便您验证您的体验。
title: 如何删除 [!DNL Target] Cookie?
feature: 隐私和安全
role: Developer
exl-id: f2bc079e-593a-4689-a7cd-dfc6f86f6bb4
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 4%

---

# 删除[!DNL Target] Cookie

您可以删除[!DNL Adobe Target]浏览器cookie(mbox)，以便在测试过程中验证所有体验。

如果没有[!DNL Target] cookie(mbox)，则您将被视为新访客并显示新体验。 有多种方法可在不删除所有 的情况下删除您的 mbox Cookie。

>[!NOTE]
>
>以下说明对列出的浏览器和版本正确。 在Internet上搜索特定浏览器或版本的说明。

## 从Google Chrome中删除[!DNL Target] Cookie

版本 84.0.4147.105

1. 单击&#x200B;**Chrome**&#x200B;菜单> **首选项**。
1. 单击&#x200B;**隐私和安全**&#x200B;选项卡。
1. 单击&#x200B;**Cookie和其他站点数据**。
1. 单击&#x200B;**查看所有Cookie和站点数据**。
1. 展开`adobe.com`部分，选择&#x200B;**mbox** cookie，然后单击删除图标(X)。

## 从Mozilla Firefox中删除[!DNL Target] Cookie

版本 79.0

### 删除与`adobe.com`关联的所有Cookie

1. 单击&#x200B;**Firefox**&#x200B;菜单> **首选项**。
1. 单击&#x200B;**隐私和安全**&#x200B;选项卡。
1. 在&#x200B;**Cookie和Site Data**&#x200B;下，单击&#x200B;**管理数据**。
1. 选择`adobe.com`站点，然后单击&#x200B;**删除选定的**。

   >[!NOTE]
   >
   >这将删除与`adobe.com`站点关联的所有Cookie。 如果要删除站点的单个Cookie，请按照以下说明操作。

### 删除单个Cookie(mbox)

1. 在Firefox中，单击&#x200B;**工具** > **Web开发人员** > **存储检查器**。
1. 单击&#x200B;**高级**&#x200B;选项卡。
1. 导航到包含要删除的Cookie的网页。
1. 展开&#x200B;**Cookie**&#x200B;部分，然后单击`https://experience.adobe.com`。
1. 右键单击&#x200B;**mbox** cookie，然后单击&#x200B;**删除**。

## 从Microsoft Edge中删除[!DNL Target] Cookie

版本 84.0.522.52

1. 单击&#x200B;**Microsoft Edge**&#x200B;菜单> **首选项**。
1. 单击&#x200B;**站点权限**&#x200B;选项卡。
1. 单击&#x200B;**Cookie和站点数据**。
1. 单击&#x200B;**查看所有Cookie和站点数据**。
1. 展开`adobe.com`部分，选择&#x200B;**mbox** cookie，然后单击删除图标(X)。

## 从Apple Safari中删除[!DNL Target] Cookie

版本 13.1.2

### 删除与`adobe.com`关联的所有Cookie

1. 单击&#x200B;**Safari**&#x200B;菜单> **首选项**。
1. 单击&#x200B;**隐私**&#x200B;选项卡。
1. 单击&#x200B;**管理网站数据**。
1. 选择要删除的Cookie的站点，然后单击&#x200B;**删除**。

   >[!NOTE]
   >
   >这将删除与`adobe.com`站点关联的所有Cookie。 如果要删除站点的单个Cookie，请按照以下说明操作。

### 删除单个Cookie(mbox)

1. 单击&#x200B;**Safari**&#x200B;菜单> **首选项**。
1. 单击&#x200B;**高级**&#x200B;选项卡。
1. 选择菜单栏&#x200B;**中的**“显示修改照片”菜单。
1. 导航到包含要删除的Cookie的网页。
1. 单击&#x200B;**“Develop**”菜单> **“Show Web Inspector**”。
1. 单击&#x200B;**存储**&#x200B;选项卡。
1. 展开&#x200B;**Cookie**&#x200B;部分，然后单击`www.adobe.com`。
1. 右键单击&#x200B;**mbox** cookie，然后单击&#x200B;**删除**。
