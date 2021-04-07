---
keywords: 实现；实现；设置；设置；批量用户档案更新
description: 使用批量用户档案更新API将数据导入目标。
title: 如何使用批量用户档案更新API将数据导入目标?
feature: 实施
role: Developer
translation-type: tm+mt
source-git-commit: e8c25685341319fea4381386cad1ce0c5b80face
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 78%

---

# 批量配置文件更新 API

通过API向[!DNL Adobe Target]发送.csv文件，其中包含许多访客的访客用户档案更新。 每个访客配置文件均可以在一次调用中通过多个页面内配置文件属性进行更新。

此选项与“客户属性”类似，但有以下几点差异：

* 客户属性使用 FTP 上传，而 Target 批量配置文件更新 API 则使用 HTTP POST API。
* 客户属性数据可以与 Analytics 共享。批量配置文件更新只能在 Target 中使用。
* 客户属性支持为尚未使用 Target 的用户创建配置文件。批量配置文件更新 API 仅更新现有的 Target 配置文件。
* 客户属性需要使用 Experience Cloud ID (ECID)。批量配置文件更新 API 需要 TNT ID 或 `mbox3rdPartyId`。
* 不能在 `mbox3rdPartyID` 中发送下列字符：加号 (+) 和正斜线 (/)。

## 格式

.csv 文件必须通过访客的 Target PCID 或 mboxThirdPartyId 对每个访客进行引用。不支持 Experience Cloud ID (ECID)。所有配置文件属性/值都可通过 API 创建和更新。格式详细信息可在 API 文档中找到。

## 示例用例

您在 CRM 或其他内部系统中存储那些要持续更新到 Target 的有关访客的宝贵数据，从而无需在您的页面实施中暴露配置文件数据。

## 方法的优势

配置文件属性的数量没有限制。

通过该站点发送的配置文件属性可以通过 API 进行更新，反之亦然。

## 注意事项

批处理文件必须小于 50 MB。另外，每次上传的总行数不应超过 500,000 行。

在后续的批处理中，您在 24 小时内上传的数量或行数不受限制。但是，为了确保其他进程能够高效运行，这些数据的吸收过程在工作时间可能会受到节流限制。

对于相同 thirdPartyId，如果连续的 [V2 批量更新调用](https://developers.adobetarget.com/api/#updating-profiles)之间没有 mbox 调用，则会覆盖在第一次批量更新调用中更新的属性。

## 代码示例

请参阅[更新配置文件](https://developers.adobetarget.com/api/#updating-profiles)。

### 相关信息的链接

[更新配置文件](https://developers.adobetarget.com/api/#updating-profiles)