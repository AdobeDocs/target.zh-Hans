---
keywords: 实施；设置；设置；客户属性
description: 将数据导入 [!DNL Target] 使用客户属性。
title: 如何将数据导入 [!DNL Target] 使用客户属性？
feature: Implementation
role: Developer
exl-id: b6c4a286-7994-492d-bde9-346af7aa314f
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 56%

---

# 客户属性

客户属性可让您通过 FTP 将访客配置文件数据上传到 [!DNL Adobe Experience Cloud]. 上传后，在 [!DNL Adobe Analytics] 和 [!DNL Adobe Target].

Target Standard客户可以应用五个属性，Target Premium客户可以应用200个属性。

## 格式

使用 Experience Cloud ID (ECID) 和属性名称/值对的 .csv 文件，可通过 FTP 或手动上传到 Experience Cloud UI 中。

## 用例示例

您在 CRM 或其他内部系统中存储那些要与 Adobe Experience Cloud（包括 Target 和 Analytics）共享的宝贵信息。

## 方法的好处

即使访客尚未使用 Target，通过上传客户数据也会为该访客在 Target 中创建一个配置文件条目。

会在 Target 和 Analytics 中自动提供相同的数据。

与 API 相比，FTP 的实施方法可能更简单。

## 注意事项

Target Standard客户可以应用五个属性，Target Premium客户可以应用200个属性

只能通过客户属性而不是在页面上来更新值。

需要 Experience Cloud ID (ECID) 实施。

## 代码示例

有关详细信息可在 [创建客户属性来源并上传数据文件](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).

### 相关信息的链接

[创建客户属性来源并上传数据文件](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).
