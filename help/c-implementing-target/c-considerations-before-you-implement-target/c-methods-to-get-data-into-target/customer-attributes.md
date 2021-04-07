---
keywords: 实现；实现；设置；设置；客户属性
description: 使用客户属性将数据导入目标。
title: 如何使用客户属性将数据导入目标?
feature: 实施
role: Developer
translation-type: tm+mt
source-git-commit: e8c25685341319fea4381386cad1ce0c5b80face
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 56%

---

# 客户属性

客户属性可让您通过 FTP 将访客配置文件数据上传到 [!DNL Adobe Experience Cloud]. 上载后，使用[!DNL Adobe Analytics]和[!DNL Adobe Target]中的数据。

Target Standard客户可以应用五个属性，目标 Premium客户可以应用200个属性。

## 格式

使用 Experience Cloud ID (ECID) 和属性名称/值对的 .csv 文件，可通过 FTP 或手动上传到 Experience Cloud UI 中。

## 示例用例

您在 CRM 或其他内部系统中存储那些要与 Adobe Experience Cloud（包括 Target 和 Analytics）共享的宝贵信息。

## 方法的优势

即使访客尚未使用 Target，通过上传客户数据也会为该访客在 Target 中创建一个配置文件条目。

会在 Target 和 Analytics 中自动提供相同的数据。

与 API 相比，FTP 的实施方法可能更简单。

## 注意事项

Target Standard客户可以应用五个属性，目标 Premium客户可以应用200个属性

只能通过客户属性而不是在页面上来更新值。

需要 Experience Cloud ID (ECID) 实施。

## 代码示例

有关详细信息，请参阅[创建客户属性源并上传数据文件](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html)。

### 相关信息的链接

[创建客户属性来源并上传数据文件](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).